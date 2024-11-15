# SystemAudioPlayer Plugin
**Version: [1.0.10](https://github.com/rdkcentral/rdkservices/blob/main/SystemAudioPlayer/CHANGELOG.md)**
### Table of Contents
- [Abbreviation, Acronyms and Terms](#head.Abbreviation,_Acronyms_and_Terms)
- [Description](#head.Description)
- [Configuration](#head.Configuration)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)
<a name="head.Abbreviation,_Acronyms_and_Terms"></a>
# Abbreviation, Acronyms and Terms
 [[Refer to this link](userguide/aat.md)]
<a name="head.Description"></a>
# Description

 The `SystemAudioPlayer` plugin provides system audio playback functionality for client applications. It supports various audio types (viz., pcm, mp3, wav) and can play them from various sources (viz., websocket, httpsrc, filesrc, data buffer).  

**Note**: MP3 playback development remains a work-in-progress.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].
<a name="head.Configuration"></a>
# Configuration
The table below lists configuration options of the plugin.
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.SystemAudioPlayer*) |
| classname | string | Class name: *org.rdk.SystemAudioPlayer* |
| locator | string | Library name: *libWPEFrameworkSystemAudioPlayer.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="head.Methods"></a>
# Methods and Notifications
The following methods are provided by the org.rdk.SystemAudioPlayer plugin:
| Method | Description |Event|
| :-------- | :-------- | :-------- |
| [Open](#method.Open) | Opens a player instance | NA |
| [Play](#method.Play) | Plays audio on specified player | [OnSAPEvents](#event.OnSAPEvents)|
| [PlayBuffer](#method.PlayBuffer) | Buffers the audio playback | [OnSAPEvents](#event.OnSAPEvents)|
| [Pause](#method.Pause) | Pauses playback on player | [OnSAPEvents](#event.OnSAPEvents)|
| [Resume](#method.Resume) | Resumes playback on player | [OnSAPEvents](#event.OnSAPEvents)|

<a name="method.Open"></a>
## Open<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method opens a player instance and assigns it a unique ID. The player ID is used to reference the player when calling other methods. The SystemAudioPlayer plugin can have a maximum of 1 system and 1 application play mode player at a time. 

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| audiotype | string | The audio type. If the audio type is pcm, then the application is expected to also provide the format using the playmode parameter. The playmode parameter is ignored for the other audio types. (must be one of the following: pcm, mp3, wav) |
| sourcetype | string | The source type (must be one of the following: data, httpsrc, filesrc, websocket) |
| playmode | string | The play mode. The play mode is only set if the `audiotype` parameter is set to pcm. (must be one of the following: system, app) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | uint32_t | The unique ID assigned to the opened player instance |
| success | bool | Indicates whether the operation was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.SystemAudioPlayer.1.Open",
"params":{
"audiotype":"pcm",
"sourcetype":"httpsrc",
"playmode":"system"
}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.SystemAudioPlayer.1.Open", "params":{"audiotype":"pcm", "sourcetype":"httpsrc", "playmode":"system"}}'http://127.0.0.1:9998/jsonrpc

```
</details>


<details>
 <summary><kbd>JS</kbd></summary>
 
 ```javascript

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function openPlayer(audiotype, sourcetype, playmode) {
  thunderJS.SystemAudioPlayer.Open({audiotype: audiotype, sourcetype: sourcetype, playmode: playmode})
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="openPlayer('pcm', 'httpsrc', 'system')">Open Player</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void OpenPlayer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["audiotype"] = "pcm";
    parameters["sourcetype"] = "data";
    parameters["playmode"] = "system";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "id": 1,
        "success": true
    }
}
```

<a name="method.Play"></a>
## Play<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method plays audio on the specified player. Note that if a player is using one play mode and another player tries to play audio using the same play mode, then an error returns indicating that the hardware resource has already been acquired by the session and includes the player ID. This method is useful for managing multiple audio players and ensuring that hardware resources are not overused.

This method triggers the [OnSAPEvents](#event.OnSAPEvents)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | digit | A unique digit identifier for a player instance |
| url | string | The source URL. If no port number is provided for a web socket source, then the player uses 40001 as the default port |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the audio is played successfully, false otherwise |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.SystemAudioPlayer.1.Play",
"params":{"id":123, "url":"http://example.com/audio.mp3"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.SystemAudioPlayer.1.Play", "params":{"id":123, "url":"http://example.com/audio.mp3"}}'http://127.0.0.1:9998/jsonrpc

```
</details>


<details>
 <summary><kbd>JS</kbd></summary>
 
 ```javascript

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function playAudio(id, url) {
  thunderJS.SystemAudioPlayer.Play({id: id, url: url})
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="playAudio(1, 'http://example.com/audio.mp3')">Play Audio</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void Play(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["id"] = "1";
    parameters["url"] = "http://example.com";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true
    }
}
```

<a name="method.PlayBuffer"></a>
## PlayBuffer<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method buffers the audio playback on the specified player. It requires a unique digit identifier for a player instance and the size of the buffer. The method is designed to enhance the audio playback experience by buffering the audio data before playing it.

This method triggers the [OnSAPEvents](#event.OnSAPEvents)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | integer | A unique digit identifier for a player instance |
| data | integer | Size of the buffer |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the buffering is successful, false otherwise |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.SystemAudioPlayer.1.PlayBuffer",
"params":{"id":123, "data":500}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.SystemAudioPlayer.1.PlayBuffer", "params":{"id":123, "data":1024}}'http://127.0.0.1:9998/jsonrpc

```
</details>


<details>
 <summary><kbd>JS</kbd></summary>
 
 ```javascript

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function playBuffer(input) {
  thunderJS.SystemAudioPlayer.PlayBuffer(input)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="playBuffer('input')">PlayBuffer</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void PlayBuffer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["id"] = "123"; // replace with actual id
    parameters["data"] = "1024"; // replace with actual buffer size
    std::string result;
    if (invokeJSONRPC(remoteObject, "SystemAudioPlayer.PlayBuffer", parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true
    }
}
```

<a name="method.Pause"></a>
## Pause<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method pauses playback on the specified player. Pause is only supported for HTTP and file source types. It requires a unique digit identifier for a player instance to function.

This method triggers the [OnSAPEvents](#event.OnSAPEvents)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | string | A unique digit identifier for a player instance |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation is successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.SystemAudioPlayer.1.Pause",
"params":{"id":12345}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.SystemAudioPlayer.1.Pause", "params":{"id":123}}'http://127.0.0.1:9998/jsonrpc

```
</details>


<details>
 <summary><kbd>JS</kbd></summary>
 
 ```javascript

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function pausePlayer(id) {
  thunderJS.SystemAudioPlayer.Pause(id)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="pausePlayer(1)">Pause Player</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void Pause(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["id"] = "123"; // replace 123 with actual id
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true
    }
}
```

<a name="method.Resume"></a>
## Resume<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method resumes playback on the specified player. Resume is only supported for HTTP and file source types. It requires a unique digit identifier for a player instance to function.

This method triggers the [OnSAPEvents](#event.OnSAPEvents)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | string | A unique digit identifier for a player instance |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation is successful |

Note: The method `Resume` is a virtual function and returns a `uint32_t` value. However, for the purpose of this documentation, the return type is simplified to a boolean value indicating the success of the operation.

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.SystemAudioPlayer.1.Resume",
"params":{"id":12345}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.SystemAudioPlayer.1.Resume", "params":{"id":123}}'http://127.0.0.1:9998/jsonrpc

```
</details>


<details>
 <summary><kbd>JS</kbd></summary>
 
 ```javascript

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function resumePlayback(id) {
  thunderJS.SystemAudioPlayer.Resume({id: id})
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="resumePlayback(1)">Resume Playback</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void Resume(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["id"] = "123"; // replace 123 with actual id
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true
    }
}
```
<a name="head.Notifications"></a>
# Notifications
Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.
The following events are provided by the org.rdk.SystemAudioPlayer plugin:
<a name="event.OnSAPEvents"></a>
## OnSAPEvents<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This event is triggered during playback for each player. Events from each player are broadcast to all registered clients. The client is responsible for checking the player `id` attribute and discarding events for unwanted players. 

The following events can be triggered:

- `PLAYBACK_STARTED`: Triggered when playback starts.
- `PLAYBACK_FINISHED`: Triggered when playback finishes normally. **Note**: Web socket playback is continuous and does not receive the `PLAYBACK_FINISHED` event until the stream contains `EOS`.
- `PLAYBACK_PAUSED`: Triggered when playback is paused.
- `PLAYBACK_RESUMED`: Triggered when playback resumes.
- `NETWORK_ERROR`: Triggered when a playback network error occurs (httpsrc/web socket).
- `PLAYBACK_ERROR`: Triggered when any other playback error occurs (internal issue).
- `NEED_DATA`: Triggered when the buffer needs more data to play.

This event is triggered by [Resume](#method.Resume)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| id | string | A unique identifier for a player instance |
| event | string | A playback event |

### Example

```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnSAPEvents",
  "params": {"id": "unique_player_id", "event": "PLAYBACK_STARTED"}
}
```

