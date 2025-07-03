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


The **UserSettings** service in the RDK framework is a plugin designed to manage and inspect user preferences related to audio, captions, and language settings. It provides interfaces for configuring and retrieving settings such as preferred audio languages, audio descriptions, captions, and presentation languages. This service ensures a streamlined way to handle user-specific configurations for media playback and accessibility features.

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
| [setAudioDescription](#method.setAudioDescription) | Sets audio description | [onAudioDescriptionChanged](#event.onAudioDescriptionChanged) |
| [setPreferredAudioLanguages](#method.setPreferredAudioLanguages) | Set preferred audio languages | [onPreferredAudioLanguagesChanged](#event.onPreferredAudioLanguagesChanged) |
| [setPresentationLanguage](#method.setPresentationLanguage) | set presentation language | [onPresentationLanguageChanged](#event.onPresentationLanguageChanged) |
| [setCaptions](#method.setCaptions) | set captions functionality | [onCaptionsChanged](#event.onCaptionsChanged) |
| [setPreferredCaptionsLanguages](#method.setPreferredCaptionsLanguages) | Set preferred captions languages | [onPreferredCaptionsLanguagesChanged](#event.onPreferredCaptionsLanguagesChanged) |
| [setPreferredClosedCaptionService](#method.setPreferredClosedCaptionService) | Set preferred caption service | [onPreferredClosedCaptionServiceChanged](#event.onPreferredClosedCaptionServiceChanged) |
| [setPrivacyMode](#method.setPrivacyMode) | manage privacy mode | [onPrivacyModeChanged](#event.onPrivacyModeChanged) |
| [setPinControl](#method.setPinControl) | set pin control | [onPinControlChanged](#event.onPinControlChanged) |
| [setViewingRestrictions](#method.setViewingRestrictions) | set viewing restrictions | [onViewingRestrictionsChanged](#event.onViewingRestrictionsChanged) |
| [setViewingRestrictionsWindow](#method.setViewingRestrictionsWindow) | set viewing restrictions window | [onViewingRestrictionsWindowChanged](#event.onViewingRestrictionsWindowChanged) |
| [setLiveWatershed](#method.setLiveWatershed) | set live watershed | [onLiveWatershedChanged](#event.onLiveWatershedChanged) |
| [setPlaybackWatershed](#method.setPlaybackWatershed) | Set playback watershed | [onPlaybackWatershedChanged](#event.onPlaybackWatershedChanged) |
| [setBlockNotRatedContent](#method.setBlockNotRatedContent) | Block unrated content | [onBlockNotRatedContentChanged](#event.onBlockNotRatedContentChanged) |
| [setPinOnPurchase](#method.setPinOnPurchase) | Set PIN on purchase | [onPinOnPurchaseChanged](#event.onPinOnPurchaseChanged) |
| [setHighContrast](#method.setHighContrast) | Set high contrast mode | [onHighContrastChanged](#event.onHighContrastChanged) |
| [setVoiceGuidance](#method.setVoiceGuidance) | set voice guidance | [onVoiceGuidanceChanged](#event.onVoiceGuidanceChanged) |
| [setVoiceGuidanceRate](#method.setVoiceGuidanceRate) | Sets voice guidance rate | [onVoiceGuidanceRateChanged](#event.onVoiceGuidanceRateChanged) |
| [setVoiceGuidanceHints](#method.setVoiceGuidanceHints) | Set voice guidance hints | [onVoiceGuidanceHintsChanged](#event.onVoiceGuidanceHintsChanged) |
| [setContentPin](#method.setContentPin) | set content pin | [onContentPinChanged](#event.onContentPinChanged) |
| [getAudioDescription](#method.getAudioDescription) | fetch audio description | NA |
| [getPreferredAudioLanguages](#method.getPreferredAudioLanguages) | fetch preferred audio languages | NA |
| [getPresentationLanguage](#method.getPresentationLanguage) | get presentation language | NA |
| [getCaptions](#method.getCaptions) | fetch video captions | NA |
| [getPreferredCaptionsLanguages](#method.getPreferredCaptionsLanguages) | fetch preferred captions languages | NA |
| [getPreferredClosedCaptionService](#method.getPreferredClosedCaptionService) | preferred caption service | NA |
| [getPrivacyMode](#method.getPrivacyMode) | Get privacy mode status | NA |
| [getPinControl](#method.getPinControl) | get pin control details | NA |
| [getViewingRestrictions](#method.getViewingRestrictions) | viewing restrictions info | NA |
| [getViewingRestrictionsWindow](#method.getViewingRestrictionsWindow) | Get viewing restrictions window | NA |
| [getLiveWatershed](#method.getLiveWatershed) | Get live watershed data | NA |
| [getPlaybackWatershed](#method.getPlaybackWatershed) | playback watershed info | NA |
| [getBlockNotRatedContent](#method.getBlockNotRatedContent) | Get unrated content | NA |
| [getPinOnPurchase](#method.getPinOnPurchase) | Get PIN on purchase | NA |
| [getHighContrast](#method.getHighContrast) | Get high contrast mode | NA |
| [getVoiceGuidance](#method.getVoiceGuidance) | fetch voice guidance | NA |
| [getVoiceGuidanceRate](#method.getVoiceGuidanceRate) | fetch voice guidance rate | NA |
| [getVoiceGuidanceHints](#method.getVoiceGuidanceHints) | fetch voice guidance hints | NA |
| [getMigrationState](#method.getMigrationState) | get migration state | NA |
| [getMigrationStates](#method.getMigrationStates) | retrieve migration states | NA |
| [getContentPin](#method.getContentPin) | get content pin details | NA |


<a name="setAudioDescription"></a>
## *setAudioDescription*


The `setAudioDescription` API allows users to enable or disable the audio description feature on their device. Audio description is an accessibility feature that provides additional audio narration to describe visual elements of a video, such as actions, settings, and scene changes, making content more accessible to visually impaired users. By using this API, users can customize their viewing experience based on their accessibility needs.

This API modifies the user settings to reflect the desired state of the audio description feature. Once enabled, the system ensures that audio descriptions are provided for supported content. Conversely, disabling this feature stops the additional narration.

### Related Functions
[getAudioDescription](#getAudioDescription) : Retrieves the current state of the audio description feature (enabled or disabled).

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setAudioDescription` API updates the user settings by modifying the value associated with the `USERSETTINGS_AUDIO_DESCRIPTION_KEY`. The function converts the boolean input (`true` or `false`) into a string representation ("true" or "false") before storing it.

Error codes:
- `Core::ERROR_NONE`: Indicates successful execution.
- `Core::ERROR_GENERAL`: Indicates a general failure during the operation.

The API logs the operation status and the input value for debugging purposes.
</details>

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

<a name="setPreferredAudioLanguages"></a>
## *setPreferredAudioLanguages*


The `setPreferredAudioLanguages` API allows users to specify their preferred audio languages for content playback. This setting ensures that the audio track in the selected language is prioritized whenever available, enhancing the user experience by aligning audio preferences with the user's linguistic needs. For example, if a user prefers "English" and "Spanish," the system will attempt to play content in these languages in the specified order of preference.

This API is particularly useful for multilingual users or households where different members have distinct language preferences. By setting the preferred audio languages, users can avoid manually selecting the audio track for each piece of content, streamlining the playback experience.

### Related Functions
[GetPreferredAudioLanguages](#GetPreferredAudioLanguages) : Retrieves the currently set preferred audio languages, allowing users to verify or review their preferences.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPreferredAudioLanguages` API calls the `SetUserSettingsValue` function with the key `USERSETTINGS_PREFERRED_AUDIO_LANGUAGES_KEY` to store the preferred audio languages in the user settings database. If the operation is successful, it returns `Core::ERROR_NONE`. Otherwise, it returns `Core::ERROR_GENERAL` to indicate a failure.

Additionally, the API triggers the `PREFERRED_AUDIO_CHANGED` event to notify other components or listeners about the change in preferred audio languages.
</details>

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

<a name="setPresentationLanguage"></a>
## *setPresentationLanguage*


The `setPresentationLanguage` API is used to configure the preferred presentation language for a user. This function allows users to set their desired language for the interface or content presentation, ensuring a personalized and accessible experience. By invoking this API, the system updates the user's settings to reflect the specified language preference, which can influence various aspects of the user interface, captions, or other language-dependent features. This API is particularly useful for multilingual environments where users may want to interact with the system in their native or preferred language.

### Related Functions
[GetPresentationLanguage](#GetPresentationLanguage) : Retrieves the currently set presentation language for the user. This function complements `setPresentationLanguage` by allowing users to verify or retrieve the language setting they have configured.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPresentationLanguage` API calls the `SetUserSettingsValue` function with the key `USERSETTINGS_PRESENTATION_LANGUAGE_KEY` to store the specified language in the user settings database. If the operation is successful, the status returned is `Core::ERROR_NONE`. Otherwise, it returns `Core::ERROR_GENERAL` in case of failure. Additionally, the API triggers the `PRESENTATION_LANGUAGE_CHANGED` event to notify other components or listeners about the change in presentation language.
</details>

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

<a name="setCaptions"></a>
## *setCaptions*


The `setCaptions` API is designed to enable or disable captions for the user. Captions are textual representations of spoken dialogue, sound effects, and other audio elements in video content, making it accessible for individuals who are deaf, hard of hearing, or prefer to watch content with text-based assistance. This API allows users to control whether captions are displayed during playback, providing a customizable viewing experience.

When captions are enabled, the system ensures that the appropriate settings are updated to reflect the user's preference. Conversely, disabling captions will turn off the display of text-based assistance during playback. This API is particularly useful for accessibility settings and user preferences in multimedia applications.

### Related Functions
[GetCaptions](#GetCaptions) : Retrieves the current status of captions (enabled or disabled), allowing users to check the existing setting.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setCaptions` API updates the user settings by calling the `SetUserSettingsValue` function with the key `USERSETTINGS_CAPTIONS_KEY`. The value is set to `"true"` if captions are enabled and `"false"` if disabled. The function also triggers the `CAPTIONS_CHANGED` event to notify other components or listeners about the change in captions status.

Error codes such as `Core::ERROR_GENERAL` may be returned if the operation fails due to unexpected issues.
</details>

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

<a name="setPreferredCaptionsLanguages"></a>
## *setPreferredCaptionsLanguages*


The `setPreferredCaptionsLanguages` API allows users to specify their preferred languages for captions. This function is particularly useful for enhancing accessibility and personalization, enabling users to select the languages in which they would like captions to appear during content playback. By setting a preferred language, the system ensures that captions are displayed in the user's desired language whenever available, improving the overall viewing experience.

This API is part of the user settings management system and interacts with the underlying storage to save the user's preferences persistently. Once the preferred captions language is set, it remains in effect until explicitly changed by the user.

### Related Functions
[GetPreferredCaptionsLanguages](#GetPreferredCaptionsLanguages) : Retrieves the currently set preferred captions languages. This function complements `setPreferredCaptionsLanguages` by allowing users to verify or retrieve their current preference.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPreferredCaptionsLanguages` function updates the user settings storage with the specified language preference using the key `USERSETTINGS_PREFERRED_CAPTIONS_LANGUAGES_KEY`. It logs the operation for debugging purposes and dispatches an event (`PREFERRED_CAPTIONS_LANGUAGE_CHANGED`) to notify other components of the change. The function returns a status code indicating the success or failure of the operation. Common error codes include `Core::ERROR_NONE` for success and `Core::ERROR_GENERAL` for a generic failure.
</details>

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

<a name="setPreferredClosedCaptionService"></a>
## *setPreferredClosedCaptionService*


The `setPreferredClosedCaptionService` API allows users to specify their preferred closed captioning service. Closed captions are essential for accessibility, providing on-screen text for spoken dialogue and other audio cues in video content. This function enables users to customize their viewing experience by selecting a closed captioning service that best suits their needs, such as a specific language or style of captions. Once set, the system will use the specified service as the default for closed captions.

### Related Functions
[getPreferredClosedCaptionService](#getPreferredClosedCaptionService) : Retrieves the currently set preferred closed captioning service, allowing users to verify or review their selection.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, this function updates the user settings by storing the preferred closed captioning service under the key `USERSETTINGS_PREFERRED_CLOSED_CAPTIONS_SERVICE_KEY`. If the operation is successful, it returns a success status; otherwise, it returns an error code such as `Core::ERROR_GENERAL`. The function also triggers an event (`PREFERRED_CLOSED_CAPTIONS_SERVICE_CHANGED`) to notify other components of the change.
</details>

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

<a name="setPrivacyMode"></a>
## *setPrivacyMode*


The `setPrivacyMode` function allows users to configure the privacy settings of their device by specifying whether their data should be shared or not. This function accepts a privacy mode value, which can either be "SHARE" or "DO_NOT_SHARE". By setting this value, users can control how their personal data is handled, ensuring compliance with their privacy preferences. If an invalid value is provided, the function logs an error and retains the default privacy mode.

This function is particularly useful for users who are concerned about data privacy and want to ensure that their preferences are respected. It updates the privacy mode setting in the device's storage and triggers an event to notify other components of the change.

### Related Functions
[GetPrivacyMode](#GetPrivacyMode) : Retrieves the current privacy mode setting, allowing users to verify their configured preference.

<details>
<summary><kbd>Additional information</kbd></summary>
- Internally, the function interacts with a remote storage object (`_remotStoreObject`) to persist the privacy mode setting under the `USERSETTINGS_PRIVACY_MODE_KEY` namespace.
- The function validates the input value to ensure it is either "SHARE" or "DO_NOT_SHARE". If the value is invalid, it logs an error and does not update the setting.
- If the new privacy mode differs from the existing one, the function updates the value in the storage and unlocks the administrative lock (`_adminLock`) after the operation.
- Error codes:
  - `Core::ERROR_GENERAL`: Returned when an invalid privacy mode value is provided or if the operation fails.
  - `Core::ERROR_NONE`: Indicates successful execution.
</details>

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

<a name="setPinControl"></a>
## *setPinControl*


The `setPinControl` API is used to enable or disable the PIN control feature in the user settings. This feature is typically used to enforce parental controls or restrict access to certain content based on user preferences. By setting the PIN control to `true`, the system ensures that a PIN is required for accessing restricted content or performing specific actions. Conversely, setting it to `false` disables this requirement.

This API is particularly useful for users who want to manage content access for children or other users of the system. It provides a straightforward way to toggle the PIN control feature on or off, ensuring a secure and customizable user experience.

### Related Functions
[getPinControl](#getPinControl) : Retrieves the current status of the PIN control feature (enabled or disabled).

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPinControl` function calls `SetUserSettingsValue` to update the `USERSETTINGS_PIN_CONTROL_KEY` with the value `"true"` or `"false"`, depending on the input. If the operation is successful, it returns `Core::ERROR_NONE`. Otherwise, it returns `Core::ERROR_GENERAL` in case of a failure.

Error Codes:
- `Core::ERROR_NONE`: Indicates that the operation was successful.
- `Core::ERROR_GENERAL`: Indicates a general failure during the operation.

The function logs the input value for debugging purposes using `LOGINFO`.
</details>

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

<a name="setViewingRestrictions"></a>
## *setViewingRestrictions*


The `setViewingRestrictions` API is designed to configure and enforce specific viewing restrictions for a user. This function allows the system to store and apply restrictions based on the provided input, ensuring that content access aligns with user preferences or regulatory requirements. The restrictions could include parental controls, content ratings, or other criteria that limit what content can be viewed. This API is particularly useful for managing content accessibility in shared environments, such as households with children, or in compliance with content guidelines.

### Related Functions
[GetViewingRestrictions](#GetViewingRestrictions) : Retrieves the current viewing restrictions that have been set for the user. This function complements `setViewingRestrictions` by allowing users to verify or review the restrictions currently in place.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setViewingRestrictions` function calls `SetUserSettingsValue` with the key `USERSETTINGS_VIEWING_RESTRICTIONS_KEY` to store the provided restrictions. If the operation is successful, it returns a status code indicating success; otherwise, it returns an error code such as `Core::ERROR_GENERAL`. The function also logs the input value for debugging purposes. Additionally, any changes to the viewing restrictions trigger the `OnViewingRestrictionsChanged` event, which notifies other components of the update.
</details>

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

<a name="setViewingRestrictionsWindow"></a>
## *setViewingRestrictionsWindow*


The `setViewingRestrictionsWindow` API is used to configure the time window during which specific viewing restrictions are applied. This function allows users to define a specific period (e.g., hours or days) during which content restrictions, such as parental controls or content ratings, are enforced. It is particularly useful for households with children or shared viewing environments where content access needs to be regulated during certain times.

This API ensures that the defined restrictions are stored persistently, so they remain effective even after a system restart or user session change. The function updates the user settings with the provided time window and triggers relevant notifications to inform other components or listeners about the change.

### Related Functions
[GetViewingRestrictionsWindow](#GetViewingRestrictionsWindow) : Retrieves the currently configured viewing restrictions window. This function complements `setViewingRestrictionsWindow` by allowing users to verify or review the existing settings.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setViewingRestrictionsWindow` function calls `SetUserSettingsValue` with the key `USERSETTINGS_VIEWING_RESTRICTIONS_WINDOW_KEY` to store the provided time window in the user settings database. If the operation is successful, it returns `Core::ERROR_NONE`. Otherwise, it returns an error code such as `Core::ERROR_GENERAL` to indicate a failure.

Additionally, the function dispatches the `VIEWING_RESTRICTIONS_WINDOW_CHANGED` event to notify all registered listeners about the update. This ensures that any dependent components or services are aware of the change and can adjust their behavior accordingly.
</details>

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

<a name="setLiveWatershed"></a>
## *setLiveWatershed*


The `setLiveWatershed` API is used to enable or disable the live watershed setting for a user. The live watershed setting typically determines whether certain content restrictions, such as age-based or time-based viewing limitations, are applied to live content. By invoking this function, users can control whether these restrictions are enforced during live broadcasts. This setting is particularly useful for parental controls or content moderation purposes.

### Related Functions
[GetLiveWatershed](#GetLiveWatershed) : Retrieves the current status of the live watershed setting, indicating whether it is enabled or disabled.

<details>
<summary><kbd>Additional information</kbd></summary>
- Internally, the function updates the `USERSETTINGS_LIVE_WATERSHED_KEY` value in the user settings database to either "true" or "false" based on the input.
- Logs the updated status of the live watershed setting for debugging purposes.
- Returns an error code (`Core::hresult`) to indicate the success or failure of the operation. Common error codes include `Core::ERROR_NONE` for success and `Core::ERROR_GENERAL` for a generic failure.
- Triggers the `OnLiveWatershedChanged` event to notify listeners about the change in the live watershed setting.
</details>

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

<a name="setPlaybackWatershed"></a>
## *setPlaybackWatershed*


The `setPlaybackWatershed` API is used to configure the "Playback Watershed" setting for a user. This setting determines whether certain content, based on its classification or rating, is restricted during playback. By enabling or disabling this setting, users can control access to specific types of content, ensuring that playback adheres to their preferences or parental control requirements. This API is particularly useful for managing content restrictions in environments where content sensitivity is a concern.

When the `playbackWatershed` parameter is set to `true`, the restriction is enabled, and content that falls under the defined watershed criteria will be blocked during playback. Conversely, setting it to `false` disables the restriction, allowing unrestricted playback of all content.

### Related Functions
[GetPlaybackWatershed](#GetPlaybackWatershed) : Retrieves the current status of the "Playback Watershed" setting, indicating whether the restriction is enabled or disabled.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPlaybackWatershed` API updates the user settings by storing the value (`true` or `false`) in the `USERSETTINGS_PLAYBACK_WATERSHED_KEY`. It logs the change for debugging purposes and returns a status code indicating the success or failure of the operation. Possible error codes include `Core::ERROR_NONE` for success and `Core::ERROR_GENERAL` for a generic failure. Additionally, the API triggers the `PLAYBACK_WATERSHED_CHANGED` event to notify other components of the change.
</details>

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

<a name="setBlockNotRatedContent"></a>
## *setBlockNotRatedContent*


The `setBlockNotRatedContent` API is used to configure whether content that is not rated should be blocked or allowed. This setting is particularly useful for parental control features, where users may want to restrict access to unrated content to ensure that only age-appropriate material is accessible. By enabling or disabling this setting, users can customize their content viewing preferences based on their household's requirements.

When this API is called, it updates the internal user settings to reflect the desired state for blocking unrated content. The change is then persisted, ensuring that the setting remains consistent across sessions. Additionally, any relevant notifications or events are triggered to inform other components or systems about the change in this setting.

### Related Functions
[GetBlockNotRatedContent](#GetBlockNotRatedContent) : Retrieves the current state of the "block unrated content" setting, allowing users to check whether unrated content is currently being blocked.

<details>
<summary><kbd>Additional information</kbd></summary>
- Internally, the function calls `SetUserSettingsValue` with the key `USERSETTINGS_BLOCK_NOT_RATED_CONTENT_KEY` and a value of `"true"` or `"false"` based on the input parameter.
- If the operation is successful, the function returns `Core::ERROR_NONE`. Otherwise, it returns `Core::ERROR_GENERAL` to indicate a failure.
- The function triggers the `BLOCK_NOT_RATED_CONTENT_CHANGED` event to notify other components about the change in the setting.
</details>

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

<a name="setPinOnPurchase"></a>
## *setPinOnPurchase*


The `setPinOnPurchase` API allows users to enable or disable the requirement of a PIN when making purchases. This feature is designed to enhance security and prevent unauthorized transactions, especially in shared environments or when children have access to the device. By enabling this setting, users can ensure that a PIN must be entered before completing any purchase, adding an extra layer of protection.

This API is particularly useful for parents or individuals who want to control spending on their devices. When the setting is turned off, purchases can be made without requiring a PIN, which may be convenient in secure, single-user environments.

### Related Functions
[getPinOnPurchase](#getPinOnPurchase) : Retrieves the current status of the "PIN on Purchase" setting, indicating whether it is enabled or disabled.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setPinOnPurchase` function updates the user settings by calling `SetUserSettingsValue` with the key `USERSETTINGS_PIN_ON_PURCHASE_KEY`. The value is stored as a string ("true" or "false") to represent the enabled or disabled state.

Error codes:
- `Core::ERROR_NONE`: Indicates the operation was successful.
- `Core::ERROR_GENERAL`: Indicates a general failure during the operation.

The function logs the status of the operation for debugging purposes using `LOGINFO`. It also triggers the `OnPinOnPurchaseChanged` event to notify other components of the change in the setting.
</details>

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

<a name="setHighContrast"></a>
## *setHighContrast*


The `setHighContrast` API is designed to enable or disable the high contrast mode for the user interface. High contrast mode is a feature that enhances the visual accessibility of the system by increasing the contrast between text, images, and the background. This is particularly useful for users with visual impairments or those who prefer a more distinct visual separation for better readability. By calling this API, users can toggle the high contrast mode on or off based on their preferences.

### Related Functions
[getHighContrast](#getHighContrast) : This function retrieves the current status of the high contrast mode (enabled or disabled).

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setHighContrast` function updates the user settings by storing the high contrast preference (`true` for enabled, `false` for disabled) in the system's settings database. It uses the `SetUserSettingsValue` function to persist the value under the key `USERSETTINGS_HIGH_CONTRAST_KEY`. The function returns a status code indicating the success or failure of the operation. Common status codes include `Core::ERROR_NONE` for success and `Core::ERROR_GENERAL` for a generic failure.

Additionally, when the high contrast setting is changed, an event (`HIGH_CONTRAST_CHANGED`) is dispatched to notify other components or listeners about the update.
</details>

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

<a name="setVoiceGuidance"></a>
## *setVoiceGuidance*


The `setVoiceGuidance` API is used to enable or disable voice guidance functionality within the system. Voice guidance is a feature designed to assist users by providing audio cues or spoken instructions, enhancing accessibility and usability for individuals who may prefer or require auditory feedback. By invoking this API, users can toggle the voice guidance feature on or off based on their preferences or needs. This API is particularly useful for accessibility settings, ensuring that the system can cater to a diverse range of users, including those with visual impairments.

### Related Functions
[getVoiceGuidance](#getVoiceGuidance) : Retrieves the current status of the voice guidance feature (enabled or disabled).

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setVoiceGuidance` API interacts with the user settings storage by updating the `USERSETTINGS_VOICE_GUIDANCE_KEY` with a value of `"true"` or `"false"` depending on whether the feature is being enabled or disabled. The function logs the operation for debugging purposes and returns a status code indicating the success or failure of the operation. Common error codes include `Core::ERROR_GENERAL` for general errors and `Core::ERROR_NONE` for successful execution.
</details>

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

<a name="setVoiceGuidanceRate"></a>
## *setVoiceGuidanceRate*


The `setVoiceGuidanceRate` API is used to configure the speed or rate at which voice guidance is delivered to the user. This function allows users to customize the pace of voice instructions, ensuring that the guidance is delivered at a speed that suits their preferences or needs. For example, users who prefer slower instructions for better comprehension or faster instructions for efficiency can adjust the rate accordingly. The API validates the input rate against predefined minimum and maximum limits to ensure the value is within acceptable bounds. If the provided rate is valid, it updates the user settings with the new voice guidance rate.

### Related Functions
[getVoiceGuidanceRate](#getVoiceGuidanceRate) : Retrieves the current voice guidance rate set by the user. This function complements `setVoiceGuidanceRate` by allowing users to check the existing rate before making adjustments.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setVoiceGuidanceRate` function calls `SetUserSettingsValue` to store the new rate in the user settings database. If the provided rate is outside the acceptable range, the function returns an error code `Core::ERROR_INVALID_PARAMETER`. Successful updates return `Core::ERROR_NONE`. The function logs the rate value for debugging purposes and ensures the rate is within the predefined limits (`minVGR` and `maxVGR`).
</details>

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

<a name="setVoiceGuidanceHints"></a>
## *setVoiceGuidanceHints*


The `setVoiceGuidanceHints` API is used to enable or disable voice guidance hints in the system. Voice guidance hints are auditory cues or prompts that assist users in navigating or interacting with the system, particularly useful for accessibility purposes. By calling this function, users can customize their experience by turning these hints on or off based on their preferences. This API is particularly beneficial for users who rely on voice guidance for better accessibility or enhanced user experience.

### Related Functions
[GetVoiceGuidanceHints](#GetVoiceGuidanceHints) : Retrieves the current state of voice guidance hints (enabled or disabled).

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setVoiceGuidanceHints` function updates the user settings by modifying the value associated with the key `USERSETTINGS_VOICE_GUIDANCE_HINTS_KEY`. It converts the boolean input (`true` or `false`) into a string representation ("true" or "false") before storing it. The function returns a status code indicating the success or failure of the operation. Common error codes include `Core::ERROR_NONE` for successful execution and `Core::ERROR_GENERAL` for any general failure.

Additionally, when the state of voice guidance hints is changed, the system triggers the `OnVoiceGuidanceHintsChanged` event to notify other components or listeners about the update. This ensures that the change is propagated throughout the system for consistent behavior.
</details>

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

<a name="setContentPin"></a>
## *setContentPin*


The `setContentPin` API is used to set or update the content PIN for user settings. A content PIN is typically a 4-digit numeric code that can be used to restrict access to certain content or features based on user preferences. This API ensures that the PIN provided is valid (a 4-digit numeric value) or allows clearing the PIN by passing an empty value. If the PIN is invalid, the API returns an error, ensuring that only valid PINs are stored.

This function is particularly useful for parental controls or content access restrictions, allowing users to manage their settings securely. It validates the PIN format before storing it, ensuring compliance with expected standards.

### Related Functions
[GetContentPin](#GetContentPin) : Retrieves the currently stored content PIN, allowing users to view or verify the PIN they have set.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `setContentPin` function uses a regular expression (`std::regex`) to validate the PIN format, ensuring it is a 4-digit numeric value. If the PIN is valid or empty, it calls the `SetUserSettingsValue` function to store the PIN in the user settings database. If the PIN is invalid, the function returns the error code `Core::ERROR_INVALID_PARAMETER`.

Error codes:
- `Core::ERROR_GENERAL`: Indicates a general failure in the operation.
- `Core::ERROR_INVALID_PARAMETER`: Indicates that the provided PIN does not meet the required format.

Additionally, the function logs the PIN value for debugging purposes and dispatches an event (`CONTENT_PIN_CHANGED`) when the PIN is successfully updated.
</details>

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

<a name="getAudioDescription"></a>
## *getAudioDescription*


The `getAudioDescription` API is designed to retrieve the current status of the audio description feature. Audio description is an accessibility feature that provides additional narration to describe visual elements in a video, such as actions, settings, and characters, for individuals who are visually impaired. This API allows users to check whether the audio description feature is enabled or disabled, helping them ensure that the accessibility settings align with their preferences or requirements.

This function is particularly useful for users who rely on audio descriptions to enhance their viewing experience. By using this API, users can confirm the status of the feature without navigating through multiple settings menus, making it a convenient tool for accessibility management.

### Related Functions
[SetAudioDescription](#SetAudioDescription) : Allows users to enable or disable the audio description feature. This function complements `getAudioDescription` by providing the ability to modify the audio description setting.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getAudioDescription` API retrieves the value of the `USERSETTINGS_AUDIO_DESCRIPTION_KEY` from the user settings database. If the value is `"true"`, the function sets the `enabled` parameter to `true`, indicating that the audio description feature is active. Conversely, if the value is not `"true"`, the `enabled` parameter is set to `false`.

Error codes:
- `Core::ERROR_NONE`: Indicates successful retrieval of the audio description status.
- `Core::ERROR_GENERAL`: Indicates a failure in retrieving the status due to an internal error.

This function does not modify any settings; it is strictly a read operation.
</details>

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

<a name="getPreferredAudioLanguages"></a>
## *getPreferredAudioLanguages*


The `getPreferredAudioLanguages` API retrieves the user's preferred audio language settings. This function is particularly useful for applications or services that provide multilingual audio options, such as streaming platforms or media players. By calling this API, the application can determine the user's preferred audio language(s) and adjust the audio track accordingly, ensuring a personalized and seamless user experience.

This API fetches the value stored under the `USERSETTINGS_PREFERRED_AUDIO_LANGUAGES_KEY` in the user settings database. If the preferred audio languages have been set previously, the function returns the corresponding value. If not, it may return an error or a default value, depending on the implementation.

### Related Functions
[SetPreferredAudioLanguages](#SetPreferredAudioLanguages) : Allows the user to set their preferred audio language(s). This function complements `getPreferredAudioLanguages` by enabling the user to define their preferences, which can later be retrieved using this API.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getPreferredAudioLanguages` API calls the `GetUserSettingsValue` function with the key `USERSETTINGS_PREFERRED_AUDIO_LANGUAGES_KEY` to fetch the stored value. If the operation is successful, it returns the preferred audio languages as a string. In case of failure, it returns an error code such as `Core::ERROR_GENERAL`.

Error codes:
- `Core::ERROR_NONE`: The operation was successful, and the preferred audio languages were retrieved.
- `Core::ERROR_GENERAL`: A general error occurred, and the preferred audio languages could not be retrieved.

This API is part of the broader user settings management system, which includes other related settings such as captions, presentation language, and privacy mode.
</details>

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

<a name="getPresentationLanguage"></a>
## *getPresentationLanguage*


The `getPresentationLanguage` API is used to retrieve the current presentation language setting for the user. This setting determines the language in which the user interface, captions, or other presentation elements are displayed. It is particularly useful for applications that support multilingual environments, allowing users to view content in their preferred language. The API ensures that the language preference is fetched accurately from the user settings, enabling seamless customization of the user experience.

### Related Functions
[SetPresentationLanguage](#SetPresentationLanguage) : Allows the user to set or update the preferred presentation language. This function complements `getPresentationLanguage` by enabling the modification of the language setting.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getPresentationLanguage` function retrieves the value of the `USERSETTINGS_PRESENTATION_LANGUAGE_KEY` from the user settings storage. If the operation is successful, the preferred language is returned; otherwise, an error code such as `Core::ERROR_GENERAL` is returned to indicate a failure.
</details>

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

<a name="getCaptions"></a>
## *getCaptions*


The `getCaptions` API is designed to retrieve the current status of captions functionality within the user settings. Captions are textual representations of spoken dialogue and other audio cues, often used to enhance accessibility for individuals who are deaf or hard of hearing or for users who prefer subtitles. This API provides a way to check whether captions are enabled or disabled in the system settings. It is particularly useful for applications or services that need to adapt their behavior based on the user's accessibility preferences.

### Related Functions
[SetCaptions](#SetCaptions) : Allows you to enable or disable captions in the user settings. This function complements `getCaptions` by providing the ability to modify the captions status.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getCaptions` API calls the `GetUserSettingsValue` function with the key `USERSETTINGS_CAPTIONS_KEY` to fetch the current value of the captions setting. The API returns a status code, such as `Core::ERROR_GENERAL`, to indicate the success or failure of the operation. If successful, the retrieved value is stored in the `enabled` parameter, which is a boolean indicating whether captions are currently enabled (`true`) or disabled (`false`).
</details>

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

<a name="getPreferredCaptionsLanguages"></a>
## *getPreferredCaptionsLanguages*


The `getPreferredCaptionsLanguages` API retrieves the user's preferred languages for captions. This function is particularly useful for users who want to customize their viewing experience by selecting specific languages for captions. The API ensures that the preferred caption languages are fetched from the user settings, allowing applications to adapt the content display accordingly. This feature is beneficial for multilingual users or those who require captions in a specific language for better accessibility.

### Related Functions
[setPreferredCaptionsLanguages](#setPreferredCaptionsLanguages) : Allows users to set their preferred languages for captions. This function complements `getPreferredCaptionsLanguages` by enabling the configuration of the preferred languages.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getPreferredCaptionsLanguages` function retrieves the value of the preferred captions languages from the user settings storage using the key `USERSETTINGS_PREFERRED_CAPTIONS_LANGUAGES_KEY`. If the operation is successful, it returns `Core::ERROR_NONE`. In case of failure, it returns an error code such as `Core::ERROR_GENERAL`. The function logs the retrieved value for debugging purposes.
</details>

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

<a name="getPreferredClosedCaptionService"></a>
## *getPreferredClosedCaptionService*


The `getPreferredClosedCaptionService` API retrieves the user's preferred closed captioning service setting. Closed captioning services provide text-based transcriptions of spoken dialogue and other audio cues, enabling accessibility for individuals with hearing impairments or those who prefer text-based content. This API is useful for applications or systems that need to display or manage accessibility settings, ensuring that the user's preferred service is applied consistently across the platform.

The function returns the current value of the preferred closed captioning service, which is stored in the user settings. This value can be used to configure the closed captioning feature in media playback or other relevant scenarios.

### Related Functions
[SetPreferredClosedCaptionService](#SetPreferredClosedCaptionService) : Allows the user to set or update their preferred closed captioning service.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the function retrieves the value associated with the key `USERSETTINGS_PREFERRED_CLOSED_CAPTIONS_SERVICE_KEY` from the user settings storage. If the retrieval is successful, the preferred service is returned; otherwise, an error code (`Core::ERROR_GENERAL`) is returned to indicate a failure. This API does not modify any settings but solely focuses on fetching the stored value.
</details>

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

<a name="getPrivacyMode"></a>
## *getPrivacyMode*


The `getPrivacyMode` API is used to retrieve the current privacy mode setting of the device. Privacy mode determines how user data is shared or protected, with typical values being "SHARE" or "DO_NOT_SHARE." This API is particularly useful for users who want to verify the current privacy configuration of their device to ensure their data-sharing preferences are being respected. The function ensures that the privacy mode is fetched securely and accurately from the device's settings storage.

### Related Functions
[SetPrivacyMode](#SetPrivacyMode) : Allows users to update the privacy mode setting to either "SHARE" or "DO_NOT_SHARE" based on their preferences.

<details>
<summary><kbd>Additional information</kbd></summary>
- Internally, the function locks administrative access using `_adminLock` to ensure thread safety while accessing the privacy mode setting.
- It interacts with the `_remotStoreObject` to fetch the value of `USERSETTINGS_PRIVACY_MODE_KEY` from the device's settings storage.
- If the retrieved value is invalid or not recognized, the function defaults the privacy mode to "SHARE" and logs a warning.
- Error codes such as `Core::ERROR_NONE` indicate successful retrieval, while other codes like `Core::ERROR_GENERAL` may signal issues during execution.
</details>

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

<a name="getPinControl"></a>
## *getPinControl*


The `getPinControl` API is used to retrieve the current status of the "Pin Control" setting in the user settings. This setting typically determines whether a PIN is required to access certain features or content, providing an additional layer of security or parental control. By calling this function, users can check if the "Pin Control" feature is enabled or disabled.

### Related Functions
[SetPinControl](#SetPinControl) : Allows users to enable or disable the "Pin Control" feature by setting its value.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getPinControl` function retrieves the value of the "Pin Control" setting from the user settings storage. If the operation is successful, it returns the current status (enabled or disabled). In case of an error, it returns an appropriate error code, such as `Core::ERROR_GENERAL`.
</details>

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

<a name="getViewingRestrictions"></a>
## *getViewingRestrictions*


The `getViewingRestrictions` API is designed to retrieve the current viewing restrictions set for a user. Viewing restrictions are typically used to enforce content access limitations based on criteria such as age ratings, parental controls, or other user-defined preferences. This API ensures that the application can fetch and display the current restrictions, enabling users to understand the limitations applied to their content consumption.

This function is particularly useful in scenarios where parental controls or content filtering are implemented, as it allows the system to query and enforce the appropriate restrictions dynamically. The retrieved information can be used to display the current settings in the user interface or to validate content access requests.

### Related Functions
[SetViewingRestrictions](#SetViewingRestrictions) : This function allows the application to set or update the viewing restrictions for a user. It complements `getViewingRestrictions` by providing the ability to modify the restrictions.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getViewingRestrictions` function calls `GetUserSettingsValue` with the key `USERSETTINGS_VIEWING_RESTRICTIONS_KEY` to fetch the stored viewing restrictions. If the operation is successful, the function returns the retrieved value. In case of an error, it returns a general error code (`Core::ERROR_GENERAL`).

Error codes:
- `Core::ERROR_NONE`: Indicates successful retrieval of the viewing restrictions.
- `Core::ERROR_GENERAL`: Indicates a failure in fetching the viewing restrictions.

This function does not modify any settings; it is purely a retrieval mechanism.
</details>

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

<a name="getViewingRestrictionsWindow"></a>
## *getViewingRestrictionsWindow*


The `getViewingRestrictionsWindow` API is used to retrieve the current viewing restrictions window settings configured for a user. The viewing restrictions window typically defines a specific time frame during which certain content restrictions are applied, such as parental controls or content access limitations. This API is useful for applications or services that need to display or enforce these restrictions based on user preferences or regulatory requirements. By calling this API, users or systems can access the configured time window and ensure compliance with the defined restrictions.

### Related Functions
[SetViewingRestrictionsWindow](#SetViewingRestrictionsWindow) : Allows the user or system to configure or update the viewing restrictions window settings.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getViewingRestrictionsWindow` API retrieves the value of the `USERSETTINGS_VIEWING_RESTRICTIONS_WINDOW_KEY` from the user settings storage. If the retrieval is successful, the API returns the configured viewing restrictions window. In case of an error, it returns an appropriate error code, such as `Core::ERROR_GENERAL`.
</details>

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

<a name="getLiveWatershed"></a>
## *getLiveWatershed*


The `getLiveWatershed` API is used to retrieve the current status of the "Live Watershed" setting. This setting typically determines whether certain content restrictions or guidelines are applied during live content playback. For example, it may be used to enforce parental controls or content filtering based on user preferences. The API fetches the stored value of the "Live Watershed" setting and returns it as a boolean value, where `true` indicates that the setting is enabled, and `false` indicates that it is disabled.

This API is particularly useful for applications or systems that need to check the current status of content restrictions before allowing live content playback. It ensures that the user’s preferences are respected and applied consistently.

### Related Functions
[SetLiveWatershed](#SetLiveWatershed) : This function allows you to modify the "Live Watershed" setting. It is the counterpart to `getLiveWatershed`, enabling you to set the value that `getLiveWatershed` retrieves.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getLiveWatershed` API calls the `GetUserSettingsValue` function with the key `USERSETTINGS_LIVE_WATERSHED_KEY` to fetch the stored value. If the value is `"true"`, the API returns `true`; otherwise, it returns `false`.

Error codes:
- `Core::ERROR_NONE`: Indicates successful retrieval of the setting.
- `Core::ERROR_GENERAL`: Indicates a failure in retrieving the setting, possibly due to an internal issue or missing data.
</details>

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

<a name="getPlaybackWatershed"></a>
## *getPlaybackWatershed*


The `getPlaybackWatershed` API is used to retrieve the current status of the playback watershed setting. This setting typically determines whether certain content restrictions are applied during playback based on predefined watershed rules. Watershed rules are often used to restrict access to content that may not be suitable for certain audiences, such as children, during specific times or under specific conditions. By using this API, users can check if the playback watershed feature is enabled or disabled, allowing them to understand the current configuration of their content playback settings.

This API is particularly useful for applications or systems that need to enforce parental controls or content restrictions based on user preferences. It ensures that the playback experience aligns with the user's desired level of content filtering.

### Related Functions
[SetPlaybackWatershed](#SetPlaybackWatershed) : Allows users to modify the playback watershed setting by enabling or disabling it.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getPlaybackWatershed` API retrieves the value of the `USERSETTINGS_PLAYBACK_WATERSHED_KEY` from the user settings storage. If the value is "true," the playback watershed is considered enabled; otherwise, it is disabled. The function returns a status code indicating the success or failure of the operation. Common error codes include `Core::ERROR_NONE` for successful retrieval and `Core::ERROR_GENERAL` for general errors.
</details>

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

<a name="getBlockNotRatedContent"></a>
## *getBlockNotRatedContent*


The `getBlockNotRatedContent` API retrieves the current setting that determines whether content without a rating is blocked. This setting is typically used in parental control systems to ensure that unrated content is restricted based on user preferences. The API fetches the stored value for this setting and returns it as a boolean, where `true` indicates that unrated content is blocked, and `false` indicates that it is not.

This function is particularly useful for applications or systems that need to enforce content restrictions based on user-defined preferences. For example, it can be used in streaming platforms, set-top boxes, or other media devices to ensure that unrated content is either accessible or restricted, depending on the user's choice.

### Related Functions
[SetBlockNotRatedContent](#SetBlockNotRatedContent) : Allows the user to modify the setting for blocking unrated content. This function complements `getBlockNotRatedContent` by providing the ability to update the value that is retrieved by this API.

<details>
<summary><kbd>Additional information</kbd></summary>
- **Internal Function Calls**: The API internally calls `GetUserSettingsValue` with the key `USERSETTINGS_BLOCK_NOT_RATED_CONTENT_KEY` to fetch the stored value.
- **Error Codes**:
  - `Core::ERROR_NONE`: Indicates successful retrieval of the setting.
  - `Core::ERROR_GENERAL`: Indicates a failure in retrieving the setting.
- **Default Value**: If the setting is not explicitly configured, the default value is `false` (unrated content is not blocked).
</details>

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

<a name="getPinOnPurchase"></a>
## *getPinOnPurchase*


The `getPinOnPurchase` API is used to retrieve the current status of the "Pin on Purchase" setting. This setting determines whether a PIN is required to authorize purchases, providing an additional layer of security for transactions. By calling this function, users can check if the PIN requirement is enabled or disabled for purchases. This is particularly useful for parental controls or for users who want to ensure secure purchasing behavior on their devices.

### Related Functions
[SetPinOnPurchase](#SetPinOnPurchase) : Allows users to enable or disable the "Pin on Purchase" setting by setting its value.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the function retrieves the value of the `USERSETTINGS_PIN_ON_PURCHASE_KEY` from the user settings storage. If the value is "true," the function sets the `pinOnPurchase` variable to `true`; otherwise, it sets it to `false`. The function returns a status code, such as `Core::ERROR_NONE` for successful retrieval or `Core::ERROR_GENERAL` for errors.
</details>

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

<a name="getHighContrast"></a>
## *getHighContrast*


The `getHighContrast` API is used to retrieve the current status of the High Contrast mode setting. High Contrast mode is an accessibility feature designed to improve the visibility of text and interface elements for users with visual impairments. When enabled, it adjusts the color scheme of the user interface to provide better contrast between text, backgrounds, and other visual elements, making it easier to read and navigate. This API is particularly useful for applications or systems that need to adapt their behavior or appearance based on the user's accessibility preferences.

### Related Functions
[SetHighContrast](#SetHighContrast) : Allows you to enable or disable the High Contrast mode by setting its value.

<details>
<summary><kbd>Additional information</kbd></summary>
- Internally, the `getHighContrast` function retrieves the value of the High Contrast setting from the user settings storage using the key `USERSETTINGS_HIGH_CONTRAST_KEY`.
- The function returns a status code to indicate the success or failure of the operation.
  - `Core::ERROR_NONE`: Indicates that the operation was successful, and the value was retrieved.
  - `Core::ERROR_GENERAL`: Indicates a general error occurred during the retrieval process.
- The retrieved value is compared against the string "true" to determine whether High Contrast mode is enabled (`true`) or disabled (`false`).
</details>

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

<a name="getVoiceGuidance"></a>
## *getVoiceGuidance*


The `getVoiceGuidance` API retrieves the current status of the voice guidance feature, indicating whether it is enabled or disabled. Voice guidance is a feature designed to assist users by providing audio cues or spoken instructions, enhancing accessibility and usability for individuals who may prefer or require auditory feedback. This API is particularly useful for applications or devices that support accessibility features, allowing users to confirm the activation state of voice guidance.

### Related Functions
[SetVoiceGuidance](#SetVoiceGuidance) : Allows users to enable or disable the voice guidance feature.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getVoiceGuidance` function retrieves the value associated with the `USERSETTINGS_VOICE_GUIDANCE_KEY` from the user settings storage. If the value is "true," the function sets the `enabled` parameter to `true`; otherwise, it sets it to `false`. The function returns a status code, where `Core::ERROR_NONE` indicates successful execution, and `Core::ERROR_GENERAL` indicates a failure.
</details>

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

<a name="getVoiceGuidanceRate"></a>
## *getVoiceGuidanceRate*


The `getVoiceGuidanceRate` API retrieves the current rate of voice guidance, which is a setting that determines the speed at which voice guidance instructions are delivered to the user. This feature is particularly useful for accessibility purposes, allowing users to customize the pace of spoken instructions to suit their preferences or needs. For example, users who prefer faster or slower voice guidance can adjust the rate accordingly, and this API provides the means to query the current setting. The rate is returned as a numerical value, typically within a predefined range.

### Related Functions
[SetVoiceGuidanceRate](#SetVoiceGuidanceRate) : Allows users to set a new rate for voice guidance. This function complements `getVoiceGuidanceRate` by enabling the modification of the rate retrieved by this API.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getVoiceGuidanceRate` API calls the `GetUserSettingsValue` function to fetch the stored value associated with the `USERSETTINGS_VOICE_GUIDANCE_RATE_KEY`. If the value is successfully retrieved and is not empty, it is converted from a string to a double and returned. Error codes such as `Core::ERROR_GENERAL` or `Core::ERROR_NONE` are used to indicate the success or failure of the operation.
</details>

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

<a name="getVoiceGuidanceHints"></a>
## *getVoiceGuidanceHints*


The `getVoiceGuidanceHints` API is used to retrieve the current status of voice guidance hints in the system. Voice guidance hints are typically designed to assist users by providing additional auditory cues or instructions, enhancing accessibility and usability for individuals who rely on voice-based navigation or feedback. This function queries the system settings to determine whether voice guidance hints are enabled or disabled and returns the result to the caller. It is particularly useful for applications or services that need to adapt their behavior based on the user's accessibility preferences.

### Related Functions
[SetVoiceGuidanceHints](#SetVoiceGuidanceHints) : Allows the user to enable or disable voice guidance hints in the system.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getVoiceGuidanceHints` function calls `GetUserSettingsValue` with the key `USERSETTINGS_VOICE_GUIDANCE_HINTS_KEY` to fetch the stored value for voice guidance hints. If the value retrieved is `"true"`, the function sets the `hints` parameter to `true`, indicating that voice guidance hints are enabled. Otherwise, it sets the parameter to `false`.

Error codes:
- `Core::ERROR_NONE`: Indicates successful retrieval of the voice guidance hints status.
- `Core::ERROR_GENERAL`: Indicates a failure in retrieving the voice guidance hints status.

</details>

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

<a name="getMigrationState"></a>
## *getMigrationState*


The `getMigrationState` API is designed to retrieve the migration status of a specific user setting identified by a key. This function is particularly useful for determining whether a particular setting requires migration to a newer format or system. It provides a boolean value (`requiresMigration`) indicating whether the migration is necessary. This API is beneficial for users who want to ensure their settings are up-to-date and compatible with the latest system requirements.

### Related Functions
[getMigrationStates](#getMigrationStates) : Retrieves the migration states for all user settings, providing a comprehensive view of which settings require migration.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getMigrationState` function interacts with a remote store object to fetch the value associated with the given key. It checks the status of the operation and determines the migration requirement based on specific error codes (`Core::ERROR_NOT_EXIST`, `Core::ERROR_UNKNOWN_KEY`). If the key is invalid or the remote store object is null, appropriate error handling is performed. The function uses locking mechanisms (`_adminLock`) to ensure thread safety during execution.

Error codes:
- `Core::ERROR_NONE`: Indicates successful retrieval of the migration state.
- `Core::ERROR_NOT_EXIST`: Indicates the key does not exist, requiring migration.
- `Core::ERROR_UNKNOWN_KEY`: Indicates the key is unknown, requiring migration.
- `Core::ERROR_GENERAL`: Indicates a general error during execution.
</details>

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

<a name="getMigrationStates"></a>
## *getMigrationStates*


The `getMigrationStates` API is designed to retrieve the migration states of user settings within the system. It provides an iterator containing a list of settings and their respective migration statuses. This API is particularly useful for understanding whether specific user settings require migration or are already up-to-date. The migration state is determined based on the existence and validity of the settings in the system. If a setting does not exist or has an unknown key, it is flagged as requiring migration. This API is beneficial for applications or services that need to ensure user settings are properly migrated during updates or transitions.

### Related Functions
[getMigrationState](#getMigrationState) : Retrieves the migration state for a specific settings key, indicating whether it requires migration.

<details>
<summary><kbd>Additional information</kbd></summary>
- **Internal Function Calls**: The API internally locks administrative resources using `_adminLock` to ensure thread safety while accessing or modifying settings. It also interacts with `_remotStoreObject` to fetch settings values and determine their migration state.
- **Error Codes**:
  - `Core::ERROR_GENERAL`: Indicates a general error occurred during the operation.
  - `Core::ERROR_NOT_EXIST`: Indicates the setting does not exist in the system.
  - `Core::ERROR_UNKNOWN_KEY`: Indicates the key provided is unknown or invalid.
  - `Core::ERROR_NONE`: Indicates the operation was successful.
- **Output**: The API creates an iterator (`IUserSettingsMigrationStateIterator`) containing the migration states of all relevant settings.
- **Logging**: The API logs key details, such as whether migration is required for specific settings, and errors encountered during execution.
</details>

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

<a name="getContentPin"></a>
## *getContentPin*


The `getContentPin` API is used to retrieve the current content PIN set by the user. A content PIN is typically used to restrict access to certain content or features based on user preferences, such as parental controls or purchase restrictions. This API ensures that the user can access the stored PIN value securely and reliably. If no PIN is set, the API may return an empty value. This function is particularly useful for applications that need to verify or display the current PIN configuration to the user.

### Related Functions
[SetContentPin](#SetContentPin) : Allows the user to set or update the content PIN. This function complements `getContentPin` by enabling the modification of the PIN value.

<details>
<summary><kbd>Additional information</kbd></summary>
Internally, the `getContentPin` function calls `GetUserSettingsValue` with the key `USERSETTINGS_CONTENT_PIN_KEY` to fetch the stored PIN value. If the operation is successful, the PIN is returned; otherwise, an error code such as `Core::ERROR_GENERAL` is returned. 
</details>

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


The `onAudioDescriptionChanged` event is triggered whenever there is a change in the audio description setting of the system. Audio description is a feature designed to improve accessibility for visually impaired users by providing additional audio narration that describes visual elements of the content, such as actions, scenes, or text displayed on the screen. This event notifies the user when the audio description feature is enabled or disabled, allowing them to stay informed about the current accessibility settings.

This event is particularly useful for users who rely on audio descriptions to enhance their viewing experience. It ensures that users are aware of any changes to this setting, whether they are made manually or programmatically, so they can adjust their preferences accordingly.

### Related Functions
[SetAudioDescription](#SetAudioDescription) : This API is used to enable or disable the audio description feature. When this function is called, it triggers the `onAudioDescriptionChanged` event to notify users about the updated status of the audio description setting.

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


The `onPreferredAudioLanguagesChanged` event is triggered whenever there is a change in the user's preferred audio language settings. This event notifies the system or application about the updated audio language preferences, allowing it to adapt and provide content in the newly selected language(s). For example, if a user updates their preferred audio language to "French," this event ensures that the system is aware of the change and can deliver audio content in French wherever available.

This event is particularly useful for users who consume multilingual content and want their preferences to be reflected seamlessly across supported applications and services. It enhances the user experience by ensuring that audio content aligns with their language preferences without requiring manual adjustments for each piece of content.

### Related Functions
[SetPreferredAudioLanguages](#SetPreferredAudioLanguages) : This function is used to update the user's preferred audio language(s). When this function is called with a new language or set of languages, it triggers the `onPreferredAudioLanguagesChanged` event to notify the system of the change.

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


The `onPresentationLanguageChanged` event is triggered whenever the presentation language setting is updated. This event notifies the system and relevant components about the change in the language used for presenting content, such as menus, subtitles, or other user interface elements. It ensures that the user experience is consistent with their preferred language settings. For example, if a user changes the presentation language to French, this event will propagate the update, allowing the system to adjust the language of displayed content accordingly.

This event is particularly useful for users who prefer to interact with their devices in a specific language. It enhances accessibility and personalization by dynamically adapting the system's presentation language to match the user's preferences.

### Related Functions
[SetPresentationLanguage](#SetPresentationLanguage) : This API is used to update the presentation language setting. When invoked, it triggers the `onPresentationLanguageChanged` event to notify the system and other components about the change.

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


The `onCaptionsChanged` event is triggered whenever the captions feature is enabled or disabled in the user settings. Captions are textual representations of spoken dialogue and other audio cues in video content, designed to make media accessible to individuals who are deaf or hard of hearing, or for users who prefer to watch content with subtitles. This event notifies the system or application about changes in the captions setting, allowing it to adapt accordingly, such as displaying captions on the screen or disabling them based on user preferences.

This event is particularly useful for ensuring accessibility and enhancing the viewing experience for users who rely on captions. It helps maintain synchronization between user preferences and the actual behavior of the application or device.

### Related Functions
[dispatchEvent](#dispatchEvent) : This API triggers the `onCaptionsChanged` event when the user modifies the captions setting in the user interface or through system preferences. It ensures that the change is communicated to all relevant components or listeners in the system.

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


The `onPreferredCaptionsLanguagesChanged` event is triggered whenever there is a change in the user's preferred captions languages setting. This event notifies the system or application about the updated language preferences for captions, allowing it to adjust the displayed captions accordingly. For example, if a user updates their preferred captions language from English to Spanish, this event ensures that the captions are displayed in the newly selected language wherever applicable. This feature is particularly useful for enhancing accessibility and personalization, ensuring that users can enjoy content in their preferred language.

### Related Functions
[SetPreferredCaptionsLanguages](#SetPreferredCaptionsLanguages) : This function is used to update the user's preferred captions languages. When this function is called with a new language preference, it triggers the `onPreferredCaptionsLanguagesChanged` event to notify the system of the change.

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


The `onPreferredClosedCaptionServiceChanged` event is triggered whenever the user's preferred closed caption service is updated. Closed captions are an essential accessibility feature that provides text-based transcriptions of spoken dialogue and other audio elements in video content. This event ensures that any changes made to the preferred closed caption service are communicated to the system, allowing applications or services to adapt accordingly.

For example, if a user selects a specific closed caption service (e.g., "AUTO" or a third-party service) as their preference, this event notifies the system and relevant applications about the change. This helps maintain a seamless viewing experience by ensuring that the updated closed caption settings are applied across the platform.

This event is particularly useful for accessibility settings, enabling users to customize their viewing experience based on their needs. It also supports dynamic updates, meaning that changes to the preferred closed caption service are reflected immediately without requiring manual intervention or restarting the application.

### Related Functions
[SetPreferredClosedCaptionService](#SetPreferredClosedCaptionService) : This API allows users to set their preferred closed caption service. When this function is called, it triggers the `onPreferredClosedCaptionServiceChanged` event to notify the system and applications about the updated preference.

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


The `onPrivacyModeChanged` event is triggered whenever there is a change in the privacy mode setting of the device. Privacy mode determines how user data is shared or restricted. This event notifies the user about the updated privacy mode, which can either be "SHARE" (indicating that user data can be shared) or "DO_NOT_SHARE" (indicating that user data sharing is restricted).

This event is particularly useful for users who want to stay informed about changes to their privacy preferences, ensuring that they are aware of how their data is being handled. For example, if the privacy mode is changed by another application or a system-level setting, this event will notify the user about the change.

### Related Functions
[SetPrivacyMode](#SetPrivacyMode) : This function is used to update the privacy mode setting. It allows the user to explicitly set the privacy mode to either "SHARE" or "DO_NOT_SHARE". When this function is called, it triggers the `onPrivacyModeChanged` event to notify about the change.

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


The `onPinControlChanged` event is triggered whenever there is a change in the "Pin Control" setting within the user settings. This event notifies the system or application about the updated status of the Pin Control feature, which is typically used to enable or disable restrictions based on a PIN (Personal Identification Number). This feature is commonly utilized in parental control settings to restrict access to certain content or functionalities.

When this event is triggered, it ensures that all relevant components or modules in the system are updated with the new Pin Control status, allowing them to enforce or relax restrictions accordingly. For example, enabling Pin Control might require users to enter a PIN to access restricted content, while disabling it removes this requirement.

This event is particularly useful for users who want to manage access to specific content or features, ensuring a secure and controlled environment for themselves or their families.

### Related Functions
[SetPinControl](#SetPinControl) : This API is used to update the Pin Control setting. When this function is called to enable or disable Pin Control, it triggers the `onPinControlChanged` event to notify the system of the change.

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


The `onViewingRestrictionsChanged` event is triggered whenever there is a change in the viewing restrictions settings for a user. Viewing restrictions are typically used to enforce content access limitations based on criteria such as age ratings, parental controls, or other regulatory requirements. This event notifies the system or application that the viewing restrictions have been updated, allowing it to take appropriate actions, such as updating the user interface, restricting access to certain content, or logging the change for compliance purposes.

This event is particularly useful for scenarios where dynamic updates to viewing restrictions are required, such as when a parent modifies parental control settings or when regulatory policies change. By listening to this event, applications can ensure that the user experience remains consistent with the updated restrictions.

### Related Functions
[SetViewingRestrictions](#SetViewingRestrictions) : This API is used to update the viewing restrictions settings. When this function is called, it triggers the `onViewingRestrictionsChanged` event to notify the system of the change.

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


The `onViewingRestrictionsWindowChanged` event is triggered whenever there is a change in the "viewing restrictions window" setting. This setting typically defines a specific time window during which certain content restrictions are applied, such as parental controls or content access limitations. For example, it may be used to enforce restrictions on viewing certain types of content during specific hours of the day. This event notifies the system or application that the time window for these restrictions has been updated, allowing it to adjust its behavior accordingly.

This event is particularly useful for users who want to manage content accessibility based on time, such as parents setting restrictions for their children or organizations enforcing content policies during specific hours.

### Related Functions
[SetViewingRestrictionsWindow](#SetViewingRestrictionsWindow) : This API is used to update the "viewing restrictions window" setting. When this function is called, it triggers the `onViewingRestrictionsWindowChanged` event to notify the system or application about the change.

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


The `onLiveWatershedChanged` event is triggered whenever there is a change in the "Live Watershed" setting. The "Live Watershed" setting is typically used to enforce content restrictions based on age ratings or other criteria during live broadcasts. This event notifies the system or application that the status of the "Live Watershed" setting has been updated, allowing it to take appropriate actions, such as enabling or disabling access to certain content.

This event is particularly useful for users who want to manage content restrictions dynamically, ensuring that live content adheres to their preferences or regulatory requirements. For example, parents can use this feature to restrict access to certain live programs for their children.

### Related Functions
[SetLiveWatershed](#SetLiveWatershed) : This API is used to update the "Live Watershed" setting. When this function is called, it triggers the `onLiveWatershedChanged` event to notify the system of the change.

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


The `onPlaybackWatershedChanged` event is triggered whenever there is a change in the playback watershed setting. The playback watershed is a user-defined setting that determines whether certain content restrictions or guidelines are applied during playback. This setting is typically used to enforce viewing restrictions based on content ratings, parental controls, or other criteria defined by the user.

When this event occurs, it notifies the system or application that the playback watershed setting has been updated. This allows the application to adjust its behavior accordingly, such as restricting access to certain types of content or enabling specific playback features. For example, if the playback watershed is enabled, the application may block content that is not rated or deemed inappropriate based on the user's preferences.

This event is particularly useful for users who want to maintain control over the type of content that can be accessed during playback, ensuring a personalized and secure viewing experience.

### Related Functions
[SetPlaybackWatershed](#SetPlaybackWatershed) : This API is used to update the playback watershed setting. When the `SetPlaybackWatershed` function is called, it triggers the `onPlaybackWatershedChanged` event to notify the system of the change.

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


The `onBlockNotRatedContentChanged` event is triggered whenever there is a change in the user setting that determines whether content without a rating should be blocked. This setting is particularly useful for users who want to ensure that unrated content is restricted, providing an additional layer of control over the type of media accessible on their device. When this event occurs, it notifies the system and any subscribed components about the updated preference, enabling them to take appropriate actions, such as enforcing content restrictions or updating the user interface to reflect the new setting.

This event is designed to enhance parental controls and user customization, ensuring that users can tailor their viewing experience according to their preferences. For example, enabling this setting can help parents prevent their children from accessing unrated content, while disabling it allows unrestricted access to all types of media.

### Related Functions
[SetBlockNotRatedContent](#SetBlockNotRatedContent) : This API is used to update the user setting for blocking unrated content. When invoked, it modifies the setting and triggers the `onBlockNotRatedContentChanged` event to notify the system and subscribed components about the change.

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


The `onPinOnPurchaseChanged` event is triggered whenever there is a change in the "Pin on Purchase" setting. This setting determines whether a PIN is required to authorize purchases, providing an additional layer of security for users. When this event is fired, it indicates that the user has either enabled or disabled the requirement for a PIN during purchase transactions. This event is particularly useful for applications or systems that need to monitor or respond to changes in user preferences related to purchase security.

For example, if a user decides to enable the "Pin on Purchase" feature, this event will notify the system, allowing it to update its behavior accordingly, such as prompting for a PIN during the next purchase attempt. Conversely, if the user disables this feature, the system will stop requiring a PIN for purchases.

### Related Functions
[SetPinOnPurchase](#SetPinOnPurchase) : This API is used to programmatically enable or disable the "Pin on Purchase" setting. When this function is called, it triggers the `onPinOnPurchaseChanged` event to notify the system and other components about the change in the setting.

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


The `onHighContrastChanged` event is triggered whenever there is a change in the High Contrast setting of the user interface. High Contrast mode is an accessibility feature designed to improve the visibility of text and UI elements for users with visual impairments. When this setting is enabled, the system adjusts the color scheme to provide a higher contrast between text, backgrounds, and other interface elements, making it easier to read and navigate.

This event notifies subscribers about the updated state of the High Contrast setting, allowing applications or services to adapt their behavior or appearance accordingly. For example, an application might adjust its theme or notify the user about the change to ensure a seamless and accessible experience.

### Related Functions
[SetHighContrast](#SetHighContrast) : This function is used to enable or disable the High Contrast mode programmatically. It updates the High Contrast setting based on the provided value (`true` for enabling and `false` for disabling). When the setting is changed, the `onHighContrastChanged` event is dispatched to notify all relevant components or listeners about the update.

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


The `onVoiceGuidanceChanged` event is triggered whenever the voice guidance feature is enabled or disabled in the user settings. Voice guidance is an accessibility feature designed to assist users by providing spoken instructions or feedback, making it easier to navigate and interact with the system. This event notifies the application or system when the state of voice guidance changes, allowing it to adapt its behavior accordingly. For example, enabling voice guidance might prompt the system to start providing audio cues, while disabling it would stop these cues.

This event is particularly useful for users who rely on auditory feedback for navigation due to visual impairments or other accessibility needs. It ensures that the system remains responsive to changes in user preferences and provides a seamless experience.

### Related Functions
[SetVoiceGuidance](#SetVoiceGuidance) : This API is used to enable or disable the voice guidance feature. When this function is called, it triggers the `onVoiceGuidanceChanged` event to notify the system of the updated state.

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


The `onVoiceGuidanceRateChanged` event is triggered whenever there is a change in the playback speed of the voice guidance feature. Voice guidance is an accessibility feature designed to assist users by providing spoken feedback for on-screen content and navigation. This event notifies the system or application that the rate (speed) at which the voice guidance is delivered has been updated. The rate can be adjusted to suit user preferences, allowing for faster or slower speech delivery depending on individual needs.

This event is particularly useful for users who rely on voice guidance for accessibility, as it ensures that any changes to the speech rate are immediately reflected in the system, providing a seamless and personalized user experience.

### Related Functions
[SetVoiceGuidanceRate](#SetVoiceGuidanceRate) : This function is used to set the desired playback speed for voice guidance. It triggers the `onVoiceGuidanceRateChanged` event when the rate is successfully updated.

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


The `onVoiceGuidanceHintsChanged` event is triggered whenever there is a change in the status of voice guidance hints. Voice guidance hints are additional auditory cues or instructions provided to assist users, particularly those with visual impairments, in navigating and interacting with a device or application. This event notifies the system or application that the state of these hints has been updated, enabling it to respond accordingly, such as by updating the user interface or adjusting the auditory feedback.

This event is particularly useful for users who rely on accessibility features, as it ensures that they are informed about changes in the availability or activation of voice guidance hints. For example, if a user enables or disables voice guidance hints through the settings, this event ensures that the system reflects the change immediately.

### Related Functions
[SetVoiceGuidanceHints](#SetVoiceGuidanceHints) : This function is used to enable or disable voice guidance hints. When this function is called, it triggers the `onVoiceGuidanceHintsChanged` event to notify the system or application about the change in the hints' status.

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


The `onContentPinChanged` event is triggered whenever the content PIN is updated or modified. This event serves as a notification mechanism to inform users about changes to the PIN used for controlling access to specific content. The content PIN is typically used to enforce parental controls or restrict access to certain types of media or features based on user preferences.

This event ensures that users are aware of any updates to the PIN, allowing them to take necessary actions, such as verifying the change or updating their settings accordingly. It is particularly useful in scenarios where multiple devices or applications are synchronized, ensuring consistent enforcement of content restrictions across all platforms.

### Related Functions
[SetContentPin](#SetContentPin) : This API is responsible for updating the content PIN. It validates the provided PIN to ensure it meets the required format (e.g., a 4-digit numeric PIN) and triggers the `onContentPinChanged` event upon successful modification.

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
