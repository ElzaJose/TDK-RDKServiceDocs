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

This API sets the AudioDescription to either ON or OFF. When enabled, players should prefer Audio Descriptive tracks over the normal audio track. This is particularly useful for visually impaired users who require additional narration to understand the content. The change in AudioDescription triggers the OnAudioDescriptionChanged event.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Determines whether the AudioDescription is Enabled (true) or Disabled (false) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The API returns "null" after successfully setting the AudioDescription. |

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

This API gets the current AudioDescription setting. It checks whether the audio description is enabled or disabled and returns the status. This is useful for accessibility features where audio descriptions are provided for visually impaired users.

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
"method":"org.rdk.UserSettings.1.GetAudioDescription",
"params":{}
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

This API is used to set a prioritized list of ISO 639-2/B codes for the preferred audio languages, expressed as a comma-separated list of languages of zero or more elements. The players will pick the audio track that has the best match compared with this list. In the absence of a matching track, the player should by best effort select the preferred audio track. This method triggers the `OnPreferredAudioLanguagesChanged` event.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | A comma-separated list of ISO 639-2/B codes representing the preferred audio languages. |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | This method returns "null". |

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
<button onclick="setPreferredAudioLanguages('en,fr,de')">Set Preferred Audio Languages</button>
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

This API gets the current PreferredAudioLanguages setting. It is used to retrieve the user's preferred audio languages for media playback. The preferred languages are returned as a string.

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
    "result": "English,French,Spanish"
}
```

<a name="method.SetPresentationLanguage"></a>
## SetPresentationLanguage<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the presentationLanguages in a full BCP 47 value, including script, region, variant. It accepts a string parameter representing the language in BCP 47 format such as "en-US", "es-US", "en-CA", "fr-CA". When the presentation language is changed, it triggers the OnPresentationLanguageChanged event.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The language to be set in BCP 47 format |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The API returns "null" after successfully setting the presentation language |

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

This API is used to get the presentation languages. The presentation languages can be "en-US", "es-US", "en-CA", "fr-CA". The method returns a string representation of the presentation language.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The presentation language. Possible values are "en-US", "es-US", "en-CA", "fr-CA". |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.UserSettings.1.GetPresentationLanguage"
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

This API sets the captions ON or OFF. A setting of ON indicates that Players should select a subtitle track for presentation. The setting does not influence any running sessions. It is up to the player to enforce the setting. This is a global state persisted by the TextTrack plug-in applying to all forms of text; closed captions, Captions and timed text types. Media players should listen to OnCaptionsChanged notifications to react to platform wide dynamic state changes of this state while a playback is active. When media players start playback, they should also call the GetCaptions method to retrieve the current enabled state. This holds true for media players that utilize TextTrack render sessions for text track decode-display and also for media players or apps that decode-display internally.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Sets the state of the captions |

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

This API is used to get the captions setting. It retrieves the current state of the captions setting and returns a boolean value indicating whether the captions are enabled or not.

### Parameters
This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | bool | Returns true if captions are enabled, false otherwise. |

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

This API is used to set the preferred languages for captions. It takes a prioritized list of ISO 639-2/B codes for the preferred Captions languages, expressed as a comma-separated list of languages of zero or more elements. The players will pick the subtitle track that has the best match compared with this list. In the absence of a matching track, the player should by best effort select the preferred subtitle track.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The list to set (e.g. "eng,fra") |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | "null" |

Note: This method triggers the `OnPreferredCaptionsLanguagesChanged` event when the preferred languages are changed.

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
    parameters["preferredLanguages"] = "eng,fra";
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

<a name="method.GetPreferredCaptionsLanguages"></a>
## GetPreferredCaptionsLanguages<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the current PreferredCaptionsLanguages setting. It retrieves the preferred languages for captions, for example, "eng,fra". This method is useful when you need to know the user's language preference for captions.

### Parameters
This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The preferred languages for captions, e.g., "eng,fra". |

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

This API sets the PreferredClosedCaptionService. The setting should be honored by the player. The behaviour of AUTO may be player specific. Valid input for service is "CC[1-4]", "TEXT[1-4]", "SERVICE[1-64]". This method triggers the event OnPreferredClosedCaptionServiceChanged.

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
    "result": "null"
}
```

<a name="method.GetPreferredClosedCaptionService"></a>
## GetPreferredClosedCaptionService<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API gets the current PreferredClosedCaptionService setting. It identifies the service to display, for example, "CC3". This method is used to retrieve the preferred closed caption service from the system.

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

This API sets the PrivacyMode. The setting should be honored by the Telemetry. If privacyMode is "DO_NOT_SHARE", logs and crash report should not be uploaded. This is crucial for maintaining user privacy and ensuring data security. The event `OnPrivacyModeChanged` is triggered when the privacy mode is changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The privacy mode to be set. Possible values are "SHARE", "DO_NOT_SHARE" |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The return of the API is "null". |

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

This API gets the current PrivacyMode setting. The PrivacyMode setting determines the level of privacy the user has chosen for their data. For example, a PrivacyMode of "SHARE" would indicate that the user has chosen to share their data.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The current PrivacyMode setting. Possible return value could be "SHARE". |

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
## OnAudioDescriptionChanged

The AudioDescription setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Enabled/Disabled |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnAudioDescriptionChanged",
  "params": {"enabled": true}
}
```

<a name="event.OnPreferredAudioLanguagesChanged"></a>
## OnPreferredAudioLanguagesChanged

The preferredLanguages setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The preferred audio languages |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPreferredAudioLanguagesChanged",
  "params": {"preferredLanguages": "English, Spanish"}
}
```

<a name="event.OnPresentationLanguageChanged"></a>
## OnPresentationLanguageChanged

This event is triggered when the PresentationLanguages setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| presentationLanguages | string | The new PresentationLanguages setting. |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPresentationLanguageChanged",
  "params": {"presentationLanguages": "English"}
}
```

<a name="event.OnCaptionsChanged"></a>
## OnCaptionsChanged

The Captions setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| enabled | bool | Enabled/Disabled |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnCaptionsChanged",
  "params": {"enabled": true}
}
```

<a name="event.OnPreferredCaptionsLanguagesChanged"></a>
## OnPreferredCaptionsLanguagesChanged

This event is triggered when the PreferredCaptionsLanguages setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| preferredLanguages | string | The new preferred languages for captions. |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPreferredCaptionsLanguagesChanged",
  "params": {"preferredLanguages": "English, Spanish"}
}
```

<a name="event.OnPreferredClosedCaptionServiceChanged"></a>
## OnPreferredClosedCaptionServiceChanged

This event is triggered when the PreferredClosedCaptionService setting has changed.

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
## OnPrivacyModeChanged

This event is triggered when the PrivacyMode setting has changed.

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| privacyMode | string | The new privacy mode setting. Possible values are "SHARE" or "DO_NOT_SHARE". |

### Example


```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnPrivacyModeChanged",
  "params": {"privacyMode": "SHARE"}
}
```
