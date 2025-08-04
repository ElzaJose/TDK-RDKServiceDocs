<!-- Generated automatically, DO NOT EDIT! -->
<a name="UserSettings_Plugin"></a>
# UserSettings Plugin

**Version: [1.0.0]()**

A org.rdk.UserSettings plugin for Thunder framework.

### Table of Contents

- [Abbreviation, Acronyms and Terms](#Abbreviation,_Acronyms_and_Terms)
- [Description](#Description)
- [Configuration](#Configuration)
- [Methods](#Methods)
- [Notifications](#Notifications)

<a name="Abbreviation,_Acronyms_and_Terms"></a>
# Abbreviation, Acronyms and Terms

[[Refer to this link](overview/aat.md)]

<a name="Description"></a>
# Description


The **UserSettings** service in the RDK framework is a plugin designed to manage and inspect user preferences related to audio, captions, and presentation settings. It provides interfaces for configuring and retrieving settings such as preferred audio languages, audio descriptions, captions, and their respective languages. This service ensures a customizable and accessible user experience by allowing applications to interact with these settings programmatically.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.UserSettings*) |
| classname | string | Class name: *org.rdk.UserSettings* |
| locator | string | Library name: *libWPEFrameworkUserSettings.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.UserSettings plugin:

org.rdk.UserSettings interface methods:

| Method | Description |Event|
| :-------- | :-------- | :-------- |
| [setAudioDescription](#setAudioDescription) | set audio description | [onAudioDescriptionChanged](#onAudioDescriptionChanged) |
| [setPreferredAudioLanguages](#setPreferredAudioLanguages) | Set preferred audio languages | [onPreferredAudioLanguagesChanged](#onPreferredAudioLanguagesChanged) |
| [setPresentationLanguage](#setPresentationLanguage) | Sets presentation language | [onPresentationLanguageChanged](#onPresentationLanguageChanged) |
| [setCaptions](#setCaptions) | manage captions settings | [onCaptionsChanged](#onCaptionsChanged) |
| [setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) | Set preferred captions languages | [onPreferredCaptionsLanguagesChanged](#onPreferredCaptionsLanguagesChanged) |
| [setPreferredClosedCaptionService](#setPreferredClosedCaptionService) | Set preferred caption service | [onPreferredClosedCaptionServiceChanged](#onPreferredClosedCaptionServiceChanged) |
| [setPrivacyMode](#setPrivacyMode) | Set privacy mode | [onPrivacyModeChanged](#onPrivacyModeChanged) |
| [setPinControl](#setPinControl) | set pin control | [onPinControlChanged](#onPinControlChanged) |
| [setViewingRestrictions](#setViewingRestrictions) | set viewing restrictions | [onViewingRestrictionsChanged](#onViewingRestrictionsChanged) |
| [setViewingRestrictionsWindow](#setViewingRestrictionsWindow) | Set viewing restrictions window | [onViewingRestrictionsWindowChanged](#onViewingRestrictionsWindowChanged) |
| [setLiveWatershed](#setLiveWatershed) | set live watershed | [onLiveWatershedChanged](#onLiveWatershedChanged) |
| [setPlaybackWatershed](#setPlaybackWatershed) | set playback watershed | [onPlaybackWatershedChanged](#onPlaybackWatershedChanged) |
| [setBlockNotRatedContent](#setBlockNotRatedContent) | Block unrated content | [onBlockNotRatedContentChanged](#onBlockNotRatedContentChanged) |
| [setPinOnPurchase](#setPinOnPurchase) | Set pin on purchase | [onPinOnPurchaseChanged](#onPinOnPurchaseChanged) |
| [setHighContrast](#setHighContrast) | enable high contrast | [onHighContrastChanged](#onHighContrastChanged) |
| [setVoiceGuidance](#setVoiceGuidance) | configure voice guidance | [onVoiceGuidanceChanged](#onVoiceGuidanceChanged) |
| [setVoiceGuidanceRate](#setVoiceGuidanceRate) | Sets voice guidance rate | [onVoiceGuidanceRateChanged](#onVoiceGuidanceRateChanged) |
| [setVoiceGuidanceHints](#setVoiceGuidanceHints) | set voice guidance hints | [onVoiceGuidanceHintsChanged](#onVoiceGuidanceHintsChanged) |
| [setContentPin](#setContentPin) | set content pin | [onContentPinChanged](#onContentPinChanged) |
| [getAudioDescription](#getAudioDescription) | audio description retrieval | NA |
| [getPreferredAudioLanguages](#getPreferredAudioLanguages) | Get preferred audio languages | NA |
| [getPresentationLanguage](#getPresentationLanguage) | presentation language retrieval | NA |
| [getCaptions](#getCaptions) | fetch video captions | NA |
| [getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) | preferred captions languages | NA |
| [getPreferredClosedCaptionService](#getPreferredClosedCaptionService) | preferred caption service | NA |
| [getPrivacyMode](#getPrivacyMode) | privacy mode details | NA |
| [getPinControl](#getPinControl) | Pin control management | NA |
| [getViewingRestrictions](#getViewingRestrictions) | viewing restrictions info | NA |
| [getViewingRestrictionsWindow](#getViewingRestrictionsWindow) | viewing restrictions window | NA |
| [getLiveWatershed](#getLiveWatershed) | live watershed data | NA |
| [getPlaybackWatershed](#getPlaybackWatershed) | playback watershed details | NA |
| [getBlockNotRatedContent](#getBlockNotRatedContent) | Get unrated content | NA |
| [getPinOnPurchase](#getPinOnPurchase) | Get PIN on purchase | NA |
| [getHighContrast](#getHighContrast) | high contrast settings | NA |
| [getVoiceGuidance](#getVoiceGuidance) | voice guidance retrieval | NA |
| [getVoiceGuidanceRate](#getVoiceGuidanceRate) | voice guidance rate | NA |
| [getVoiceGuidanceHints](#getVoiceGuidanceHints) | voice guidance hints | NA |
| [getMigrationState](#getMigrationState) | migration state retrieval | NA |
| [getMigrationStates](#getMigrationStates) | migration states retrieval | NA |
| [getContentPin](#getContentPin) | get content pin details | NA |


<a name="setAudioDescription"></a>
## *setAudioDescription*


Enables or disables audio descriptions, which provide spoken narration of key visual elements in content for users with visual impairments. This feature enhances accessibility by making video content more inclusive and easier to follow for visually impaired audiences.

### Related Functions
[getAudioDescription](#getAudioDescription) : Retrieves the current status of the audio description setting.

### Events

| Event | Description |
| :-------- | :-------- |
| [onAudioDescriptionChanged](#onAudioDescriptionChanged) | Triggered when the audio description changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Audio Description Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setAudioDescription",
    "params": {
        "enabled": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setAudioDescription",
"params": {
"enabled": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.setAudioDescription(enabled)
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
<button onclick="setAudioDescription(true)">setAudioDescription</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setAudioDescription(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enabled"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPreferredAudioLanguages"></a>
## *setPreferredAudioLanguages*


Allows users to set their preferred audio languages for content playback, ensuring a personalized and seamless viewing experience. This function helps prioritize audio tracks in the specified languages when available, enhancing accessibility and convenience.

### Related Functions
[getPreferredAudioLanguages](#getPreferredAudioLanguages) : Retrieves the currently set preferred audio languages.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPreferredAudioLanguagesChanged](#onPreferredAudioLanguagesChanged) | Triggered when the audio preferred Audio languages changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.preferredLanguages | string | A prioritized list of ISO 639-2/B codes for the preferred audio languages |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPreferredAudioLanguages",
    "params": {
        "preferredLanguages": "eng"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPreferredAudioLanguages",
"params": {
"preferredLanguages": "eng"
}
}' http://127.0.0.1:9998/jsonrpc
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
  thunderJS.setPreferredAudioLanguages(preferredLanguages)
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
<button onclick="setPreferredAudioLanguages('eng')">setPreferredAudioLanguages</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPreferredAudioLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["preferredLanguages"] = "eng";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPresentationLanguage"></a>
## *setPresentationLanguage*


Allows users to set their preferred presentation language for content, ensuring a personalized viewing experience tailored to their language preferences. This setting impacts the language used for on-screen text, menus, and other presentation elements.

### Related Functions
[getPresentationLanguage](#getPresentationLanguage) : Retrieves the currently set presentation language.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPresentationLanguageChanged](#onPresentationLanguageChanged) | Triggered when the presentation Language changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.presentationLanguage | string | The preferred presentationLanguage in a full BCP 47 value, including script, * region, variant The language set and used by Immerse UI |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPresentationLanguage",
    "params": {
        "presentationLanguage": "en-US"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPresentationLanguage",
"params": {
"presentationLanguage": "en-US"
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setPresentationLanguage(presentationLanguage) {
  thunderJS.setPresentationLanguage(presentationLanguage)
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
<button onclick="setPresentationLanguage('en-US')">setPresentationLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPresentationLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["presentationLanguage"] = "en-US";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setCaptions"></a>
## *setCaptions*


Enables or disables captions for your viewing experience, allowing you to customize accessibility settings based on your preferences. This function is essential for users who rely on captions for better understanding or accessibility while watching content.

### Related Functions
[getCaptions](#getCaptions) : Retrieves the current status of captions (enabled or disabled).

### Events

| Event | Description |
| :-------- | :-------- |
| [onCaptionsChanged](#onCaptionsChanged) | Triggered when the captions changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Captions Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setCaptions",
    "params": {
        "enabled": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setCaptions",
"params": {
"enabled": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setCaptions(params) {
  thunderJS.setCaptions(params)
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
<button onclick="setCaptions({enabled: true})">setCaptions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setCaptions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enabled"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPreferredCaptionsLanguages"></a>
## *setPreferredCaptionsLanguages*


Allows users to set their preferred languages for captions, ensuring a more personalized and accessible viewing experience. This function helps tailor content to match the user's language preferences, enhancing usability and inclusivity.

### Related Functions
[getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) : Retrieves the currently set preferred captions languages.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPreferredCaptionsLanguagesChanged](#onPreferredCaptionsLanguagesChanged) | Triggered when the PreferredCaption Languages changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.preferredLanguages | string | A prioritized list of ISO 639-2/B codes for the preferred captions languages |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPreferredCaptionsLanguages",
    "params": {
        "preferredLanguages": "eng"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPreferredCaptionsLanguages",
"params": {
"preferredLanguages": "eng"
}
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.setPreferredCaptionsLanguages({ preferredLanguages: preferredLanguages })
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
<button onclick="setPreferredCaptionsLanguages('eng')">setPreferredCaptionsLanguages</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPreferredCaptionsLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["preferredLanguages"] = "eng";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPreferredClosedCaptionService"></a>
## *setPreferredClosedCaptionService*


Allows users to select their preferred closed captioning service for enhanced accessibility and personalized viewing experiences. This setting ensures captions are displayed using the chosen service, improving usability for those who rely on closed captions.

### Related Functions
[getPreferredClosedCaptionService](#getPreferredClosedCaptionService) : Retrieves the currently selected closed captioning service.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPreferredClosedCaptionServiceChanged](#onPreferredClosedCaptionServiceChanged) | Triggered when the Preferred Closed Caption changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.service | string | A string for the preferred closed captions service.  Valid values are AUTO, CC[1-4], TEXT[1-4], SERVICE[1-64] where CC and TEXT is CTA-608 and SERVICE is CTA-708.  AUTO indicates that the choice is left to the player |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPreferredClosedCaptionService",
    "params": {
        "service": "CC3"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPreferredClosedCaptionService",
"params": {
"service": "CC3"
}
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.setPreferredClosedCaptionService(service)
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
<button onclick="setPreferredClosedCaptionService('CC3')">setPreferredClosedCaptionService</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPreferredClosedCaptionService(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["service"] = "CC3";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPrivacyMode"></a>
## *setPrivacyMode*


Allows users to configure their privacy preferences by setting the mode to either "SHARE" or "DO_NOT_SHARE." This ensures control over how personal data is handled, enhancing user privacy and customization.

### Related Functions
[getPrivacyMode](#getPrivacyMode) : Retrieves the current privacy mode setting to confirm or review user preferences.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPrivacyModeChanged](#onPrivacyModeChanged) | Triggered when the Privacy Mode changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.privacyMode | string | The Privacy Mode. Valid values are SHARE, DO_NOT_SHARE |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPrivacyMode",
    "params": {
        "privacyMode": "SHARE"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPrivacyMode",
"params": {
"privacyMode": "SHARE"
}
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.setPrivacyMode(privacyMode)
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
<button onclick="setPrivacyMode('SHARE')">setPrivacyMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPrivacyMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["privacyMode"] = "SHARE";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPinControl"></a>
## *setPinControl*


Enables or disables the PIN control feature, which helps manage access to restricted content or settings based on user preferences. This function is essential for maintaining parental controls or other security measures to prevent unauthorized changes.

### Related Functions
[getPinControl](#getPinControl) : Retrieves the current status of the PIN control feature.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPinControlChanged](#onPinControlChanged) | Triggered when the pincontrol changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.pinControl | boolean | PinControl Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPinControl",
    "params": {
        "pinControl": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPinControl",
"params": {
"pinControl": true
}
}' http://127.0.0.1:9998/jsonrpc
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
function setPinControl(pinControl) {
  thunderJS.setPinControl(pinControl)
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
<button onclick="setPinControl(true)">setPinControl</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPinControl(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["pinControl"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setViewingRestrictions"></a>
## *setViewingRestrictions*


This API allows users to define specific viewing restrictions, such as content access limitations based on age ratings or other criteria, ensuring a controlled and safe viewing experience. It is particularly useful for managing parental controls or enforcing content guidelines tailored to individual preferences.

### Related Functions
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions settings.

### Events

| Event | Description |
| :-------- | :-------- |
| [onViewingRestrictionsChanged](#onViewingRestrictionsChanged) | Triggered when the viewingRestrictions changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.viewingRestrictions | string | A project-specific representation of the time interval when viewing |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setViewingRestrictions",
    "params": {
        "viewingRestrictions": "{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setViewingRestrictions",
"params": {
"viewingRestrictions": "{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setViewingRestrictions(viewingRestrictions) {
  thunderJS.setViewingRestrictions(viewingRestrictions)
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
<button onclick="setViewingRestrictions({\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]})">setViewingRestrictions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setViewingRestrictions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["viewingRestrictions"] = "{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setViewingRestrictionsWindow"></a>
## *setViewingRestrictionsWindow*


Allows users to define a specific time window during which viewing restrictions are applied, ensuring content access aligns with personal or parental control preferences. This feature is useful for managing screen time or restricting access to certain content during designated periods.

### Related Functions
[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the currently set time window for viewing restrictions.

### Events

| Event | Description |
| :-------- | :-------- |
| [onViewingRestrictionsWindowChanged](#onViewingRestrictionsWindowChanged) | Triggered when the viewingRestrictionsWindow changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.viewingRestrictionsWindow | string | A project-specific representation of the time interval |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setViewingRestrictionsWindow",
    "params": {
        "viewingRestrictionsWindow": "ALWAYS"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setViewingRestrictionsWindow",
"params": {
"viewingRestrictionsWindow": "{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}"
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setViewingRestrictionsWindow(viewingRestrictionsWindow) {
  thunderJS.setViewingRestrictionsWindow(viewingRestrictionsWindow)
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
<button onclick="setViewingRestrictionsWindow('{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}')">setViewingRestrictionsWindow</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setViewingRestrictionsWindow(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["viewingRestrictionsWindow"] = "{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setLiveWatershed"></a>
## *setLiveWatershed*


Enables or disables the live watershed setting, which helps manage content accessibility based on predefined viewing restrictions. This feature is particularly useful for ensuring that live content adheres to user-defined guidelines, such as age-appropriate viewing.

### Related Functions
[getLiveWatershed](#getLiveWatershed) : Retrieves the current status of the live watershed setting.

### Events

| Event | Description |
| :-------- | :-------- |
| [onLiveWatershedChanged](#onLiveWatershedChanged) | Triggered when the liveWatershed changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.liveWatershed | boolean | LiveWatershed Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setLiveWatershed",
    "params": {
        "liveWatershed": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setLiveWatershed",
"params": {
"liveWatershed": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setLiveWatershed(liveWatershed) {
  thunderJS.setLiveWatershed({ liveWatershed: liveWatershed })
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
<button onclick="setLiveWatershed(true)">setLiveWatershed</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setLiveWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["liveWatershed"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPlaybackWatershed"></a>
## *setPlaybackWatershed*


Enables or disables the playback watershed setting, which helps enforce content viewing restrictions based on user-defined preferences. This feature is useful for managing access to age-sensitive or restricted content during playback.

### Related Functions
[getPlaybackWatershed](#getPlaybackWatershed) : Retrieves the current status of the playback watershed setting.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPlaybackWatershedChanged](#onPlaybackWatershedChanged) | Triggered when the playbackWatershed changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.playbackWatershed | boolean | PlaybackWatershed Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPlaybackWatershed",
    "params": {
        "playbackWatershed": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPlaybackWatershed",
"params": {
"liveWatershed": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setPlaybackWatershed(liveWatershed) {
  thunderJS.setPlaybackWatershed({ liveWatershed: liveWatershed })
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
<button onclick="setPlaybackWatershed(true)">setPlaybackWatershed</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPlaybackWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["liveWatershed"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setBlockNotRatedContent"></a>
## *setBlockNotRatedContent*


Enables or disables the blocking of unrated content to help users manage viewing restrictions and ensure a safer entertainment experience. This function is particularly useful for parents or guardians who want to prevent access to content without a rating.

### Related Functions
[getBlockNotRatedContent](#getBlockNotRatedContent) : Retrieves the current setting for blocking unrated content.

### Events

| Event | Description |
| :-------- | :-------- |
| [onBlockNotRatedContentChanged](#onBlockNotRatedContentChanged) | Triggered when the blockNotRatedContent changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.blockNotRatedContent | boolean | BlockNotRatedContent Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setBlockNotRatedContent",
    "params": {
        "blockNotRatedContent": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setBlockNotRatedContent",
"params": {
"blockNotRatedContent": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setBlockNotRatedContent(blockNotRatedContent) {
  thunderJS.setBlockNotRatedContent(blockNotRatedContent)
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
<button onclick="setBlockNotRatedContent(true)">setBlockNotRatedContent</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setBlockNotRatedContent(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["blockNotRatedContent"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPinOnPurchase"></a>
## *setPinOnPurchase*


Enables or disables the requirement for a PIN when making purchases, providing an added layer of security to prevent unauthorized transactions. This feature is particularly useful for households with shared access to devices or accounts.

### Related Functions
[getPinOnPurchase](#getPinOnPurchase) : Retrieves the current status of the PIN requirement for purchases.

### Events

| Event | Description |
| :-------- | :-------- |
| [onPinOnPurchaseChanged](#onPinOnPurchaseChanged) | Triggered when the pin on the purchase changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.pinOnPurchase | boolean | setPinOnPurchase Enabled: true/false |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setPinOnPurchase",
    "params": {
        "pinOnPurchase": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setPinOnPurchase",
"params": {
"pinOnPurchase": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setPinOnPurchase(pinOnPurchase) {
  thunderJS.setPinOnPurchase(pinOnPurchase)
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
<button onclick="setPinOnPurchase(true)">setPinOnPurchase</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPinOnPurchase(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["pinOnPurchase"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setHighContrast"></a>
## *setHighContrast*


Enables or disables high contrast mode to improve on-screen visibility for users with visual impairments. This feature enhances accessibility by adjusting the display to provide better contrast between text, images, and backgrounds, making content easier to read and navigate.

### Related Functions
[getHighContrast](#getHighContrast) : Retrieves the current status of high contrast mode (enabled or disabled).

### Events

| Event | Description |
| :-------- | :-------- |
| [onHighContrastChanged](#onHighContrastChanged) | Triggers when the highContrast changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | high contrast enabled(true) or disabled(false) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setHighContrast",
    "params": {
        "enabled": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setHighContrast",
"params": {
"enabled": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setHighContrast(enabled) {
  thunderJS.setHighContrast({ enabled: enabled })
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
<button onclick="setHighContrast(true)">setHighContrast</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setHighContrast(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enabled"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVoiceGuidance"></a>
## *setVoiceGuidance*


Enables or disables voice guidance, a feature designed to assist users with visual impairments by providing audio feedback for on-screen content and navigation. This setting enhances accessibility, ensuring a more inclusive user experience.

### Related Functions
[getVoiceGuidance](#getVoiceGuidance) : Retrieves the current status of the voice guidance feature.

### Events

| Event | Description |
| :-------- | :-------- |
| [onVoiceGuidanceChanged](#onVoiceGuidanceChanged) | Triggers after the voice guidance enabled settings changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | voice guidance enabled(true) or disabled(false) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setVoiceGuidance",
    "params": {
        "enabled": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setVoiceGuidance",
"params": {
"enabled": true
}
}' http://127.0.0.1:9998/jsonrpc
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
function setVoiceGuidance(enabled) {
  thunderJS.setVoiceGuidance(enabled)
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
<button onclick="setVoiceGuidance(true)">setVoiceGuidance</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVoiceGuidance(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enabled"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVoiceGuidanceRate"></a>
## *setVoiceGuidanceRate*


Adjusts the speed of voice guidance to enhance accessibility for users who rely on audio navigation. This function allows customization of the voice guidance rate within a predefined range, ensuring a comfortable and personalized experience.

### Related Functions
[getVoiceGuidanceRate](#getVoiceGuidanceRate) : Retrieves the current speed setting of voice guidance.

### Events

| Event | Description |
| :-------- | :-------- |
| [onVoiceGuidanceRateChanged](#onVoiceGuidanceRateChanged) | Triggered after the voice guidance rate changed. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.rate | number | voice guidance rate value |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setVoiceGuidanceRate",
    "params": {
        "rate": 0.1
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setVoiceGuidanceRate",
"params": {
"rate": 0.1
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setVoiceGuidanceRate(rate) {
  thunderJS.setVoiceGuidanceRate(rate)
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
<button onclick="setVoiceGuidanceRate(0.1)">setVoiceGuidanceRate</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVoiceGuidanceRate(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["rate"] = 0.1;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVoiceGuidanceHints"></a>
## *setVoiceGuidanceHints*


Enables or disables additional hints for voice guidance, providing users with more detailed spoken instructions to enhance navigation and accessibility. This feature is particularly useful for individuals who rely on voice guidance for a more intuitive and supportive user experience.

### Related Functions
[getVoiceGuidanceHints](#getVoiceGuidanceHints) : Retrieves the current status of voice guidance hints (enabled or disabled).

### Events

| Event | Description |
| :-------- | :-------- |
| [onVoiceGuidanceHintsChanged](#onVoiceGuidanceHintsChanged) | Triggered after the voice guidance hints changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hints | boolean | voiceGuidanceHints enabled(true) or disabled(false) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setVoiceGuidanceHints",
    "params": {
        "hints": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setVoiceGuidanceHints",
"params": {
"hints": true
}
}'
http://127.0.0.1:9998/jsonrpc
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
function setVoiceGuidanceHints(hints) {
  thunderJS.setVoiceGuidanceHints({ hints: hints })
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
<button onclick="setVoiceGuidanceHints(true)">setVoiceGuidanceHints</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVoiceGuidanceHints(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["hints"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setContentPin"></a>
## *setContentPin*


Allows users to set or update the content PIN, which is used to restrict access to certain content based on parental controls or other security settings. The PIN must be a 4-digit numeric code, ensuring simplicity and security. This feature helps maintain control over content accessibility, providing a safer and more personalized viewing experience.

### Related Functions
[getContentPin](#getContentPin) : Retrieves the currently set content PIN.

### Events

| Event | Description |
| :-------- | :-------- |
| [onContentPinChanged](#onContentPinChanged) | Triggered when the ContentPin changes. |

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.contentPin | string | contentPin |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | null | On success null will be returned |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.setContentPin",
    "params": {
        "contentPin": "1234"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": null
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.setContentPin",
"params": {
"contentPin": "1234"
}
}' \
http://127.0.0.1:9998/jsonrpc
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
function setContentPin(contentPin) {
  thunderJS.setContentPin(contentPin)
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
<button onclick="setContentPin('1234')">setContentPin</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setContentPin(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["contentPin"] = "1234";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAudioDescription"></a>
## *getAudioDescription*


Retrieves the current status of the audio description feature, which provides additional audio narration for visually impaired users by describing on-screen actions, settings, and events. This function helps users ensure that the audio description feature is enabled or disabled according to their preferences, enhancing accessibility and inclusivity.

### Related Functions
[setAudioDescription](#setAudioDescription) : Enables or disables the audio description feature.

### Events

No Events


### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Audio Description Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getAudioDescription"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getAudioDescription"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getAudioDescription()
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
<button onclick="getAudioDescription()">getAudioDescription</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioDescription(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPreferredAudioLanguages"></a>
## *getPreferredAudioLanguages*


Retrieves the user's preferred audio languages for media playback, ensuring a personalized viewing experience by selecting audio tracks that match their language preferences. This function is essential for users who want to enjoy content in their desired language without manual adjustments.

### Related Functions
[setPreferredAudioLanguages](#setPreferredAudioLanguages) : Allows users to set their preferred audio languages for media playback.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | A prioritized list of ISO 639-2/B codes for the preferred audio languages |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPreferredAudioLanguages"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "eng"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.UserSettings.getPreferredAudioLanguages"}' http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getPreferredAudioLanguages()
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
<button onclick="getPreferredAudioLanguages()">getPreferredAudioLanguages</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPreferredAudioLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPresentationLanguage"></a>
## *getPresentationLanguage*


Retrieves the current presentation language setting, allowing users to confirm or adjust their preferred language for on-screen menus, notifications, and other interface elements. This function ensures a personalized and accessible user experience by aligning the interface language with user preferences.

### Related Functions
[setPresentationLanguage](#setPresentationLanguage) : Allows users to set their preferred presentation language.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The preferred presentationLanguage in a full BCP 47 value, including script, * region, variant The language set and used by Immerse UI |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPresentationLanguage"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "en-US"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getPresentationLanguage"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getPresentationLanguage()
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
<button onclick="getPresentationLanguage()">getPresentationLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPresentationLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getCaptions"></a>
## *getCaptions*


Retrieves the current status of captions, indicating whether they are enabled or disabled. This function helps users confirm their caption settings, ensuring accessibility preferences are met for an improved viewing experience.

### Related Functions
[setCaptions](#setCaptions) : Allows users to enable or disable captions based on their preferences.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Captions Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getCaptions"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getCaptions"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getCaptions()
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
<button onclick="getCaptions()">getCaptions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getCaptions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPreferredCaptionsLanguages"></a>
## *getPreferredCaptionsLanguages*


Retrieves the user's preferred languages for captions, enabling a personalized viewing experience by displaying subtitles in the desired language. This function is essential for ensuring accessibility and convenience for multilingual users.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : Allows users to set their preferred languages for captions.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | A prioritized list of ISO 639-2/B codes for the preferred captions languages |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPreferredCaptionsLanguages"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "eng"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getPreferredCaptionsLanguages"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getPreferredCaptionsLanguages()
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
<button onclick="getPreferredCaptionsLanguages()">getPreferredCaptionsLanguages</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPreferredCaptionsLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPreferredClosedCaptionService"></a>
## *getPreferredClosedCaptionService*


Retrieves the user's preferred closed captioning service setting, allowing users to customize their viewing experience based on their accessibility needs. This function ensures that the selected closed captioning service aligns with the user's preferences for enhanced accessibility and convenience.

### Related Functions
[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : Allows users to set their preferred closed captioning service.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | A string for the preferred closed captions service.  Valid values are AUTO, CC[1-4], TEXT[1-4], SERVICE[1-64] where CC and TEXT is CTA-608 and SERVICE is CTA-708.  AUTO indicates that the choice is left to the player |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPreferredClosedCaptionService"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "CC3"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getPreferredClosedCaptionService"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getPreferredClosedCaptionService()
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
<button onclick="getPreferredClosedCaptionService()">getPreferredClosedCaptionService</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPreferredClosedCaptionService(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPrivacyMode"></a>
## *getPrivacyMode*


The `getPrivacyMode` API retrieves the current privacy mode status, indicating whether privacy settings are enabled or disabled on the device. This function is essential for users who want to verify their privacy configuration and ensure their personal data is protected during device usage.

### Related Functions
[setPrivacyMode](#setPrivacyMode) : Allows users to enable or disable privacy mode on the device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | The Privacy Mode. Valid values are SHARE, DO_NOT_SHARE |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPrivacyMode"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "SHARE"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getPrivacyMode"
}'
http://127.0.0.1:9998/jsonrpc
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
  thunderJS.getPrivacyMode()
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
<button onclick="getPrivacyMode()">getPrivacyMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPrivacyMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPinControl"></a>
## *getPinControl*


Retrieves the current settings for parental control PIN management, allowing users to check if PIN protection is enabled for specific actions like purchases or content access. This API is essential for ensuring secure and personalized access to restricted features.

### Related Functions
[setPinControl](#setPinControl) : Enables or modifies parental control PIN settings.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Pin Control Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPinControl"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.UserSettings.getPinControl"}' http://127.0.0.1:9998/jsonrpc
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
function getPinControl() {
  thunderJS.getPinControl()
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
<button onclick="getPinControl()">getPinControl</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPinControl(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getViewingRestrictions"></a>
## *getViewingRestrictions*


Retrieves the current viewing restrictions set for the user, such as content access limitations based on age ratings or other criteria. This function helps users ensure their preferences or parental controls are applied effectively.

### Related Functions
[setViewingRestrictions](#setViewingRestrictions) : Allows users to configure or update viewing restrictions.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | A project-specific representation of the time interval when viewing |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getViewingRestrictions"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.UserSettings.getViewingRestrictions"}' http://127.0.0.1:9998/jsonrpc
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
function getViewingRestrictions() {
  thunderJS.getViewingRestrictions()
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
<button onclick="getViewingRestrictions()">getViewingRestrictions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getViewingRestrictions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getViewingRestrictionsWindow"></a>
## *getViewingRestrictionsWindow*


Retrieves the current time window during which viewing restrictions are applied, helping users manage and enforce content access limitations effectively. This function is useful for ensuring compliance with parental controls or other content restriction settings.

### Related Functions
[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Allows users to define or update the time window for viewing restrictions.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | A project-specific representation of the time interval |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getViewingRestrictionsWindow"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "ALWAYS"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getViewingRestrictionsWindow"
}'
http://127.0.0.1:9998/jsonrpc
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
function getViewingRestrictionsWindow() {
  thunderJS.getViewingRestrictionsWindow()
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
<button onclick="getViewingRestrictionsWindow()">getViewingRestrictionsWindow</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getViewingRestrictionsWindow(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getLiveWatershed"></a>
## *getLiveWatershed*


Retrieves the current status of the live watershed setting, which determines whether content restrictions based on watershed rules are applied during live broadcasts. This function is essential for users who want to ensure appropriate content filtering is active for live programming.

### Related Functions
[setLiveWatershed](#setLiveWatershed) : Enables or disables the live watershed setting.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Live Watershed Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getLiveWatershed"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getLiveWatershed"
}'
http://127.0.0.1:9998/jsonrpc
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
function getLiveWatershed() {
  thunderJS.getLiveWatershed()
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
<button onclick="getLiveWatershed()">getLiveWatershed</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getLiveWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPlaybackWatershed"></a>
## *getPlaybackWatershed*


Retrieves the current playback watershed setting, which determines whether content is restricted based on watershed guidelines. This feature is useful for managing viewing restrictions and ensuring age-appropriate content during specific times.

### Related Functions
[setPlaybackWatershed](#setPlaybackWatershed) : Allows you to configure the playback watershed setting.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Playback Watershed Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPlaybackWatershed"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getPlaybackWatershed"
}'
http://127.0.0.1:9998/jsonrpc
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
function getPlaybackWatershed() {
  thunderJS.getPlaybackWatershed()
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
<button onclick="getPlaybackWatershed()">getPlaybackWatershed</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPlaybackWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getBlockNotRatedContent"></a>
## *getBlockNotRatedContent*


Retrieves the current setting that determines whether content without a rating is blocked. This feature is useful for users who want to ensure that unrated content is restricted for safety or preference reasons.

### Related Functions
[setBlockNotRatedContent](#setBlockNotRatedContent) : Allows users to enable or disable the blocking of unrated content.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | BlockNotRatedContent Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getBlockNotRatedContent"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getBlockNotRatedContent"
}'
http://127.0.0.1:9998/jsonrpc
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
function getBlockNotRatedContent() {
  thunderJS.getBlockNotRatedContent()
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
<button onclick="getBlockNotRatedContent()">getBlockNotRatedContent</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getBlockNotRatedContent(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPinOnPurchase"></a>
## *getPinOnPurchase*


Retrieves the current status of the "PIN on Purchase" setting, indicating whether a PIN is required to authorize purchases. This feature helps users maintain control over unauthorized or accidental purchases, enhancing security and parental control.

### Related Functions
[setPinOnPurchase](#setPinOnPurchase) : Enables or disables the "PIN on Purchase" setting.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | PinOnPurchase Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getPinOnPurchase"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.UserSettings.getPinOnPurchase"}' http://127.0.0.1:9998/jsonrpc
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
function getPinOnPurchase() {
  thunderJS.getPinOnPurchase()
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
<button onclick="getPinOnPurchase()">getPinOnPurchase</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPinOnPurchase(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getHighContrast"></a>
## *getHighContrast*


Retrieves the current status of the High Contrast mode, indicating whether it is enabled or disabled. This feature enhances visual accessibility by improving text readability and interface clarity, making it easier for users with visual impairments to navigate the system.

### Related Functions
[setHighContrast](#setHighContrast) : Allows users to enable or disable High Contrast mode.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | HighContrast Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getHighContrast"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getHighContrast"
}'
http://127.0.0.1:9998/jsonrpc
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
function getHighContrast() {
  thunderJS.getHighContrast()
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
<button onclick="getHighContrast()">getHighContrast</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getHighContrast(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getVoiceGuidance"></a>
## *getVoiceGuidance*


Retrieves the current status of voice guidance, indicating whether it is enabled or disabled. This feature is essential for enhancing accessibility by providing audio feedback for on-screen actions, helping users navigate and interact with the interface more effectively.

### Related Functions
[setVoiceGuidance](#setVoiceGuidance) : Allows you to enable or disable voice guidance.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | voiceGuidance Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getVoiceGuidance"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getVoiceGuidance"
}'
http://127.0.0.1:9998/jsonrpc
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
function getVoiceGuidance() {
  thunderJS.getVoiceGuidance()
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
<button onclick="getVoiceGuidance()">getVoiceGuidance</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVoiceGuidance(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getVoiceGuidanceRate"></a>
## *getVoiceGuidanceRate*


Retrieves the current speed setting for voice guidance, allowing users to understand how quickly spoken instructions are delivered. This feature is essential for tailoring accessibility options to individual preferences, ensuring a more comfortable and personalized experience.

### Related Functions
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : Adjusts the speed of voice guidance to match user preferences.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | number | voice guidance rate value |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getVoiceGuidanceRate"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": 0.1
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getVoiceGuidanceRate"
}' \
http://127.0.0.1:9998/jsonrpc
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
function getVoiceGuidanceRate() {
  thunderJS.getVoiceGuidanceRate()
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
<button onclick="getVoiceGuidanceRate()">getVoiceGuidanceRate</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVoiceGuidanceRate(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getVoiceGuidanceHints"></a>
## *getVoiceGuidanceHints*


Retrieves the current status of voice guidance hints, indicating whether additional contextual audio cues are enabled to assist users during navigation. This feature is particularly useful for enhancing accessibility and improving the user experience for individuals who rely on auditory guidance.

### Related Functions
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Enables or disables voice guidance hints.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | voiceGuidanceHints Enabled: true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getVoiceGuidanceHints"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getVoiceGuidanceHints"
}'
http://127.0.0.1:9998/jsonrpc
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
function getVoiceGuidanceHints() {
  thunderJS.getVoiceGuidanceHints()
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
<button onclick="getVoiceGuidanceHints()">getVoiceGuidanceHints</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVoiceGuidanceHints(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMigrationState"></a>
## *getMigrationState*


Retrieves the current migration state of a service or plugin, providing insight into its operational status (e.g., activated, hibernated, or suspended). This is useful for monitoring and managing the lifecycle of services to ensure optimal performance and resource allocation.

### Related Functions
[getMigrationStates](#getMigrationStates) : Retrieves the migration states for multiple services or plugins.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.key | string | the property key, for which we need to get migration state |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | migration state of the respective key true/false |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getMigrationState",
    "params": {
        "key": "VOICE_GUIDANCE_RATE"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": true
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getMigrationState",
"params": {
"key": "VOICE_GUIDANCE_RATE"
}
}' http://127.0.0.1:9998/jsonrpc
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
function getMigrationState(key) {
  thunderJS.getMigrationState({ key: key })
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
<button onclick="getMigrationState('VOICE_GUIDANCE_RATE')">getMigrationState</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMigrationState(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["key"] = "VOICE_GUIDANCE_RATE";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMigrationStates"></a>
## *getMigrationStates*


Provides a comprehensive overview of the current states of various system components or services, such as their activation, suspension, or hibernation status. This API is essential for monitoring and managing the operational states of services, ensuring smooth transitions and system stability during updates or migrations.

### Related Functions
[getMigrationState](#getMigrationState) : Retrieves the state of a specific service or component.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | array | migration state of all the defined keys |
| result[#] | object | Keys and it's migration states |
| result[#]?.key | string | <sup>*(optional)*</sup> key of the property |
| result[#]?.requiresMigration | boolean | <sup>*(optional)*</sup> migration state of the property |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getMigrationStates"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "key": "PREFERRED_AUDIO_LANGUAGES",
            "requiresMigration": true
        }
    ]
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "DeviceInfo.getMigrationStates"
}'
http://127.0.0.1:9998/jsonrpc
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
function getMigrationStates() {
  thunderJS.DeviceInfo.getMigrationStates()
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
<button onclick="getMigrationStates()">getMigrationStates</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMigrationStates(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getContentPin"></a>
## *getContentPin*


Retrieve the current content PIN set for your device, which is used to manage access to restricted content or parental controls. This function helps ensure secure viewing by allowing users to verify or update their PIN settings as needed.

### Related Functions
[setContentPin](#setContentPin) : Update the content PIN to control access to restricted content.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | string | contentPin |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UserSettings.getContentPin"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": "1234"
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.UserSettings.getContentPin"
}'
http://127.0.0.1:9998/jsonrpc
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
function getContentPin() {
  thunderJS.getContentPin()
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
<button onclick="getContentPin()">getContentPin</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getContentPin(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#Thunder)] for information on how to register for a notification.

The following events are provided by the org.rdk.UserSettings plugin:

org.rdk.UserSettings interface events:

| Event | Description |
| :-------- | :-------- |
| [onAudioDescriptionChanged](#onAudioDescriptionChanged) | Triggered after the audio description changes (see `SetAudioDescription`) |
| [onPreferredAudioLanguagesChanged](#onPreferredAudioLanguagesChanged) | Triggered after the audio preferred Audio languages changes (see `SetPreferredAudioLanguages`) |
| [onPresentationLanguageChanged](#onPresentationLanguageChanged) | Triggered after the Presentation Language changes (see `SetPresentationLanguage`) |
| [onCaptionsChanged](#onCaptionsChanged) | Triggered after the captions changes (see `SetCaptions`) |
| [onPreferredCaptionsLanguagesChanged](#onPreferredCaptionsLanguagesChanged) | Triggered after the PreferredCaption Languages changes (see `SetPreferredCaptionsLanguages`) |
| [onPreferredClosedCaptionServiceChanged](#onPreferredClosedCaptionServiceChanged) | Triggered after the Preferred Closed Caption changes (see `SetPreferredClosedCaptionService`) |
| [onPrivacyModeChanged](#onPrivacyModeChanged) | Triggered after the Privacy Mode changes (see `SetPrivacyMode`) |
| [onPinControlChanged](#onPinControlChanged) | Triggered after the pin control changes (see `setPinControl`) |
| [onViewingRestrictionsChanged](#onViewingRestrictionsChanged) | Triggered after the viewingRestrictions changes (see `setViewingRestrictions`) |
| [onViewingRestrictionsWindowChanged](#onViewingRestrictionsWindowChanged) | Triggered after the viewingRestrictionsWindow changes (see `setViewingRestrictionsWindow`) |
| [onLiveWatershedChanged](#onLiveWatershedChanged) | Triggered after the liveWatershed changes (see `setLiveWatershed`) |
| [onPlaybackWatershedChanged](#onPlaybackWatershedChanged) | Triggered after the playbackWatershed changes (see `setPlaybackWatershed`) |
| [onBlockNotRatedContentChanged](#onBlockNotRatedContentChanged) | Triggered after the blockNotRatedContent changes (see `setBlockNotRatedContent`) |
| [onPinOnPurchaseChanged](#onPinOnPurchaseChanged) | Triggered after the pinOnPurchase changes (see `setPinOnPurchase`) |
| [onHighContrastChanged](#onHighContrastChanged) | Triggered after the high contrast settings changes(see `SetHighContrast`) |
| [onVoiceGuidanceChanged](#onVoiceGuidanceChanged) | Triggered after the voice guidance enabled settings changes |
| [onVoiceGuidanceRateChanged](#onVoiceGuidanceRateChanged) | Triggered after the voice guidance rate changed |
| [onVoiceGuidanceHintsChanged](#onVoiceGuidanceHintsChanged) | Triggered after the voice guidance hints changes |
| [onContentPinChanged](#onContentPinChanged) | Triggered after the ContentPin changes (see `setContentPin`) |


<a name="onAudioDescriptionChanged"></a>
## *onAudioDescriptionChanged*


This event notifies users when the audio description feature has been enabled or disabled. Audio description is an accessibility feature that provides additional audio narration to describe visual elements of a video, making content more accessible to visually impaired users. The event is triggered whenever the audio description setting is changed, ensuring users are informed about the current status of this feature.

### Related Functions
[setAudioDescription](#setAudioDescription) : This function triggers the event when the audio description setting is updated, either enabling or disabling the feature.

[getAudioDescription](#getAudioDescription) : This function can be used to retrieve the current status of the audio description setting, which may have triggered the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Receive audio description changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onAudioDescriptionChanged",
    "params": {
        "enabled": true
    }
}
```

<a name="onPreferredAudioLanguagesChanged"></a>
## *onPreferredAudioLanguagesChanged*


This event is triggered whenever the user's preferred audio language settings are updated. It notifies the system or application that the preferred audio language has been changed, allowing for adjustments to audio playback to match the user's new preferences. This ensures a personalized and seamless audio experience for the user.

### Related Functions
[setPreferredAudioLanguages](#setPreferredAudioLanguages) : This function triggers the event when the user updates their preferred audio language settings.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.preferredLanguages | string | Receive preferred Audio languages changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPreferredAudioLanguagesChanged",
    "params": {
        "preferredLanguages": "eng"
    }
}
```

<a name="onPresentationLanguageChanged"></a>
## *onPresentationLanguageChanged*


This event is triggered whenever the presentation language setting is updated. The presentation language determines the primary language used for on-screen menus, notifications, and other interface elements. Users may change this setting to better suit their language preferences, and this event ensures that the system responds appropriately to the update.

### Related Functions
[setPresentationLanguage](#setPresentationLanguage) : This function triggers the event when the presentation language is updated by the user. It ensures that the new language preference is applied across the system.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.presentationLanguage | string | Receive Presentation Language changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPresentationLanguageChanged",
    "params": {
        "presentationLanguage": "en-US"
    }
}
```

<a name="onCaptionsChanged"></a>
## *onCaptionsChanged*


This event is triggered whenever the captions setting is changed. Captions are a visual representation of spoken dialogue and other audio elements, designed to enhance accessibility for users who are deaf or hard of hearing, or for those who prefer text-based audio descriptions. The event notifies users when captions are enabled or disabled, ensuring they are aware of changes to their viewing experience.

### Related Functions
[getCaptions](#getCaptions) : This function retrieves the current state of the captions setting, which directly influences the triggering of the `onCaptionsChanged` event.

[setCaptions](#setCaptions) : This function allows users to enable or disable captions. Any change made through this function will trigger the `onCaptionsChanged` event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onCaptionsChanged",
    "params": {
        "enabled": true
    }
}
```

<a name="onPreferredCaptionsLanguagesChanged"></a>
## *onPreferredCaptionsLanguagesChanged*


This event is triggered whenever the user's preferred captions languages are updated. It reflects changes made to the list of languages that the user has prioritized for captions, ensuring that the system adapts to their preferences. This event helps maintain a personalized viewing experience by dynamically adjusting captions to match the user's updated language settings.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : This function triggers the event when the user updates their preferred captions languages. It ensures that the system reflects the new preferences immediately.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.preferredLanguages | string | Receive PreferredCaption Languages changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPreferredCaptionsLanguagesChanged",
    "params": {
        "preferredLanguages": "eng"
    }
}
```

<a name="onPreferredClosedCaptionServiceChanged"></a>
## *onPreferredClosedCaptionServiceChanged*


This event is triggered whenever the user's preferred closed captioning service is updated. Closed captioning services provide text-based transcriptions of audio content, which can be essential for accessibility or personal preference. The event ensures that any changes to the preferred service are recognized and applied, allowing users to seamlessly switch to their desired captioning provider.

### Related Functions
[getPreferredClosedCaptionService](#getPreferredClosedCaptionService) : Retrieves the currently set preferred closed captioning service, which is monitored for changes that trigger this event.

[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : Updates the user's preferred closed captioning service, directly triggering this event to reflect the change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.service | string | Receive Preferred Closed Caption Service changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPreferredClosedCaptionServiceChanged",
    "params": {
        "service": "CC3"
    }
}
```

<a name="onPrivacyModeChanged"></a>
## *onPrivacyModeChanged*


This event is triggered whenever the privacy mode setting is updated. Privacy mode determines whether the device is configured to share or not share certain user-related data. For example, switching between "SHARE" and "DO_NOT_SHARE" modes can impact how the device handles data privacy preferences. This event ensures users are notified of changes to their privacy settings, helping them stay informed about their data-sharing status.

### Related Functions
[getPrivacyMode](#getPrivacyMode) : Retrieves the current privacy mode setting, allowing users to check whether their device is set to "SHARE" or "DO_NOT_SHARE."

[setPrivacyMode](#setPrivacyMode) : Updates the privacy mode setting, triggering the event when the mode is changed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.privacyMode | string | Receive Privacy Mode changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPrivacyModeChanged",
    "params": {
        "privacyMode": "DO_NOT_SHARE"
    }
}
```

<a name="onPinControlChanged"></a>
## *onPinControlChanged*


This event is triggered whenever there is a change in the "Pin Control" setting. The "Pin Control" feature allows users to enable or disable the requirement of a PIN for accessing certain content or features. For example, this setting can be used to restrict access to specific content based on parental controls. When the "Pin Control" setting is updated, this event notifies the system or application of the change, ensuring that the new setting is applied immediately.

### Related Functions
[setPinControl](#setPinControl) : This function triggers the event when the "Pin Control" setting is updated. It allows users to enable or disable the PIN requirement.

[getPinControl](#getPinControl) : This function retrieves the current state of the "Pin Control" setting, which can be used to verify the change that triggered the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.pinControl | boolean | Receive pin control changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPinControlChanged",
    "params": {
        "pinControl": true
    }
}
```

<a name="onViewingRestrictionsChanged"></a>
## *onViewingRestrictionsChanged*


This event is triggered whenever the viewing restrictions for content are updated. Viewing restrictions are settings that control access to certain types of content based on criteria such as age ratings, parental controls, or other limitations. This event ensures that users are notified when these restrictions are changed, allowing them to stay informed about updates to their content access settings.

### Related Functions
[setViewingRestrictions](#setViewingRestrictions) : This function updates the viewing restrictions, which directly triggers the `onViewingRestrictionsChanged` event to notify users of the change.

[getViewingRestrictions](#getViewingRestrictions) : This function retrieves the current viewing restrictions, which may be used to confirm or display the updated settings after the event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.viewingRestrictions | string | Receive viewingRestrictions changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onViewingRestrictionsChanged",
    "params": {
        "viewingRestrictions": "{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"
    }
}
```

<a name="onViewingRestrictionsWindowChanged"></a>
## *onViewingRestrictionsWindowChanged*


The `onViewingRestrictionsWindowChanged` event is triggered whenever there is a change in the viewing restrictions window settings. This event notifies users about updates to the time frame or conditions during which specific content restrictions are applied. For example, this could include changes to parental control settings that limit access to certain types of content during specific hours. This ensures users are always aware of updates to their content access preferences.

### Related Functions
[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the current settings for the viewing restrictions window, which can trigger this event when changes are detected.

[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Updates the viewing restrictions window settings, directly triggering this event to notify users of the change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.viewingRestrictionsWindow | string | Receive viewingRestrictionsWindow changes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onViewingRestrictionsWindowChanged",
    "params": {
        "viewingRestrictionsWindow": "ALWAYS"
    }
}
```

<a name="onLiveWatershedChanged"></a>
## *onLiveWatershedChanged*


The *onLiveWatershedChanged* event occurs when there is a change in the live watershed setting. This setting determines the content restrictions applied during live playback based on watershed rules, which are typically used to enforce age-appropriate viewing guidelines. The event is triggered whenever the live watershed status is updated, ensuring users are informed of changes to content accessibility during live streaming.

### Related Functions
[getLiveWatershed](#getLiveWatershed) : Retrieves the current status of the live watershed setting, which can trigger this event when the value changes.

[setLiveWatershed](#setLiveWatershed) : Updates the live watershed setting, directly triggering the *onLiveWatershedChanged* event to reflect the new status.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.liveWatershed | boolean | Receives liveWatershed changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onLiveWatershedChanged",
    "params": {
        "liveWatershed": true
    }
}
```

<a name="onPlaybackWatershedChanged"></a>
## *onPlaybackWatershedChanged*


The **onPlaybackWatershedChanged** event notifies users when the playback watershed setting has been updated. This setting determines whether certain content is restricted based on its watershed classification, which is typically used to enforce age-appropriate viewing restrictions. The event is triggered whenever the playback watershed status is changed, ensuring users are informed of updates to this setting.

### Related Functions
[setPlaybackWatershed](#setPlaybackWatershed) : This function triggers the event when the playback watershed setting is modified, either enabling or disabling the restriction.

[getPlaybackWatershed](#getPlaybackWatershed) : This function retrieves the current status of the playback watershed setting, which may have been updated and triggered the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.playbackWatershed | boolean | Receive playbackWatershed changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPlaybackWatershedChanged",
    "params": {
        "playbackWatershed": true
    }
}
```

<a name="onBlockNotRatedContentChanged"></a>
## *onBlockNotRatedContentChanged*


This event is triggered whenever there is a change in the setting that controls whether content without a rating is blocked. It notifies users about updates to the "Block Not Rated Content" preference, which is used to restrict access to unrated content for enhanced parental control. This event ensures that users are aware of any modifications to this setting, allowing them to maintain their desired content restrictions.

### Related Functions
[setBlockNotRatedContent](#setBlockNotRatedContent) : This function triggers the event when the "Block Not Rated Content" setting is updated.
[getBlockNotRatedContent](#getBlockNotRatedContent) : This function can retrieve the current state of the "Block Not Rated Content" setting, which may be relevant when the event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.blockNotRatedContent | boolean | Receive blockNotRatedContent changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onBlockNotRatedContentChanged",
    "params": {
        "blockNotRatedContent": true
    }
}
```

<a name="onPinOnPurchaseChanged"></a>
## *onPinOnPurchaseChanged*


This event is triggered whenever the "Pin on Purchase" setting is updated. The "Pin on Purchase" feature ensures that a PIN is required to authorize purchases, adding an extra layer of security to prevent unauthorized transactions. Users can enable or disable this feature based on their preferences, and any changes to this setting will activate the event.

### Related Functions
[getPinOnPurchase](#getPinOnPurchase) : Retrieves the current status of the "Pin on Purchase" setting, indicating whether the PIN requirement for purchases is enabled or disabled.

[setPinOnPurchase](#setPinOnPurchase) : Updates the "Pin on Purchase" setting, enabling or disabling the PIN requirement for purchases. Changes made through this function trigger the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.pinOnPurchase | boolean | Receive pinOnPurchase changes enable or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPinOnPurchaseChanged",
    "params": {
        "pinOnPurchase": true
    }
}
```

<a name="onHighContrastChanged"></a>
## *onHighContrastChanged*


This event is triggered whenever the High Contrast mode setting is changed. High Contrast mode is a visual accessibility feature designed to improve readability and visibility for users with visual impairments by increasing the contrast between text and background elements. When this setting is enabled or disabled, the event notifies the system or application to adapt its interface accordingly.

### Related Functions
[setHighContrast](#setHighContrast) : This function allows users to enable or disable High Contrast mode, which directly triggers the `onHighContrastChanged` event.

[getHighContrast](#getHighContrast) : This function retrieves the current state of High Contrast mode. Changes detected through this function can also trigger the `onHighContrastChanged` event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Receive high contrast enabled or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onHighContrastChanged",
    "params": {
        "enabled": true
    }
}
```

<a name="onVoiceGuidanceChanged"></a>
## *onVoiceGuidanceChanged*


This event is triggered whenever the Voice Guidance feature is enabled or disabled. Voice Guidance is an accessibility feature designed to assist users by providing spoken feedback for navigating menus, settings, and other on-screen elements. The event notifies the system or application when the Voice Guidance setting changes, allowing it to adapt accordingly.

### Related Functions
[setVoiceGuidance](#setVoiceGuidance) : This function directly triggers the event by enabling or disabling the Voice Guidance feature based on user preferences.

[getVoiceGuidance](#getVoiceGuidance) : This function retrieves the current state of the Voice Guidance feature, which can be used to confirm the change that triggered the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Receive voice guidance enabled or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onVoiceGuidanceChanged",
    "params": {
        "enabled": true
    }
}
```

<a name="onVoiceGuidanceRateChanged"></a>
## *onVoiceGuidanceRateChanged*


This event is triggered whenever the speed of voice guidance is adjusted. Voice guidance is an accessibility feature that provides spoken feedback to help users navigate and interact with their device. The event notifies users about changes to the voice guidance rate, ensuring they are aware of updates to the speed at which the guidance is delivered.

### Related Functions
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : This function allows users to set the desired speed for voice guidance. When the rate is successfully updated, the `onVoiceGuidanceRateChanged` event is triggered to reflect the change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.rate | number | voice guidance rate value |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onVoiceGuidanceRateChanged",
    "params": {
        "rate": 0.1
    }
}
```

<a name="onVoiceGuidanceHintsChanged"></a>
## *onVoiceGuidanceHintsChanged*


This event is triggered whenever there is a change in the status of voice guidance hints. Voice guidance hints provide additional spoken cues to assist users in navigating menus, settings, or other interface elements. This event ensures that users are informed when these hints are enabled or disabled, enhancing accessibility and usability for individuals who rely on voice guidance features.

### Related Functions
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : This function allows users to enable or disable voice guidance hints. Changes made through this function directly trigger the `onVoiceGuidanceHintsChanged` event, reflecting the updated status of the hints.

[getVoiceGuidanceHints](#getVoiceGuidanceHints) : This function retrieves the current status of voice guidance hints (enabled or disabled). If the status changes, the `onVoiceGuidanceHintsChanged` event is triggered to notify users of the update.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hints | boolean | Receive voice guidance hints enabled or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onVoiceGuidanceHintsChanged",
    "params": {
        "hints": true
    }
}
```

<a name="onContentPinChanged"></a>
## *onContentPinChanged*


This event is triggered whenever the content PIN is updated or changed. The content PIN is a security feature used to restrict access to certain types of content or actions, such as purchases or viewing restricted material. Users may update their content PIN to enhance privacy and control over their viewing experience. This event ensures that any changes to the content PIN are recognized and appropriately handled by the system.

### Related Functions
[setContentPin](#setContentPin) : This function allows users to update the content PIN. When the PIN is successfully changed using this function, the `onContentPinChanged` event is triggered to notify the system of the update.

[getContentPin](#getContentPin) : This function retrieves the current content PIN. While it does not directly trigger the event, it is closely related as it provides access to the PIN that may have been updated through the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.contentPin | string | contentPin |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onContentPinChanged",
    "params": {
        "contentPin": "1234"
    }
}
```
