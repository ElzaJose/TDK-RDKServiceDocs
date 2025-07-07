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


The **UserSettings** RDK service is a WPEFramework plugin designed to manage and configure user-specific settings for multimedia experiences. It provides interfaces for accessing and modifying preferences such as audio descriptions, preferred audio languages, captions, and presentation languages. This service ensures a customizable and accessible user experience by allowing dynamic adjustments to these settings.

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
| [setPresentationLanguage](#setPresentationLanguage) | Set presentation language | [onPresentationLanguageChanged](#onPresentationLanguageChanged) |
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
| [setPinOnPurchase](#setPinOnPurchase) | set pin on purchase | [onPinOnPurchaseChanged](#onPinOnPurchaseChanged) |
| [setHighContrast](#setHighContrast) | Sets high contrast mode | [onHighContrastChanged](#onHighContrastChanged) |
| [setVoiceGuidance](#setVoiceGuidance) | configure voice guidance | [onVoiceGuidanceChanged](#onVoiceGuidanceChanged) |
| [setVoiceGuidanceRate](#setVoiceGuidanceRate) | Sets voice guidance rate | [onVoiceGuidanceRateChanged](#onVoiceGuidanceRateChanged) |
| [setVoiceGuidanceHints](#setVoiceGuidanceHints) | set voice guidance hints | [onVoiceGuidanceHintsChanged](#onVoiceGuidanceHintsChanged) |
| [setContentPin](#setContentPin) | set content pin | [onContentPinChanged](#onContentPinChanged) |
| [getAudioDescription](#getAudioDescription) | audio description retrieval | NA |
| [getPreferredAudioLanguages](#getPreferredAudioLanguages) | preferred audio languages | NA |
| [getPresentationLanguage](#getPresentationLanguage) | presentation language retrieval | NA |
| [getCaptions](#getCaptions) | fetch video captions | NA |
| [getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) | preferred captions languages | NA |
| [getPreferredClosedCaptionService](#getPreferredClosedCaptionService) | Preferred caption service | NA |
| [getPrivacyMode](#getPrivacyMode) | get privacy mode | NA |
| [getPinControl](#getPinControl) | Pin control management | NA |
| [getViewingRestrictions](#getViewingRestrictions) | viewing restrictions info | NA |
| [getViewingRestrictionsWindow](#getViewingRestrictionsWindow) | viewing restrictions window | NA |
| [getLiveWatershed](#getLiveWatershed) | live watershed data | NA |
| [getPlaybackWatershed](#getPlaybackWatershed) | playback watershed details | NA |
| [getBlockNotRatedContent](#getBlockNotRatedContent) | Block unrated content | NA |
| [getPinOnPurchase](#getPinOnPurchase) | Get PIN on purchase | NA |
| [getHighContrast](#getHighContrast) | high contrast mode | NA |
| [getVoiceGuidance](#getVoiceGuidance) | voice guidance details | NA |
| [getVoiceGuidanceRate](#getVoiceGuidanceRate) | get voice guidance rate | NA |
| [getVoiceGuidanceHints](#getVoiceGuidanceHints) | voice guidance hints | NA |
| [getMigrationState](#getMigrationState) | migration state retrieval | NA |
| [getMigrationStates](#getMigrationStates) | migration states info | NA |
| [getContentPin](#getContentPin) | get content pin details | NA |


<a name="setAudioDescription"></a>
## *setAudioDescription*


The `setAudioDescription` API allows users to enable or disable the audio description feature for their media content. Audio description is an accessibility feature that provides additional audio narration to describe visual elements in a video, such as actions, settings, and scene changes, making the content more accessible to visually impaired users. By using this API, users can customize their viewing experience to include or exclude this narration based on their preferences. Once enabled, the system ensures that audio descriptions are provided whenever available for the selected content.

This API is particularly useful for users who rely on audio descriptions to fully understand and enjoy video content. It ensures that accessibility settings can be tailored to individual needs, enhancing the inclusivity of the media experience.

### Related Functions
[getAudioDescription](#getAudioDescription) : Retrieves the current status of the audio description feature (enabled or disabled). This function complements `setAudioDescription` by allowing users to check the current setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setAudioDescription",
    "params":{"enabled":true}}'
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
    function setAudioDescription(params) {
      thunderJS.setAudioDescription(params)
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
    <button onclick="setAudioDescription({enabled: true})">setAudioDescription</button>
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


The `setPreferredAudioLanguages` API allows users to specify their preferred audio languages for content playback. This function is particularly useful for multilingual users who want to prioritize certain languages when consuming media. By setting preferred audio languages, the system can automatically select the most suitable audio track based on the user's preferences, enhancing the viewing experience. This feature is commonly used in streaming platforms, set-top boxes, and other media devices to ensure that users can enjoy content in their desired language without manual selection each time.

### Related Functions
[getPreferredAudioLanguages](#getPreferredAudioLanguages) : Retrieves the currently set preferred audio languages, allowing users to confirm or review their preferences.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPreferredAudioLanguages",
    "params":{"preferredLanguages":"eng"}}'
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
    function setAudioLanguages(preferredLanguages) {
      thunderJS.org.rdk.UserSettings.setPreferredAudioLanguages({ preferredLanguages })
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
    <button onclick="setAudioLanguages('eng')">setAudioLanguages</button>
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


The `setPresentationLanguage` API allows users to define the preferred language for the presentation of content, such as menus, subtitles, or other on-screen text. This function is particularly useful for tailoring the user experience to match individual language preferences, ensuring accessibility and convenience for multilingual audiences. By setting the presentation language, users can customize their viewing environment to align with their linguistic needs, enhancing usability and engagement.

### Related Functions
[getPresentationLanguage](#getPresentationLanguage) : Retrieves the currently set presentation language, allowing users to confirm or review their language preference.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPresentationLanguage",
    "params":{"presentationLanguage":"en-US"}}'
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
    function setLanguage(presentationLanguage) {
      thunderJS.org.rdk.UserSettings.setPresentationLanguage({ presentationLanguage })
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
    <button onclick="setLanguage('en-US')">setLanguage</button>
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


The `setCaptions` function allows users to enable or disable captions for their viewing experience. Captions are textual representations of spoken dialogue, sound effects, and other audio elements in a video, designed to enhance accessibility for individuals who are deaf, hard of hearing, or prefer to watch content with text-based assistance. By using this function, users can toggle captions on or off based on their preferences. This setting is particularly useful for improving comprehension in noisy environments, understanding content in a non-native language, or accommodating personal accessibility needs.

### Related Functions
[getCaptions](#getCaptions) : Retrieves the current status of captions (enabled or disabled), allowing users to check whether captions are currently active.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setCaptions",
    "params":{"enabled":true}}'
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
    function setCaptions(enabled) {
      thunderJS.setCaptions({ enabled: enabled })
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
    <button onclick="setCaptions(true)">setCaptions</button>
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


The `setPreferredCaptionsLanguages` function allows users to specify their preferred languages for captions. This feature is particularly useful for individuals who rely on captions to enhance their viewing experience, such as those who are hard of hearing or watching content in a non-native language. By setting preferred caption languages, users can ensure that their chosen language is prioritized whenever captions are available for the content they are watching. This setting helps create a more personalized and accessible viewing experience.

### Related Functions
[getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) : Retrieves the currently set preferred captions languages, allowing users to verify or review their preferences.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPreferredCaptionsLanguages",
    "params":{"preferredLanguages":"eng"}}'
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
    function setCaptionsLanguage(preferredLanguages) {
      thunderJS.setCaptionsLanguage(preferredLanguages)
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
    <button onclick="setCaptionsLanguage('eng')">setCaptionsLanguage</button>
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


The `setPreferredClosedCaptionService` API allows users to specify their preferred closed captioning service for video content. Closed captioning services provide text-based transcriptions of spoken dialogue and other audio cues, enhancing accessibility for individuals who are deaf or hard of hearing. By setting a preferred closed captioning service, users can customize their viewing experience to align with their accessibility needs or language preferences. This API ensures that the selected service is applied across supported content, providing a consistent and personalized experience.

### Related Functions
[getPreferredClosedCaptionService](#getPreferredClosedCaptionService) : Retrieves the currently set preferred closed captioning service, allowing users to confirm or review their selection.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPreferredClosedCaptionService",
    "params":{"service":"CC3"}}'
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
      thunderJS.setPreferredClosedCaptionService({ service: service })
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


The `setPrivacyMode` API allows users to configure the privacy settings of their device. This function enables the user to specify whether their device should share or not share certain data, ensuring control over their privacy preferences. The privacy mode can be set to either "SHARE" or "DO_NOT_SHARE," depending on the user's preference. If an invalid value is provided, the function defaults to "SHARE." This API is particularly useful for users who want to manage their data-sharing preferences and ensure their device operates in accordance with their privacy requirements.

### Related Functions
[getPrivacyMode](#getPrivacyMode) : Retrieves the current privacy mode setting of the device, allowing users to check whether their device is configured to share or not share data.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPrivacyMode",
    "params":{"privacyMode":"SHARE"}}'
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
    function setPrivacyMode(params) {
      thunderJS.setPrivacyMode(params)
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
    <button onclick="setPrivacyMode({ privacyMode: 'SHARE' })">setPrivacyMode</button>
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


The `setPinControl` API allows users to enable or disable the PIN control feature on their device. PIN control is a security feature that restricts access to certain functionalities or content based on user-defined settings. By enabling PIN control, users can ensure that sensitive actions, such as accessing restricted content or modifying settings, require a PIN for authentication. This feature is particularly useful for parental controls or safeguarding personal preferences. Disabling PIN control removes the requirement for a PIN, allowing unrestricted access to the associated functionalities.

### Related Functions
[getPinControl](#getPinControl) : Retrieves the current status of the PIN control feature (enabled or disabled).

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPinControl",
    "params":{"pinControl":true}}'
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
    function setPinControl(pinControl) {
      thunderJS.org.rdk.UserSettings.setPinControl({ pinControl: pinControl })
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
    std::string result;
    parameters["pinControl"] = true;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="setViewingRestrictions"></a>
## *setViewingRestrictions*


The `setViewingRestrictions` API allows users to define specific viewing restrictions for content based on their preferences or requirements. This function is particularly useful for managing access to content that may not be suitable for certain audiences, such as children or individuals with specific sensitivities. By setting viewing restrictions, users can ensure that only content meeting their defined criteria is accessible, providing a tailored and secure viewing experience. This API is often used in conjunction with parental controls or content filtering systems to enforce content guidelines effectively.

### Related Functions
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions that have been set, allowing users to review or confirm the applied settings.

[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Defines a specific time window during which the viewing restrictions are enforced, adding flexibility to the restriction settings.

[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the current time window for viewing restrictions, enabling users to verify or adjust the enforcement period.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setViewingRestrictions",
    "params":{"viewingRestrictions":"{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"}}'
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
    <button onclick="setViewingRestrictions({viewingRestrictions: '{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}'})">setViewingRestrictions</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void org_rdk_UserSettings_setViewingRestrictions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `setViewingRestrictionsWindow` API allows users to define a specific time window during which viewing restrictions are applied. This function is particularly useful for parents or guardians who want to enforce content restrictions during certain hours, such as when children are likely to be watching TV. By setting a viewing restrictions window, users can ensure that inappropriate or restricted content is blocked during the specified timeframe. This feature provides an additional layer of control over content accessibility, complementing other parental control settings.

### Related Functions
[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the currently configured viewing restrictions window, allowing users to verify or review the active time window for restrictions.
[setViewingRestrictions](#setViewingRestrictions) : Sets general viewing restrictions, which can work in conjunction with the viewing restrictions window to enforce content limitations.
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions settings, providing insight into the active content limitations.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setViewingRestrictionsWindow",
    "params":{"viewingRestrictionsWindow":"{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}"}}'
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


The `setLiveWatershed` API allows users to configure the live watershed setting for their device or application. The watershed setting is typically used to enforce content restrictions based on time or age-related guidelines, ensuring that certain types of content are only accessible during specific hours or under specific conditions. By enabling or disabling the live watershed, users can control whether these restrictions are applied to live content. This feature is particularly useful for households with children or environments where content control is necessary to comply with regulatory or personal preferences.

### Related Functions
[getLiveWatershed](#getLiveWatershed) : Retrieves the current status of the live watershed setting, allowing users to check whether the restrictions are enabled or disabled.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setLiveWatershed",
    "params":{"liveWatershed":true}}'
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
    function setLiveWatershed(params) {
      thunderJS.setLiveWatershed(params)
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
    <button onclick="setLiveWatershed({ liveWatershed: true })">setLiveWatershed</button>
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


The `setPlaybackWatershed` API is used to configure the playback watershed setting for a user. The playback watershed is a feature that allows users to define a threshold or restriction for content playback based on specific criteria, such as age ratings or time-based restrictions. By enabling or disabling this setting, users can control the type of content that can be played back, ensuring it aligns with their preferences or parental control requirements. This setting is particularly useful for families or individuals who want to enforce content restrictions during certain hours or for specific types of media.

### Related Functions
[getPlaybackWatershed](#getPlaybackWatershed) : Retrieves the current playback watershed setting, allowing users to check whether the restriction is enabled or disabled.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPlaybackWatershed",
    "params":{"playbackWatershed":true}}'
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
    function setPlaybackWatershed(playbackWatershed) {
      thunderJS.setPlaybackWatershed(playbackWatershed)
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
        parameters["playbackWatershed"] = true;
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


The `setBlockNotRatedContent` API allows users to enable or disable the blocking of content that has not been rated. This feature is particularly useful for parents or guardians who want to ensure that unclassified or unrated content is not accessible to children or other viewers. By setting this option to `true`, the system will restrict access to content that lacks a formal rating, providing an additional layer of control over viewing preferences. Conversely, setting it to `false` will allow unrated content to be accessible. This setting is part of the broader user settings configuration, enabling users to customize their viewing experience according to their preferences or parental control requirements.

### Related Functions
[getBlockNotRatedContent](#getBlockNotRatedContent) : Retrieves the current status of the block-not-rated-content setting, indicating whether unrated content is being blocked or allowed.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setBlockNotRatedContent",
    "params":{"blockNotRatedContent":true}}'
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


The `setPinOnPurchase` function allows users to enable or disable the requirement of a PIN when making purchases. This feature is particularly useful for households with multiple users, such as children, where parental control over purchases is necessary. By enabling this setting, users can ensure that unauthorized or accidental purchases are prevented, adding an extra layer of security and control over transactional activities.

When this setting is enabled, the system will prompt the user to enter a PIN before completing any purchase. Conversely, disabling this setting removes the PIN requirement, allowing purchases to be made without additional authentication. This feature is ideal for managing spending and ensuring that only authorized users can make purchases.

### Related Functions
[getPinOnPurchase](#getPinOnPurchase) : Retrieves the current status of the PIN-on-purchase setting, indicating whether the PIN requirement is enabled or disabled.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setPinOnPurchase",
    "params":{"pinOnPurchase":true}}'
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


The `setHighContrast` API allows users to enable or disable the high contrast mode on their device. High contrast mode is an accessibility feature designed to improve the visibility of text and interface elements for users with visual impairments. When enabled, this feature adjusts the color scheme of the user interface to increase the contrast between text, backgrounds, and other elements, making it easier to read and navigate. This setting is particularly useful for individuals with low vision or color blindness, as it enhances the overall clarity of the display.

### Related Functions
[getHighContrast](#getHighContrast) : Retrieves the current status of the high contrast mode (enabled or disabled). This function complements `setHighContrast` by allowing users to check the current state of the high contrast setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setHighContrast",
    "params":{"enabled":true}}'
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
    function setHighContrast(params) {
      thunderJS.setHighContrast(params)
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
    <button onclick="setHighContrast({enabled: true})">setHighContrast</button>
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


The `setVoiceGuidance` API allows users to enable or disable the voice guidance feature on their device. Voice guidance is an accessibility feature designed to assist visually impaired users by providing audio feedback for on-screen content and navigation. By enabling this feature, users can receive spoken instructions and descriptions, making it easier to interact with the device's interface. Disabling the feature turns off the audio feedback, reverting the device to its standard operation mode.

This API is particularly useful for users who rely on auditory assistance to navigate menus, access content, or perform other tasks on their device. It ensures a more inclusive and accessible user experience.

### Related Functions
[getVoiceGuidance](#getVoiceGuidance) : Retrieves the current status of the voice guidance feature (enabled or disabled), allowing users to check whether the feature is active.
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : Adjusts the speed at which the voice guidance audio is delivered, providing users with control over the pace of spoken feedback.
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Configures additional hints or contextual information provided by the voice guidance feature, enhancing the level of detail in the audio feedback.
[getVoiceGuidanceRate](#getVoiceGuidanceRate) : Retrieves the current rate of voice guidance audio playback.
[getVoiceGuidanceHints](#getVoiceGuidanceHints) : Retrieves the current status of voice guidance hints (enabled or disabled).

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setVoiceGuidance",
    "params":{"enabled":true}}'
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
    function setVoiceGuidance(params) {
      thunderJS.setVoiceGuidance(params)
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
    <button onclick="setVoiceGuidance({enabled: true})">setVoiceGuidance</button>
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


The `setVoiceGuidanceRate` API allows users to adjust the speed at which voice guidance is delivered. Voice guidance is an accessibility feature designed to assist visually impaired users by providing spoken feedback for navigating menus, settings, and other on-screen elements. By using this API, users can customize the rate of speech to suit their preferences, ensuring a more comfortable and efficient experience. The rate can be set within a predefined range, ensuring that the speech remains intelligible and effective. This feature is particularly useful for users who may prefer faster or slower speech depending on their individual needs.

### Related Functions
[getVoiceGuidanceRate](#getVoiceGuidanceRate) : Retrieves the current rate of voice guidance, allowing users to check the existing setting before making adjustments.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setVoiceGuidanceRate",
    "params":{"rate":0.1}}'
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
      thunderJS.setVoiceGuidanceRate({ rate: rate })
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


The `setVoiceGuidanceHints` API allows users to enable or disable voice guidance hints within the system. Voice guidance hints are additional auditory cues or instructions provided to assist users in navigating and interacting with the system, particularly beneficial for individuals with visual impairments or those who prefer audio-based guidance. By enabling this feature, users can receive contextual hints that enhance accessibility and usability, making the system more intuitive and user-friendly. Conversely, disabling this feature removes these auditory cues, which may be preferred by users who do not require additional guidance or wish to streamline their experience.

This API is particularly useful for tailoring the accessibility settings to individual preferences, ensuring that the system accommodates a wide range of user needs.

### Related Functions
[getVoiceGuidanceHints](#getVoiceGuidanceHints) : Retrieves the current status of voice guidance hints, indicating whether they are enabled or disabled.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setVoiceGuidanceHints",
    "params":{"hints":true}}'
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
      thunderJS.org.rdk.UserSettings.setVoiceGuidanceHints({ hints: hints })
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
    void org_rdk_UserSettings_setVoiceGuidanceHints(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `setContentPin` function allows users to set or update the content PIN for their account. This PIN is typically used to restrict access to certain content or features, ensuring that only authorized users can view or modify restricted settings. The PIN must be a 4-digit numeric value, ensuring simplicity and ease of use. If an empty string is provided, the existing PIN is cleared. This function is particularly useful for parental controls or other content access restrictions.

### Related Functions
[getContentPin](#getContentPin) : Retrieves the currently set content PIN, allowing users to verify or review the existing PIN.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.setContentPin",
    "params":{"contentPin":"1234"}}'
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
    void org_rdk_UserSettings_setContentPin(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getAudioDescription` API is used to retrieve the current status of the audio description feature. Audio description is an accessibility feature that provides additional audio narration to describe visual elements in a video, such as actions, settings, and characters, for individuals who are visually impaired. This API allows users to check whether the audio description feature is enabled or disabled, helping them ensure that the feature is active when needed for an enhanced viewing experience.

### Related Functions
[setAudioDescription](#setAudioDescription) : Allows users to enable or disable the audio description feature. This function complements `getAudioDescription` by providing the ability to modify the audio description setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getAudioDescription",
    "params":{}}'
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
    void org_rdk_UserSettings_getAudioDescription(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPreferredAudioLanguages` API retrieves the user's preferred audio languages for media playback. This function is particularly useful for users who consume content in multiple languages or have specific language preferences for audio tracks. By accessing this information, the system can ensure that media playback aligns with the user's language preferences, enhancing the overall viewing experience. For example, if a user prefers audio in French and Spanish, the system will prioritize these languages when selecting audio tracks for media content. This API is essential for personalization and accessibility, allowing users to enjoy content in their desired languages without manual adjustments.

### Related Functions
[setPreferredAudioLanguages](#setPreferredAudioLanguages) : Allows users to set their preferred audio languages, which can later be retrieved using the `getPreferredAudioLanguages` API.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPreferredAudioLanguages",
    "params":{}}'
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
    function getAudioLanguages() {
      thunderJS.org.rdk.UserSettings.getPreferredAudioLanguages()
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
    <button onclick="getAudioLanguages()">getAudioLanguages</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void org_rdk_UserSettings_getPreferredAudioLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPresentationLanguage` API retrieves the current presentation language setting for the user. This setting determines the language used for on-screen text, menus, and other interface elements in the application or device. By calling this function, users can confirm the language currently configured for their viewing experience, ensuring it aligns with their preferences or accessibility needs. This API is particularly useful for multilingual environments or when users need to verify the language setting before making changes.

### Related Functions
[setPresentationLanguage](#setPresentationLanguage) : Allows users to update the presentation language to their preferred choice.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPresentationLanguage",
    "params":{}}'
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
    void org_rdk_UserSettings_getPresentationLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getCaptions` function is used to retrieve the current status of the captions feature in the user settings. Captions are an accessibility feature that displays text on the screen to represent spoken dialogue, sound effects, and other audio elements in a video or broadcast. This function allows users to check whether captions are currently enabled or disabled. It is particularly useful for users who rely on captions for better comprehension of content, such as individuals with hearing impairments or those watching content in a noisy environment. By using this function, users can confirm the current state of captions and make adjustments if necessary.

### Related Functions
[setCaptions](#setCaptions) : Allows users to enable or disable the captions feature. This function complements `getCaptions` by providing the ability to modify the captions setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getCaptions",
    "params":{}}'
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
    void org_rdk_UserSettings_getCaptions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPreferredCaptionsLanguages` API retrieves the user's preferred languages for captions. Captions are textual representations of spoken dialogue and other audio elements in video content, designed to enhance accessibility for viewers who are deaf, hard of hearing, or prefer to watch content with subtitles. This function allows users to access their current preferences for caption languages, ensuring that video content is displayed in the most suitable language for their needs. By using this API, users can verify or adjust their settings to align with their language preferences, improving their overall viewing experience.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : Allows users to set their preferred languages for captions. This function complements `getPreferredCaptionsLanguages` by enabling users to update their preferences.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPreferredCaptionsLanguages",
    "params":{}}'
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
    function org_rdk_UserSettings_getPreferredCaptionsLanguages() {
      thunderJS.org.rdk.UserSettings.getPreferredCaptionsLanguages()
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
    <button onclick="org_rdk_UserSettings_getPreferredCaptionsLanguages()">org_rdk_UserSettings_getPreferredCaptionsLanguages</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void org_rdk_UserSettings_getPreferredCaptionsLanguages(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPreferredClosedCaptionService` function retrieves the user's preferred closed captioning service setting. Closed captioning services provide on-screen text descriptions of spoken dialogue, sound effects, and other audio elements in video content, making it accessible to individuals who are deaf or hard of hearing. This function allows users to check which closed captioning service is currently set as their preference, ensuring that their viewing experience aligns with their accessibility needs. The retrieved value can be used to confirm or adjust settings to enhance accessibility and personalization.

### Related Functions
[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : Allows users to set their preferred closed captioning service. This function complements `getPreferredClosedCaptionService` by enabling the modification of the preferred service.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPreferredClosedCaptionService"}'
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
    void org_rdk_UserSettings_getPreferredClosedCaptionService(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPrivacyMode` API retrieves the current privacy mode setting of the device. Privacy mode determines how user data is handled, specifically whether it is shared or not. The two possible values for privacy mode are `"SHARE"` and `"DO_NOT_SHARE"`. When privacy mode is set to `"SHARE"`, the device allows sharing of user data for personalization or other purposes. Conversely, when set to `"DO_NOT_SHARE"`, the device restricts sharing of user data, ensuring a higher level of privacy. This API is useful for users who want to verify the current privacy configuration of their device and ensure it aligns with their preferences for data sharing and privacy.

### Related Functions
[setPrivacyMode](#setPrivacyMode) : Allows users to modify the privacy mode setting of the device, enabling them to switch between `"SHARE"` and `"DO_NOT_SHARE"` based on their privacy preferences.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPrivacyMode",
    "params":{}}
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
    void org_rdk_UserSettings_getPrivacyMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPinControl` API is used to retrieve the current status of the PIN control feature in the user settings. PIN control is a security feature that allows users to restrict access to certain content or functionalities by requiring a PIN. This API helps users check whether the PIN control is enabled or disabled, providing a way to verify the current configuration of this feature. It is particularly useful for parents or administrators who want to ensure that access restrictions are properly enforced.

### Related Functions
[setPinControl](#setPinControl) : Allows users to enable or disable the PIN control feature by setting its value.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPinControl",
    "params":{}}'
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
    function callMethod() {
      thunderJS.org.rdk.UserSettings.getPinControl()
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
    <button onclick="callMethod()">callMethod</button>
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


The `getViewingRestrictions` API retrieves the current viewing restrictions set for the user. Viewing restrictions are rules or limitations applied to the content that can be accessed, typically based on factors such as age ratings, parental controls, or other content filtering criteria. This function is useful for users who want to verify the existing restrictions applied to their profiles, ensuring that the content they or their family members access aligns with their preferences or regulatory requirements.

This API is particularly helpful in environments where parental controls or content filtering are critical, such as households with children or shared devices. By using this function, users can confirm the active restrictions and make adjustments if necessary using the corresponding `setViewingRestrictions` API.

### Related Functions
[setViewingRestrictions](#setViewingRestrictions) : Allows users to configure or update the viewing restrictions based on their preferences or requirements.

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
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getViewingRestrictions",
    "params":{}}'
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
    void org_rdk_UserSettings_getViewingRestrictions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getViewingRestrictionsWindow` API retrieves the current time window during which specific viewing restrictions are applied. This function is particularly useful for users who want to understand the active time frame for content restrictions, such as parental controls or content access limitations. By using this API, users can ensure that the restrictions align with their preferences or household rules. For example, it can help parents verify the restricted viewing hours for their children or allow users to confirm the enforcement of content restrictions during specific times of the day.

### Related Functions
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions applied to the content.
[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Allows users to set or modify the time window during which viewing restrictions are enforced.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getViewingRestrictionsWindow",
    "params":{}}'
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
    void org_rdk_UserSettings_getViewingRestrictionsWindow(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getLiveWatershed` function is used to retrieve the current status of the "Live Watershed" setting. This setting determines whether certain content restrictions are applied during live broadcasts based on predefined watershed rules. Watershed rules are typically used to restrict access to content that may not be suitable for certain audiences, such as children, during specific times of the day. By using this function, users can check if the "Live Watershed" feature is enabled or disabled, allowing them to understand the current content restriction settings for live broadcasts.

This function is particularly useful for users who want to ensure that their content preferences align with their household's viewing restrictions. For example, parents can use this function to verify if the live watershed restrictions are active, ensuring that inappropriate content is not accessible during live programming.

### Related Functions
[setLiveWatershed](#setLiveWatershed) : Allows users to enable or disable the "Live Watershed" setting. This function is the counterpart to `getLiveWatershed`, as it is used to modify the status of the live watershed feature.

[getPlaybackWatershed](#getPlaybackWatershed) : Retrieves the status of the "Playback Watershed" setting, which applies similar content restrictions but for playback content instead of live broadcasts.

[setPlaybackWatershed](#setPlaybackWatershed) : Allows users to enable or disable the "Playback Watershed" setting, complementing the `getPlaybackWatershed` function.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getLiveWatershed",
    "params":{}}'
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
    void org_rdk_UserSettings_getLiveWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPlaybackWatershed` API retrieves the current status of the playback watershed setting. The playback watershed is a feature that allows users to control access to certain types of content based on predefined time restrictions or content ratings. This setting is particularly useful for parental control or content management purposes, ensuring that specific content is only accessible during appropriate times or under certain conditions. By using this API, users can check whether the playback watershed is enabled or disabled, helping them make informed decisions about content accessibility.

### Related Functions
[setPlaybackWatershed](#setPlaybackWatershed) : Allows users to enable or disable the playback watershed setting. This function complements `getPlaybackWatershed` by providing the ability to modify the playback watershed status.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPlaybackWatershed",
    "params":{}}'
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
    void org_rdk_UserSettings_getPlaybackWatershed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getBlockNotRatedContent` API is used to retrieve the current setting that determines whether content without a rating is blocked or allowed. This feature is particularly useful for users who want to enforce parental controls or viewing restrictions on unrated content, ensuring that only rated content is accessible. By using this API, users can check if the system is configured to block unrated content, providing an additional layer of control over the type of content that can be viewed.

This API is beneficial for households with children or shared viewing environments where content restrictions are necessary. It helps users maintain a safe and controlled viewing experience by ensuring that unrated content does not bypass content filtering settings.

### Related Functions
[setBlockNotRatedContent](#setBlockNotRatedContent) : Allows users to configure the system to block or allow unrated content. This function complements `getBlockNotRatedContent` by enabling the user to modify the setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getBlockNotRatedContent",
    "params":{}}'
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
    function callMethod() {
      thunderJS.org.rdk.UserSettings.getBlockNotRatedContent()
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
    <button onclick="callMethod()">callMethod</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void org_rdk_UserSettings_getBlockNotRatedContent(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getPinOnPurchase` function is used to retrieve the current status of the "PIN on Purchase" setting. This setting determines whether a user is required to enter a PIN code when making purchases, adding an extra layer of security to prevent unauthorized transactions. By calling this function, users can check if the PIN-on-purchase feature is enabled or disabled. This is particularly useful for households with multiple users, ensuring that purchases are controlled and authorized by the account owner or an authorized individual.

### Related Functions
[setPinOnPurchase](#setPinOnPurchase) : This function allows users to enable or disable the "PIN on Purchase" feature. It is the corresponding function to modify the setting that `getPinOnPurchase` retrieves.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getPinOnPurchase",
    "params":{}}'
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
    void org_rdk_UserSettings_getPinOnPurchase(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getHighContrast` API is designed to retrieve the current status of the High Contrast mode setting. High Contrast mode is a feature that enhances the visibility of on-screen elements by increasing the contrast between text, images, and backgrounds. This is particularly beneficial for users with visual impairments or those who prefer a more distinct visual experience. By using this API, users can determine whether High Contrast mode is currently enabled or disabled on their device. This information can help users ensure their accessibility preferences are correctly applied or assist in troubleshooting visual display settings.

### Related Functions
[setHighContrast](#setHighContrast) : Allows users to enable or disable High Contrast mode based on their preferences.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getHighContrast",
    "params":{}}'
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
    void org_rdk_UserSettings_getHighContrast(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getVoiceGuidance` API is designed to retrieve the current status of voice guidance functionality in the system. Voice guidance is an accessibility feature that provides audio feedback to assist users in navigating and interacting with the system. This feature is particularly beneficial for visually impaired users, as it enables them to receive spoken instructions or descriptions of on-screen elements. By using this API, users can determine whether voice guidance is currently enabled or disabled, allowing them to verify the accessibility settings of their device.

### Related Functions
[setVoiceGuidance](#setVoiceGuidance) : Allows users to enable or disable the voice guidance feature. This function complements `getVoiceGuidance` by providing the ability to modify the voice guidance setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getVoiceGuidance",
    "params":{}}'
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
    void org_rdk_UserSettings_getVoiceGuidance(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getVoiceGuidanceRate` API retrieves the current rate of voice guidance, which is a feature designed to assist users by providing spoken feedback for navigation and interaction within the system. The voice guidance rate determines the speed at which the spoken feedback is delivered, allowing users to customize the pace to suit their preferences or accessibility needs. This API is particularly useful for users who rely on voice guidance for accessibility purposes, enabling them to check the current rate and make adjustments if necessary.

### Related Functions
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : Allows users to set the desired rate for voice guidance, enabling customization of the speed at which spoken feedback is delivered.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getVoiceGuidanceRate",
    "params":{}}'
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
      thunderJS.org.rdk.UserSettings.getVoiceGuidanceRate()
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
    void org_rdk_UserSettings_getVoiceGuidanceRate(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getVoiceGuidanceHints` API retrieves the current status of voice guidance hints in the system. Voice guidance hints are additional audio cues or instructions designed to assist users, particularly those with visual impairments, in navigating and interacting with the system more effectively. This feature enhances accessibility by providing contextual information about the interface or actions, making the user experience more intuitive and inclusive. The API returns a boolean value indicating whether voice guidance hints are enabled (`true`) or disabled (`false`).

This function is particularly useful for users who rely on voice guidance for accessibility and want to confirm the current configuration of their system. It ensures that users can verify if the hints are active and adjust their settings accordingly if needed.

### Related Functions
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Allows users to enable or disable voice guidance hints. This function complements `getVoiceGuidanceHints` by providing the ability to modify the setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getVoiceGuidanceHints",
    "params":{}}'
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
    void org_rdk_UserSettings_getVoiceGuidanceHints(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getMigrationState` API is designed to help users determine whether a specific user setting requires migration. Migration in this context refers to the process of updating or transitioning a setting to align with newer configurations or standards. This API takes a specific settings key as input and returns a boolean value indicating whether migration is required for that key. It is particularly useful for ensuring that user settings are up-to-date and compatible with the latest system requirements, providing a seamless user experience.

This API is beneficial for users who want to verify the status of their settings and ensure that they are functioning optimally without manual intervention. By identifying settings that require migration, users can take appropriate actions to update or modify them, ensuring compatibility and avoiding potential issues.

### Related Functions
[getMigrationStates](#getMigrationStates) : Provides a comprehensive list of all user settings and their respective migration states, allowing users to view the migration status of multiple settings at once.

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
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getMigrationState",
    "params":{"key":"VOICE_GUIDANCE_RATE"}}'
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
    function getMigrationState(params) {
      thunderJS.getMigrationState(params)
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
    <button onclick="getMigrationState({ key: 'VOICE_GUIDANCE_RATE' })">getMigrationState</button>
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


The `getMigrationStates` API provides a comprehensive overview of the migration status for various user settings. This function is particularly useful for identifying which settings require migration to ensure compatibility with updated system configurations or new application versions. By retrieving a list of settings and their respective migration states, users can gain insights into whether specific settings need to be updated or adjusted to align with the latest system requirements. This API is essential for maintaining a seamless user experience during system upgrades or transitions.

### Related Functions
[getMigrationState](#getMigrationState) : Retrieves the migration state for a specific setting key, allowing users to check the migration requirement for an individual setting.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getMigrationStates",
    "params":{}}'
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
      thunderJS.getMigrationStates()
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
    void org_rdk_UserSettings_getMigrationStates(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `getContentPin` API retrieves the current content PIN set by the user. This PIN is typically used to enforce parental controls, restrict access to certain content, or manage other security-related settings. The function ensures that the stored PIN is fetched securely and returned to the caller. If no PIN is set, the function may return an empty value, indicating that no content PIN is currently configured. This API is useful for users who want to verify or manage their existing content PIN settings.

### Related Functions
[setContentPin](#setContentPin) : Allows users to set or update the content PIN. This function complements `getContentPin` by enabling the configuration of the PIN value.

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
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"org.rdk.UserSettings.getContentPin",
    "params":{}}'
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
    void org_rdk_UserSettings_getContentPin(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


The `onAudioDescriptionChanged` event is triggered whenever there is a change in the audio description setting of the system. Audio description is a feature designed to assist visually impaired users by providing additional audio narration that describes visual elements of the content, such as actions, settings, and scene changes. This event notifies the user that the audio description feature has been enabled or disabled, ensuring they are aware of the current accessibility settings.

This event is particularly useful for users who rely on audio descriptions to enhance their viewing experience. It ensures that any changes to the audio description setting are communicated promptly, allowing users to adjust their preferences or settings as needed.

### Related Functions
[setAudioDescription](#setAudioDescription) : This API is used to enable or disable the audio description feature. When this function is called, it triggers the `onAudioDescriptionChanged` event to notify users about the change in the audio description setting.

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


The `onPreferredAudioLanguagesChanged` event is triggered whenever the user's preferred audio language settings are updated. This event notifies the system or application about the change, ensuring that the audio playback aligns with the user's updated preferences. For example, if a user changes their preferred audio language to "French," this event will be triggered, allowing the application to adjust the audio track accordingly. This ensures a seamless and personalized audio experience for the user.

### Related Functions
[setPreferredAudioLanguages](#setPreferredAudioLanguages) : This function is used to set the user's preferred audio languages. When this function is called, it updates the preferred audio language settings, which in turn triggers the `onPreferredAudioLanguagesChanged` event.

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


The `onPresentationLanguageChanged` event is triggered whenever the presentation language setting is updated. This event notifies the user that the language used for the presentation of content, such as menus, subtitles, or other on-screen text, has been changed. This ensures that users are aware of the updated language setting and can experience the interface in their preferred language. It is particularly useful in multilingual environments where users may frequently switch between languages for accessibility or personal preference.

### Related Functions
[setPresentationLanguage](#setPresentationLanguage) : This API is used to set the presentation language. When the language is updated using this function, it triggers the `onPresentationLanguageChanged` event to notify the system and the user about the change.

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


The `onCaptionsChanged` event is triggered whenever there is a change in the captions settings of the user interface. Captions are textual representations of spoken dialogue, sound effects, and other audio elements in video content, designed to enhance accessibility for users who are deaf or hard of hearing, or for those who prefer to watch content with subtitles. This event notifies the system or application that the captions feature has been enabled or disabled, allowing it to respond accordingly, such as updating the user interface or saving the new preference.

This event is particularly useful for users who rely on captions for better comprehension of video content. It ensures that any changes made to the captions settings are reflected immediately, providing a seamless and accessible viewing experience. For example, if a user enables captions, the system can automatically display subtitles for the selected content without requiring additional input.

### Related Functions
[setCaptions](#setCaptions) : This API allows users to enable or disable captions for video content. It directly triggers the `onCaptionsChanged` event when the captions setting is modified.

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


The `onPreferredCaptionsLanguagesChanged` event is triggered whenever the user's preferred captions languages are updated. This event is particularly useful for applications or services that need to adapt their content presentation based on the user's language preferences for captions. For example, streaming platforms or media players can use this event to dynamically adjust the captions displayed during playback to match the user's updated preferences. This ensures a more personalized and accessible viewing experience for users who rely on captions in their preferred languages.

The event provides the updated list of preferred captions languages, allowing applications to respond accordingly, such as by fetching captions in the specified languages or updating the user interface to reflect the changes. This event is part of a broader set of user settings that enhance accessibility and personalization in media consumption.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : This API allows users to set their preferred captions languages. When this function is called, it triggers the `onPreferredCaptionsLanguagesChanged` event to notify the system and applications about the updated preferences.

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


The `onPreferredClosedCaptionServiceChanged` event is triggered whenever there is a change in the user's preferred closed caption service. Closed captions are an essential accessibility feature that provides text-based transcriptions of spoken dialogue, sound effects, and other audio cues in video content. This event ensures that users are notified when their preferred closed caption service is updated, allowing them to stay informed about changes to their accessibility settings.

This event is particularly useful for users who rely on specific closed caption services to enhance their viewing experience. For example, users may prefer a particular service that offers better synchronization, more accurate transcriptions, or additional customization options. By being notified of changes, users can ensure their settings align with their preferences and accessibility needs.

### Related Functions
[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : This function allows users to set their preferred closed caption service. When this function is called, it triggers the `onPreferredClosedCaptionServiceChanged` event to notify the system and the user about the update.

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


The `onPrivacyModeChanged` event is triggered whenever there is a change in the privacy mode setting of the device. Privacy mode determines how user data is shared or restricted. For example, it can toggle between modes like "SHARE" (allowing data sharing) and "DO_NOT_SHARE" (restricting data sharing). This event notifies the system or application about the updated privacy mode, enabling it to adjust its behavior accordingly. This ensures that user preferences regarding data privacy are respected and applied consistently across the system.

This event is particularly useful for users who want to maintain control over their data-sharing preferences. For instance, switching to "DO_NOT_SHARE" mode ensures that the device does not share personal data with external systems or services. Conversely, "SHARE" mode allows the device to share data, which might be necessary for certain features or services to function optimally.

### Related Functions
[setPrivacyMode](#setPrivacyMode) : This function is used to update the privacy mode setting. It accepts values like "SHARE" or "DO_NOT_SHARE" to define the desired privacy behavior. When this function is called, it triggers the `onPrivacyModeChanged` event to notify the system of the change.

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


The `onPinControlChanged` event is triggered whenever there is a change in the PIN control settings. PIN control is a feature that allows users to enable or disable the requirement of a PIN for accessing certain content or performing specific actions. This event notifies the system or application about the updated state of the PIN control, ensuring that any dependent features or settings can respond accordingly. For example, enabling PIN control might restrict access to certain content, while disabling it could allow unrestricted access. This event is particularly useful for maintaining parental controls, content restrictions, or other security-related configurations.

### Related Functions
[setPinControl](#setPinControl) : This API is used to enable or disable the PIN control feature. When this function is called, it updates the PIN control setting and triggers the `onPinControlChanged` event to notify the system of the change.

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


The `onViewingRestrictionsChanged` event is triggered whenever there is a change in the viewing restrictions settings. Viewing restrictions are typically used to control access to certain types of content based on user preferences or regulatory requirements, such as parental controls, content ratings, or time-based restrictions. This event notifies the system or application that the viewing restrictions have been updated, ensuring that the changes are reflected in real-time. For example, if a parent updates the content rating restrictions to block certain types of content, this event will be triggered to apply the new settings across the platform.

This event is particularly useful for users who want to maintain control over the content accessible on their devices, ensuring a safe and tailored viewing experience for themselves or their family members.

### Related Functions
[setViewingRestrictions](#setViewingRestrictions) : This function is used to update the viewing restrictions settings. When this function is called, it triggers the `onViewingRestrictionsChanged` event to notify the system of the updated restrictions.

[getViewingRestrictions](#getViewingRestrictions) : This function retrieves the current viewing restrictions settings. It allows users to check the active restrictions applied to their content.

[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : This function sets a specific time window during which the viewing restrictions are applied. Changes made using this function may also trigger the `onViewingRestrictionsChanged` event.

[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : This function retrieves the current time window for the viewing restrictions, providing users with details about when the restrictions are active.

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


The `onViewingRestrictionsWindowChanged` event is triggered whenever there is a change in the viewing restrictions window settings. This event is particularly useful for users who want to manage or monitor the time-based restrictions applied to content viewing. For example, parents or guardians can use this feature to enforce specific time windows during which certain types of content can be accessed. The event ensures that any updates to the viewing restrictions window are communicated promptly, allowing users to stay informed and maintain control over their content preferences.

This event is designed to enhance user experience by providing real-time updates about changes in the viewing restrictions window. It is especially beneficial for users who rely on time-based content restrictions to manage access to specific types of media. By leveraging this event, users can ensure that their preferences are consistently applied and updated across the system.

### Related Functions
[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : This API allows users to define or update the viewing restrictions window. It sets the specific time frames during which content restrictions are applied, triggering the `onViewingRestrictionsWindowChanged` event to notify users of the change.

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


The `onLiveWatershedChanged` event is triggered whenever there is a change in the "Live Watershed" setting. The Live Watershed setting is used to enforce content restrictions based on specific time periods or user-defined rules. This event notifies the user or application when the Live Watershed setting is updated, ensuring that the system can respond appropriately to the change. For example, this could involve updating the content filtering rules or notifying the user about the change in restrictions. This event is particularly useful for maintaining compliance with parental controls or content viewing policies.

### Related Functions
[setLiveWatershed](#setLiveWatershed) : This API is used to update the Live Watershed setting. When this function is called, it triggers the `onLiveWatershedChanged` event to notify the system and any listeners about the change.

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


The `onPlaybackWatershedChanged` event is triggered whenever there is a change in the playback watershed setting. The playback watershed setting is a user-defined restriction that determines whether certain content, based on its rating or classification, can be played. This feature is particularly useful for households or environments where content restrictions are necessary to ensure that viewers only access age-appropriate or permitted content. For example, enabling the playback watershed setting might block content rated for mature audiences during specific times or entirely, depending on the configuration.

This event notifies the system or application that the playback watershed setting has been updated, allowing it to take appropriate actions, such as enforcing content restrictions or updating the user interface to reflect the new setting. It ensures that the system remains synchronized with the user's preferences and provides a seamless experience in managing content accessibility.

### Related Functions
[setPlaybackWatershed](#setPlaybackWatershed) : This function is used to enable or disable the playback watershed setting. When this function is called, it updates the playback watershed configuration, which in turn triggers the `onPlaybackWatershedChanged` event to notify the system of the change.

[getPlaybackWatershed](#getPlaybackWatershed) : This function retrieves the current state of the playback watershed setting. It allows the system or application to check whether the playback watershed is enabled or disabled.

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


The `onBlockNotRatedContentChanged` event is triggered whenever there is a change in the setting that controls whether unrated content is blocked. This feature is particularly useful for users who want to enforce viewing restrictions based on content ratings. By enabling or disabling this setting, users can ensure that unrated content is either accessible or restricted, depending on their preferences or parental control requirements. This event notifies the system and any subscribed components about the change, allowing them to update their behavior accordingly. For example, streaming platforms or media players can adjust their content availability based on this setting to align with user preferences.

This event is essential for maintaining a controlled viewing environment, especially in households with children or where content restrictions are a priority. It ensures that changes to the "Block Not Rated Content" setting are communicated effectively across the system, enabling seamless enforcement of the user's preferences.

### Related Functions
[setBlockNotRatedContent](#setBlockNotRatedContent) : This API is used to enable or disable the blocking of unrated content. When this setting is changed, it triggers the `onBlockNotRatedContentChanged` event to notify the system and subscribed components about the update.

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


The `onPinOnPurchaseChanged` event is triggered whenever there is a change in the "Pin on Purchase" setting. This setting is used to enforce an additional layer of security by requiring a PIN to authorize purchases. It is particularly useful for households with children or shared devices, ensuring that unauthorized purchases are prevented. When this event is triggered, it notifies the system or application that the "Pin on Purchase" preference has been updated, allowing the user interface or related functionalities to reflect the change accordingly. This event is designed to enhance user control and security over purchase-related activities.

### Related Functions
[setPinOnPurchase](#setPinOnPurchase) : This API is used to enable or disable the "Pin on Purchase" feature. It allows users to configure whether a PIN is required for purchases, thereby triggering the `onPinOnPurchaseChanged` event when the setting is updated.

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


The `onHighContrastChanged` event is triggered whenever the high contrast mode setting is changed on the device. High contrast mode is an accessibility feature designed to improve the visibility of text and interface elements for users with visual impairments. When enabled, it adjusts the color scheme of the user interface to provide greater contrast between text, images, and backgrounds, making it easier to read and navigate. This event notifies applications or services that rely on user settings to adapt their behavior or appearance accordingly, ensuring a seamless and accessible experience for users.

This event is particularly useful for users who require enhanced visual accessibility, as it allows applications to dynamically respond to changes in the high contrast setting. For example, an application might adjust its color palette, text rendering, or graphical elements to align with the high contrast mode, ensuring consistent usability across the platform.

### Related Functions
[setHighContrast](#setHighContrast) : This API is used to enable or disable the high contrast mode. When the high contrast setting is updated using this function, the `onHighContrastChanged` event is triggered to notify relevant components or applications about the change.

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


The `onVoiceGuidanceChanged` event is triggered whenever the voice guidance feature is enabled or disabled in the user settings. Voice guidance is an accessibility feature designed to assist users by providing spoken feedback for navigating menus, settings, and other on-screen elements. This event notifies the system or application about changes in the voice guidance state, allowing it to adapt its behavior accordingly. For example, enabling voice guidance can activate audio prompts to help visually impaired users interact with the interface more effectively. Conversely, disabling voice guidance stops these audio prompts, reverting the interface to its standard mode of operation.

This event is particularly useful for ensuring accessibility settings are synchronized across different components of the system or application. It helps maintain a seamless user experience by dynamically responding to changes in accessibility preferences.

### Related Functions
[setVoiceGuidance](#setVoiceGuidance) : This API is used to enable or disable the voice guidance feature. When this function is called, it triggers the `onVoiceGuidanceChanged` event to notify the system of the updated state.

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


The `onVoiceGuidanceRateChanged` event is triggered whenever the rate of voice guidance is updated. Voice guidance is a feature designed to assist users, particularly those with visual impairments, by providing spoken feedback for navigating menus, settings, and other on-screen elements. The rate of voice guidance determines the speed at which the spoken feedback is delivered, allowing users to customize it to their preference for better accessibility and usability. For example, users may prefer a slower rate for easier comprehension or a faster rate for quicker navigation. This event ensures that any changes to the voice guidance rate are communicated effectively, enabling applications or systems to respond accordingly, such as updating the user interface or saving the new rate setting.

### Related Functions
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : This API is used to set the rate of voice guidance. It allows users to specify the desired speed for spoken feedback, ensuring a personalized and accessible experience. Changes made through this function trigger the `onVoiceGuidanceRateChanged` event.

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


The `onVoiceGuidanceHintsChanged` event is triggered whenever there is a change in the state of voice guidance hints. Voice guidance hints are additional audio cues or instructions provided to assist users in navigating and interacting with the system, particularly beneficial for users with visual impairments. This event notifies the system or application that the voice guidance hints setting has been updated, enabling it to adapt its behavior accordingly. For example, enabling or disabling voice guidance hints can enhance accessibility by providing more detailed or simplified audio feedback based on user preferences. This event ensures that the system remains responsive to user accessibility needs and preferences.

### Related Functions
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : This function allows users to enable or disable voice guidance hints. By invoking this API, the system triggers the `onVoiceGuidanceHintsChanged` event to reflect the updated state of voice guidance hints.

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


The `onContentPinChanged` event is triggered whenever the content PIN is updated or modified. This event serves as a notification mechanism to inform the user or system about changes to the PIN used for controlling access to specific content. The content PIN is typically used to enforce parental controls, restrict access to certain types of content, or ensure secure viewing preferences. By listening to this event, users or applications can stay updated on changes to the PIN and take appropriate actions, such as updating UI elements, logging changes, or enforcing new restrictions based on the updated PIN.

This event is particularly useful for maintaining a secure and personalized viewing experience, ensuring that only authorized users can access restricted content. It also helps in scenarios where the PIN needs to be dynamically updated to reflect changes in user preferences or security policies.

### Related Functions
[setContentPin](#setContentPin) : This API is responsible for setting or updating the content PIN. It triggers the `onContentPinChanged` event whenever a new PIN is set or the existing PIN is modified.

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
