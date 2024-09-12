# UserSettings Plugin
**Version: [1.0.0](https://github.com/rdkcentral/rdkservices/blob/main/UserSettings/CHANGELOG.md)**
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
The `UserSettings` that is responsible for persisting and notifying listeners of any change of these settings.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].
<a name="head.Configuration"></a>
# Configuration
The table below lists configuration options of the plugin.
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.UserSettings*) |
| classname | string | Class name: *org.rdk.UserSettings* |
| locator | string | Library name: *libWPEFrameworkUserSettings.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="head.Methods"></a>
# Methods and Notifications
The following methods are provided by the org.rdk.UserSettings plugin:
| Method | Description |Event|
| :-------- | :-------- | :-------- |
| [SetAudioDescription](#method.SetAudioDescription) | Sets AudioDescription ON/OFF | [OnAudioDescriptionChanged](#event.OnAudioDescriptionChanged)|
| [GetAudioDescription](#method.GetAudioDescription) | Gets current AudioDescription setting | NA |
| [SetPreferredAudioLanguages](#method.SetPreferredAudioLanguages) | Set preferred audio languages | [OnPreferredAudioLanguagesChanged](#event.OnPreferredAudioLanguagesChanged)|
| [GetPreferredAudioLanguages](#method.GetPreferredAudioLanguages) | Gets Preferred Audio Languages | NA |
| [SetPresentationLanguage](#method.SetPresentationLanguage) | Sets the presentation languages | [OnPresentationLanguageChanged](#event.OnPresentationLanguageChanged)|
| [GetPresentationLanguage](#method.GetPresentationLanguage) | Gets the presentation languages | NA |
| [SetCaptions](#method.SetCaptions) | Sets Captions ON/OFF | [OnCaptionsChanged](#event.OnCaptionsChanged)|
| [GetCaptions](#method.GetCaptions) | Gets the Captions setting | NA |
| [SetPreferredCaptionsLanguages](#method.SetPreferredCaptionsLanguages) | Set preferred languages for captions | [OnPreferredCaptionsLanguagesChanged](#event.OnPreferredCaptionsLanguagesChanged)|
| [GetPreferredCaptionsLanguages](#method.GetPreferredCaptionsLanguages) | Gets current captions languages | NA |
| [SetPreferredClosedCaptionService](#method.SetPreferredClosedCaptionService) | Sets the Preferred Closed Caption Service | [OnPreferredClosedCaptionServiceChanged](#event.OnPreferredClosedCaptionServiceChanged)|
| [GetPreferredClosedCaptionService](#method.GetPreferredClosedCaptionService) | Gets current CC Service setting | NA |
| [SetPrivacyMode](#method.SetPrivacyMode) | Sets the Privacy Mode | [OnPrivacyModeChanged](#event.OnPrivacyModeChanged)|
| [GetPrivacyMode](#method.GetPrivacyMode) | Gets current PrivacyMode setting | NA |

<a name="method.SetAudioDescription"></a>
## SetAudioDescription<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the audio description ON/OFF. Players should prefer audio descriptive tracks over normal audio track when enabled. This is particularly useful for users who require additional auditory assistance.

This method triggers the [OnAudioDescriptionChanged](#event.OnAudioDescriptionChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Enables or disables the audio description |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | Returns "null" after successful execution |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetAudioDescription",
"params":{"enabled":true}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetAudioDescription", "params":{"enabled":true}}'http://127.0.0.1:9998/jsonrpc

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
function setAudioDescription(enabled) {
  thunderJS.UserSettings.SetAudioDescription(enabled)
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
<button onclick="setAudioDescription(true)">Set Audio Description</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetAudioDescription(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["enabled"] = true; // replace with actual value
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
    "result": "null"
}
```

<a name="method.GetAudioDescription"></a>
## GetAudioDescription<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the current audio description setting. It checks whether the audio description is enabled or disabled and returns the status. This method is useful for accessibility features, particularly for visually impaired users who might rely on audio descriptions.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Returns true if the audio description is enabled, false if it is disabled. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetAudioDescription"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetAudioDescription"}' http://127.0.0.1:9998/jsonrpc

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
function getAudioDescription() {
  thunderJS.UserSettings.GetAudioDescription()
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
<button onclick="getAudioDescription()">Get Audio Description</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetAudioDescription(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": true
}
```

<a name="method.SetPreferredAudioLanguages"></a>
## SetPreferredAudioLanguages<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets a prioritized list of ISO 639-2/B codes for the preferred audio languages, expressed as a comma-separated list of languages of zero or more elements. The players will pick the audio track that has the best match compared with this list. In the absence of a matching track, the player should by best effort select the preferred audio track.

This method triggers the [OnPreferredAudioLanguagesChanged](#event.OnPreferredAudioLanguagesChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | A prioritized list of ISO 639-2/B codes for the preferred audio languages |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | "null" |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetPreferredAudioLanguages",
"params":{"preferredLanguages":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetPreferredAudioLanguages", "params":{"preferredLanguages":"en,fr,de"}}'http://127.0.0.1:9998/jsonrpc

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
function setPreferredAudioLanguages(preferredLanguages) {
  thunderJS.UserSettings.SetPreferredAudioLanguages(preferredLanguages)
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
<button onclick="setPreferredAudioLanguages('eng,fra')">setPreferredAudioLanguages</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetPreferredAudioLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    parameters["preferredLanguages"] = "en,fr,de";
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
    "result": null
}
```

<a name="method.GetPreferredAudioLanguages"></a>
## GetPreferredAudioLanguages<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the current preferred audio languages setting. It retrieves the user's preferred languages for audio output. This is particularly useful in multilingual applications or systems where the user's language preference is required.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The current preferred audio languages setting. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPreferredAudioLanguages"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetPreferredAudioLanguages"}' http://127.0.0.1:9998/jsonrpc

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
function getPreferredAudioLanguages() {
  thunderJS.UserSettings.GetPreferredAudioLanguages()
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
<button onclick="getPreferredAudioLanguages()">Get Preferred Audio Languages</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetPreferredAudioLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": "English,Spanish"
}
```

<a name="method.SetPresentationLanguage"></a>
## SetPresentationLanguage<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the presentation languages in a full BCP 47 value, including script, region, and variant. The presentation languages can be set to "en-US", "es-US", "en-CA", "fr-CA". This method is used to change the language of the presentation.

This method triggers the [OnPresentationLanguageChanged](#event.OnPresentationLanguageChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The presentation language to be set in BCP 47 format |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The method returns "null" after successfully setting the presentation language |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetPresentationLanguage",
"params":{"presentationLanguages":"en-US"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetPresentationLanguage", "params":{"presentationLanguages":"en-US"}}'http://127.0.0.1:9998/jsonrpc

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
function setPresentationLanguage(presentationLanguages) {
  thunderJS.UserSettings.SetPresentationLanguage(presentationLanguages)
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
<button onclick="setPresentationLanguage('en-US')">Set Presentation Language</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetPresentationLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["presentationLanguages"] = "en-US";
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
    "result": "null"
}
```

<a name="method.GetPresentationLanguage"></a>
## GetPresentationLanguage<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method gets the presentation languages. The presentation languages can be "en-US", "es-US", "en-CA", "fr-CA". This method is used to retrieve the current language setting of the presentation.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The current language setting of the presentation. Possible values are "en-US", "es-US", "en-CA", "fr-CA". |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPresentationLanguage",
"params":{}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetPresentationLanguage"}' http://127.0.0.1:9998/jsonrpc

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
function getPresentationLanguage() {
  thunderJS.UserSettings.GetPresentationLanguage()
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
<button onclick="getPresentationLanguage()">Get Presentation Language</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetPresentationLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": "en-US"
}
```

<a name="method.SetCaptions"></a>
## SetCaptions<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method sets captions ON/OFF. A setting of ON indicates that players should select a subtitle track for presentation. The setting does not influence any running sessions. It is up to the player to enforce the setting. This is a global state persisted by the text track plug-in applying to all forms of text; closed captions, captions and timed text types. Media players should listen to OnCaptionsChanged notifications to react to platform wide dynamic state changes of this state while a playback is active. When media players start playback, they should also call the GetCaptions method to retrieve the current enabled state. This holds true for media players that utilize text track render sessions for text track decode-display and also for media players or apps that decode-display internally.

This method triggers the [OnCaptionsChanged](#event.OnCaptionsChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Sets the state |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | "null" |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetCaptions",
"params":{"enabled":true}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetCaptions", "params":{"enabled":true}}'http://127.0.0.1:9998/jsonrpc

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
function setCaptions(enabled) {
  thunderJS.UserSettings.SetCaptions(enabled)
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
<button onclick="setCaptions(true)">Set Captions</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetCaptions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["enabled"] = true; // Set the value for 'enabled' parameter
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
    "result": "null"
}
```

<a name="method.GetCaptions"></a>
## GetCaptions<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the captions setting. It retrieves the current state of the captions setting and returns it. This method is useful when you need to check if the captions are enabled or not.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Returns true if captions are enabled, false otherwise. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetCaptions"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetCaptions"}' http://127.0.0.1:9998/jsonrpc

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
function getCaptions() {
  thunderJS.UserSettings.GetCaptions()
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
<button onclick="getCaptions()">Get Captions</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetCaptions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": true
}
```

<a name="method.SetPreferredCaptionsLanguages"></a>
## SetPreferredCaptionsLanguages<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the preferred languages for captions. It takes a prioritized list of ISO 639-2/B codes for the preferred captions languages, expressed as a comma-separated list of languages of zero or more elements. The players will pick the subtitle track that has the best match compared with this list. In the absence of a matching track, the player should by best effort select the preferred subtitle track.

This method triggers the [OnPreferredCaptionsLanguagesChanged](#event.OnPreferredCaptionsLanguagesChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The list to set (e.g. "eng,fra") |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | "null" |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetPreferredCaptionsLanguages",
"params":{"preferredLanguages":"eng,fra"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetPreferredCaptionsLanguages", "params":{"preferredLanguages":"eng,fra"}}'http://127.0.0.1:9998/jsonrpc

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
function setPreferredCaptionsLanguages(preferredLanguages) {
  thunderJS.UserSettings.SetPreferredCaptionsLanguages(preferredLanguages)
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
<button onclick="setPreferredCaptionsLanguages('eng,fra')">Set Preferred Captions Languages</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetPreferredCaptionsLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    parameters["preferredLanguages"] = "eng,fra";
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
    "result": "null"
}
```

<a name="method.GetPreferredCaptionsLanguages"></a>
## GetPreferredCaptionsLanguages<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the current preferred captions languages setting. It retrieves the languages that are currently set as preferred for captions. The languages are represented in a string format (e.g. "eng,fra").

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The current preferred captions languages setting. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPreferredCaptionsLanguages"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetPreferredCaptionsLanguages"}' http://127.0.0.1:9998/jsonrpc

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
function getPreferredCaptionsLanguages() {
  thunderJS.UserSettings.GetPreferredCaptionsLanguages()
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
<button onclick="getPreferredCaptionsLanguages()">Get Preferred Captions Languages</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetPreferredCaptionsLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": "eng,fra"
}
```

<a name="method.SetPreferredClosedCaptionService"></a>
## SetPreferredClosedCaptionService<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the preferred closed caption service. The setting should be honored by the player. The behavior of AUTO may be player specific. Valid input for service is "CC[1-4]", "TEXT[1-4]", "SERVICE[1-64]".


This method triggers the [OnPreferredClosedCaptionServiceChanged](#event.OnPreferredClosedCaptionServiceChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| service | string | Identifies the service to display e.g. "CC3". |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | "null" |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetPreferredClosedCaptionService",
"params":{"service":"CC3"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetPreferredClosedCaptionService", "params":{"service":"CC3"}}'http://127.0.0.1:9998/jsonrpc

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
function setPreferredClosedCaptionService(service) {
  thunderJS.UserSettings.SetPreferredClosedCaptionService(service)
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
<button onclick="setPreferredClosedCaptionService('CC3')">Set Preferred Closed Caption Service</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetPreferredClosedCaptionService(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["service"] = "CC3";
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
    "result": null
}
```

<a name="method.GetPreferredClosedCaptionService"></a>
## GetPreferredClosedCaptionService<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method gets the current preferred closed caption service setting. It identifies the service to display, for example, "CC3".

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| service | string | The preferred closed caption service setting. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPreferredClosedCaptionService"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetPreferredClosedCaptionService"}' http://127.0.0.1:9998/jsonrpc

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
function getPreferredClosedCaptionService() {
  thunderJS.UserSettings.GetPreferredClosedCaptionService()
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
<button onclick="getPreferredClosedCaptionService()">Get Preferred Closed Caption Service</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetPreferredClosedCaptionService(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": "CC3"
}
```

<a name="method.SetPrivacyMode"></a>
## SetPrivacyMode<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method sets the privacy mode. The setting should be honored by the telemetry. If privacy mode is "do_not_share", logs and crash report should not be uploaded. This is crucial for maintaining user privacy and ensuring data security.

This method triggers the [OnPrivacyModeChanged](#event.OnPrivacyModeChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The privacy mode to be set. Possible values are "share", "do_not_share" |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The return of this API is "null". |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.SetPrivacyMode",
"params":{"privacyMode":"SHARE"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.SetPrivacyMode", "params":{"privacyMode":"SHARE"}}'http://127.0.0.1:9998/jsonrpc

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
function setPrivacyMode(privacyMode) {
  thunderJS.UserSettings.SetPrivacyMode(privacyMode)
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
<button onclick="setPrivacyMode('SHARE')">Set Privacy Mode</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void SetPrivacyMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["privacyMode"] = "SHARE"; // or "DO_NOT_SHARE"
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
    "result": null
}
```

<a name="method.GetPrivacyMode"></a>
## GetPrivacyMode<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method gets the current privacy mode setting. The privacy mode can be set to different levels such as "SHARE". The current setting is returned as a string.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The current privacy mode setting. For example, "SHARE". |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPrivacyMode"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.UserSettings.1.GetPrivacyMode"}' http://127.0.0.1:9998/jsonrpc

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
function getPrivacyMode() {
  thunderJS.UserSettings.GetPrivacyMode()
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
<button onclick="getPrivacyMode()">Get Privacy Mode</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>

 ```cpp

void GetPrivacyMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
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
    "result": "SHARE"
}
```
<a name="head.Notifications"></a>
# Notifications
Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.
The following events are provided by the org.rdk.UserSettings plugin:
<a name="event.OnAudioDescriptionChanged"></a>
## OnAudioDescriptionChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The audio description setting has changed.

This event is triggered by [SetAudioDescription](#method.SetAudioDescription)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Indicates whether the audio description is enabled or disabled |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnAudioDescriptionChanged",
  "params": {"enabled": true}
}
```

<a name="event.OnPreferredAudioLanguagesChanged"></a>
## OnPreferredAudioLanguagesChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This event is triggered when the preferred languages setting has changed.

This event is triggered by [SetPreferredAudioLanguages](#method.SetPreferredAudioLanguages)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The new preferred audio languages |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPreferredAudioLanguagesChanged",
  "params": {"preferredLanguages": "English, Spanish"}
}
```

<a name="event.OnPresentationLanguageChanged"></a>
## OnPresentationLanguageChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The presentation languages setting has changed.

This event is triggered by [SetPresentationLanguage](#method.SetPresentationLanguage)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The new presentation languages setting |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPresentationLanguageChanged",
  "params": {"presentationLanguages": "English"}
}
```

<a name="event.OnCaptionsChanged"></a>
## OnCaptionsChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The captions setting has changed.

This event is triggered by [SetCaptions](#method.SetCaptions)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Indicates whether the captions are enabled or disabled |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnCaptionsChanged",
  "params": {"enabled": true}
}
```

<a name="event.OnPreferredCaptionsLanguagesChanged"></a>
## OnPreferredCaptionsLanguagesChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The preferred captions languages setting has changed.

This event is triggered by [SetPreferredCaptionsLanguages](#method.SetPreferredCaptionsLanguages)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The preferred languages for captions. |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPreferredCaptionsLanguagesChanged",
  "params": {"preferredLanguages": "English, Spanish"}
}
```

<a name="event.OnPreferredClosedCaptionServiceChanged"></a>
## OnPreferredClosedCaptionServiceChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The preferred closed caption service setting has changed.

This event is triggered by [SetPreferredClosedCaptionService](#method.SetPreferredClosedCaptionService)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| service | string | The new preferred closed caption service. Possible values are "CC[1-4]", "TEXT[1-4]", "SERVICE[1-64]". |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPreferredClosedCaptionServiceChanged",
  "params": {"service": "CC1"}
}
```

<a name="event.OnPrivacyModeChanged"></a>
## OnPrivacyModeChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The privacy mode setting has changed.

This event is triggered by [SetPrivacyMode](#method.SetPrivacyMode)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The new privacy mode. Possible values are "SHARE", "DO_NOT_SHARE". |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPrivacyModeChanged",
  "params": {"privacyMode": "SHARE"}
}
```
