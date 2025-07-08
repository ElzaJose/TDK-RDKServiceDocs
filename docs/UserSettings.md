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


The **UserSettings** RDK service is a WPEFramework plugin designed to manage and configure user-specific settings for audio, captions, and language preferences. It provides interfaces for accessing and modifying settings such as preferred audio languages, audio descriptions, captions, and presentation languages. This service ensures a customizable and accessible user experience by allowing dynamic configuration of these preferences.

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
| [setViewingRestrictions](#setViewingRestrictions) | Set viewing restrictions | [onViewingRestrictionsChanged](#onViewingRestrictionsChanged) |
| [setViewingRestrictionsWindow](#setViewingRestrictionsWindow) | set viewing restrictions | [onViewingRestrictionsWindowChanged](#onViewingRestrictionsWindowChanged) |
| [setLiveWatershed](#setLiveWatershed) | set live watershed | [onLiveWatershedChanged](#onLiveWatershedChanged) |
| [setPlaybackWatershed](#setPlaybackWatershed) | set playback watershed | [onPlaybackWatershedChanged](#onPlaybackWatershedChanged) |
| [setBlockNotRatedContent](#setBlockNotRatedContent) | Block unrated content | [onBlockNotRatedContentChanged](#onBlockNotRatedContentChanged) |
| [setPinOnPurchase](#setPinOnPurchase) | set pin on purchase | [onPinOnPurchaseChanged](#onPinOnPurchaseChanged) |
| [setHighContrast](#setHighContrast) | Enables high contrast | [onHighContrastChanged](#onHighContrastChanged) |
| [setVoiceGuidance](#setVoiceGuidance) | configure voice guidance | [onVoiceGuidanceChanged](#onVoiceGuidanceChanged) |
| [setVoiceGuidanceRate](#setVoiceGuidanceRate) | Sets voice guidance rate | [onVoiceGuidanceRateChanged](#onVoiceGuidanceRateChanged) |
| [setVoiceGuidanceHints](#setVoiceGuidanceHints) | set voice guidance hints | [onVoiceGuidanceHintsChanged](#onVoiceGuidanceHintsChanged) |
| [setContentPin](#setContentPin) | set content pin | [onContentPinChanged](#onContentPinChanged) |
| [getAudioDescription](#getAudioDescription) | audio description retrieval | NA |
| [getPreferredAudioLanguages](#getPreferredAudioLanguages) | preferred audio languages | NA |
| [getPresentationLanguage](#getPresentationLanguage) | presentation language retrieval | NA |
| [getCaptions](#getCaptions) | fetch video captions | NA |
| [getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) | preferred captions languages | NA |
| [getPreferredClosedCaptionService](#getPreferredClosedCaptionService) | Get preferred closed captions | NA |
| [getPrivacyMode](#getPrivacyMode) | get privacy mode info | NA |
| [getPinControl](#getPinControl) | Pin control management | NA |
| [getViewingRestrictions](#getViewingRestrictions) | viewing restrictions info | NA |
| [getViewingRestrictionsWindow](#getViewingRestrictionsWindow) | viewing restrictions window | NA |
| [getLiveWatershed](#getLiveWatershed) | live watershed data | NA |
| [getPlaybackWatershed](#getPlaybackWatershed) | playback watershed details | NA |
| [getBlockNotRatedContent](#getBlockNotRatedContent) | Get unrated content | NA |
| [getPinOnPurchase](#getPinOnPurchase) | Get PIN on purchase | NA |
| [getHighContrast](#getHighContrast) | get high contrast | NA |
| [getVoiceGuidance](#getVoiceGuidance) | voice guidance details | NA |
| [getVoiceGuidanceRate](#getVoiceGuidanceRate) | Get voice guidance rate | NA |
| [getVoiceGuidanceHints](#getVoiceGuidanceHints) | Get voice guidance hints | NA |
| [getMigrationState](#getMigrationState) | migration state retrieval | NA |
| [getMigrationStates](#getMigrationStates) | migration states info | NA |
| [getContentPin](#getContentPin) | get content pin details | NA |


<a name="setAudioDescription"></a>
## *setAudioDescription*


The `setAudioDescription` API allows users to enable or disable the audio description feature for their media content. Audio description is an accessibility feature that provides additional audio narration to describe visual elements in a video, such as actions, settings, or scene changes, making the content more accessible to visually impaired users. By using this API, users can customize their viewing experience to include or exclude this feature based on their preferences. Once enabled, the system will provide descriptive audio tracks where available.

### Related Functions  
[getAudioDescription](#getAudioDescription) : Retrieves the current status of the audio description feature (enabled or disabled). This function complements `setAudioDescription` by allowing users to verify the current setting.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setAudioDescription", 
    "params":{"enabled":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPreferredAudioLanguages"></a>
## *setPreferredAudioLanguages*


The `setPreferredAudioLanguages` API allows users to specify their preferred audio languages for content playback. This setting ensures that the audio track in the selected language is prioritized whenever available, enhancing the viewing experience by aligning it with the user's language preferences. For example, if a user prefers "English" and "Spanish," the system will attempt to play content in these languages in the specified order of preference. This feature is particularly useful in multilingual households or for users who consume content in multiple languages.

### Related Functions 
[getPreferredAudioLanguages](#getPreferredAudioLanguages) : Retrieves the currently set preferred audio languages, allowing users to verify or review their preferences.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPreferredAudioLanguages", 
    "params":{"preferredLanguages":"eng"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPresentationLanguage"></a>
## *setPresentationLanguage*


The `setPresentationLanguage` API allows users to define their preferred language for the presentation of content, such as menus, on-screen text, and other user interface elements. By setting the presentation language, users can customize their viewing experience to align with their language preferences, ensuring that the interface is accessible and easy to navigate. This setting is particularly useful in multilingual households or for users who prefer a specific language for better comprehension and usability. Once the presentation language is set, the system updates the user interface accordingly.

### Related Functions  
[getPresentationLanguage](#getPresentationLanguage) : Retrieves the currently set presentation language, allowing users to confirm or review their existing language preference.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPresentationLanguage", 
    "params":{"presentationLanguage":"en-US"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
      thunderJS.org.rdk.UserSettings.setPresentationLanguage({ presentationLanguage: presentationLanguage })
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
    
=== "CPP"

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
    

<a name="setCaptions"></a>
## *setCaptions*


The `setCaptions` function allows users to enable or disable captions for their viewing experience. Captions are textual representations of the audio content in a video, including dialogue, sound effects, and other audio cues. This feature is particularly useful for individuals who are deaf or hard of hearing, or for those who prefer to watch content with captions for better comprehension. By enabling captions, users can ensure that they do not miss any important audio information, even in noisy environments or when the audio is muted. Conversely, disabling captions provides a cleaner viewing experience for those who do not require them.

This function is part of the user settings and ensures that the preference for captions is saved and applied consistently across the platform. Once set, the system may notify relevant components or services about the change, ensuring a seamless experience for the user.

### Related Functions  
[getCaptions](#getCaptions) : Retrieves the current status of captions (enabled or disabled), allowing users to check their existing preference.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setCaptions", 
    "params":{"enabled":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPreferredCaptionsLanguages"></a>
## *setPreferredCaptionsLanguages*


The `setPreferredCaptionsLanguages` function allows users to specify their preferred languages for captions. This feature is particularly useful for individuals who rely on captions to enhance their viewing experience, such as those who are hard of hearing or watching content in a non-native language. By setting a preferred language, users can ensure that captions are displayed in their desired language whenever available, providing a more personalized and accessible viewing experience. This setting is typically applied across supported content and platforms, making it a convenient way to maintain consistent preferences.

### Related Functions  
[getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) : Retrieves the currently set preferred captions languages, allowing users to verify or review their existing preferences.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPreferredCaptionsLanguages", 
    "params":{"preferredLanguages":"eng"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPreferredClosedCaptionService"></a>
## *setPreferredClosedCaptionService*


The `setPreferredClosedCaptionService` API allows users to specify their preferred closed captioning service for video content. Closed captions provide textual representation of audio elements in a video, such as dialogue, sound effects, and other auditory information, making content accessible to individuals with hearing impairments or those who prefer textual aids. By setting a preferred closed caption service, users can ensure that their chosen service is consistently applied across supported content, enhancing their viewing experience. This API is particularly useful for customizing accessibility settings to align with individual preferences.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPreferredClosedCaptionService", 
    "params":{"service":"CC3"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPrivacyMode"></a>
## *setPrivacyMode*


The `setPrivacyMode` API allows users to configure the privacy settings of their device. This function enables users to choose between two modes: "SHARE" and "DO_NOT_SHARE." When set to "SHARE," the device permits sharing of certain user data, which may be used for personalization or other purposes. Conversely, "DO_NOT_SHARE" ensures that user data is not shared, prioritizing privacy. This setting is particularly useful for users who are concerned about data security and wish to control how their information is handled. The API validates the input to ensure only the supported values ("SHARE" or "DO_NOT_SHARE") are accepted, providing a safeguard against incorrect configurations.  

### Related Functions  
[getPrivacyMode](#getPrivacyMode) : Retrieves the current privacy mode setting of the device, allowing users to check whether their device is configured to "SHARE" or "DO_NOT_SHARE."

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPrivacyMode", 
    "params":{"privacyMode":"SHARE"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPinControl"></a>
## *setPinControl*


The `setPinControl` API allows users to enable or disable the PIN control feature on their device. PIN control is a security feature that restricts access to certain functionalities or content based on user-defined settings. By enabling PIN control, users can ensure that sensitive actions, such as accessing restricted content or making purchases, require a PIN for authorization. This feature is particularly useful for parental controls or safeguarding against unauthorized access.

### Related Functions
[getPinControl](#getPinControl) : Retrieves the current status of the PIN control feature, indicating whether it is enabled or disabled.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPinControl", 
    "params":{"pinControl":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

    ```cpp
    void org_rdk_UserSettings_setPinControl(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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
    

<a name="setViewingRestrictions"></a>
## *setViewingRestrictions*


The `setViewingRestrictions` API allows users to define specific restrictions for content viewing based on their preferences or requirements. This function is particularly useful for managing access to content that may be inappropriate for certain audiences, such as children or individuals with specific sensitivities. By setting viewing restrictions, users can ensure that only content meeting their defined criteria is accessible, providing a tailored and secure viewing experience. This API is often used in conjunction with parental controls or content filtering systems to enforce content guidelines effectively.

### Related Functions  
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions set by the user. This function complements `setViewingRestrictions` by allowing users to verify or review the restrictions they have applied.  

[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Defines a specific time window during which the viewing restrictions are enforced. This function works alongside `setViewingRestrictions` to provide more granular control over content accessibility.  

[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the current time window settings for viewing restrictions, enabling users to review or confirm the enforcement period.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setViewingRestrictions", 
    "params":{"viewingRestrictions":"{\"restrictions\": [{\"scheme\": \"US_TV\", \"restrict\": [\"TV-Y7/FV\"]}, {\"scheme\": \"MPAA\", \"restrict\": []}]}"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setViewingRestrictionsWindow"></a>
## *setViewingRestrictionsWindow*


The `setViewingRestrictionsWindow` API allows users to define a specific time window during which viewing restrictions are applied. This function is particularly useful for parents or guardians who want to enforce content restrictions during certain hours, such as when children are likely to be watching TV. By setting a viewing restrictions window, users can ensure that inappropriate or restricted content is blocked during the specified timeframe. This feature enhances control over content accessibility and helps maintain a safe viewing environment.

### Related Functions  
[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : Retrieves the currently set viewing restrictions window, allowing users to confirm or review the active time window for restrictions.  
[setViewingRestrictions](#setViewingRestrictions) : Sets general viewing restrictions, which can complement the time-based restrictions defined by `setViewingRestrictionsWindow`.  
[getViewingRestrictions](#getViewingRestrictions) : Retrieves the current viewing restrictions, providing insight into the active content limitations.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setViewingRestrictionsWindow", 
    "params":{"viewingRestrictionsWindow":"{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    <button onclick="setViewingRestrictionsWindow({viewingRestrictionsWindow: '{\"startTime\": \"08:00\", \"endTime\": \"20:00\"}'})">setViewingRestrictionsWindow</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="setLiveWatershed"></a>
## *setLiveWatershed*


The `setLiveWatershed` API allows users to configure the live watershed setting for their device or application. The live watershed setting is typically used to enforce content restrictions based on time-based guidelines, such as ensuring that certain types of content are only accessible during specific hours. By enabling or disabling this feature, users can control whether live content adheres to watershed rules, which are often designed to protect younger audiences from inappropriate material during certain times of the day. This setting is particularly useful for households with children or for users who want to customize their viewing experience based on content restrictions.

### Related Functions
[getLiveWatershed](#getLiveWatershed) : Retrieves the current status of the live watershed setting, allowing users to check whether the feature is enabled or disabled.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setLiveWatershed", 
    "params":{"liveWatershed":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setPlaybackWatershed"></a>
## *setPlaybackWatershed*


The `setPlaybackWatershed` API is used to configure the playback watershed setting for a user. The playback watershed is a feature that allows users to set restrictions on the type of content that can be played based on its suitability for certain age groups or time periods. By enabling or disabling this setting, users can control whether content deemed inappropriate for certain audiences is restricted during playback. This is particularly useful for parental controls or adhering to content guidelines.

When the playback watershed is enabled, the system ensures that content flagged as unsuitable for the specified criteria is blocked from being played. Conversely, disabling the playback watershed removes these restrictions, allowing all content to be played regardless of its suitability.

This API is ideal for users who want to manage content accessibility based on age ratings or other criteria, ensuring a safe and controlled viewing experience.

### Related Functions
[getPlaybackWatershed](#getPlaybackWatershed) : Retrieves the current status of the playback watershed setting, allowing users to check whether the restriction is enabled or disabled.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPlaybackWatershed", 
    "params":{"playbackWatershed":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
      thunderJS.setPlaybackWatershed({ playbackWatershed: playbackWatershed })
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
    
=== "CPP"

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
    

<a name="setBlockNotRatedContent"></a>
## *setBlockNotRatedContent*


The `setBlockNotRatedContent` API allows users to enable or disable the blocking of content that has not been rated. This feature is particularly useful for parents or guardians who want to ensure that unrated content is restricted from being accessed, providing an additional layer of control over the type of media that can be viewed. By setting this option, users can enforce viewing restrictions based on content ratings, ensuring that unrated material is treated as restricted.

This API is part of user settings and is typically used in scenarios where content control and parental guidance are required. When enabled, unrated content will be blocked, and when disabled, unrated content will be accessible. The API modifies the user settings to reflect the desired behavior.

### Related Functions
[getBlockNotRatedContent](#getBlockNotRatedContent) : Retrieves the current status of the block-not-rated-content setting, allowing users to check whether unrated content is currently being blocked or not.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setBlockNotRatedContent", 
    "params":{"blockNotRatedContent":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
      thunderJS.setBlockNotRatedContent({ blockNotRatedContent: blockNotRatedContent })
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
    
=== "CPP"

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
    

<a name="setPinOnPurchase"></a>
## *setPinOnPurchase*


The `setPinOnPurchase` API allows users to enable or disable the requirement of a PIN when making purchases. This feature is particularly useful for households with multiple users, especially when there are children or individuals who should not have unrestricted access to purchasing content. By enabling this setting, users can ensure that a PIN must be entered before any purchase is completed, adding an extra layer of security and preventing unauthorized or accidental purchases. Conversely, disabling this setting removes the PIN requirement, allowing purchases to be made more conveniently but with less control.

This setting is part of the broader parental control and security features available in the system, giving users the flexibility to manage their preferences based on their specific needs.

### Related Functions
[getPinOnPurchase](#getPinOnPurchase) : Retrieves the current status of the "PIN on Purchase" setting, indicating whether the PIN requirement is enabled or disabled.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setPinOnPurchase", 
    "params":{"pinOnPurchase":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setHighContrast"></a>
## *setHighContrast*


The `setHighContrast` API allows users to enable or disable the high contrast mode on their device. High contrast mode is a feature designed to improve the visibility of text and interface elements for users with visual impairments or those who prefer a more distinct visual presentation. When enabled, the device adjusts its display settings to use a higher contrast color scheme, making text and other elements stand out more clearly against their backgrounds. This feature is particularly useful for accessibility purposes, ensuring that the device is more inclusive and user-friendly for individuals with specific visual needs.

### Related Functions  
[getHighContrast](#getHighContrast) : Retrieves the current status of the high contrast mode, indicating whether it is enabled or disabled.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setHighContrast", 
    "params":{"enabled":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setVoiceGuidance"></a>
## *setVoiceGuidance*


The `setVoiceGuidance` API allows users to enable or disable the voice guidance feature on their device. Voice guidance is an accessibility feature designed to assist visually impaired users by providing audio feedback for on-screen content and navigation. By enabling this feature, users can receive spoken instructions and descriptions, making it easier to interact with the device's interface. Disabling the feature turns off the audio feedback, reverting the device to its standard visual interface.

This API is particularly useful for users who rely on auditory cues to navigate menus, access content, or perform other tasks on their device. It ensures a more inclusive and accessible user experience.

### Related Functions
[getVoiceGuidance](#getVoiceGuidance) : Retrieves the current status of the voice guidance feature (enabled or disabled).  
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : Adjusts the speed at which the voice guidance audio is delivered.  
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Configures additional hints or prompts provided by the voice guidance feature.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setVoiceGuidance", 
    "params":{"enabled":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setVoiceGuidanceRate"></a>
## *setVoiceGuidanceRate*


The `setVoiceGuidanceRate` API allows users to adjust the speed at which voice guidance is delivered. Voice guidance is an accessibility feature designed to assist visually impaired users by providing spoken feedback about on-screen content and navigation. By using this API, users can customize the rate of speech to suit their preferences, making the experience more comfortable and tailored to their needs. The rate can be set within a predefined range, ensuring that the speech remains intelligible and effective. This feature is particularly useful for users who may prefer faster or slower speech depending on their listening abilities or familiarity with the content.

### Related Functions  
[getVoiceGuidanceRate](#getVoiceGuidanceRate) : Retrieves the current voice guidance rate setting, allowing users to confirm or review the configured speech rate.  
[setVoiceGuidance](#setVoiceGuidance) : Enables or disables the voice guidance feature, which must be active for the rate setting to take effect.  
[getVoiceGuidance](#getVoiceGuidance) : Checks whether the voice guidance feature is currently enabled or disabled.  
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Configures additional hints or prompts provided by the voice guidance system, complementing the rate setting.  
[getVoiceGuidanceHints](#getVoiceGuidanceHints) : Retrieves the current status of voice guidance hints, providing insight into the overall voice guidance configuration.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setVoiceGuidanceRate", 
    "params":{"rate":0.1}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="setVoiceGuidanceHints"></a>
## *setVoiceGuidanceHints*


The `setVoiceGuidanceHints` API allows users to enable or disable voice guidance hints in their system settings. Voice guidance hints are additional auditory cues or instructions provided to assist users in navigating and interacting with the system, particularly beneficial for individuals with visual impairments or those who prefer audio-based guidance. By enabling this feature, users can receive contextual hints that enhance their overall accessibility experience. Conversely, disabling it will turn off these auditory cues, providing a more streamlined experience for users who do not require them.

This API is particularly useful for tailoring the accessibility settings of the system to meet individual user preferences. It ensures that users can customize their interaction with the system to suit their needs, making it more inclusive and user-friendly.

### Related Functions
[getVoiceGuidanceHints](#getVoiceGuidanceHints) : Retrieves the current status of voice guidance hints (enabled or disabled), allowing users to check whether the feature is active.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setVoiceGuidanceHints", 
    "params":{"hints":true}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    function setVoiceGuidanceHints(params) {
      thunderJS.setVoiceGuidanceHints(params)
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
    <button onclick="setVoiceGuidanceHints({hints: true})">setVoiceGuidanceHints</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="setContentPin"></a>
## *setContentPin*


The `setContentPin` function allows users to set or update the content PIN for their account. This PIN is typically used to restrict access to certain content or features, ensuring that only authorized users can view or modify restricted settings. The PIN must be a 4-digit numeric value, ensuring simplicity and ease of use. If an empty string is provided, the existing PIN is cleared. This function is particularly useful for parents or guardians who want to enforce content restrictions for children or other users.  

### Related Functions  
[getContentPin](#getContentPin) : Retrieves the currently set content PIN, allowing users to verify or confirm the existing PIN.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.setContentPin", 
    "params":{"contentPin":"1234"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
      thunderJS.setContentPin({ contentPin: contentPin })
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
    
=== "CPP"

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
    

<a name="getAudioDescription"></a>
## *getAudioDescription*


The `getAudioDescription` API is used to retrieve the current status of the audio description feature. Audio description is an accessibility feature that provides additional audio narration to describe visual elements in a video, such as actions, settings, and characters, for individuals who are visually impaired. This API allows users to check whether the audio description feature is enabled or disabled, helping them ensure that the accessibility settings align with their preferences or requirements.  

### Related Functions  
[setAudioDescription](#setAudioDescription) : This API allows users to enable or disable the audio description feature. It complements the `getAudioDescription` API by providing the ability to modify the audio description setting.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getAudioDescription", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPreferredAudioLanguages"></a>
## *getPreferredAudioLanguages*


The `getPreferredAudioLanguages` API retrieves the user's preferred audio languages for media playback. This function is particularly useful for users who consume content in multiple languages or have specific language preferences for audio tracks. By accessing this information, the system can automatically select the most suitable audio track based on the user's preferences, enhancing the viewing experience without requiring manual adjustments. This API ensures that users can enjoy content in their desired language seamlessly, making it ideal for multilingual households or individuals with specific language needs.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPreferredAudioLanguages", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    <button onclick="getPreferredAudioLanguages()">getPreferredAudioLanguages</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="getPresentationLanguage"></a>
## *getPresentationLanguage*


The `getPresentationLanguage` API retrieves the current presentation language setting for the user. This language setting determines the primary language used for on-screen menus, notifications, and other user interface elements. It ensures that the user interface is displayed in the language most comfortable for the user, enhancing accessibility and personalization. This function is particularly useful for multi-lingual households or users who prefer a specific language for their viewing experience.

### Related Functions
[setPresentationLanguage](#setPresentationLanguage) : Allows the user to set or update the preferred presentation language. This function complements `getPresentationLanguage` by enabling the modification of the language setting.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPresentationLanguage", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    function callUserSettings() {
      thunderJS.org.rdk.UserSettings.getPresentationLanguage()
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
    <button onclick="callUserSettings()">callUserSettings</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="getCaptions"></a>
## *getCaptions*


The `getCaptions` API is designed to retrieve the current status of captions functionality in the user settings. Captions are textual representations of spoken dialogue, sound effects, and other audio elements in video content, making it accessible for individuals who are deaf or hard of hearing. This API allows users to check whether captions are enabled or disabled in their system settings. By using this function, users can confirm the current state of captions and ensure that their accessibility preferences are correctly configured.

This API is particularly useful for users who want to verify their accessibility settings or for applications that need to adapt their behavior based on whether captions are enabled. For example, streaming platforms or media players can use this API to display captions automatically if they are enabled in the user's settings.

### Related Functions  
[setCaptions](#setCaptions) : Allows users to enable or disable captions functionality in the system settings. This function complements `getCaptions` by providing the ability to modify the captions setting.  

[getPreferredCaptionsLanguages](#getPreferredCaptionsLanguages) : Retrieves the user's preferred languages for captions, ensuring that captions are displayed in the desired language when available.  

[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : Sets the user's preferred languages for captions, enabling customization of caption language preferences.  

[getPreferredClosedCaptionService](#getPreferredClosedCaptionService) : Retrieves the preferred closed captioning service configured by the user, providing additional customization options for captions.  

[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : Allows users to set their preferred closed captioning service, complementing the retrieval functionality of `getPreferredClosedCaptionService`.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getCaptions", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPreferredCaptionsLanguages"></a>
## *getPreferredCaptionsLanguages*


The `getPreferredCaptionsLanguages` API retrieves the user's preferred languages for captions. Captions are textual representations of spoken dialogue and other audio elements in video content, designed to enhance accessibility for viewers who are deaf, hard of hearing, or prefer to watch content with text-based assistance. This function allows users to access their current preferences for caption languages, ensuring that video content is displayed in a language that aligns with their needs or preferences. By using this API, users can verify or confirm the caption language settings they have previously configured.

This API is particularly useful for users who consume multilingual content or require captions in specific languages for better comprehension. It ensures that the viewing experience is tailored to the user's linguistic preferences, enhancing accessibility and personalization.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : Allows users to set their preferred languages for captions. This function complements `getPreferredCaptionsLanguages` by enabling users to update or modify their caption language preferences.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPreferredCaptionsLanguages", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPreferredClosedCaptionService"></a>
## *getPreferredClosedCaptionService*


The `getPreferredClosedCaptionService` function retrieves the user's preferred closed captioning service setting. Closed captioning services provide on-screen text descriptions of spoken dialogue, sound effects, and other audio elements in video content, making it accessible to individuals who are deaf or hard of hearing. This function allows users to check which closed captioning service is currently set as their preference, ensuring that their viewing experience aligns with their accessibility needs. The retrieved value can be used to confirm or adjust settings as needed.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPreferredClosedCaptionService"}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPrivacyMode"></a>
## *getPrivacyMode*


The `getPrivacyMode` API retrieves the current privacy mode setting of the device. Privacy mode determines how user data is handled, specifically whether it is shared or not. The privacy mode can have two values: `"SHARE"` or `"DO_NOT_SHARE"`. When set to `"SHARE"`, the device allows sharing of user data, while `"DO_NOT_SHARE"` ensures that user data remains private and is not shared. This API is useful for users who want to verify the current privacy configuration of their device to ensure it aligns with their preferences for data sharing and privacy.

### Related Functions  
[setPrivacyMode](#setPrivacyMode) : Allows users to update the privacy mode setting to either `"SHARE"` or `"DO_NOT_SHARE"`.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPrivacyMode", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPinControl"></a>
## *getPinControl*


The `getPinControl` API is used to retrieve the current status of the PIN control feature in the user settings. PIN control is a security feature that allows users to restrict access to certain content or functionalities by requiring a PIN for authentication. This API is particularly useful for users who want to verify whether PIN control is enabled or disabled on their device. By using this function, users can ensure that their content and settings are protected according to their preferences.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPinControl", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getViewingRestrictions"></a>
## *getViewingRestrictions*


The `getViewingRestrictions` API retrieves the current viewing restrictions set for the user. Viewing restrictions are rules or limitations applied to the content that can be accessed, typically based on factors such as age ratings, parental controls, or content categories. This function is particularly useful for users who want to verify the restrictions currently in place, ensuring that the content available aligns with their preferences or parental control settings. For example, parents can use this API to confirm that age-appropriate restrictions are active for their children.

This API is a read-only function, meaning it does not modify any settings but simply provides the current state of the viewing restrictions.

### Related Functions
[setViewingRestrictions](#setViewingRestrictions) : Allows users to configure or update the viewing restrictions. This function complements `getViewingRestrictions` by enabling the modification of the restrictions that can later be retrieved using this API.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getViewingRestrictions", 
    "params":{}}
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getViewingRestrictionsWindow"></a>
## *getViewingRestrictionsWindow*


The `getViewingRestrictionsWindow` API retrieves the current time window during which specific viewing restrictions are applied. This function is particularly useful for users who want to understand the active time frame for content restrictions, such as parental controls or content access limitations. By accessing this information, users can ensure that the restrictions align with their preferences or household requirements. For example, parents can verify the time periods during which certain content is restricted to ensure a safe viewing environment for children.

### Related Functions  
[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : Allows users to configure or modify the time window during which viewing restrictions are enforced.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getViewingRestrictionsWindow", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getLiveWatershed"></a>
## *getLiveWatershed*


The `getLiveWatershed` function retrieves the current status of the "Live Watershed" setting. This setting is typically used to enforce content restrictions based on time-sensitive guidelines, such as preventing access to certain types of content during specific hours (e.g., watershed hours). The function returns a boolean value indicating whether the "Live Watershed" feature is enabled (`true`) or disabled (`false`). This feature is particularly useful for households or environments where content access needs to be regulated based on time-based restrictions.

### Related Functions
[setLiveWatershed](#setLiveWatershed) : Allows you to enable or disable the "Live Watershed" setting. Use this function to modify the status of the "Live Watershed" feature.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getLiveWatershed", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getPlaybackWatershed"></a>
## *getPlaybackWatershed*


The `getPlaybackWatershed` API retrieves the current status of the playback watershed setting. The playback watershed is a feature that allows users to control access to certain types of content based on predefined time restrictions or content ratings. This setting is particularly useful for parental control or content management purposes, ensuring that specific content is only accessible during appropriate times or under specific conditions. By using this API, users can check whether the playback watershed is enabled or disabled, helping them make informed decisions about content accessibility.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPlaybackWatershed", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    function org_rdk_UserSettings_getPlaybackWatershed() {
      thunderJS.org_rdk_UserSettings_getPlaybackWatershed()
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
    <button onclick="org_rdk_UserSettings_getPlaybackWatershed()">org_rdk_UserSettings_getPlaybackWatershed</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="getBlockNotRatedContent"></a>
## *getBlockNotRatedContent*


The `getBlockNotRatedContent` API retrieves the current setting that determines whether content without a rating is blocked. This feature is particularly useful for users who want to enforce parental controls or viewing restrictions on unrated content, ensuring that only rated content is accessible. By using this API, users can check if the system is configured to block unrated content, providing an additional layer of control over the content that can be viewed.

This API is beneficial for households with children or shared viewing environments where content restrictions are necessary. It allows users to verify the status of the "block unrated content" setting, ensuring that their preferences for content control are being enforced.

### Related Functions
[setBlockNotRatedContent](#setBlockNotRatedContent) : Allows users to enable or disable the blocking of unrated content. This function is used to configure the setting that `getBlockNotRatedContent` retrieves.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getBlockNotRatedContent", 
    "params":{}}' 
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    function executeMethod() {
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
    <button onclick="executeMethod()">executeMethod</button>
    </body>
    </html>
    ```
    
=== "CPP"

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
    

<a name="getPinOnPurchase"></a>
## *getPinOnPurchase*


The `getPinOnPurchase` function retrieves the current status of the "PIN on Purchase" setting. This setting determines whether a PIN is required to authorize purchases, providing an additional layer of security to prevent unauthorized transactions. When enabled, users must enter their PIN before completing any purchase, ensuring that only authorized individuals can make purchases on the platform. This feature is particularly useful for households with multiple users, including children, as it helps prevent accidental or unauthorized purchases.

### Related Functions
[setPinOnPurchase](#setPinOnPurchase) : Allows users to enable or disable the "PIN on Purchase" setting. This function is used to configure the status that can later be retrieved using `getPinOnPurchase`.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getPinOnPurchase", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getHighContrast"></a>
## *getHighContrast*


The `getHighContrast` API is designed to retrieve the current status of the High Contrast mode setting. High Contrast mode is an accessibility feature that enhances the visibility of on-screen elements by adjusting the color scheme to provide better contrast between text, images, and backgrounds. This feature is particularly beneficial for users with visual impairments or those who find it difficult to distinguish between similar colors. By using this API, users can determine whether High Contrast mode is currently enabled or disabled on their device.

### Related Functions
[setHighContrast](#setHighContrast) : Allows users to enable or disable the High Contrast mode. This function complements `getHighContrast` by providing the ability to modify the High Contrast setting.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getHighContrast", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getVoiceGuidance"></a>
## *getVoiceGuidance*


The `getVoiceGuidance` API is designed to retrieve the current status of the voice guidance feature in a user settings environment. Voice guidance is an accessibility feature that provides audio feedback to assist users in navigating and interacting with the system. This API allows users to check whether voice guidance is enabled or disabled, helping them understand the current accessibility configuration of their device. It is particularly useful for users who rely on audio cues for system navigation due to visual impairments or other accessibility needs.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getVoiceGuidance", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getVoiceGuidanceRate", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getVoiceGuidanceHints"></a>
## *getVoiceGuidanceHints*


The `getVoiceGuidanceHints` function retrieves the current status of voice guidance hints in the system. Voice guidance hints are additional audio cues or instructions designed to assist users, particularly those with visual impairments, in navigating and interacting with the system more effectively. This function is useful for determining whether these hints are currently enabled or disabled, allowing users to understand the accessibility settings of their device.

Voice guidance hints can provide supplementary information, such as contextual tips or detailed descriptions, to enhance the overall user experience. This feature is particularly beneficial for users who rely on audio feedback for accessibility.

### Related Functions
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : Allows users to enable or disable voice guidance hints.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getVoiceGuidanceHints", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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
    

<a name="getMigrationState"></a>
## *getMigrationState*


The `getMigrationState` API is designed to help users determine whether a specific setting requires migration. Migration in this context refers to the process of updating or transitioning a setting from an older format or system to a newer one. This API takes a specific settings key as input and returns a boolean value indicating whether migration is required for that key. This functionality is particularly useful for ensuring that user settings are up-to-date and compatible with the latest system requirements, providing a seamless user experience.

By using this API, users can identify settings that need attention and take appropriate actions to ensure their system operates optimally. It is a diagnostic tool that helps maintain the integrity and compatibility of user settings.

### Related Functions
[getMigrationStates](#getMigrationStates) : Provides a comprehensive list of all settings and their respective migration states, allowing users to view the migration requirements for multiple settings at once.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getMigrationState", 
    "params":{"key":"VOICE_GUIDANCE_RATE"}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

    ```cpp
        void org_rdk_UserSettings_getMigrationState(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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
    

<a name="getMigrationStates"></a>
## *getMigrationStates*


The `getMigrationStates` API provides a comprehensive overview of the migration status for various user settings. This function is particularly useful for identifying which settings require migration to ensure compatibility with updated system configurations or new application versions. By invoking this API, users can retrieve a list of settings along with their respective migration states, indicating whether a specific setting requires migration or not. This information is essential for maintaining a seamless user experience during system upgrades or transitions, as it helps in proactively addressing potential issues related to outdated or incompatible settings.

### Related Functions  
[getMigrationState](#getMigrationState) : This function retrieves the migration state for a specific setting key, allowing users to check the migration requirement for an individual setting.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getMigrationStates", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
      thunderJS.org.rdk.UserSettings.getMigrationStates()
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
    
=== "CPP"

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
    

<a name="getContentPin"></a>
## *getContentPin*


The `getContentPin` API retrieves the current content PIN set by the user. The content PIN is a four-digit numeric code used to enforce parental controls, restrict access to certain content, or manage other security-related settings. This API is useful for users who want to verify or retrieve the existing PIN for reference or validation purposes. If no PIN is set, the API may return an empty value, indicating that no content PIN is currently configured.

This function is particularly helpful in scenarios where users need to confirm their PIN before making changes to settings, such as enabling or disabling parental controls, or when troubleshooting PIN-related issues.

### Related Functions  
[setContentPin](#setContentPin) : Allows users to set or update the content PIN. This function is complementary to `getContentPin`, as it enables the configuration of the PIN that can later be retrieved using `getContentPin`.

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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.UserSettings.getContentPin", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc
    ```
        
=== "JS"

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
    
=== "CPP"

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


The `onAudioDescriptionChanged` event is triggered whenever there is a change in the audio description setting. Audio description is a feature designed to enhance the viewing experience for visually impaired users by providing additional narration that describes visual elements of the content, such as actions, settings, and scene changes. This event notifies the user about the activation or deactivation of the audio description feature, ensuring that they are aware of the current state of this accessibility option.

This event is particularly useful for users who rely on audio descriptions to enjoy content fully. It ensures that any changes to the audio description setting are communicated promptly, allowing users to adjust their preferences or settings as needed.

### Related Functions
[setAudioDescription](#setAudioDescription) : This function allows users to enable or disable the audio description feature. When this function is called, it triggers the `onAudioDescriptionChanged` event to notify users about the updated state of the audio description setting.

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


The `onPreferredAudioLanguagesChanged` event is triggered whenever the user's preferred audio language settings are updated. This event notifies the system or application about the change, ensuring that the audio playback aligns with the user's updated preferences. For example, if a user changes their preferred audio language to "French," this event will be triggered, allowing the application to adjust the audio track accordingly. This feature is particularly useful for multilingual users who want to customize their viewing experience by selecting their preferred language for audio playback.

This event enhances user experience by ensuring that the audio language is always in sync with the user's preferences, providing a seamless and personalized entertainment experience.

### Related Functions  
[setPreferredAudioLanguages](#setPreferredAudioLanguages) : This function allows users to set their preferred audio languages. When this function is called, it updates the user's audio language preferences and triggers the `onPreferredAudioLanguagesChanged` event to notify the system of the change.

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


The `onPresentationLanguageChanged` event is triggered whenever the presentation language setting is updated. This event notifies the user about changes to the language used for on-screen menus, guides, and other interface elements. It ensures that the user interface reflects the newly selected language, enhancing accessibility and personalization for users who prefer different languages. This event is particularly useful for users in multilingual households or those who frequently switch between languages for better comprehension.

### Related Functions  
[setPresentationLanguage](#setPresentationLanguage) : This API is used to set the presentation language for the user interface. When the language is updated using this function, it triggers the `onPresentationLanguageChanged` event to notify the system and the user about the change.

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


The `onCaptionsChanged` event is triggered whenever there is a change in the captions settings of the user interface. Captions are textual representations of spoken dialogue, sound effects, and other audio elements in video content, designed to enhance accessibility for users who are deaf or hard of hearing or for those who prefer to watch content with subtitles. This event notifies the system or application when captions are enabled or disabled, allowing it to respond accordingly, such as updating the display settings or saving the user's preferences.  

This event is particularly useful for users who rely on captions for accessibility or language support, ensuring that their viewing experience is tailored to their needs. For example, enabling captions can make content more inclusive by providing visual text for audio elements, while disabling captions can declutter the screen for users who do not require them.  

### Related Functions  
[setCaptions](#setCaptions) : This API allows users to enable or disable captions manually. When the captions setting is changed using this function, it triggers the `onCaptionsChanged` event to notify the system of the update.

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


The `onPreferredCaptionsLanguagesChanged` event is triggered whenever there is a change in the user's preferred captions languages. This event notifies the system or application that the user has updated their language preferences for captions, ensuring that the content displayed aligns with their updated preferences. This feature is particularly useful for users who consume content in multiple languages or have specific accessibility needs. By listening to this event, applications can dynamically adjust the captions language to enhance the user experience without requiring manual intervention.

For example, if a user updates their preferred captions language from English to Spanish, this event will notify the system, allowing it to automatically switch the captions language for supported content. This ensures a seamless and personalized viewing experience.

### Related Functions  
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : This function allows users to set their preferred captions languages. When this function is called, it triggers the `onPreferredCaptionsLanguagesChanged` event to notify the system of the updated preferences.

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


The `onPreferredClosedCaptionServiceChanged` event is triggered whenever the preferred closed caption service is updated. Closed captions are an essential accessibility feature that provides text-based transcriptions of spoken dialogue and other audio elements in video content. This event ensures that users are notified when their preferred closed caption service is changed, allowing them to stay informed about updates to their accessibility settings. This can be particularly useful for users who rely on specific closed caption services for better comprehension or accessibility.

The event is designed to enhance the user experience by providing real-time updates about changes to the closed caption service preferences. For example, if a user switches from one closed caption service to another (e.g., from "AUTO" to a specific service), this event will notify relevant components or applications about the change, ensuring seamless integration and functionality across the system.

### Related Functions
[setPreferredClosedCaptionService](#setPreferredClosedCaptionService) : This API allows users to set their preferred closed caption service. When this function is called to update the preferred service, it triggers the `onPreferredClosedCaptionServiceChanged` event to notify the system and applications about the change.

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


The `onPrivacyModeChanged` event is triggered whenever there is a change in the privacy mode setting of the device. Privacy mode determines how user data is shared or restricted. This event notifies the system or application about the updated privacy mode, which can either be "SHARE" (allowing data sharing) or "DO_NOT_SHARE" (restricting data sharing). This ensures that the system or application can adapt its behavior based on the user's privacy preferences. For example, certain features or functionalities that rely on data sharing may be disabled when privacy mode is set to "DO_NOT_SHARE."

This event is particularly useful for users who want to maintain control over their data sharing preferences. It ensures that any changes to privacy settings are immediately reflected across the system, providing a seamless and secure user experience.

### Related Functions  
[setPrivacyMode](#setPrivacyMode) : This function is used to update the privacy mode setting. It accepts a value of either "SHARE" or "DO_NOT_SHARE" to specify the desired privacy mode. When this function is called, it triggers the `onPrivacyModeChanged` event to notify the system of the change.

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


The `onPinControlChanged` event is triggered whenever there is a change in the PIN control setting. PIN control is a feature that allows users to enable or disable the requirement of a PIN for accessing certain content or features. This event notifies the system or application about the updated state of the PIN control, ensuring that any dependent functionalities or user interfaces can adapt accordingly. For example, if PIN control is enabled, the system may prompt users to enter a PIN before accessing restricted content. Conversely, if it is disabled, such restrictions may be lifted.

This event is particularly useful for users who want to manage access to content based on their preferences, such as parental controls or privacy settings. It ensures that the system remains synchronized with the user's preferences in real-time.

### Related Functions
[setPinControl](#setPinControl) : This API is used to enable or disable the PIN control feature. When this function is called, it triggers the `onPinControlChanged` event to notify the system about the updated state of the PIN control setting.

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

This event is particularly useful for maintaining a consistent user experience by dynamically adapting the content availability based on the updated restrictions. It ensures that the system remains compliant with user-defined preferences and any applicable content guidelines.  

### Related Functions  
[setViewingRestrictions](#setViewingRestrictions) : This function is used to update the viewing restrictions settings. When this function is called, it triggers the `onViewingRestrictionsChanged` event to notify the system of the changes.  

[getViewingRestrictions](#getViewingRestrictions) : This function retrieves the current viewing restrictions settings. It can be used to verify the updated restrictions after the `onViewingRestrictionsChanged` event is triggered.  

[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : This function sets a specific time window during which the viewing restrictions are applied. Changes made using this function may also trigger the `onViewingRestrictionsChanged` event if they affect the overall restrictions.  

[getViewingRestrictionsWindow](#getViewingRestrictionsWindow) : This function retrieves the current time window for viewing restrictions. It can be used to check the active restrictions window after the `onViewingRestrictionsChanged` event is triggered.  

[setPinControl](#setPinControl) : This function enables or disables the PIN control feature, which is often used in conjunction with viewing restrictions to secure access to restricted content. Changes to PIN control settings may indirectly influence the behavior of viewing restrictions.  

[getPinControl](#getPinControl) : This function retrieves the current status of the PIN control feature. It can be used to verify the PIN control settings after changes to viewing restrictions.

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


The `onViewingRestrictionsWindowChanged` event is triggered whenever there is a change in the viewing restrictions window settings. This event is particularly useful for users who want to manage or monitor the time-based restrictions applied to content viewing. For example, parents or guardians can use this feature to ensure that certain content is only accessible during specific hours, aligning with their preferences or household rules. The event notifies the system or application about the updated viewing restrictions window, enabling real-time adjustments or updates to the user interface or content accessibility.

This event enhances user experience by providing dynamic feedback and ensuring that the viewing restrictions window settings are consistently applied across the platform. It is especially beneficial for maintaining control over content accessibility based on time-based rules, ensuring compliance with user-defined preferences.

### Related Functions  
[setViewingRestrictionsWindow](#setViewingRestrictionsWindow) : This API allows users to define or update the viewing restrictions window. By setting specific time frames during which content can be accessed, this function directly triggers the `onViewingRestrictionsWindowChanged` event to notify the system of the updated settings.

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


The `onLiveWatershedChanged` event is triggered whenever there is a change in the "Live Watershed" setting. This setting is typically used to enforce content viewing restrictions based on the time of day or other criteria, ensuring that certain content is only accessible during specific periods. For example, it may be used to restrict access to mature content during hours when children are likely to be watching. When the "Live Watershed" setting is updated, this event notifies the system or application of the change, allowing it to adjust content availability or other related behaviors accordingly.  

This event is particularly useful for users who want to maintain control over the type of content accessible in their household or environment, ensuring compliance with viewing restrictions or parental controls.  

### Related Functions  
[setLiveWatershed](#setLiveWatershed) : This function is used to update the "Live Watershed" setting. When this function is called, it triggers the `onLiveWatershedChanged` event to notify the system of the change.

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


The `onPlaybackWatershedChanged` event is triggered whenever there is a change in the playback watershed setting. The playback watershed setting is a user-defined restriction that determines the type of content that can be played based on its age rating or content classification. This event notifies the system or application that the playback watershed setting has been updated, ensuring that the appropriate content restrictions are applied in real-time. For example, if the playback watershed is enabled, content deemed inappropriate for certain age groups will be restricted from playback. This event is particularly useful for parents or guardians who want to enforce content restrictions for children or for users who wish to customize their viewing experience based on personal preferences.

### Related Functions  
[setPlaybackWatershed](#setPlaybackWatershed) : This function is used to enable or disable the playback watershed setting. When this function is called, it triggers the `onPlaybackWatershedChanged` event to notify the system of the updated setting.  

[getPlaybackWatershed](#getPlaybackWatershed) : This function retrieves the current status of the playback watershed setting, indicating whether it is enabled or disabled.

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


The `onBlockNotRatedContentChanged` event is triggered whenever there is a change in the setting that determines whether content without a rating should be blocked. This event is particularly useful for users who want to enforce viewing restrictions based on content ratings, ensuring that unrated content is either allowed or restricted based on their preferences. For example, parents or guardians can use this feature to prevent access to unrated content that may not be suitable for children. When this setting is updated, the event notifies the system and any subscribed components, allowing them to respond accordingly, such as updating the user interface or enforcing the restriction in real-time.

### Related Functions  
[setBlockNotRatedContent](#setBlockNotRatedContent) : This API is used to enable or disable the blocking of unrated content. When this setting is changed, it triggers the `onBlockNotRatedContentChanged` event to notify the system and relevant components about the update.

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


The `onPinOnPurchaseChanged` event is triggered whenever there is a change in the "Pin on Purchase" setting. This setting is used to enforce an additional layer of security by requiring a PIN to authorize purchases. It is particularly useful for households with multiple users or children, ensuring that unauthorized purchases are prevented. When this event is triggered, it notifies the system and any subscribed components about the updated status of the "Pin on Purchase" feature, allowing them to respond accordingly, such as updating the user interface or enforcing the new setting.

This event is beneficial for users who want to maintain control over purchases made on their devices, providing peace of mind and preventing accidental or unauthorized transactions. It ensures that the PIN requirement is consistently applied whenever the setting is modified.

### Related Functions  
[setPinOnPurchase](#setPinOnPurchase) : This API is used to enable or disable the "Pin on Purchase" feature. When this function is called, it triggers the `onPinOnPurchaseChanged` event to notify the system and other components about the change in the setting.

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


The `onHighContrastChanged` event is triggered whenever the high contrast mode setting is updated. High contrast mode is an accessibility feature designed to improve the visibility of text and interface elements for users with visual impairments. When this event occurs, it indicates that the high contrast mode has been either enabled or disabled. This feature is particularly useful for users who require enhanced visual clarity to navigate and interact with the user interface effectively.  

This event ensures that any changes to the high contrast setting are communicated to the relevant components or applications, allowing them to adjust their visual presentation accordingly. For example, when high contrast mode is enabled, the interface may switch to a color scheme with higher contrast between text and background, making it easier to read and interact with.  

### Related Functions  
[setHighContrast](#setHighContrast) : This API is used to enable or disable the high contrast mode. When the high contrast setting is updated using this function, it triggers the `onHighContrastChanged` event to notify other components or applications about the change.

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


The `onVoiceGuidanceChanged` event is triggered whenever the voice guidance feature is enabled or disabled. Voice guidance is an accessibility feature designed to assist users, particularly those with visual impairments, by providing spoken feedback about on-screen content, navigation, and settings. This event notifies the system or application when the state of voice guidance changes, allowing it to adapt accordingly. For example, enabling voice guidance might prompt the system to provide audio cues for menu navigation, while disabling it would stop such cues. This event ensures that the user experience remains seamless and accessible, reflecting the user's preferences in real-time.

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


The `onVoiceGuidanceRateChanged` event is triggered whenever the rate of voice guidance is updated. Voice guidance is a feature designed to assist users, particularly those with visual impairments, by providing spoken feedback for navigating menus, settings, and other interface elements. The rate of voice guidance determines the speed at which the spoken feedback is delivered, allowing users to customize it to their preference for better accessibility and usability. This event ensures that any changes made to the voice guidance rate are communicated effectively, enabling the system or application to respond accordingly, such as updating the user interface or saving the new rate setting.

### Related Functions  
[setVoiceGuidanceRate](#setVoiceGuidanceRate) : This function allows users to set the desired rate for voice guidance. It triggers the `onVoiceGuidanceRateChanged` event when the rate is successfully updated, ensuring the system reflects the new setting.

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


The `onVoiceGuidanceHintsChanged` event is triggered whenever there is a change in the state of voice guidance hints. Voice guidance hints are additional auditory cues provided to assist users in navigating and interacting with the system, particularly beneficial for users with visual impairments. These hints can include spoken instructions or contextual information that enhance the accessibility of the user interface. For example, enabling voice guidance hints might provide more detailed descriptions of menu options or actions, making the system easier to use for individuals who rely on auditory feedback. This event ensures that the system or application can respond dynamically to changes in the voice guidance hints setting, allowing for real-time updates to the user experience.

### Related Functions  
[setVoiceGuidanceHints](#setVoiceGuidanceHints) : This API is used to enable or disable voice guidance hints. By calling this function, users can customize their accessibility preferences, and any changes made will trigger the `onVoiceGuidanceHintsChanged` event to notify the system of the updated state.

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


The `onContentPinChanged` event is triggered whenever there is a change in the content PIN settings. This event notifies the user about updates to the PIN used for controlling access to specific content, ensuring that the user is aware of any modifications to the security settings. The content PIN is typically used to restrict access to certain types of content based on parental controls or viewing restrictions. This event is particularly useful for users who want to monitor or confirm changes to their PIN settings, ensuring that their preferences for content access remain secure and consistent.

### Related Functions  
[setContentPin](#setContentPin) : This API allows the user to set or update the content PIN. It validates the PIN format (typically a 4-digit numeric code) and ensures that the new PIN is applied correctly. Changes made using this function trigger the `onContentPinChanged` event.

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
