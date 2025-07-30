<!-- Generated automatically, DO NOT EDIT! -->
<a name="DisplaySettings_Plugin"></a>
# DisplaySettings Plugin

A org.rdk.DisplaySettings plugin for Thunder framework.

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


**Overview of DisplaySettings**
The `DisplaySettings` RDK service is designed to manage and configure video output settings for connected displays. It provides functionality to retrieve and modify display resolutions, handle video port statuses, and manage HDR (High Dynamic Range) capabilities for both TVs and set-top boxes. Additionally, it supports event handling for changes in display settings, such as resolution updates and connected device statuses.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.DisplaySettings*) |
| classname | string | Class name: *org.rdk.DisplaySettings* |
| locator | string | Library name: *libWPEFrameworkDisplaySettings.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.DisplaySettings plugin:

DisplaySettings interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [enableSurroundDecoder](#enableSurroundDecoder) | Enables or disables Surround Decoder capability | NA |
| [getActiveInput](#getActiveInput) | Returns `true` if the STB HDMI output is currently connected to the active input of the sink device (determined by `RxSense`) | NA |
| [getAudioDelay](#getAudioDelay) | Returns the audio delay (in ms) on the selected audio port | NA |
| [getAudioDelayOffset](#getAudioDelayOffset) | Returns the audio delay offset (in ms) on the selected audio port | NA |
| [getAudioFormat](#getAudioFormat) | Returns the currently set audio format | NA |
| [getBassEnhancer](#getBassEnhancer) | Returns the current status of the Bass Enhancer settings | NA |
| [getConnectedAudioPorts](#getConnectedAudioPorts) | Returns connected audio output ports (a subset of the ports supported on the device) | NA |
| [getConnectedVideoDisplays](#getConnectedVideoDisplays) | Returns connected video displays | NA |
| [getCurrentOutputSettings](#getCurrentOutputSettings) | Returns current output settings | NA |
| [getCurrentResolution](#getCurrentResolution) | Returns the current resolution on the selected video display port | NA |
| [getDefaultResolution](#getDefaultResolution) | Gets the default resolution supported by the HDMI0 video output port | NA |
| [getDialogEnhancement](#getDialogEnhancement) | Returns the current Dialog Enhancer level (port HDMI0) | NA |
| [getDolbyVolumeMode](#getDolbyVolumeMode) | Returns whether Dolby Volume mode is enabled or disabled (audio output port HDMI0) | NA |
| [getDRCMode](#getDRCMode) | Returns the current Dynamic Range Control mode | NA |
| [getEnableAudioPort](#getEnableAudioPort) |  Returns the current status of the specified input audio port | NA |
| [setAssociatedAudioMixing](#setAssociatedAudioMixing) | Sets the Associated Audio Mixing Enable/Disable | NA |
| [getAssociatedAudioMixing](#getAssociatedAudioMixing) | Returns the Associated Audio Mixing status | NA |
| [setFaderControl](#setFaderControl) | Sets the set the mixerbalance betweeen main and associated audio | NA |
| [getFaderControl](#getFaderControl) | Returns the mixerbalance betweeen main and associated audio | NA |
| [setPrimaryLanguage](#setPrimaryLanguage) | Sets the Primary language | NA |
| [getPrimaryLanguage](#getPrimaryLanguage) | Returns the Primary language | NA |
| [setSecondaryLanguage](#setSecondaryLanguage) | Sets the secondary language | NA |
| [getSecondaryLanguage](#getSecondaryLanguage) | Returns the Secondary language | NA |
| [getGain](#getGain) | Returns the current gain value | NA |
| [getGraphicEqualizerMode](#getGraphicEqualizerMode) | Returns the current Graphic Equalizer Mode setting (port HDMI0) | NA |
| [getIntelligentEqualizerMode](#getIntelligentEqualizerMode) | Returns the current Intelligent Equalizer Mode setting (port HDMI0) | NA |
| [getMISteering](#getMISteering) | Returns the current status of Media Intelligence Steering settings | NA |
| [getMS12AudioCompression](#getMS12AudioCompression) | Returns the current audio compression settings | NA |
| [getMS12AudioProfile](#getMS12AudioProfile) | Returns the current MS12 audio profile settings | NA |
| [getMuted](#getMuted) | Returns whether audio is muted on a given port | NA |
| [getPreferredColorDepth](#getPreferredColorDepth) | Returns the current color depth on the selected video display port | NA |
| [getSettopAudioCapabilities](#getSettopAudioCapabilities) | Returns the set-top audio capabilities for the specified audio port | NA |
| [getSettopHDRSupport](#getSettopHDRSupport) | Returns an HDR support object (list of standards that the STB supports) | NA |
| [getSettopMS12Capabilities](#getSettopMS12Capabilities) | Returns the set-top MS12 audio capabilities for the specified audio port | NA |
| [getSinkAtmosCapability](#getSinkAtmosCapability) | Returns the ATMOS capability of the sink (HDMI0) | NA |
| [getSoundMode](#getSoundMode) | Returns the sound mode for the incoming video display | NA |
| [getSupportedAudioModes](#getSupportedAudioModes) | Returns a list of strings containing the supported audio modes | NA |
| [getSupportedAudioPorts](#getSupportedAudioPorts) | Returns all audio ports supported on the device (all ports that are physically present) | NA |
| [getSupportedMS12AudioProfiles](#getSupportedMS12AudioProfiles) | Returns list of platform supported MS12 audio profiles for the specified audio port | NA |
| [getSupportedResolutions](#getSupportedResolutions) | Returns supported resolutions on the selected video display port (both TV and STB) by its name | NA |
| [getSupportedSettopResolutions](#getSupportedSettopResolutions) | Returns supported STB resolutions | NA |
| [getSupportedTvResolutions](#getSupportedTvResolutions) | Returns supported TV resolutions on the selected video display port | NA |
| [getSupportedVideoDisplays](#getSupportedVideoDisplays) | Returns all video ports supported on the device (all ports that are physically present) | NA |
| [getSurroundVirtualizer](#getSurroundVirtualizer) | (Version 2) Returns the current surround virtualizer boost settings | NA |
| [getTVHDRCapabilities](#getTVHDRCapabilities) | Gets HDR capabilities supported by the TV | NA |
| [getTvHDRSupport](#getTvHDRSupport) | Returns an HDR support object (list of standards that the TV supports) | NA |
| [getVideoFormat](#getVideoFormat) | Returns the current and supported video formats | NA |
| [getVideoPortStatusInStandby](#getVideoPortStatusInStandby) | Returns video port status in standby mode (failure if the port name is missing) | NA |
| [getVolumeLevel](#getVolumeLevel) | Returns the current volume level | NA |
| [getVolumeLeveller](#getVolumeLeveller) | (Version 2) Returns the current Volume Leveller setting | NA |
| [getZoomSetting](#getZoomSetting) | Returns the zoom setting value | NA |
| [isConnectedDeviceRepeater](#isConnectedDeviceRepeater) | Indicates whether the device connected to the HDMI0 video output port is an HDCP repeater | NA |
| [isSurroundDecoderEnabled](#isSurroundDecoderEnabled) | Returns the current status of Surround Decoder | NA |
| [readEDID](#readEDID) | Reads the EDID from the connected HDMI (output) device | NA |
| [readHostEDID](#readHostEDID) | Reads the EDID of the host | NA |
| [resetBassEnhancer](#resetBassEnhancer) | Resets the dialog enhancer level to its default bassboost value | NA |
| [resetDialogEnhancement](#resetDialogEnhancement) | Resets the dialog enhancer level to its default enhancer level | NA |
| [resetSurroundVirtualizer](#resetSurroundVirtualizer) | Resets the surround virtualizer to its default boost value | NA |
| [resetVolumeLeveller](#resetVolumeLeveller) | Resets the Volume Leveller level to default volume value | NA |
| [setAudioAtmosOutputMode](#setAudioAtmosOutputMode) | Sets ATMOS audio output mode (on HDMI0) | NA |
| [setAudioDelay](#setAudioDelay) | Sets the audio delay (in ms) on the selected audio port | NA |
| [setAudioDelayOffset](#setAudioDelayOffset) | Sets the audio delay offset (in ms) on the selected audio port | NA |
| [setBassEnhancer](#setBassEnhancer) | Sets the Bass Enhancer | NA |
| [setCurrentResolution](#setCurrentResolution) | Sets the current resolution | [resolutionPreChange](#resolutionPreChange), [resolutionChanged](#resolutionChanged) |
| [setDialogEnhancement](#setDialogEnhancement) | Sets the Dialog Enhancer level | NA |
| [setDolbyVolumeMode](#setDolbyVolumeMode) | Enables or disables Dolby Volume mode on audio track (audio output port HDMI0) | NA |
| [setDRCMode](#setDRCMode) | Sets the Dynamic Range Control (DRC) setting | NA |
| [setEnableAudioPort](#setEnableAudioPort) | Enable or disable the specified audio port based on the input audio port name | NA |
| [setForceHDRMode](#setForceHDRMode) | Enables or disables the force HDR mode | NA |
| [setGain](#setGain) | Adjusts the gain on a specific port | NA |
| [setGraphicEqualizerMode](#setGraphicEqualizerMode) | Sets the Graphic Equalizer Mode | NA |
| [setIntelligentEqualizerMode](#setIntelligentEqualizerMode) | Sets the Intelligent Equalizer Mode (port HDMI0) | NA |
| [setMISteering](#setMISteering) | Enables or Disables Media Intelligent Steering | NA |
| [setMS12AudioCompression](#setMS12AudioCompression) | Sets the audio dynamic range compression level (port HDMI0) | NA |
| [setMS12AudioProfile](#setMS12AudioProfile) | Sets the selected MS12 audio profile | NA |
| [setMS12ProfileSettingsOverride](#setMS12ProfileSettingsOverride) | Overrides individual MS12 audio settings in order to optimize the customer experience (for example, enabling dialog enhancement in sports mode) | NA |
| [setMuted](#setMuted) | Mutes or unmutes audio on a specific port | [muteStatusChanged](#muteStatusChanged) |
| [setPreferredColorDepth](#setPreferredColorDepth) | Sets the current color depth for the videoDisplay | NA |
| [setScartParameter](#setScartParameter) | Sets SCART parameters | NA |
| [setSoundMode](#setSoundMode) | Sets the current sound mode for the corresponding video display | NA |
| [setSurroundVirtualizer](#setSurroundVirtualizer) | (Version 2) Sets the Surround Virtualizer boost | NA |
| [setVideoPortStatusInStandby](#setVideoPortStatusInStandby) | Sets the specified video port status to be used in standby mode (failure if the port name is missing) | NA |
| [setVolumeLevel](#setVolumeLevel) | Adjusts the Volume Level on a specific port | [volumeLevelChanged](#volumeLevelChanged) |
| [setVolumeLeveller](#setVolumeLeveller) | (Version 2) Sets the Volume Leveller level | NA |
| [setZoomSetting](#setZoomSetting) | Sets the current zoom value | [zoomSettingUpdated](#zoomSettingUpdated) |
| [getColorDepthCapabilities](#getColorDepthCapabilities) | Returns supported color depth capabilities | NA |
| [getSupportedMS12Config](#getSupportedMS12Config) | Returns supported ms12 config by the platform, possible values couldbe CONFG_Z, CONFIG_X, CONFIG_Y, CONFIG_NONE | NA |


<a name="enableSurroundDecoder"></a>
## *enableSurroundDecoder*


Enables or disables the surround sound decoder for the specified audio output port, enhancing the audio experience by providing immersive surround sound when supported. This function is useful for users who want to optimize their audio settings for a more cinematic or spatial sound experience.

### Related Functions
[isSurroundDecoderEnabled](#isSurroundDecoderEnabled) : Checks if the surround sound decoder is currently enabled.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.surroundDecoderEnable | boolean | Whether Surround Decoder is is enabled (`true`) or disabled (`false`) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.enableSurroundDecoder",
    "params": {
        "audioPort": "SPEAKER0",
        "surroundDecoderEnable": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.enableSurroundDecoder",
"params": {
"audioPort": "SPEAKER0",
"surroundDecoderEnable": true
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
function enableSurroundDecoder(params) {
  thunderJS.enableSurroundDecoder(params)
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
<button onclick="enableSurroundDecoder({audioPort: 'SPEAKER0', surroundDecoderEnable: true})">enableSurroundDecoder</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void enableSurroundDecoder(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["surroundDecoderEnable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getActiveInput"></a>
## *getActiveInput*


Determines whether the currently selected video input is active and in use. This function is useful for identifying if a connected display is actively receiving a signal, helping users troubleshoot connectivity or input issues.

### Related Functions  
[getConnectedVideoDisplays](#getConnectedVideoDisplays) : Provides a list of all connected video displays.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.videoDisplay | string | <sup>*(optional)*</sup> Video display port name. The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.activeInput | boolean | `true`:  1. STB is connected to TV's active input 2. Unable to determine if STB is connected to the TV's active input or not (because STB does not support RxSense) ; `false`: 1.STB is not connected to TV's Active input 2. TV is off  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getActiveInput",
    "params": {
        "videoDisplay": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "activeInput": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getActiveInput",
"params": {
"videoDisplay": "HDMI0"
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
function getActiveInput(videoDisplay) {
  thunderJS.getActiveInput({ videoDisplay: videoDisplay })
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
<button onclick="getActiveInput('HDMI0')">getActiveInput</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getActiveInput(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAudioDelay"></a>
## *getAudioDelay*


Retrieves the current audio delay setting (in milliseconds) for a specified audio output port, ensuring audio and video synchronization. This function is useful for addressing lip-sync issues and enhancing the viewing experience.

### Related Functions  
[setAudioDelay](#setAudioDelay) : Adjusts the audio delay for a specified audio output port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.audioDelay | string | Delay (in ms) on the selected audio port |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getAudioDelay",
    "params": {
        "audioPort": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "audioDelay": "0",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getAudioDelay",
"params": {
"audioPort": "HDMI0"
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
function getAudioDelay(audioPort) {
  thunderJS.getAudioDelay({ audioPort: audioPort })
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
<button onclick="getAudioDelay('HDMI0')">getAudioDelay</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioDelay(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAudioDelayOffset"></a>
## *getAudioDelayOffset*


Retrieves the current audio delay offset, which adjusts the synchronization between audio and video playback. This function is essential for ensuring a seamless viewing experience by eliminating noticeable audio-video lag.

### Related Functions
[getAudioDelay](#getAudioDelay) : Retrieves the overall audio delay setting.  
[setAudioDelayOffset](#setAudioDelayOffset) : Adjusts the audio delay offset to fine-tune synchronization.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.audioDelayOffset | string | Delay offset (in ms) on the selected audio port |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getAudioDelayOffset",
    "params": {
        "audioPort": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "audioDelayOffset": "0",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getAudioDelayOffset",
"params": {
"audioPort": "HDMI0"
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
function getAudioDelayOffset(audioPort) {
  thunderJS.getAudioDelayOffset({ audioPort: audioPort })
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
<button onclick="getAudioDelayOffset('HDMI0')">getAudioDelayOffset</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioDelayOffset(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAudioFormat"></a>
## *getAudioFormat*


Retrieves the current audio format being used by the device, such as PCM, AAC, or Dolby Atmos, and provides a list of supported audio formats. This function helps users understand the audio capabilities of their device and ensures compatibility with connected audio systems.

### Related Functions  
[getSettopAudioCapabilities](#getSettopAudioCapabilities) : Provides detailed information about the audio capabilities of the set-top box.  
[getSinkAtmosCapability](#getSinkAtmosCapability) : Checks if the connected audio sink supports Dolby Atmos.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedAudioFormat | array | A list of supported audio formats |
| result.supportedAudioFormat[#] | string |  |
| result.currentAudioFormat | string | The currently set audio format |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getAudioFormat"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedAudioFormat": [
            "`NONE`, `PCM`, `DOLBY AC3`, `DOLBY EAC3`, `DOLBY AC4`, `DOLBY MAT', 'DOLBY TRUEHD', 'DOLBY EAC3 ATMOS', 'DOLBY TRUEHD ATMOS', 'DOLBY MAT ATMOS', 'DOLBY AC4 ATMOS'"
        ],
        "currentAudioFormat": "PCM",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getAudioFormat"
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
function getAudioFormat() {
  thunderJS.getAudioFormat()
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
<button onclick="getAudioFormat()">getAudioFormat</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioFormat(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getBassEnhancer"></a>
## *getBassEnhancer*


Retrieves the current status and level of bass enhancement for a specified audio port, helping users optimize their audio experience by adjusting bass output. This function is useful for ensuring rich and immersive sound quality tailored to individual preferences.

### Related Functions  
[setBassEnhancer](#setBassEnhancer) : Allows users to configure the bass enhancement level for a specified audio port.  
[resetBassEnhancer](#resetBassEnhancer) : Resets the bass enhancement settings to their default values.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.enable | boolean | <sup>*(optional)*</sup> `true` if Bass Enhancer is enabled, otherwise `false` |
| result?.bassBoost | integer | <sup>*(optional)*</sup> Value between 0 and 100, where 0 means no bass boost (disabled) and 100 means max bass boost |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getBassEnhancer",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": true,
        "bassBoost": 50,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getBassEnhancer",
"params": {
"audioPort": "SPEAKER0"
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
function getBassEnhancer(audioPort) {
  thunderJS.getBassEnhancer({ audioPort: audioPort })
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
<button onclick="getBassEnhancer('SPEAKER0')">getBassEnhancer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getBassEnhancer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getConnectedAudioPorts"></a>
## *getConnectedAudioPorts*


Identifies and lists all currently connected audio ports on your device, such as HDMI or SPDIF. This function helps users understand which audio outputs are active, ensuring proper setup and troubleshooting of audio connections.

### Related Functions  
[getSupportedAudioPorts](#getSupportedAudioPorts) : Provides a list of all audio ports supported by the device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.connectedAudioPorts | array | A string [] of connected audio port names |
| result.connectedAudioPorts[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getConnectedAudioPorts"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "connectedAudioPorts": [
            "HDMI0"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getConnectedAudioPorts"
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
function getConnectedAudioPorts() {
  thunderJS.getConnectedAudioPorts()
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
<button onclick="getConnectedAudioPorts()">getConnectedAudioPorts</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getConnectedAudioPorts(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getConnectedVideoDisplays"></a>
## *getConnectedVideoDisplays*


Retrieves a list of video displays currently connected to the device, such as HDMI ports. This function helps users identify active video output connections, ensuring proper setup and troubleshooting of display configurations.

### Related Functions  
[getSupportedVideoDisplays](#getSupportedVideoDisplays) : Provides a list of all video displays supported by the device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.connectedVideoDisplays | array | A string [] of connected video display port names |
| result.connectedVideoDisplays[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getConnectedVideoDisplays"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "connectedVideoDisplays": [
            "HDMI0"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DisplaySettings.getConnectedVideoDisplays"}' http://127.0.0.1:9998/jsonrpc
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
function getConnectedVideoDisplays() {
  thunderJS.getConnectedVideoDisplays()
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
<button onclick="getConnectedVideoDisplays()">getConnectedVideoDisplays</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getConnectedVideoDisplays(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getCurrentOutputSettings"></a>
## *getCurrentOutputSettings*


Retrieves the current audio and video output settings of the device, including details like resolution, audio format, and connected ports. This function helps users understand the active configuration of their device to ensure optimal compatibility and performance with connected displays and audio systems.

### Related Functions  
[getCurrentResolution](#getCurrentResolution) : Provides the current video resolution settings.  
[getConnectedAudioPorts](#getConnectedAudioPorts) : Lists the audio ports currently connected to the device.  
[getConnectedVideoDisplays](#getConnectedVideoDisplays) : Identifies the video displays currently connected to the device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.colorSpace | integer | The color space. Possible values: `0` (dsDISPLAY_COLORSPACE_UNKNOWN), `1` (sDISPLAY_COLORSPACE_RGB, `2` (dsDISPLAY_COLORSPACE_YCbCr422), `3` (dsDISPLAY_COLORSPACE_YCbCr444), `4` (dsDISPLAY_COLORSPACE_YCbCr420), `5` (dsDISPLAY_COLORSPACE_AUTO) |
| result.colorDepth | integer | The color depth. The value that is returned from `dsGetCurrentOutputSettings` |
| result.matrixCoefficients | integer | matrix coefficients. Possible values: `0` (dsDISPLAY_MATRIXCOEFFICIENT_UNKNOWN), `1` (dsDISPLAY_MATRIXCOEFFICIENT_BT_709), `2` (dsDISPLAY_MATRIXCOEFFICIENT_BT_470_2_BG), `3` (dsDISPLAY_MATRIXCOEFFICIENT_SMPTE_170M), `4` (dsDISPLAY_MATRIXCOEFFICIENT_XvYCC_709), `5` (dsDISPLAY_MATRIXCOEFFICIENT_eXvYCC_601), `6` (dsDISPLAY_MATRIXCOEFFICIENT_BT_2020_NCL), `7` (dsDISPLAY_MATRIXCOEFFICIENT_BT_2020_CL) |
| result.videoEOTF | integer | HDR standard. Possible values: `0x0` (dsHDRSTANDARD_NONE), `0x01` (dsHDRSTANDARD_HDR10), `0x02` (dsHDRSTANDARD_HLG), `0x04` (dsHDRSTANDARD_DolbyVision), `0x08` (dsHDRSTANDARD_TechnicolorPrime), `0x10` (dsHDRSTANDARD_HDR10PLUS), `0x20` (dsHDRSTANDARD_SDR), `0x80` (dsHDRSTANDARD_Invalid) |
| result?.quantizationRange | integer | <sup>*(optional)*</sup> The supported quantization range |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getCurrentOutputSettings"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "colorSpace": 5,
        "colorDepth": 0,
        "matrixCoefficients": 0,
        "videoEOTF": 0,
        "quantizationRange": 235,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getCurrentOutputSettings"
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
function getCurrentOutputSettings() {
  thunderJS.getCurrentOutputSettings()
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
<button onclick="getCurrentOutputSettings()">getCurrentOutputSettings</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getCurrentOutputSettings(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getCurrentResolution"></a>
## *getCurrentResolution*


Retrieves the current resolution setting of the specified video display, providing users with clarity on the active video output configuration (e.g., 720p, 1080p). This function is essential for ensuring compatibility with connected devices and optimizing viewing experiences.

### Related Functions  
[getDefaultResolution](#getDefaultResolution) : Provides the default resolution for the selected video display.  
[setCurrentResolution](#setCurrentResolution) : Allows users to change the resolution of the video display.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.videoDisplay | string | <sup>*(optional)*</sup> Video display port name. The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.resolution | string | Video display resolution |
| result.w | number | The width |
| result.h | number | The height |
| result?.progressive | boolean | <sup>*(optional)*</sup> The type of scan signal |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getCurrentResolution",
    "params": {
        "videoDisplay": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "resolution": "1080p",
        "w": 1920,
        "h": 1080,
        "progressive": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getCurrentResolution",
"params": {
"videoDisplay": "HDMI0"
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
function getCurrentResolution(videoDisplay) {
  thunderJS.getCurrentResolution(videoDisplay)
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
<button onclick="getCurrentResolution('HDMI0')">getCurrentResolution</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getCurrentResolution(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getDefaultResolution"></a>
## *getDefaultResolution*


Retrieves the default video resolution for a specified video display port, ensuring optimal compatibility and performance for connected devices. This function is useful for identifying the default resolution setting without manually checking the display configuration, saving time and effort.

### Related Functions
[getSupportedResolutions](#getSupportedResolutions) : Provides a list of all resolutions supported by the specified video display.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.defaultResolution | string | Default resolution supported by the HDMI0 video output port |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getDefaultResolution"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "defaultResolution": "720p",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getDefaultResolution"
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
function getDefaultResolution() {
  thunderJS.getDefaultResolution()
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
<button onclick="getDefaultResolution()">getDefaultResolution</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDefaultResolution(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getDialogEnhancement"></a>
## *getDialogEnhancement*


Retrieves the current status and level of dialog enhancement for audio output, helping users improve speech clarity in their audio experience. This feature is particularly useful for enhancing dialogue in movies, shows, or other content where speech may be difficult to hear.

### Related Functions  
[setDialogEnhancement](#setDialogEnhancement) : Allows users to adjust the dialog enhancement level to their preference.  
[resetDialogEnhancement](#resetDialogEnhancement) : Resets the dialog enhancement settings to default values.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enable | boolean | `true` if Dialog Enhancer Mode is enabled, otherwise `false` |
| result.enhancerlevel | integer | Value between 0 and 16, where 0 means no enhancement and 16 means maximum enhancement |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getDialogEnhancement",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": false,
        "enhancerlevel": 0,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getDialogEnhancement",
"params": {
"audioPort": "SPEAKER0"
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
function getDialogEnhancement(audioPort) {
  thunderJS.getDialogEnhancement({ audioPort: audioPort })
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
<button onclick="getDialogEnhancement('SPEAKER0')">getDialogEnhancement</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDialogEnhancement(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getDolbyVolumeMode"></a>
## *getDolbyVolumeMode*


Retrieves the current Dolby Volume Mode setting for the specified audio port, providing information on how audio is being processed (e.g., Dolby Digital, Dolby Digital Plus, or Stereo). This function helps users understand and verify the audio output configuration for optimal listening experiences.

### Related Functions  
[setDolbyVolumeMode](#setDolbyVolumeMode) : Allows you to configure the Dolby Volume Mode for the audio output.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.dolbyVolumeMode | boolean | <sup>*(optional)*</sup> Whether Dolby Volume mode is enabled (`true`) or disabled (`false`) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getDolbyVolumeMode"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "dolbyVolumeMode": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getDolbyVolumeMode"
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
function getDolbyVolumeMode() {
  thunderJS.getDolbyVolumeMode()
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
<button onclick="getDolbyVolumeMode()">getDolbyVolumeMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDolbyVolumeMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getDRCMode"></a>
## *getDRCMode*


Retrieves the current Dynamic Range Compression (DRC) mode, which adjusts the audio's dynamic range to enhance clarity during playback. This feature is particularly useful for maintaining consistent audio levels in environments with varying sound conditions, such as late-night viewing or noisy surroundings.

### Related Functions  
[setDRCMode](#setDRCMode) : Allows you to configure the Dynamic Range Compression (DRC) mode.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.DRCMode | string | <sup>*(optional)*</sup> The DRC Mode value: either `line` or `RF` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getDRCMode",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "DRCMode": "line",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getDRCMode",
"params": {
"audioPort": "SPEAKER0"
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
function getDRCMode(audioPort) {
  thunderJS.getDRCMode({ audioPort: audioPort })
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
<button onclick="getDRCMode('SPEAKER0')">getDRCMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDRCMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getEnableAudioPort"></a>
## *getEnableAudioPort*


Retrieves the current enablement status of a specified audio port, such as HDMI or HDMI ARC, indicating whether the port is active and ready for audio output. This function helps users verify the operational state of their audio connections for seamless audio playback.

### Related Functions  
[setEnableAudioPort](#setEnableAudioPort) : Allows users to enable or disable a specific audio port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enable | boolean | `true` if the audio port is enabled, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getEnableAudioPort",
    "params": {
        "audioPort": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "getEnableAudioPort"
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
function getEnableAudioPort() {
  thunderJS.getEnableAudioPort()
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
<button onclick="getEnableAudioPort()">getEnableAudioPort</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getEnableAudioPort(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="setAssociatedAudioMixing"></a>
## *setAssociatedAudioMixing*


Enables or disables the mixing of associated audio, such as secondary audio tracks or commentary, with the primary audio output. This function allows users to customize their audio experience by controlling whether additional audio content is integrated into the main audio stream. It is particularly useful for accessibility features or enhanced viewing experiences.

### Related Functions
[getAssociatedAudioMixing](#getAssociatedAudioMixing) : Retrieves the current status of associated audio mixing.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.mixing | boolean | `true` enables the Associated Audio Mixing for specified audio port. `false` to disables |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setAssociatedAudioMixing",
    "params": {
        "audioPort": "SPEAKER0",
        "mixing": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setAssociatedAudioMixing",
"params": {
"audioPort": "SPEAKER0",
"mixing": true
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
function setAssociatedAudioMixing(params) {
  thunderJS.setAssociatedAudioMixing(params)
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
<button onclick="setAssociatedAudioMixing({audioPort: 'SPEAKER0', mixing: true})">setAssociatedAudioMixing</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setAssociatedAudioMixing(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["mixing"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAssociatedAudioMixing"></a>
## *getAssociatedAudioMixing*


Retrieves the current status of associated audio mixing, which determines whether secondary audio (e.g., commentary or descriptive audio) is mixed with the primary audio output. This feature is essential for enhancing accessibility and providing a more inclusive audio experience for users.

### Related Functions
[setAssociatedAudioMixing](#setAssociatedAudioMixing) : Allows you to enable or disable associated audio mixing.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mixing | boolean | `true` if Associated Audio Mixing enabled for the specified audio port, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getAssociatedAudioMixing",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "mixing": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getAssociatedAudioMixing",
"params": {
"audioPort": "SPEAKER0"
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
function getAssociatedAudioMixing(audioPort) {
  thunderJS.getAssociatedAudioMixing({ audioPort: audioPort })
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
<button onclick="getAssociatedAudioMixing('SPEAKER0')">getAssociatedAudioMixing</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void getAssociatedAudioMixing(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["audioPort"] = "SPEAKER0";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="setFaderControl"></a>
## *setFaderControl*


Adjusts the audio mixer balance between front and rear speakers, allowing users to customize sound distribution for an optimal listening experience. This function is useful for tailoring audio output to suit different environments or personal preferences.

### Related Functions  
[getFaderControl](#getFaderControl) : Retrieves the current mixer balance setting for front and rear speakers.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.mixerBalance | integer | Value between -32 to +32, where -32 means mute associated and +32 means mute main |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setFaderControl",
    "params": {
        "audioPort": "SPEAKER0",
        "mixerBalance": 31
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setFaderControl",
"params": {
"audioPort": "SPEAKER0",
"mixerBalance": 31
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
function setFaderControl(params) {
  thunderJS.setFaderControl(params)
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
<button onclick="setFaderControl({audioPort: 'SPEAKER0', mixerBalance: 31})">setFaderControl</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setFaderControl(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["mixerBalance"] = 31;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getFaderControl"></a>
## *getFaderControl*


Retrieves the current audio mixer balance (fader control) for a specified audio port, allowing users to check how sound is distributed between front and rear speakers. This function is useful for optimizing audio settings to suit personal preferences or specific listening environments.

### Related Functions  
[setFaderControl](#setFaderControl) : Adjusts the audio mixer balance to customize sound distribution.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mixerBalance | integer | Value between -32 to +32, where -32 means mute associated and +32 means mute main |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getFaderControl",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "mixerBalance": 31,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getFaderControl",
"params": {
"audioPort": "SPEAKER0"
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
function getFaderControl(audioPort) {
  thunderJS.getFaderControl({ audioPort: audioPort })
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
<button onclick="getFaderControl('SPEAKER0')">getFaderControl</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getFaderControl(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPrimaryLanguage"></a>
## *setPrimaryLanguage*


The `setPrimaryLanguage` API allows users to define their preferred primary language for audio output on their device. This setting ensures that the device prioritizes the selected language when playing content with multiple language options, enhancing the user experience by aligning audio preferences with individual needs.

### Related Functions  
[getPrimaryLanguage](#getPrimaryLanguage) : Retrieves the currently set primary language.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.lang | string | 3 letter lang code should be used as per ISO 639 |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setPrimaryLanguage",
    "params": {
        "audioPort": "SPEAKER0",
        "lang": "eng"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setPrimaryLanguage",
"params": {
"audioPort": "SPEAKER0",
"lang": "eng"
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
function setPrimaryLanguage(params) {
  thunderJS.setPrimaryLanguage(params)
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
<button onclick="setPrimaryLanguage({audioPort: 'SPEAKER0', lang: 'eng'})">setPrimaryLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPrimaryLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["lang"] = "eng";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPrimaryLanguage"></a>
## *getPrimaryLanguage*


Retrieves the primary audio language currently set for the device, ensuring users can confirm or adjust their preferred language settings for audio output. This function is particularly useful for multilingual environments or when customizing audio preferences to enhance the viewing experience.

### Related Functions
[setPrimaryLanguage](#setPrimaryLanguage) : Allows users to set the primary audio language for the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.lang | string | 3 letter lang code should be used as per ISO 639 |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getPrimaryLanguage",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "lang": "eng",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getPrimaryLanguage",
"params": {
"audioPort": "SPEAKER0"
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
function getPrimaryLanguage(audioPort) {
  thunderJS.getPrimaryLanguage(audioPort)
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
<button onclick="getPrimaryLanguage('SPEAKER0')">getPrimaryLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPrimaryLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setSecondaryLanguage"></a>
## *setSecondaryLanguage*


This API allows users to set the secondary audio language for their device, ensuring a personalized viewing experience by selecting a preferred language for secondary audio tracks. It is particularly useful for multilingual content or accessibility purposes.

### Related Functions  
[getSecondaryLanguage](#getSecondaryLanguage) : Retrieves the currently set secondary audio language.  
[setPrimaryLanguage](#setPrimaryLanguage) : Sets the primary audio language for the device.  
[getPrimaryLanguage](#getPrimaryLanguage) : Retrieves the currently set primary audio language.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.lang | string | 3 letter lang code should be used as per ISO 639 |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setSecondaryLanguage",
    "params": {
        "audioPort": "SPEAKER0",
        "lang": "eng"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setSecondaryLanguage",
"params": {
"audioPort": "SPEAKER0",
"lang": "eng"
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
function setSecondaryLanguage(params) {
  thunderJS.setSecondaryLanguage(params)
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
<button onclick="setSecondaryLanguage({ audioPort: 'SPEAKER0', lang: 'eng' })">setSecondaryLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setSecondaryLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["lang"] = "eng";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSecondaryLanguage"></a>
## *getSecondaryLanguage*


Retrieves the currently configured secondary audio language for the device, allowing users to identify the alternate language setting for audio playback. This is particularly useful for multilingual content or accessibility purposes.

### Related Functions  
[getPrimaryLanguage](#getPrimaryLanguage) : Retrieves the primary audio language setting.  
[setSecondaryLanguage](#setSecondaryLanguage) : Updates the secondary audio language setting.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.lang | string | 3 letter lang code should be used as per ISO 639 |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSecondaryLanguage",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "lang": "eng",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSecondaryLanguage",
"params": {
"audioPort": "SPEAKER0"
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
function getSecondaryLanguage(audioPort) {
  thunderJS.getSecondaryLanguage(audioPort)
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
<button onclick="getSecondaryLanguage('SPEAKER0')">getSecondaryLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSecondaryLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getGain"></a>
## *getGain*


Retrieves the current audio gain level for a specified audio output port, such as HDMI. This function helps users understand and monitor the audio amplification settings, ensuring optimal sound quality for their connected devices.

### Related Functions  
[setGain](#setGain) : Allows users to adjust the audio gain level for a specific audio output port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.gain | number | Value between -2080 and 480, where -2080 means negative gain and 480 means maximum gain |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getGain",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "gain": 10.0,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getGain",
"params": {
"audioPort": "SPEAKER0"
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
function getGain(audioPort) {
  thunderJS.getGain({ audioPort: audioPort })
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
<button onclick="getGain('SPEAKER0')">getGain</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void getGain(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["audioPort"] = "SPEAKER0";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="getGraphicEqualizerMode"></a>
## *getGraphicEqualizerMode*


Retrieves the current graphic equalizer mode for the specified audio output port, allowing users to understand the active sound profile settings. This function is useful for optimizing audio performance based on user preferences or device capabilities.

### Related Functions  
[setGraphicEqualizerMode](#setGraphicEqualizerMode) : Allows users to configure the graphic equalizer mode to customize audio output.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enable | boolean | `true` if Graphic Equalizer Mode is enabled, otherwise `false` |
| result.mode | integer | Graphic Equalizer mode (`0` = mode not set or in case of error, `1` = open, `2` = rich, `3` = focused) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getGraphicEqualizerMode",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": true,
        "mode": 2,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getGraphicEqualizerMode",
"params": {
"audioPort": "SPEAKER0"
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
function getGraphicEqualizerMode(audioPort) {
  thunderJS.getGraphicEqualizerMode({ audioPort: audioPort })
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
<button onclick="getGraphicEqualizerMode('SPEAKER0')">getGraphicEqualizerMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getGraphicEqualizerMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getIntelligentEqualizerMode"></a>
## *getIntelligentEqualizerMode*


Retrieves the current Intelligent Equalizer mode for the specified audio port, providing users with information about the active audio enhancement settings. This feature helps optimize sound quality by automatically adjusting audio parameters based on the content being played.

### Related Functions  
[setIntelligentEqualizerMode](#setIntelligentEqualizerMode) : Allows users to configure the Intelligent Equalizer mode to suit their preferences.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enable | boolean | `true` if Intelligent Equalizer Mode is enabled, otherwise `false` |
| result.mode | integer | Intelligent Equalizer mode (`0` = off, `1` = open, `2` = rich, `3` = focused) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getIntelligentEqualizerMode",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": true,
        "mode": 2,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getIntelligentEqualizerMode",
"params": {
"audioPort": "SPEAKER0"
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
function getIntelligentEqualizerMode(audioPort) {
  thunderJS.getIntelligentEqualizerMode({ audioPort: audioPort })
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
<button onclick="getIntelligentEqualizerMode('SPEAKER0')">getIntelligentEqualizerMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getIntelligentEqualizerMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMISteering"></a>
## *getMISteering*


Retrieves the current status of MI Steering for a specified audio port, indicating whether it is enabled or disabled. This function helps users understand the audio output configuration and ensures optimal audio steering settings for their connected devices.

### Related Functions  
[setMISteering](#setMISteering) : Allows users to enable or disable MI Steering for a specified audio port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.MISteeringEnable | boolean | <sup>*(optional)*</sup> Whether Media Intelligence Steering is enabled (`true`) or disabled (`false`) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getMISteering",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "MISteeringEnable": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getMISteering",
"params": {
"audioPort": "SPEAKER0"
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
function getMISteering(audioPort) {
  thunderJS.getMISteering(audioPort)
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
<button onclick="getMISteering('SPEAKER0')">getMISteering</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMISteering(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMS12AudioCompression"></a>
## *getMS12AudioCompression*


Retrieves the current MS12 audio compression level and its status (enabled or disabled) for the specified audio port. This function helps users understand and manage the audio compression settings, ensuring an optimized listening experience tailored to their preferences.

### Related Functions  
[setMS12AudioCompression](#setMS12AudioCompression) : Allows users to configure the MS12 audio compression level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enable | boolean | `true` if audio compression is enabled, otherwise `false` |
| result.compressionLevel | integer | Value between 0 and 10, where 0 means no compression and 10 means maximum compression |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getMS12AudioCompression",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enable": true,
        "compressionLevel": 5,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getMS12AudioCompression",
"params": {
"audioPort": "SPEAKER0"
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
function getMS12AudioCompression(audioPort) {
  thunderJS.getMS12AudioCompression({ audioPort: audioPort })
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
<button onclick="getMS12AudioCompression('SPEAKER0')">getMS12AudioCompression</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMS12AudioCompression(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMS12AudioProfile"></a>
## *getMS12AudioProfile*


Retrieves the current MS12 audio profile being used by the specified audio port (defaulting to HDMI0 if not specified). This function helps users understand the active audio configuration, ensuring compatibility with their audio setup and preferences.

### Related Functions  
[getSupportedMS12AudioProfiles](#getSupportedMS12AudioProfiles) : Lists all MS12 audio profiles supported by the device.  
[setMS12AudioProfile](#setMS12AudioProfile) : Allows users to set a specific MS12 audio profile.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.ms12AudioProfile | string | An MS12 audio profile name from `getSupportedMS12AudioProfile` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getMS12AudioProfile",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "ms12AudioProfile": "Game",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getMS12AudioProfile",
"params": {
"audioPort": "SPEAKER0"
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
function getMS12AudioProfile(audioPort) {
  thunderJS.getMS12AudioProfile({ audioPort: audioPort })
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
<button onclick="getMS12AudioProfile('SPEAKER0')">getMS12AudioProfile</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMS12AudioProfile(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMuted"></a>
## *getMuted*


The `getMuted` API checks whether the audio output of the device is currently muted. This function is useful for users who want to verify the mute status of their device, ensuring they can manage audio settings effectively.

### Related Functions  
[setMuted](#setMuted) : Allows users to enable or disable the mute status of the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.muted | boolean | mute or unmute audio |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getMuted",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "muted": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getMuted",
"params": {
"audioPort": "SPEAKER0"
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
function getMuted(audioPort) {
  thunderJS.getMuted({ audioPort: audioPort })
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
<button onclick="getMuted('SPEAKER0')">getMuted</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMuted(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPreferredColorDepth"></a>
## *getPreferredColorDepth*


Retrieves the currently preferred color depth setting for a specified video display, such as "8 Bit," "10 Bit," "12 Bit," or "Auto." This function helps users understand the active color depth configuration, ensuring optimal video quality based on their display capabilities.

### Related Functions  
[setPreferredColorDepth](#setPreferredColorDepth) : Allows users to configure the preferred color depth for a video display.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.videoDisplay | string | <sup>*(optional)*</sup> Video display port name. The default port is `HDMI0` if no port is specified |
| params?.persist | boolean | <sup>*(optional)*</sup> Persists the color depth |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.resolution | string | <sup>*(optional)*</sup> Video display color depth. (must be one of the following: *8 Bit*, *10 Bit*, *12 Bit*, *Auto*) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getPreferredColorDepth",
    "params": {
        "videoDisplay": "HDMI0",
        "persist": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "resolution": "12 Bit",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getPreferredColorDepth",
"params": {
"videoDisplay": "HDMI0",
"persist": true
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
function getPreferredColorDepth(params) {
  thunderJS.getPreferredColorDepth(params)
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
<button onclick="getPreferredColorDepth({videoDisplay: 'HDMI0', persist: true})">getPreferredColorDepth</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPreferredColorDepth(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        parameters["persist"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSettopAudioCapabilities"></a>
## *getSettopAudioCapabilities*


Retrieves the audio capabilities supported by the set-top box, such as ATMOS, Dolby Digital, Dolby Digital Plus, and MS12. This function helps users understand the audio formats their device can handle, ensuring compatibility with connected audio systems and enhancing the overall audio experience.

### Related Functions
[getSettopMS12Capabilities](#getSettopMS12Capabilities) : Provides detailed information about MS12-specific audio capabilities.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.AudioCapabilities | array | <sup>*(optional)*</sup> An array of audio capabilities supported by STB |
| result?.AudioCapabilities[#] | string | <sup>*(optional)*</sup> Audio capability name (None in case of no audio capability support)  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSettopAudioCapabilities",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "AudioCapabilities": [
            "None"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSettopAudioCapabilities",
"params": {
"audioPort": "SPEAKER0"
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
function getSettopAudioCapabilities(audioPort) {
  thunderJS.getSettopAudioCapabilities({ audioPort: audioPort })
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
<button onclick="getSettopAudioCapabilities('SPEAKER0')">getSettopAudioCapabilities</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSettopAudioCapabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSettopHDRSupport"></a>
## *getSettopHDRSupport*


Determines whether the set-top box supports HDR (High Dynamic Range) and provides a list of supported HDR standards, such as HDR10 or Dolby Vision. This function helps users understand the HDR capabilities of their set-top box, ensuring compatibility with HDR content for an enhanced viewing experience.

### Related Functions  
[getTvHDRSupport](#getTvHDRSupport) : Checks the HDR support and standards available on the connected TV.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.standards | array | A string [] of HDR capabilities. Possible values: `none`, `HDR10`, `HDR10PLUS`, `Dolby Vision`, `Technicolor Prime`, `SDR` |
| result.standards[#] | string |  |
| result.supportsHDR | boolean | Indicates support for HDR |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSettopHDRSupport"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "standards": [
            "none"
        ],
        "supportsHDR": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSettopHDRSupport"
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
function getSettopHDRSupport() {
  thunderJS.getSettopHDRSupport()
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
<button onclick="getSettopHDRSupport()">getSettopHDRSupport</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSettopHDRSupport(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getSettopMS12Capabilities"></a>
## *getSettopMS12Capabilities*


Retrieves the MS12 audio capabilities supported by the set-top box, such as Dolby Volume, Intelligent Equalizer, and Dialogue Enhancer. This function helps users understand the advanced audio features available for enhanced sound quality and customization.

### Related Functions  
[getSettopAudioCapabilities](#getSettopAudioCapabilities) : Provides a broader list of audio capabilities supported by the set-top box, including MS12 features.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.ms12Capabilities | array | A string [] of MS12 audio capabilities |
| result.ms12Capabilities[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSettopMS12Capabilities",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "ms12Capabilities": [
            "Dolby Volume"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSettopMS12Capabilities",
"params": {
"audioPort": "SPEAKER0"
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
function getSettopMS12Capabilities(audioPort) {
  thunderJS.getSettopMS12Capabilities({ audioPort: audioPort })
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
<button onclick="getSettopMS12Capabilities('SPEAKER0')">getSettopMS12Capabilities</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSettopMS12Capabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSinkAtmosCapability"></a>
## *getSinkAtmosCapability*


This API checks if the connected audio sink device supports Dolby Atmos capabilities. It ensures users can verify Atmos compatibility for enhanced audio experiences, particularly when using HDMI or ARC connections.

### Related Functions  
[setAudioAtmosOutputMode](#setAudioAtmosOutputMode) : Configures the output mode for Dolby Atmos audio.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.atmos_capability | integer | <sup>*(optional)*</sup> ATMOS Capability (`0` = off, `1` = open, `2` = rich, `3` = focused) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSinkAtmosCapability",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "atmos_capability": 2,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSinkAtmosCapability",
"params": {
"audioPort": "SPEAKER0"
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
function getSinkAtmosCapability(audioPort) {
  thunderJS.getSinkAtmosCapability({ audioPort: audioPort })
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
<button onclick="getSinkAtmosCapability('SPEAKER0')">getSinkAtmosCapability</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSinkAtmosCapability(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSoundMode"></a>
## *getSoundMode*


Retrieves the current audio sound mode for a specified audio port or all ports if none is specified. The sound mode determines how audio is processed and can include options like stereo, surround, passthrough, Dolby Digital, and more, ensuring an optimal listening experience tailored to your setup.

### Related Functions  
[setSoundMode](#setSoundMode) : Allows you to configure the audio sound mode for a specific port or all ports.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.soundMode | string | Sound mode. Possible values: `AUTO (Dolby Digital Plus)`, `AUTO (Dolby Digital 5.1)`, `AUTO (Stereo)`, `MONO`, `STEREO`, `SURROUND`, PASSTHRU |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSoundMode",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "soundMode": "STEREO",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSoundMode",
"params": {
"audioPort": "SPEAKER0"
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
function getSoundMode(audioPort) {
  thunderJS.getSoundMode({ audioPort: audioPort })
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
<button onclick="getSoundMode('SPEAKER0')">getSoundMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSoundMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSupportedAudioModes"></a>
## *getSupportedAudioModes*


The `getSupportedAudioModes` API provides a list of audio modes supported by the specified audio port, such as "STEREO," "PASSTHRU," or "AUTO (Dolby Digital 5.1)." This helps users understand the available audio configurations for their device, ensuring optimal audio output based on their preferences and connected equipment.

### Related Functions
[getSupportedAudioPorts](#getSupportedAudioPorts) : Retrieves the list of audio ports available on the device.
If a port name is specified, this returns the audio output modes supported by the connected sink device (EDID based). If the port is not connected, the return value is same as if `Null` is specified as the parameter.
For **Auto** mode in DS5, this API has the following extra specification:
* For HDMI port, this API returns `Stereo` mode, `Dolby Digital 5.1` mode and `Auto` mode;
* For SPDIF and HDMI ARC port, this API always returns `Surround` mode, `Stereo` mode, and `PASSTHRU` Mode;
* When `AUTO` mode is returned, it includes in parenthesis the best sound mode that the STB can output and the connected sink device can support, in the format of `AUTO` _(`Best Format`)_. For example, if the connected device supports surround, the auto mode string will be `AUTO (Dolby Digital 5.1)`.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedAudioModes | array | A string [] of supported audio modes |
| result.supportedAudioModes[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedAudioModes",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedAudioModes": [
            "STEREO"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedAudioModes",
"params": {
"audioPort": "SPEAKER0"
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
function getSupportedAudioModes(audioPort) {
  thunderJS.getSupportedAudioModes({ audioPort: audioPort })
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
<button onclick="getSupportedAudioModes('SPEAKER0')">getSupportedAudioModes</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedAudioModes(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSupportedAudioPorts"></a>
## *getSupportedAudioPorts*


Retrieves a list of all audio ports physically available on the device, such as HDMI or optical ports. This function helps users identify the supported audio output options for connecting external audio devices, ensuring compatibility and optimal audio setup.

### Related Functions  
[getConnectedAudioPorts](#getConnectedAudioPorts) : Provides a list of currently connected audio ports.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedAudioPorts | array | A string [] of supported audio ports |
| result.supportedAudioPorts[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedAudioPorts"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedAudioPorts": [
            "HDMI0"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedAudioPorts"
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
function getSupportedAudioPorts() {
  thunderJS.getSupportedAudioPorts()
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
<button onclick="getSupportedAudioPorts()">getSupportedAudioPorts</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedAudioPorts(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getSupportedMS12AudioProfiles"></a>
## *getSupportedMS12AudioProfiles*


Retrieves the list of supported MS12 audio profiles available for a specified audio port. These profiles, such as "Music," "Movie," or "Night," allow users to customize their audio experience based on their preferences or content type. This function is essential for ensuring compatibility and optimizing audio settings for enhanced sound quality.

### Related Functions  
[getMS12AudioProfile](#getMS12AudioProfile) : Retrieves the currently active MS12 audio profile.  
[setMS12AudioProfile](#setMS12AudioProfile) : Sets the desired MS12 audio profile.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedMS12AudioProfiles | array | A string [] of MS12 audio profiles |
| result.supportedMS12AudioProfiles[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedMS12AudioProfiles",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedMS12AudioProfiles": [
            "Movie"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "getSupportedMS12AudioProfiles",
"params": {
"audioPort": "HDMI0"
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
function getSupportedMS12AudioProfiles(audioPort) {
  thunderJS.DeviceInfo.supportedms12audioprofiles({ audioPort: audioPort })
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
<button onclick="getSupportedMS12AudioProfiles('HDMI0')">getSupportedMS12AudioProfiles</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedMS12AudioProfiles(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSupportedResolutions"></a>
## *getSupportedResolutions*


Retrieves the list of video resolutions supported by a specified video display or the default video port. This API helps users identify compatible resolutions for their connected devices, ensuring optimal video quality and compatibility. It simplifies the process of configuring display settings by providing a clear list of supported options.

### Related Functions  
[getSupportedTvResolutions](#getSupportedTvResolutions) : Retrieves the resolutions supported specifically by the connected TV.  
[getSupportedSettopResolutions](#getSupportedSettopResolutions) : Retrieves the resolutions supported by the set-top box.  
[getSupportedVideoDisplays](#getSupportedVideoDisplays) : Provides a list of available video displays.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.videoDisplay | string | <sup>*(optional)*</sup> Video display port name. The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedResolutions | array | A string array of supported resolutions on the selected video display port |
| result.supportedResolutions[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedResolutions",
    "params": {
        "videoDisplay": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedResolutions": [
            "1080p60"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedResolutions",
"params": {
"videoDisplay": "HDMI0"
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
function getSupportedResolutions(videoDisplay) {
  thunderJS.getSupportedResolutions({ videoDisplay: videoDisplay })
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
<button onclick="getSupportedResolutions('HDMI0')">getSupportedResolutions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedResolutions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSupportedSettopResolutions"></a>
## *getSupportedSettopResolutions*


Retrieves a list of video resolutions supported by the set-top box, such as "720p," "1080i," or "1080p60." This function helps users identify the optimal resolution settings for their set-top box to ensure the best viewing experience. It is particularly useful for configuring video output to match the capabilities of connected displays.

### Related Functions
[getSupportedResolutions](#getSupportedResolutions) : Retrieves all supported resolutions across various video output ports.  
[getSupportedTvResolutions](#getSupportedTvResolutions) : Retrieves the resolutions supported specifically by the connected TV.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedSettopResolutions | array | A string array of supported STB resolutions |
| result.supportedSettopResolutions[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedSettopResolutions"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedSettopResolutions": [
            "1080p60"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedSettopResolutions"
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
function getSupportedSettopResolutions() {
  thunderJS.getSupportedSettopResolutions()
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
<button onclick="getSupportedSettopResolutions()">getSupportedSettopResolutions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedSettopResolutions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getSupportedTvResolutions"></a>
## *getSupportedTvResolutions*


Retrieves the list of TV resolutions supported by the connected display, such as 480p, 720p, 1080p, and 2160p. This function helps users identify the optimal resolution settings for their TV, ensuring the best possible viewing experience.

### Related Functions
[getSupportedSettopResolutions](#getSupportedSettopResolutions) : Retrieves the resolutions supported by the set-top box.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.videoDisplay | string | <sup>*(optional)*</sup> Video display port name. The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedTvResolutions | array | A string [] of supported TV resolutions |
| result.supportedTvResolutions[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedTvResolutions",
    "params": {
        "videoDisplay": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedTvResolutions": [
            "1080p"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedTvResolutions",
"params": {
"videoDisplay": "HDMI0"
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
function getSupportedTvResolutions(videoDisplay) {
  thunderJS.getSupportedTvResolutions({ videoDisplay: videoDisplay })
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
<button onclick="getSupportedTvResolutions('HDMI0')">getSupportedTvResolutions</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedTvResolutions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getSupportedVideoDisplays"></a>
## *getSupportedVideoDisplays*


Identifies and retrieves the list of video output ports supported by the device, such as HDMI or other physical connections. This function helps users understand which video displays are available for use, ensuring compatibility with their setup.

### Related Functions  
[getConnectedVideoDisplays](#getConnectedVideoDisplays) : Provides information about currently connected video displays.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedVideoDisplays | array | a string [] of supported video display ports |
| result.supportedVideoDisplays[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedVideoDisplays"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedVideoDisplays": [
            "HDMI0"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedVideoDisplays"
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
function getSupportedVideoDisplays() {
  thunderJS.getSupportedVideoDisplays()
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
<button onclick="getSupportedVideoDisplays()">getSupportedVideoDisplays</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedVideoDisplays(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getSurroundVirtualizer"></a>
## *getSurroundVirtualizer*


Retrieves the current surround virtualizer settings for an audio port, allowing users to check the enhancement level applied to surround sound. This feature helps optimize audio output for a more immersive listening experience.

### Related Functions  
[setSurroundVirtualizer](#setSurroundVirtualizer) : Adjusts the surround virtualizer settings to customize audio enhancement.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mode | integer | Enables or disables volume leveling (`0` = off, `1` = on, `2` = auto) |
| result.boost | integer | Value between 0 and 96, where 0 means no boost and 96 means maximum boost |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSurroundVirtualizer",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "mode": 1,
        "boost": 90,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSurroundVirtualizer",
"params": {
"audioPort": "SPEAKER0"
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
function getSurroundVirtualizer(audioPort) {
  thunderJS.getSurroundVirtualizer(audioPort)
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
<button onclick="getSurroundVirtualizer('SPEAKER0')">getSurroundVirtualizer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSurroundVirtualizer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getTVHDRCapabilities"></a>
## *getTVHDRCapabilities*


This API checks if the connected TV supports HDR (High Dynamic Range) and identifies the specific HDR standards it supports, such as HDR10, Dolby Vision, or HLG. It helps users understand their TV's HDR capabilities to optimize video playback quality.

### Related Functions  
[getTvHDRSupport](#getTvHDRSupport) : Provides information about the HDR standards supported by the TV.
* 0x0 - HDRSTANDARD_NONE
* 0x1 - HDRSTANDARD_HDR10
* 0x2 - HDRSTANDARD_HLG
* 0x4 - HDRSTANDARD_DolbyVision
* 0x8 - HDRSTANDARD_TechnicolorPrime.
* 0x10 - HDRSTANDARD_HDR10PLUS
* 0x20 - HDRSTANDARD_SDR.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.capabilities | integer | The OR-ed value of supported HDR standards by the TV |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getTVHDRCapabilities"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "capabilities": 3,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getTVHDRCapabilities"
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
function getTVHDRCapabilities() {
  thunderJS.getTVHDRCapabilities()
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
<button onclick="getTVHDRCapabilities()">getTVHDRCapabilities</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getTVHDRCapabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getTvHDRSupport"></a>
## *getTvHDRSupport*


This API checks whether your TV supports HDR (High Dynamic Range) and provides details about the supported HDR standards, such as HDR10 or Dolby Vision. It helps users understand their TV's HDR capabilities, ensuring optimal video quality for HDR-enabled content.

### Related Functions  
[getSettopHDRSupport](#getSettopHDRSupport) : Retrieves HDR support details for the set-top box, complementing the TV's HDR capabilities.  
[getTVHDRCapabilities](#getTVHDRCapabilities) : Provides a broader overview of the TV's HDR capabilities, including supported standards.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.standards | array | A string [] of HDR capabilities. Possible values: `none`, `HDR10`, `HDR10PLUS`, `Dolby Vision`, `Technicolor Prime`, `SDR` |
| result.standards[#] | string |  |
| result.supportsHDR | boolean | Indicates support for HDR |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getTvHDRSupport"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "standards": [
            "none"
        ],
        "supportsHDR": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getTvHDRSupport"
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
function getTvHDRSupport() {
  thunderJS.getTvHDRSupport()
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
<button onclick="getTvHDRSupport()">getTvHDRSupport</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getTvHDRSupport(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getVideoFormat"></a>
## *getVideoFormat*


Provides the current video format (e.g., SDR, HDR10, HLG) being used by the device and lists all supported video formats. This helps users understand the active video output standard and compatibility with their display, ensuring optimal viewing quality.

### Related Functions  
[getSupportedVideoDisplays](#getSupportedVideoDisplays) : Retrieves the list of connected video displays.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedVideoFormat | array | A list of supported Video formats |
| result.supportedVideoFormat[#] | string |  |
| result.currentVideoFormat | string | The current video format |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getVideoFormat"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedVideoFormat": [
            "`SDR`, `HDR10`, `HDR10PLUS`, `HLG`, `DV`, `Technicolor Prime`"
        ],
        "currentVideoFormat": "SDR",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getVideoFormat"
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
function getVideoFormat() {
  thunderJS.getVideoFormat()
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
<button onclick="getVideoFormat()">getVideoFormat</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVideoFormat(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getVideoPortStatusInStandby"></a>
## *getVideoPortStatusInStandby*


Retrieves the current status of a specified video port during standby mode, indicating whether the port is enabled or disabled. This function helps users understand the operational state of their video ports when the system is in standby, ensuring better control over power and connectivity settings.

### Related Functions
[setVideoPortStatusInStandby](#setVideoPortStatusInStandby) : Allows users to enable or disable the video port during standby mode.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.portName | string | Video port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.videoPortStatusInStandby | boolean | <sup>*(optional)*</sup> video port status (enabled/disabled) in standby mode in case of success |
| result?.error_message | string | <sup>*(optional)*</sup> Error message in case of failure |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getVideoPortStatusInStandby",
    "params": {
        "portName": "HDMI0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "videoPortStatusInStandby": true,
        "error_message": "Internal error",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getVideoPortStatusInStandby",
"params": {
"portName": "HDMI0"
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
function getVideoPortStatusInStandby(portName) {
  thunderJS.getVideoPortStatusInStandby(portName)
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
<button onclick="getVideoPortStatusInStandby('HDMI0')">getVideoPortStatusInStandby</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVideoPortStatusInStandby(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["portName"] = "HDMI0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getVolumeLevel"></a>
## *getVolumeLevel*


Retrieves the current audio volume level of the device, providing users with precise information about the system's sound output. This function is useful for monitoring and adjusting audio settings to ensure an optimal listening experience.

### Related Functions
[setVolumeLevel](#setVolumeLevel) : Allows users to adjust the audio volume level of the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.volumeLevel | number | Value between 0 and 100, where 0 means no level and 100 means maximum level |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getVolumeLevel",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "volumeLevel": 50,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getVolumeLevel",
"params": {
"audioPort": "SPEAKER0"
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
function getVolumeLevel(audioPort) {
  thunderJS.getVolumeLevel({ audioPort: audioPort })
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
<button onclick="getVolumeLevel('SPEAKER0')">getVolumeLevel</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void getVolumeLevel(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
}
```
</details>


<a name="getVolumeLeveller"></a>
## *getVolumeLeveller*


The `getVolumeLeveller` API retrieves the current status and level of the volume leveller for a specified audio port, such as HDMI. This feature helps ensure consistent audio levels across different content, enhancing the listening experience by reducing sudden volume fluctuations. It is particularly useful for maintaining a balanced sound output in dynamic audio environments.

### Related Functions
[setVolumeLeveller](#setVolumeLeveller) : Adjusts the volume leveller settings, including enabling/disabling the feature and setting the desired level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mode | integer | Enables or disables volume leveling (`0` = off, `1` = on, `2` = auto) |
| result.level | integer | Value between 0 and 10, where 0 means no level and 10 means maximum level |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getVolumeLeveller",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "mode": 1,
        "level": 9,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getVolumeLeveller",
"params": {
"audioPort": "SPEAKER0"
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
function getVolumeLeveller(audioPort) {
  thunderJS.getVolumeLeveller({ audioPort: audioPort })
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
<button onclick="getVolumeLeveller('SPEAKER0')">getVolumeLeveller</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVolumeLeveller(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getZoomSetting"></a>
## *getZoomSetting*


Retrieves the current zoom setting for the video display, such as "None" or "Full," to help users understand how their content is being displayed on the screen. This function is useful for ensuring the video output matches user preferences or troubleshooting display issues.

### Related Functions  
[setZoomSetting](#setZoomSetting) : Allows users to modify the zoom setting for the video display.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.zoomSetting | string | Zoom setting. Possible values: `FULL`,  `NONE,`  `Letterbox 16x9`, `Letterbox 14x9`, `CCO`, `PanScan`, `Letterbox 2.21 on 4x3`, `Letterbox 2.21 on 16x9`, `Platform`, `Zoom 16x9`, `Pillarbox 4x3`, `Widescreen 4x3` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getZoomSetting"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "zoomSetting": "FULL",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DisplaySettings.getZoomSetting"}' http://127.0.0.1:9998/jsonrpc
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
function getZoomSetting() {
  thunderJS.getZoomSetting()
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
<button onclick="getZoomSetting()">getZoomSetting</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getZoomSetting(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="isConnectedDeviceRepeater"></a>
## *isConnectedDeviceRepeater*


Determines whether a connected device is functioning as a repeater, enabling signal transmission to other devices in the network. This is useful for verifying device roles in complex setups and ensuring seamless connectivity across multiple devices.

### Related Functions  
[readEDID](#readEDID) : Retrieves the Extended Display Identification Data (EDID) to understand device capabilities.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.HdcpRepeater | boolean | `true` if the device is an HDCP repeater otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.isConnectedDeviceRepeater"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "HdcpRepeater": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.isConnectedDeviceRepeater"
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
function isConnectedDeviceRepeater() {
  thunderJS.isConnectedDeviceRepeater()
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
<button onclick="isConnectedDeviceRepeater()">isConnectedDeviceRepeater</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void isConnectedDeviceRepeater(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="isSurroundDecoderEnabled"></a>
## *isSurroundDecoderEnabled*


Checks whether the surround decoder feature is currently enabled on the specified audio port. This function helps users verify if their audio setup is optimized for immersive surround sound playback, ensuring the best audio experience for supported content.

### Related Functions  
[enableSurroundDecoder](#enableSurroundDecoder) : Allows users to enable or disable the surround decoder feature.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.surroundDecoderEnable | boolean | <sup>*(optional)*</sup> Whether Surround Decoder is is enabled (`true`) or disabled (`false`) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.isSurroundDecoderEnabled",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "surroundDecoderEnable": true,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.isSurroundDecoderEnabled",
"params": {
"audioPort": "SPEAKER0"
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
function isSurroundDecoderEnabled(audioPort) {
  thunderJS.isSurroundDecoderEnabled({ audioPort: audioPort })
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
<button onclick="isSurroundDecoderEnabled('SPEAKER0')">isSurroundDecoderEnabled</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void isSurroundDecoderEnabled(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="readEDID"></a>
## *readEDID*


The `readEDID` API retrieves the Extended Display Identification Data (EDID) of connected video displays, providing detailed information about the display's capabilities, such as supported resolutions and refresh rates. This data is returned in a Base64-encoded format, making it easy to process and integrate into display configuration workflows. It is essential for ensuring optimal compatibility and performance between devices and displays.

### Related Functions  
[readHostEDID](#readHostEDID) : Retrieves the EDID of the host device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.EDID | string | <sup>*(optional)*</sup> A base64 encoded byte array string representing the EDID |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.readEDID"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "EDID": "AP///////wAQrMLQVEJTMQUdAQOANR546q11qVRNnSYPUFSlSwCBALMA0QBxT6lAgYDRwAEBVl4AoKCgKVAwIDUADighAAAaAAAA/wBNWTNORDkxVjFTQlQKAAAA/ABERUxMIFAyNDE4RAogAAAA/QAxVh1xHAAKICAgICAgARsCAxuxUJAFBAMCBxYBBhESFRMUHyBlAwwAEAACOoAYcTgtQFgsRQAOKCEAAB4BHYAYcRwWIFgsJQAOKCEAAJ6/FgCggDgTQDAgOgAOKCEAABp+OQCggDgfQDAgOgAOKCEAABoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA2A",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DisplaySettings.readEDID"}' http://127.0.0.1:9998/jsonrpc
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
function readEDID() {
  thunderJS.readEDID()
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
<button onclick="readEDID()">readEDID</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void readEDID(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="readHostEDID"></a>
## *readHostEDID*


Retrieves the EDID (Extended Display Identification Data) of the host device, which provides detailed information about the display's capabilities, such as supported resolutions and refresh rates. This function is essential for ensuring optimal compatibility and performance between the host device and connected displays.

### Related Functions  
[readEDID](#readEDID) : Retrieves the EDID of a specific connected display.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.EDID | string | <sup>*(optional)*</sup> A base64 encoded byte array string representing the EDID |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.readHostEDID"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "EDID": "AP///////wAQrMLQVEJTMQUdAQOANR546q11qVRNnSYPUFSlSwCBALMA0QBxT6lAgYDRwAEBVl4AoKCgKVAwIDUADighAAAaAAAA/wBNWTNORDkxVjFTQlQKAAAA/ABERUxMIFAyNDE4RAogAAAA/QAxVh1xHAAKICAgICAgARsCAxuxUJAFBAMCBxYBBhESFRMUHyBlAwwAEAACOoAYcTgtQFgsRQAOKCEAAB4BHYAYcRwWIFgsJQAOKCEAAJ6/FgCggDgTQDAgOgAOKCEAABp+OQCggDgfQDAgOgAOKCEAABoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA2A",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.readHostEDID"
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
function readHostEDID() {
  thunderJS.readHostEDID()
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
<button onclick="readHostEDID()">readHostEDID</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void readHostEDID(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="resetBassEnhancer"></a>
## *resetBassEnhancer*


Restores the bass enhancer settings of the specified audio port to their default values, ensuring optimal audio performance. This function is useful for troubleshooting or reverting unintended changes to bass enhancement configurations.

### Related Functions  
[getBassEnhancer](#getBassEnhancer) : Retrieves the current bass enhancer settings for the specified audio port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.resetBassEnhancer",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.resetBassEnhancer",
"params": {
"audioPort": "SPEAKER0"
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
function resetBassEnhancer(audioPort) {
  thunderJS.resetBassEnhancer({ audioPort: audioPort })
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
<button onclick="resetBassEnhancer('SPEAKER0')">resetBassEnhancer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void resetBassEnhancer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="resetDialogEnhancement"></a>
## *resetDialogEnhancement*


Restores the dialog enhancement settings for the specified audio port to their default values, ensuring optimal audio clarity for dialogue-heavy content. This function is useful for resetting any customizations or adjustments made to the dialog enhancement feature.

### Related Functions  
[getDialogEnhancement](#getDialogEnhancement) : Retrieves the current dialog enhancement settings.  
[setDialogEnhancement](#setDialogEnhancement) : Adjusts the dialog enhancement level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.resetDialogEnhancement",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.resetDialogEnhancement",
"params": {
"audioPort": "SPEAKER0"
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
function resetDialogEnhancement(audioPort) {
  thunderJS.resetDialogEnhancement(audioPort)
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
<button onclick="resetDialogEnhancement('SPEAKER0')">resetDialogEnhancement</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void resetDialogEnhancement(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
}
```
</details>


<a name="resetSurroundVirtualizer"></a>
## *resetSurroundVirtualizer*


Restores the surround virtualizer settings for a specified audio port to their default values, ensuring optimal audio performance and eliminating any custom adjustments that may have been applied. This function is useful for troubleshooting or resetting audio configurations to a baseline state.

### Related Functions  
[getSurroundVirtualizer](#getSurroundVirtualizer) : Retrieves the current surround virtualizer settings for the specified audio port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.resetSurroundVirtualizer",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.resetSurroundVirtualizer",
"params": {
"audioPort": "SPEAKER0"
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
function resetSurroundVirtualizer(audioPort) {
  thunderJS.resetSurroundVirtualizer({ audioPort: audioPort })
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
<button onclick="resetSurroundVirtualizer('SPEAKER0')">resetSurroundVirtualizer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void resetSurroundVirtualizer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="resetVolumeLeveller"></a>
## *resetVolumeLeveller*


Resets the volume leveller settings for a specified audio port (defaulting to HDMI0) to their original state. This ensures that any custom adjustments to the volume leveller are cleared, restoring the default audio leveling behavior. Ideal for troubleshooting or reverting to factory audio settings.

### Related Functions  
[getVolumeLeveller](#getVolumeLeveller) : Retrieves the current volume leveller settings, including its mode and level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.resetVolumeLeveller",
    "params": {
        "audioPort": "SPEAKER0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.resetVolumeLeveller",
"params": {
"audioPort": "SPEAKER0"
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
function resetVolumeLeveller(audioPort) {
  thunderJS.resetVolumeLeveller(audioPort)
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
<button onclick="resetVolumeLeveller('SPEAKER0')">resetVolumeLeveller</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void resetVolumeLeveller(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setAudioAtmosOutputMode"></a>
## *setAudioAtmosOutputMode*


Enables or disables Dolby Atmos output mode for connected audio devices, ensuring immersive sound quality when supported. This function is particularly useful for optimizing audio performance on HDMI-connected devices, such as soundbars or AV receivers.

### Related Functions  
[getAudioFormat](#getAudioFormat) : Retrieves the current audio format, including Dolby Atmos compatibility.  
[getSinkAtmosCapability](#getSinkAtmosCapability) : Checks if the connected audio device supports Dolby Atmos.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | boolean | enable or disable ATMOS audio output mode |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setAudioAtmosOutputMode",
    "params": {
        "enable": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setAudioAtmosOutputMode",
"params": {
"enable": true
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
function setAudioAtmosOutputMode(params) {
  thunderJS.setAudioAtmosOutputMode(params)
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
<button onclick="setAudioAtmosOutputMode({enable: true})">setAudioAtmosOutputMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setAudioAtmosOutputMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setAudioDelay"></a>
## *setAudioDelay*


Adjusts the audio delay for a connected audio output port to ensure proper synchronization between audio and video playback. This function is useful for eliminating lip-sync issues and enhancing the overall viewing experience.

### Related Functions  
[getAudioDelay](#getAudioDelay) : Retrieves the current audio delay setting for a specified audio output port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |
| params.audioDelay | string | Delay (in ms) on the selected audio port |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setAudioDelay",
    "params": {
        "audioPort": "HDMI0",
        "audioDelay": "0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setAudioDelay",
"params": {
"audioPort": "HDMI0",
"audioDelay": "0"
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
function setAudioDelay(params) {
  thunderJS.setAudioDelay(params)
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
<button onclick="setAudioDelay({audioPort: 'HDMI0', audioDelay: '0'})">setAudioDelay</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void setAudioDelay(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        parameters["audioDelay"] = "0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
}
```
</details>


<a name="setAudioDelayOffset"></a>
## *setAudioDelayOffset*


Adjusts the audio delay offset to synchronize audio with video playback, ensuring a seamless viewing experience. This function is particularly useful for resolving lip-sync issues caused by processing delays in audio or video systems.

### Related Functions  
[getAudioDelayOffset](#getAudioDelayOffset) : Retrieves the current audio delay offset setting.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |
| params.audioDelayOffset | string | Delay offset (in ms) on the selected audio port |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setAudioDelayOffset",
    "params": {
        "audioPort": "HDMI0",
        "audioDelayOffset": "0"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setAudioDelayOffset",
"params": {
"audioPort": "HDMI0",
"audioDelayOffset": "0"
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
function setAudioDelayOffset(params) {
  thunderJS.setAudioDelayOffset(params)
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
<button onclick="setAudioDelayOffset({audioPort: 'HDMI0', audioDelayOffset: '0'})">setAudioDelayOffset</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setAudioDelayOffset(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        parameters["audioDelayOffset"] = "0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setBassEnhancer"></a>
## *setBassEnhancer*


The `setBassEnhancer` API allows users to adjust the bass enhancement level for audio output, providing a richer and deeper sound experience. This feature is particularly useful for improving the audio quality of music, movies, or other media content. Users can customize the bass boost to suit their preferences, enhancing their overall listening experience.

### Related Functions
[getBassEnhancer](#getBassEnhancer) : Retrieves the current bass enhancement settings.  
[resetBassEnhancer](#resetBassEnhancer) : Resets the bass enhancement settings to their default values.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.bassBoost | integer | Value between 0 and 100, where 0 means no bass boost (disabled) and 100 means max bass boost |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setBassEnhancer",
    "params": {
        "audioPort": "SPEAKER0",
        "bassBoost": 50
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setBassEnhancer",
"params": {
"audioPort": "SPEAKER0",
"bassBoost": 50
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
function setBassEnhancer(params) {
  thunderJS.setBassEnhancer(params)
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
<button onclick="setBassEnhancer({audioPort: 'SPEAKER0', bassBoost: 50})">setBassEnhancer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setBassEnhancer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["bassBoost"] = 50;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setCurrentResolution"></a>
## *setCurrentResolution*


This API allows users to change the resolution of a specified video display, ensuring optimal viewing quality based on their preferences or device capabilities. It triggers a notification when the resolution is successfully updated, making it easy to track changes in display settings.

### Related Functions  
[getCurrentResolution](#getCurrentResolution) : Retrieves the current resolution of the video display.

### Events

| Event | Description |
| :-------- | :-------- |
| [resolutionPreChange](#resolutionPreChange) | Triggered when the resolution of the video display is about to change. |
| [resolutionChanged](#resolutionChanged) | Triggered when the resolution is changed by the user and returns the current resolution. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoDisplay | string | Video display port name. The default port is `HDMI0` if no port is specified |
| params.resolution | string | Video display resolution |
| params?.persist | boolean | <sup>*(optional)*</sup> Persists the resolution |
| params?.ignoreEdid | boolean | <sup>*(optional)*</sup> Ignore the supported resolutions as transmitted by the connected TV EDID |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setCurrentResolution",
    "params": {
        "videoDisplay": "HDMI0",
        "resolution": "1080p",
        "persist": true,
        "ignoreEdid": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setCurrentResolution",
"params": {
"videoDisplay": "HDMI0",
"resolution": "1080p",
"persist": true,
"ignoreEdid": true
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
function setCurrentResolution(params) {
  thunderJS.setCurrentResolution(params)
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
<button onclick="setCurrentResolution({videoDisplay: 'HDMI0', resolution: '1080p', persist: true, ignoreEdid: true})">setCurrentResolution</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setCurrentResolution(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        parameters["resolution"] = "1080p";
        parameters["persist"] = true;
        parameters["ignoreEdid"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDialogEnhancement"></a>
## *setDialogEnhancement*


Enhances the clarity of dialogue in audio playback by adjusting the dialog enhancement level. This feature is particularly useful for improving speech intelligibility in movies, TV shows, or other content with complex soundtracks.

### Related Functions  
[getDialogEnhancement](#getDialogEnhancement) : Retrieves the current dialog enhancement level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.enhancerlevel | integer | Value between 0 and 16, where 0 means no enhancement and 16 means maximum enhancement |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setDialogEnhancement",
    "params": {
        "audioPort": "SPEAKER0",
        "enhancerlevel": 0
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setDialogEnhancement",
"params": {
"audioPort": "SPEAKER0",
"enhancerlevel": 0
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
function setDialogEnhancement(params) {
  thunderJS.setDialogEnhancement(params)
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
<button onclick="setDialogEnhancement({audioPort: 'SPEAKER0', enhancerlevel: 0})">setDialogEnhancement</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDialogEnhancement(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["enhancerlevel"] = 0;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDolbyVolumeMode"></a>
## *setDolbyVolumeMode*


Allows users to enable or disable Dolby Volume Mode on a specified audio port, optimizing audio levels for a consistent listening experience. This feature ensures balanced sound output, regardless of content or source, enhancing overall audio quality.

### Related Functions
[getDolbyVolumeMode](#getDolbyVolumeMode) : Retrieves the current status of Dolby Volume Mode.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.dolbyVolumeMode | boolean | Whether Dolby Volume mode is enabled (`true`) or disabled (`false`) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setDolbyVolumeMode",
    "params": {
        "dolbyVolumeMode": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DisplaySettings.setDolbyVolumeMode", "params": {"dolbyVolumeMode": true}}' http://127.0.0.1:9998/jsonrpc
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
function setDolbyVolumeMode(dolbyVolumeMode) {
  thunderJS.setDolbyVolumeMode(dolbyVolumeMode)
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
<button onclick="setDolbyVolumeMode(true)">setDolbyVolumeMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDolbyVolumeMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["dolbyVolumeMode"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDRCMode"></a>
## *setDRCMode*


The `setDRCMode` API allows users to configure the Dynamic Range Compression (DRC) settings for audio output, optimizing sound levels for different environments. This feature is particularly useful for balancing loud and soft sounds, ensuring a consistent listening experience whether you're watching movies late at night or in a noisy setting. By adjusting the DRC mode, users can enhance audio clarity and maintain comfort without frequent volume adjustments.

### Related Functions
[getDRCMode](#getDRCMode) : Retrieves the current Dynamic Range Compression (DRC) mode setting.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.DRCMode | integer | Value of 0 or 1, where 0 is Line mode and 1 is RF mode |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setDRCMode",
    "params": {
        "audioPort": "SPEAKER0",
        "DRCMode": 1
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setDRCMode",
"params": {
"audioPort": "SPEAKER0",
"DRCMode": 1
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
function setDRCMode(params) {
  thunderJS.setDRCMode(params)
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
<button onclick="setDRCMode({audioPort: 'SPEAKER0', DRCMode: 1})">setDRCMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDRCMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["DRCMode"] = 1;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setEnableAudioPort"></a>
## *setEnableAudioPort*


Enables or disables a specified audio port, such as HDMI ARC/eARC, allowing users to control audio output settings for connected devices. This function ensures persistent user preferences and verifies the port's status to provide seamless audio configuration.

### Related Functions  
[getEnableAudioPort](#getEnableAudioPort) : Retrieves the current enablement status of a specified audio port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |
| params.enable | boolean | `true` enables the specified audio port. `false` disables the specified audio port |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setEnableAudioPort",
    "params": {
        "audioPort": "HDMI0",
        "enable": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DisplaySettings.setEnableAudioPort", "params": {"audioPort": "HDMI0", "enable": true}}' http://127.0.0.1:9998/jsonrpc
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
function setEnableAudioPort(params) {
  thunderJS.setEnableAudioPort(params)
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
<button onclick="setEnableAudioPort({ audioPort: 'HDMI0', enable: true })">setEnableAudioPort</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setEnableAudioPort(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "HDMI0";
        parameters["enable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setForceHDRMode"></a>
## *setForceHDRMode*


This API allows users to manually set the HDR mode for the connected video display, ensuring optimal visual quality based on the selected HDR standard (e.g., HDR10, Dolby Vision, HLG). It is particularly useful for overriding automatic HDR settings when specific content or display preferences require a tailored HDR configuration.

### Related Functions  
[getTvHDRSupport](#getTvHDRSupport) : Retrieves the HDR capabilities supported by the connected TV.  
[getSettopHDRSupport](#getSettopHDRSupport) : Provides information about the HDR standards supported by the set-top box.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.hdr_mode | boolean | <sup>*(optional)*</sup> `true` to force the HDR format or `false` to reset the mode to the default |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setForceHDRMode",
    "params": {
        "hdr_mode": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setForceHDRMode",
"params": {
"hdr_mode": true
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
function setForceHDRMode(hdr_mode) {
  thunderJS.setForceHDRMode(hdr_mode)
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
<button onclick="setForceHDRMode(true)">setForceHDRMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setForceHDRMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["hdr_mode"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setGain"></a>
## *setGain*


Adjusts the audio gain level for a specified audio output port, allowing users to fine-tune the volume dynamics of their audio system. This function ensures the gain value stays within a safe range to prevent distortion or damage to the audio equipment.

### Related Functions  
[getGain](#getGain) : Retrieves the current audio gain level for the specified audio output port.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.gain | number | Value between -2080 and 480, where -2080 means negative gain and 480 means maximum gain |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setGain",
    "params": {
        "audioPort": "SPEAKER0",
        "gain": 10.0
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setGain",
"params": {
"audioPort": "SPEAKER0",
"gain": 10.0
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
function setGain(params) {
  thunderJS.setGain(params)
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
<button onclick="setGain({audioPort: 'SPEAKER0', gain: 10.0})">setGain</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setGain(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["gain"] = 10.0;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setGraphicEqualizerMode"></a>
## *setGraphicEqualizerMode*


Adjust the audio output by setting the graphic equalizer mode, allowing users to fine-tune sound frequencies for a customized listening experience. This function is ideal for optimizing audio quality based on personal preferences or specific content types.

### Related Functions  
[getGraphicEqualizerMode](#getGraphicEqualizerMode) : Retrieve the current graphic equalizer mode to understand or verify the active audio settings.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.graphicEqualizerMode | integer | Graphic Equalizer mode (`0` = off, `1` = open, `2` = rich, `3` = focused) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setGraphicEqualizerMode",
    "params": {
        "audioPort": "SPEAKER0",
        "graphicEqualizerMode": 2
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setGraphicEqualizerMode",
"params": {
"audioPort": "SPEAKER0",
"graphicEqualizerMode": 2
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
function setGraphicEqualizerMode(params) {
  thunderJS.setGraphicEqualizerMode(params)
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
<button onclick="setGraphicEqualizerMode({audioPort: 'SPEAKER0', graphicEqualizerMode: 2})">setGraphicEqualizerMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setGraphicEqualizerMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["graphicEqualizerMode"] = 2;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setIntelligentEqualizerMode"></a>
## *setIntelligentEqualizerMode*


Adjusts the Intelligent Equalizer mode to optimize audio output based on predefined settings, enhancing the listening experience for different content types. This function allows users to customize sound profiles for improved clarity and balance.

### Related Functions  
[getIntelligentEqualizerMode](#getIntelligentEqualizerMode) : Retrieves the current Intelligent Equalizer mode setting.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.intelligentEqualizerMode | integer | Intelligent Equalizer mode (`0` = unset, `1` = open, `2` = rich, `3` = focused) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setIntelligentEqualizerMode",
    "params": {
        "audioPort": "SPEAKER0",
        "intelligentEqualizerMode": 2
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setIntelligentEqualizerMode",
"params": {
"audioPort": "SPEAKER0",
"intelligentEqualizerMode": 2
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
function setIntelligentEqualizerMode(params) {
  thunderJS.setIntelligentEqualizerMode(params)
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
<button onclick="setIntelligentEqualizerMode({audioPort: 'SPEAKER0', intelligentEqualizerMode: 2})">setIntelligentEqualizerMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setIntelligentEqualizerMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["intelligentEqualizerMode"] = 2;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMISteering"></a>
## *setMISteering*


Enables or disables MI Steering, a feature that optimizes audio output for specific configurations, ensuring a better listening experience. This API is useful for tailoring audio settings to match user preferences or connected devices.

### Related Functions
[getMISteering](#getMISteering) : Retrieves the current status of MI Steering (enabled or disabled).

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.MISteeringEnable | boolean | Whether Media Intelligence Steering is enabled (`true`) or disabled (`false`) |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setMISteering",
    "params": {
        "audioPort": "SPEAKER0",
        "MISteeringEnable": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setMISteering",
"params": {
"audioPort": "SPEAKER0",
"MISteeringEnable": true
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
function setMISteering(params) {
  thunderJS.setMISteering(params)
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
<button onclick="setMISteering({ audioPort: 'SPEAKER0', MISteeringEnable: true })">setMISteering</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMISteering(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["MISteeringEnable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMS12AudioCompression"></a>
## *setMS12AudioCompression*


This API allows users to configure the audio compression level for MS12 (Dolby Audio) settings, optimizing sound quality and dynamic range based on their preferences or listening environment. Adjusting the compression level can enhance audio clarity, especially in scenarios with varying sound intensities, such as movies or live broadcasts.

### Related Functions  
[getMS12AudioCompression](#getMS12AudioCompression) : Retrieves the current MS12 audio compression level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.compresionLevel | integer | Value between 0 and 10, where 0 means no compression and 10 means maximum compression |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setMS12AudioCompression",
    "params": {
        "audioPort": "SPEAKER0",
        "compresionLevel": 5
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setMS12AudioCompression",
"params": {
"audioPort": "SPEAKER0",
"compresionLevel": 5
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
function setMS12AudioCompression(params) {
  thunderJS.setMS12AudioCompression(params)
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
<button onclick="setMS12AudioCompression({audioPort: 'SPEAKER0', compresionLevel: 5})">setMS12AudioCompression</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMS12AudioCompression(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["compresionLevel"] = 5;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMS12AudioProfile"></a>
## *setMS12AudioProfile*


Allows users to configure the MS12 audio profile for their device, optimizing audio output for specific use cases such as movies, music, or dialogue clarity. This function ensures a tailored audio experience by selecting a profile that matches the user's preferences or content type.

### Related Functions  
[getMS12AudioProfile](#getMS12AudioProfile) : Retrieves the currently active MS12 audio profile.  
[getSupportedMS12AudioProfiles](#getSupportedMS12AudioProfiles) : Lists all MS12 audio profiles supported by the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.ms12AudioProfile | string | An MS12 audio profile name from `getSupportedMS12AudioProfile` |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setMS12AudioProfile",
    "params": {
        "audioPort": "SPEAKER0",
        "ms12AudioProfile": "Game"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setMS12AudioProfile",
"params": {
"audioPort": "SPEAKER0",
"ms12AudioProfile": "Game"
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
function setMS12AudioProfile(params) {
  thunderJS.setMS12AudioProfile(params)
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
<button onclick="setMS12AudioProfile({ audioPort: 'SPEAKER0', ms12AudioProfile: 'Game' })">setMS12AudioProfile</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMS12AudioProfile(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["ms12AudioProfile"] = "Game";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMS12ProfileSettingsOverride"></a>
## *setMS12ProfileSettingsOverride*


This API allows users to customize specific settings within an MS12 audio profile, such as enabling or modifying advanced audio features for a tailored listening experience. It is useful for fine-tuning audio output to match personal preferences or specific content requirements.

### Related Functions  
[getMS12AudioProfile](#getMS12AudioProfile) : Retrieves the currently active MS12 audio profile.  
[getSupportedMS12AudioProfiles](#getSupportedMS12AudioProfiles) : Lists all MS12 audio profiles supported by the system.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.operation | string | The audio profile state |
| params.profileName | string | An MS12 audio profile name from `getSupportedMS12AudioProfile` |
| params.ms12SettingsName | string | An ms12 setting name |
| params.ms12SettingsValue | string | The value to set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setMS12ProfileSettingsOverride",
    "params": {
        "audioPort": "SPEAKER0",
        "operation": "...",
        "profileName": "Sports",
        "ms12SettingsName": "Dialog Enhance",
        "ms12SettingsValue": "On"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setMS12ProfileSettingsOverride",
"params": {
"audioPort": "SPEAKER0",
"operation": "...",
"profileName": "Sports",
"ms12SettingsName": "Dialog Enhance",
"ms12SettingsValue": "On"
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
function setMS12ProfileSettingsOverride(params) {
  thunderJS.setMS12ProfileSettingsOverride(params)
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
<button onclick="setMS12ProfileSettingsOverride({
  audioPort: 'SPEAKER0',
  operation: '...',
  profileName: 'Sports',
  ms12SettingsName: 'Dialog Enhance',
  ms12SettingsValue: 'On'
})">setMS12ProfileSettingsOverride</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMS12ProfileSettingsOverride(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["operation"] = "...";
        parameters["profileName"] = "Sports";
        parameters["ms12SettingsName"] = "Dialog Enhance";
        parameters["ms12SettingsValue"] = "On";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMuted"></a>
## *setMuted*


The `setMuted` API allows users to enable or disable the mute function for a specified audio port, such as HDMI. This ensures flexibility in managing audio output, whether you want to silence the sound temporarily or restore it. The API also triggers a notification when the mute status changes, keeping users informed in real time.

### Related Functions
[getMuted](#getMuted) : Retrieves the current mute status of the audio port.

### Events

| Event | Description |
| :-------- | :-------- |
| [muteStatusChanged](#muteStatusChanged) | Triggered when the mute status changed. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.muted | boolean | mute or unmute audio |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setMuted",
    "params": {
        "audioPort": "SPEAKER0",
        "muted": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setMuted",
"params": {
"audioPort": "SPEAKER0",
"muted": true
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
function setMuted(params) {
  thunderJS.setMuted(params)
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
<button onclick="setMuted({ audioPort: 'SPEAKER0', muted: true })">setMuted</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMuted(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["muted"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setPreferredColorDepth"></a>
## *setPreferredColorDepth*


Allows users to set their preferred color depth (e.g., 8 Bit, 10 Bit, 12 Bit, or Auto) for a specified video display, enhancing the visual experience by optimizing color quality based on the display's capabilities. This function ensures compatibility with the connected display and provides a tailored viewing experience.

### Related Functions  
[getPreferredColorDepth](#getPreferredColorDepth) : Retrieves the currently set preferred color depth for a specified video display.
.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoDisplay | string | Video display port name. The default port is `HDMI0` if no port is specified |
| params.colorDepth | string | Video display color depth. (must be one of the following: *8 Bit*, *10 Bit*, *12 Bit*, *Auto*) |
| params?.persist | boolean | <sup>*(optional)*</sup> Persists the color depth |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setPreferredColorDepth",
    "params": {
        "videoDisplay": "HDMI0",
        "colorDepth": "12 Bit",
        "persist": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary \
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setPreferredColorDepth",
"params": {
"videoDisplay": "HDMI0",
"colorDepth": "12 Bit",
"persist": true
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
function setPreferredColorDepth(params) {
  thunderJS.setPreferredColorDepth(params)
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
<button onclick="setPreferredColorDepth({videoDisplay: 'HDMI0', colorDepth: '12 Bit', persist: true})">setPreferredColorDepth</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setPreferredColorDepth(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoDisplay"] = "HDMI0";
        parameters["colorDepth"] = "12 Bit";
        parameters["persist"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setScartParameter"></a>
## *setScartParameter*


This API allows users to configure specific SCART parameters for connected devices, ensuring optimal compatibility and performance. It is useful for customizing settings like video or audio output to match the requirements of SCART-enabled equipment.

### Related Functions  
[getCurrentOutputSettings](#getCurrentOutputSettings) : Retrieve the current output settings for connected devices.  
[getVideoPortStatusInStandby](#getVideoPortStatusInStandby) : Check the status of video ports when the system is in standby mode.

Possible values:
| **Parameter** | **ParameterData** |
| `aspect_ratio` | `4x3` or `16x9` |
| `tv_startup` | `on` or `off` |
| `rgb` | `on` (disables cvbs) |
| `cvbs` | `on` (disables rgb) |
| `macrovision` | not implemented |
| `cgms` |  `disabled`, `copyNever`, `copyOnce`, `copyFreely`, or `copyNoMore` |
| `port` | `on` or `off` |.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.scartParameter | string | SCART parameter name |
| params?.scartParameterData | string | <sup>*(optional)*</sup> SCART parameter data |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setScartParameter",
    "params": {
        "scartParameter": "aspect_ratio",
        "scartParameterData": "4x3"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setScartParameter",
"params": {
"scartParameter": "aspect_ratio",
"scartParameterData": "4x3"
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
function setScartParameter(params) {
  thunderJS.setScartParameter(params)
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
<button onclick="setScartParameter({scartParameter: 'aspect_ratio', scartParameterData: '4x3'})">setScartParameter</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setScartParameter(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["scartParameter"] = "aspect_ratio";
        parameters["scartParameterData"] = "4x3";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setSoundMode"></a>
## *setSoundMode*


The `setSoundMode` API allows users to configure the audio output mode for their device, such as Mono, Stereo, Surround, or Passthru. This ensures an optimized listening experience tailored to the user's preferences and the connected audio setup. It can apply settings to specific audio ports or all connected ports if none are specified.

### Related Functions  
[getSoundMode](#getSoundMode) : Retrieves the current audio output mode for the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioPort | string | Audio port name |
| params.soundMode | string | Sound mode. Possible values: `AUTO (Dolby Digital Plus)`, `AUTO (Dolby Digital 5.1)`, `AUTO (Stereo)`, `MONO`, `STEREO`, `SURROUND`, PASSTHRU |
| params?.persist | boolean | <sup>*(optional)*</sup> persists the sound mode |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setSoundMode",
    "params": {
        "audioPort": "HDMI0",
        "soundMode": "STEREO",
        "persist": true
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setSoundMode",
"params": {
"audioPort": "SPEAKER0"
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
function setSoundMode(audioPort) {
  thunderJS.setSoundMode(audioPort)
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
<button onclick="setSoundMode('SPEAKER0')">setSoundMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setSoundMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setSurroundVirtualizer"></a>
## *setSurroundVirtualizer*


Enhances your audio experience by adjusting surround sound settings, including mode and boost levels, to create a more immersive sound environment. This function allows users to customize the surround virtualizer settings for optimal audio performance based on their preferences or content type.

### Related Functions  
[getSurroundVirtualizer](#getSurroundVirtualizer) : Retrieves the current surround virtualizer settings, including mode and boost levels.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.mode | integer | Enables or disables volume leveling (`0` = off, `1` = on, `2` = auto) |
| params.boost | integer | Value between 0 and 96, where 0 means no boost and 96 means maximum boost |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setSurroundVirtualizer",
    "params": {
        "audioPort": "SPEAKER0",
        "mode": 1,
        "boost": 90
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setSurroundVirtualizer",
"params": {
"audioPort": "SPEAKER0",
"mode": 1,
"boost": 90
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
function setSurroundVirtualizer(params) {
  thunderJS.setSurroundVirtualizer(params)
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
<button onclick="setSurroundVirtualizer({audioPort: 'SPEAKER0', mode: 1, boost: 90})">setSurroundVirtualizer</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setSurroundVirtualizer(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["mode"] = 1;
        parameters["boost"] = 90;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVideoPortStatusInStandby"></a>
## *setVideoPortStatusInStandby*


Allows users to enable or disable the video port functionality while the device is in standby mode. This feature is useful for managing power consumption and ensuring the video port behaves as desired during standby, such as maintaining or cutting off video signals.

### Related Functions  
[getVideoPortStatusInStandby](#getVideoPortStatusInStandby) : Retrieves the current status of the video port in standby mode.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.portName | string | Video port name |
| params.enabled | boolean | Enable video port status to be used in standby mode |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.error_message | string | <sup>*(optional)*</sup> Error message in case of failure |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setVideoPortStatusInStandby",
    "params": {
        "portName": "HDMI0",
        "enabled": true
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "error_message": "internal error",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setVideoPortStatusInStandby",
"params": {
"portName": "HDMI0",
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
function setVideoPortStatusInStandby(params) {
  thunderJS.setVideoPortStatusInStandby(params)
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
<button onclick="setVideoPortStatusInStandby({ portName: 'HDMI0', enabled: true })">setVideoPortStatusInStandby</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVideoPortStatusInStandby(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["portName"] = "HDMI0";
        parameters["enabled"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVolumeLevel"></a>
## *setVolumeLevel*


The `setVolumeLevel` API allows users to adjust the audio output volume to a desired level. This function ensures a customized listening experience by enabling precise control over the volume settings. It is particularly useful for tailoring audio levels to suit individual preferences or specific environments.

### Related Functions  
[getVolumeLevel](#getVolumeLevel) : Retrieves the current audio output volume level.

### Events

| Event | Description |
| :-------- | :-------- |
| [volumeLevelChanged](#volumeLevelChanged) | Triggered when the volume level changed. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.volumeLevel | number | Value between 0 and 100, where 0 means no level and 100 means maximum level |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setVolumeLevel",
    "params": {
        "audioPort": "SPEAKER0",
        "volumeLevel": 50
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setVolumeLevel",
"params": {
"audioPort": "SPEAKER0",
"volumeLevel": 50
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
function setVolumeLevel(params) {
  thunderJS.setVolumeLevel(params)
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
<button onclick="setVolumeLevel({audioPort: 'SPEAKER0', volumeLevel: 50})">setVolumeLevel</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVolumeLevel(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["volumeLevel"] = 50;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setVolumeLeveller"></a>
## *setVolumeLeveller*


Adjusts the volume leveller settings to optimize audio consistency across different content types. This API allows users to set the level and mode of the volume leveller, ensuring a balanced listening experience by reducing sudden changes in audio levels.

### Related Functions  
[getVolumeLeveller](#getVolumeLeveller) : Retrieves the current volume leveller settings, including mode and level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.audioPort | string | <sup>*(optional)*</sup> Audio port name (`HDMI0`, `SPEAKER0`, `SPDIF0`, and so on). The default port is `HDMI0` if no port is specified |
| params.mode | integer | Enables or disables volume leveling (`0` = off, `1` = on, `2` = auto) |
| params.level | integer | Value between 0 and 10, where 0 means no level and 10 means maximum level |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setVolumeLeveller",
    "params": {
        "audioPort": "SPEAKER0",
        "mode": 1,
        "level": 9
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setVolumeLeveller",
"params": {
"audioPort": "SPEAKER0",
"mode": 1,
"level": 9
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
function setVolumeLeveller(params) {
  thunderJS.setVolumeLeveller(params)
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
<button onclick="setVolumeLeveller({audioPort: 'SPEAKER0', mode: 1, level: 9})">setVolumeLeveller</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVolumeLeveller(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["audioPort"] = "SPEAKER0";
        parameters["mode"] = 1;
        parameters["level"] = 9;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setZoomSetting"></a>
## *setZoomSetting*


This API allows users to adjust the zoom setting of their video display, enabling customization of how content is presented on the screen (e.g., "Full" or "None"). It ensures an optimal viewing experience by tailoring the display format to user preferences or specific content requirements.

### Related Functions  
[getZoomSetting](#getZoomSetting) : Retrieves the current zoom setting of the video display.

### Events

| Event | Description |
| :-------- | :-------- |
| [zoomSettingUpdated](#zoomSettingUpdated) | Triggered when the zoom setting changes and returns the zoom setting values for all video display types. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.zoomSetting | string | Zoom setting. Possible values: `FULL`,  `NONE,`  `Letterbox 16x9`, `Letterbox 14x9`, `CCO`, `PanScan`, `Letterbox 2.21 on 4x3`, `Letterbox 2.21 on 16x9`, `Platform`, `Zoom 16x9`, `Pillarbox 4x3`, `Widescreen 4x3` |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.setZoomSetting",
    "params": {
        "zoomSetting": "FULL"
    }
}
```

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



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.setZoomSetting",
"params": {
"zoomSetting": "FULL"
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
function setZoomSetting(zoomSetting) {
  thunderJS.setZoomSetting(zoomSetting)
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
<button onclick="setZoomSetting('FULL')">setZoomSetting</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setZoomSetting(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["zoomSetting"] = "FULL";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getColorDepthCapabilities"></a>
## *getColorDepthCapabilities*


Retrieves the supported color depth options for a specified video display, such as "8 Bit," "10 Bit," "12 Bit," or "Auto." This API helps users understand the color depth capabilities of their connected display, ensuring optimal video quality settings. If no specific capabilities are detected, it returns "none."

### Related Functions
[getPreferredColorDepth](#getPreferredColorDepth) : Retrieves the currently preferred color depth setting for the video display.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result?.getColorDepthCapabilities | array | <sup>*(optional)*</sup> A string array of supported STB color depth capabilities |
| result?.getColorDepthCapabilities[#] | string | <sup>*(optional)*</sup>  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getColorDepthCapabilities"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "getColorDepthCapabilities": [
            "8 Bit"
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getColorDepthCapabilities"
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
function getColorDepthCapabilities() {
  thunderJS.getColorDepthCapabilities()
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
<button onclick="getColorDepthCapabilities()">getColorDepthCapabilities</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getColorDepthCapabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getSupportedMS12Config"></a>
## *getSupportedMS12Config*


Retrieves the supported MS12 (Dolby MS12) audio configuration for the platform, providing details about the audio features available, such as Dolby Volume, Intelligent Equalizer, and Dialogue Enhancer. This API helps users understand the advanced audio capabilities of their device for an enhanced listening experience.

### Related Functions  
[getSettopMS12Capabilities](#getSettopMS12Capabilities) : Provides a detailed list of MS12 audio capabilities supported by the set-top box.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.ms12config | string | Supported ms12 config by platforms, possible values, CONFIG_Z, CONFIG_X, CONFIG_Y, CONFIG_NONE |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DisplaySettings.getSupportedMS12Config"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "ms12config": "CONFIG_X",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DisplaySettings.getSupportedMS12Config"
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
function getSupportedMS12Config() {
  thunderJS.getSupportedMS12Config()
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
<button onclick="getSupportedMS12Config()">getSupportedMS12Config</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getSupportedMS12Config(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

The following events are provided by the org.rdk.DisplaySettings plugin:

DisplaySettings interface events:

| Event | Description |
| :-------- | :-------- |
| [activeInputChanged](#activeInputChanged) | Triggered on active input change (RxSense) |
| [audioFormatChanged](#audioFormatChanged) | Triggered when the configured audio format changes |
| [connectedAudioPortUpdated](#connectedAudioPortUpdated) | Triggered when the connected audio port is updated |
| [connectedVideoDisplaysUpdated](#connectedVideoDisplaysUpdated) | Triggered when the connected video display is updated and returns the connected video displays |
| [resolutionChanged](#resolutionChanged) | Triggered when the resolution is changed by the user and returns the current resolution |
| [resolutionPreChange](#resolutionPreChange) | Triggered on resolution pre-change |
| [zoomSettingUpdated](#zoomSettingUpdated) | Triggered when the zoom setting changes and returns the zoom setting values for all video display types |
| [videoFormatChanged](#videoFormatChanged) | Triggered when the video format of connected video port changes and returns the new video format along with other supported formats of that video port |
| [AtmosCapabilityChanged](#AtmosCapabilityChanged) | Triggered when the audio sink device Atmos capability is changed |
| [muteStatusChanged](#muteStatusChanged) | Triggered when the mute status changed |
| [volumeLevelChanged](#volumeLevelChanged) | Triggered when the volume level changed |


<a name="activeInputChanged"></a>
## *activeInputChanged*


The *activeInputChanged* event notifies users when the active input status of the device changes. This event is triggered whenever the device detects a change in the active input, such as when a connected video display or HDMI port becomes active or inactive. For example, if a TV is turned on or off, or if an HDMI cable is plugged in or removed, this event will be triggered to reflect the updated input status. This ensures users are informed about the current state of the device's input connections.

### Related Functions  
[getActiveInput](#getActiveInput) : This function retrieves the current active input status of the device. It is directly related to the *activeInputChanged* event, as it provides the updated input state when the event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.activeInput | boolean | `true` = RXSENSE_ON, `false` = RXSENSE_OFF |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.activeInputChanged",
    "params": {
        "activeInput": true
    }
}
```

<a name="audioFormatChanged"></a>
## *audioFormatChanged*


The *audioFormatChanged* event is triggered whenever there is a change in the audio format being used by the system. This event informs users about updates to the audio format, such as switching between PCM, Dolby Atmos, AAC, or other supported formats. It ensures that users are aware of the current audio configuration, which can impact sound quality and compatibility with connected devices.  

### Related Functions  
[getAudioFormat](#getAudioFormat) : This function retrieves the current audio format, which is directly related to the *audioFormatChanged* event. When the audio format changes, this function can be used to check the updated format.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.supportedAudioFormat | array | A list of supported audio formats |
| params.supportedAudioFormat[#] | string |  |
| params.currentAudioFormat | string | The currently set audio format |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.audioFormatChanged",
    "params": {
        "supportedAudioFormat": [
            "`NONE`, `PCM`, `DOLBY AC3`, `DOLBY EAC3`, `DOLBY AC4`, `DOLBY MAT', 'DOLBY TRUEHD', 'DOLBY EAC3 ATMOS', 'DOLBY TRUEHD ATMOS', 'DOLBY MAT ATMOS', 'DOLBY AC4 ATMOS'"
        ],
        "currentAudioFormat": "PCM"
    }
}
```

<a name="connectedAudioPortUpdated"></a>
## *connectedAudioPortUpdated*


The `connectedAudioPortUpdated` event notifies users when the connection status of an audio port changes. This event is triggered whenever an audio port, such as HDMI ARC or a headphone jack, is connected or disconnected. For example, if you plug in headphones or connect an HDMI ARC-enabled audio device, this event will inform you of the updated status. It ensures users are aware of changes in audio port connectivity, enabling seamless audio device management.

### Related Functions  
- **setEnableAudioPort**: This function can trigger the `connectedAudioPortUpdated` event by enabling or disabling specific audio ports, which may result in a change in their connection status.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.HotpluggedAudioPort | string | <sup>*(optional)*</sup> Audio port ID for which the connection status has changed. Possible audio port IDs are (`HDMI_ARC0`, `HEADPHONE0`,  etc) |
| params.isConnected | string | Current connection status of the audio port (must be one of the following: *connected*, *disconnected*) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.connectedAudioPortUpdated",
    "params": {
        "HotpluggedAudioPort": "HDMI_ARC0",
        "isConnected": "connected"
    }
}
```

<a name="connectedVideoDisplaysUpdated"></a>
## *connectedVideoDisplaysUpdated*


The `connectedVideoDisplaysUpdated` event is triggered whenever there is a change in the status of connected video displays, such as when a display is connected or disconnected via HDMI. This event ensures users are informed about updates to the video output configuration, allowing them to adjust settings or troubleshoot connectivity issues. It is particularly useful for scenarios involving HDMI hot-plug events, where displays are dynamically added or removed.

### Related Functions
[getConnectedVideoDisplays](#getConnectedVideoDisplays) : This function retrieves the current list of connected video displays, providing updated information that aligns with the `connectedVideoDisplaysUpdated` event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.connectedVideoDisplays | array | A string [] of connected video display port names |
| params.connectedVideoDisplays[#] | string |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.connectedVideoDisplaysUpdated",
    "params": {
        "connectedVideoDisplays": [
            "HDMI0"
        ]
    }
}
```

<a name="resolutionChanged"></a>
## *resolutionChanged*


The `resolutionChanged` event notifies users when the screen resolution of the connected display has been updated. This event is triggered whenever the resolution settings are modified, such as when switching to a different resolution or when the display device automatically adjusts its resolution. The event provides details about the new resolution, including the width, height, and the type of video display.

This event ensures users are informed about changes to their display settings, allowing them to verify or adjust their setup as needed.

### Related Functions
[getCurrentResolution](#getCurrentResolution) : This function retrieves the current resolution of the connected display. It is directly related to the `resolutionChanged` event, as the event reflects updates to this resolution.

[getSupportedResolutions](#getSupportedResolutions) : This function lists all resolutions supported by the connected display. It is relevant to the `resolutionChanged` event because the new resolution must be one of the supported options.

[getSupportedVideoDisplays](#getSupportedVideoDisplays) : This function provides information about the connected video displays. It is connected to the `resolutionChanged` event as the event specifies which display's resolution has been updated.

[getSupportedTvResolutions](#getSupportedTvResolutions) : This function lists the resolutions supported by the connected TV. It is related to the `resolutionChanged` event because the event indicates when the TV's resolution has been changed.

[getSupportedSettopResolutions](#getSupportedSettopResolutions) : This function lists the resolutions supported by the set-top box. It is relevant to the `resolutionChanged` event as the event may reflect changes to the set-top box's output resolution.

[setCurrentResolution](#setCurrentResolution) : This function allows users to manually set the resolution of the connected display. It directly triggers the `resolutionChanged` event when a new resolution is applied.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.width | integer | Width of the video display |
| params.height | integer | Height of the video display |
| params.videoDisplayType | string | Type of video display (port) |
| params.resolution | string | Video display resolution |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.resolutionChanged",
    "params": {
        "width": 1920,
        "height": 1080,
        "videoDisplayType": "HDMI0",
        "resolution": "1080p"
    }
}
```

<a name="resolutionPreChange"></a>
## *resolutionPreChange*


The *resolutionPreChange* event is triggered when the system is about to change the video resolution settings. This event serves as a notification to inform users that a resolution change is imminent, allowing connected devices or applications to prepare for the transition. It ensures a smooth experience by signaling the pre-change state before the new resolution is applied.

### Related Functions  
[getCurrentResolution](#getCurrentResolution) : This function retrieves the current resolution settings, which may be updated after the *resolutionPreChange* event is triggered.  

[getSupportedResolutions](#getSupportedResolutions) : This function provides a list of resolutions supported by the system, which can be relevant when a resolution change is about to occur.  

[getSupportedVideoDisplays](#getSupportedVideoDisplays) : This function identifies the connected video displays, which may be affected by the resolution change signaled by the *resolutionPreChange* event.  

[getSupportedTvResolutions](#getSupportedTvResolutions) : This function lists the resolutions supported by the connected TV, helping users understand the options available during a resolution change.  

[getSupportedSettopResolutions](#getSupportedSettopResolutions) : This function provides the resolutions supported by the set-top box, which may be relevant during the resolution change process.  

[setCurrentResolution](#setCurrentResolution) : This function sets the resolution of the video output, which directly triggers the *resolutionPreChange* event as part of the resolution update process.

### Parameters

This event carries no parameters.

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.resolutionPreChange"
}
```

<a name="zoomSettingUpdated"></a>
## *zoomSettingUpdated*


The *zoomSettingUpdated* event is triggered whenever the zoom setting for video display changes. This event notifies users about updates to the zoom configuration, such as switching between "None" (no zoom) and "Full" (full zoom). It ensures that users are informed of changes to the video display's zoom settings, providing a seamless viewing experience.  

### Related Functions  
[getZoomSetting](#getZoomSetting) : Retrieves the current zoom setting of the video display, which can trigger the *zoomSettingUpdated* event when queried after a change.  

[setZoomSetting](#setZoomSetting) : Updates the zoom setting for the video display. When this function is called to modify the zoom configuration, it triggers the *zoomSettingUpdated* event to notify users of the change.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.zoomSetting | string | Zoom setting. Possible values: `FULL`,  `NONE,`  `Letterbox 16x9`, `Letterbox 14x9`, `CCO`, `PanScan`, `Letterbox 2.21 on 4x3`, `Letterbox 2.21 on 16x9`, `Platform`, `Zoom 16x9`, `Pillarbox 4x3`, `Widescreen 4x3` |
| params.videoDisplayType | string | Type of video display (port) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.zoomSettingUpdated",
    "params": {
        "zoomSetting": "FULL",
        "videoDisplayType": "HDMI0"
    }
}
```

<a name="videoFormatChanged"></a>
## *videoFormatChanged*


The *videoFormatChanged* event occurs when the video format of the connected display changes. This event is triggered whenever the system detects a change in the video format, such as switching between HDR standards (e.g., HDR10, Dolby Vision) or other video format updates. It ensures users are informed about the current video format being used, enabling them to adjust settings or troubleshoot display issues effectively.  

### Related Functions  
[getVideoFormat](#getVideoFormat) : This function retrieves the current video format of the connected display. It is directly related to the *videoFormatChanged* event, as the event uses this function to determine and notify the updated video format.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.supportedVideoFormat | array | A list of supported Video formats |
| params.supportedVideoFormat[#] | string |  |
| params.currentVideoFormat | string | The current video format |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.videoFormatChanged",
    "params": {
        "supportedVideoFormat": [
            "`SDR`, `HDR10`, `HDR10PLUS`, `HLG`, `DV`, `Technicolor Prime`"
        ],
        "currentVideoFormat": "SDR"
    }
}
```

<a name="AtmosCapabilityChanged"></a>
## *AtmosCapabilityChanged*


AtmosCapabilityChanged is an event that notifies users when the Dolby Atmos capability of the connected audio device changes. This event is triggered whenever there is a change in the system's ability to support Dolby Atmos audio, such as when a compatible device is connected or disconnected. The event provides information about the current Atmos capability status, which can either indicate that Atmos is supported or not supported.

### Related Functions

[getSinkAtmosCapability](#getSinkAtmosCapability) : This function retrieves the current Dolby Atmos capability of the connected audio device. It plays a key role in determining the Atmos capability status, which triggers the AtmosCapabilityChanged event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.currentAtmosCapability | string | Atmos capability of the connected device, ATMOS_SUPPORTED, ATMOS_NOT_SUPPORTED |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.AtmosCapabilityChanged",
    "params": {
        "currentAtmosCapability": "ATMOS_SUPPORTED"
    }
}
```

<a name="muteStatusChanged"></a>
## *muteStatusChanged*


The *muteStatusChanged* event notifies users when the mute status of the audio output changes. This event is triggered whenever the audio output is muted or unmuted, ensuring users are informed about the current state of their device's audio. For example, if the device's audio is muted or unmuted via remote control or system settings, this event will be activated to reflect the change.

### Related Functions  
[getMuted](#getMuted) : This function retrieves the current mute status of the audio output. It is directly related to the *muteStatusChanged* event, as changes in the mute status are detected and reported through this event.  

[setMuted](#setMuted) : This function allows users to mute or unmute the audio output. When this function is used to change the mute status, the *muteStatusChanged* event is triggered to notify users of the update.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.muted | boolean | mute status value |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.muteStatusChanged",
    "params": {
        "muted": true
    }
}
```

<a name="volumeLevelChanged"></a>
## *volumeLevelChanged*


The `volumeLevelChanged` event is triggered whenever the volume level of the audio output is adjusted. This event notifies users about changes in the volume level, ensuring they are aware of updates to the audio settings. It is particularly useful for applications or devices that need to monitor or respond to volume changes in real-time.  

### Related Functions  
- [setVolumeLevel](#setVolumeLevel) : This function directly modifies the volume level, which triggers the `volumeLevelChanged` event to notify users of the updated audio output level.  
- [getVolumeLevel](#getVolumeLevel) : This function retrieves the current volume level, allowing users to confirm the changes reflected by the `volumeLevelChanged` event.  
- [setVolumeLeveller](#setVolumeLeveller) : Adjusting the volume leveller settings can indirectly affect the volume level, potentially triggering the `volumeLevelChanged` event.  
- [getVolumeLeveller](#getVolumeLeveller) : This function provides information about the current volume leveller settings, which may influence the volume level changes associated with the event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.volumeLevel | integer | volume level |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.volumeLevelChanged",
    "params": {
        "volumeLevel": 10
    }
}
```
