<!-- Generated automatically, DO NOT EDIT! -->
<a name="DeviceInfo_Plugin"></a>
# DeviceInfo Plugin

**Version: [1.1.0](https://github.com/rdkcentral/rdkservices/blob/main/DeviceInfo/CHANGELOG.md)**

A DeviceInfo plugin for Thunder framework.

### Table of Contents

- [Abbreviation, Acronyms and Terms](#Abbreviation,_Acronyms_and_Terms)
- [Description](#Description)
- [Configuration](#Configuration)
- [Methods](#Methods)
- [Properties](#Properties)

<a name="Abbreviation,_Acronyms_and_Terms"></a>
# Abbreviation, Acronyms and Terms

[[Refer to this link](userguide/aat.md)]

<a name="Description"></a>
# Description


DeviceInfo is an RDK service designed to provide detailed information about a device's hardware, software, and operational status. It enables applications to retrieve essential device attributes such as model, firmware version, serial number, and network configurations.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *DeviceInfo*) |
| classname | string | Class name: *DeviceInfo* |
| locator | string | Library name: *libWPEFrameworkDeviceInfo.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the DeviceInfo plugin:

DeviceInfo interface methods:

| Method | Description |
| :-------- | :-------- |
| [supportedresolutions](#supportedresolutions) | Supported resolutions on the selected video display port |
| [defaultresolution](#defaultresolution) | Default resolution on the selected video display port |
| [supportedhdcp](#supportedhdcp) | Supported hdcp version on the selected video display port |
| [audiocapabilities](#audiocapabilities) | Audio capabilities for the specified audio port |
| [ms12capabilities](#ms12capabilities) | MS12 audio capabilities for the specified audio port |
| [supportedms12audioprofiles](#supportedms12audioprofiles) | Supported MS12 audio profiles for the specified audio port |


<a name="supportedresolutions"></a>
## *supportedresolutions*


The *supportedresolutions* API provides a comprehensive list of all video resolutions that are supported by the device. This function is particularly useful for users who want to understand the range of display capabilities of their device, such as supported screen resolutions for video playback or external display connections. By knowing the supported resolutions, users can ensure compatibility with their display devices and optimize their viewing experience. This API is essential for configuring video output settings and ensuring that the device operates seamlessly with connected displays.

### Related Functions
[defaultresolution](#defaultresolution) : Provides the default resolution setting of the device, which complements the list of supported resolutions by indicating the resolution the device is configured to use by default.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoDisplay | string | Video display port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedResolutions | array |  |
| result.supportedResolutions[#] | string | Resolution supported by the device (must be one of the following: *unknown*, *480i*, *480p*, *576i*, *576p*, *576p50*, *720p*, *720p50*, *1080i*, *1080i25*, *1080i50*, *1080p*, *1080p24*, *1080p25*, *1080p30*, *1080p50*, *1080p60*, *2160p30*, *2160p50*, *2160p60*, *4320p30*, *4320p60*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.supportedresolutions",
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
            "1080p"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.supportedresolutions",
    "params":{"videoDisplay":"HDMI0"}}'
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
    function supportedResolutions(videoDisplay) {
      thunderJS.DeviceInfo.supportedresolutions({ videoDisplay: videoDisplay })
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
    <button onclick="supportedResolutions('HDMI0')">supportedResolutions</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void supportedresolutions(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="defaultresolution"></a>
## *defaultresolution*


The *defaultresolution* API provides information about the default video resolution setting of the device. This resolution is typically the one that the device uses when it is first powered on or reset to factory settings. It is particularly useful for users who want to understand the baseline video quality their device supports without any manual configuration. This API helps in identifying the default display resolution, ensuring compatibility with connected displays or monitors. It is a key feature for users who want to optimize their viewing experience or troubleshoot display-related issues.

### Related Functions
[supportedresolutions](#supportedresolutions) : This function provides a list of all video resolutions supported by the device. It complements the *defaultresolution* API by offering a broader view of the device's video capabilities.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoDisplay | string | Video display port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.defaultResolution | string | Resolution supported by the device (must be one of the following: *unknown*, *480i*, *480p*, *576i*, *576p*, *576p50*, *720p*, *720p50*, *1080i*, *1080i25*, *1080i50*, *1080p*, *1080p24*, *1080p25*, *1080p30*, *1080p50*, *1080p60*, *2160p30*, *2160p50*, *2160p60*, *4320p30*, *4320p60*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.defaultresolution",
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
        "defaultResolution": "1080p"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
Please provide the JSON content so I can generate the appropriate `curl` command.
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
    </script>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp

    void defaultresolution(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="supportedhdcp"></a>
## *supportedhdcp*


The *supportedhdcp* API provides information about the HDCP (High-bandwidth Digital Content Protection) versions supported by the device. HDCP is a security feature used to protect digital content from unauthorized copying or interception during transmission over HDMI or other digital interfaces. This API is useful for users who want to ensure compatibility between their device and external displays or media systems that require specific HDCP versions for secure playback of protected content. By knowing the supported HDCP versions, users can make informed decisions about connecting their device to other equipment, such as TVs, monitors, or AV receivers, to ensure seamless and secure content delivery.

### Related Functions
[supportedresolutions](#supportedresolutions) : Provides information about the resolutions supported by the device, which can be useful when pairing with HDCP-supported displays.
[defaultresolution](#defaultresolution) : Indicates the default resolution of the device, which may be relevant when considering HDCP compatibility with external displays.
[supportedvideodisplays](#supportedvideodisplays) : Lists the video display types supported by the device, which can help users understand the compatibility of HDCP with various display options.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoDisplay | string | Video display port name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supportedHDCPVersion | string | HDCP support (must be one of the following: *unavailable*, *1.4*, *2.0*, *2.1*, *2.2*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.supportedhdcp",
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
        "supportedHDCPVersion": "hdcp_20"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.supportedhdcp",
    "params":{"videoDisplay":"HDMI0"}}'
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
    function supportedHdcp(videoDisplay) {
      thunderJS.DeviceInfo.supportedhdcp({ videoDisplay })
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
    <button onclick="supportedHdcp('HDMI0')">supportedHdcp</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void supportedhdcp(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="audiocapabilities"></a>
## *audiocapabilities*


The *audiocapabilities* API provides detailed information about the audio capabilities supported by the device. This includes the types of audio formats, codecs, and features that the device can handle, such as Dolby Digital, DTS, or other advanced audio technologies. It is particularly useful for users who want to ensure compatibility with external audio systems, soundbars, or home theater setups. By understanding the audio capabilities of the device, users can optimize their audio experience and make informed decisions about connecting compatible audio equipment.

### Related Functions
[ms12capabilities](#ms12capabilities) : Provides information about the Dolby MS12 audio capabilities supported by the device.
[supportedms12audioprofiles](#supportedms12audioprofiles) : Lists the specific MS12 audio profiles supported by the device.
[supportedaudioports](#supportedaudioports) : Details the audio ports available on the device for connecting external audio systems.

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
| result.AudioCapabilities | array | An array of audio capabilities |
| result.AudioCapabilities[#] | string | Audio capability (must be one of the following: *none*, *ATMOS*, *DOLBY DIGITAL*, *DOLBY DIGITAL PLUS*, *Dual Audio Decode*, *DAPv2*, *MS12*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.audiocapabilities",
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
        "AudioCapabilities": [
            "none"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.audiocapabilities",
    "params":{"audioPort":"HDMI0"}}'
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
    function audiocapabilities(audioPort) {
      thunderJS.audiocapabilities({ audioPort: audioPort })
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
    <button onclick="audiocapabilities('HDMI0')">audiocapabilities</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void audiocapabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="ms12capabilities"></a>
## *ms12capabilities*


The *ms12capabilities* API provides detailed information about the Dolby MS12 audio capabilities supported by the device. Dolby MS12 (Multistream Decoder) is an advanced audio technology that enhances the audio experience by supporting multiple audio formats, including Dolby Atmos, Dolby Digital Plus, and others. This API is particularly useful for users who want to understand the audio processing capabilities of their device, ensuring compatibility with high-quality audio content and systems. By accessing this information, users can determine whether their device supports advanced audio features like object-based audio, surround sound, and other Dolby enhancements.

### Related Functions
[supportedms12audioprofiles](#supportedms12audioprofiles) : Provides details about the specific MS12 audio profiles supported by the device.

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
| result.MS12Capabilities | array | An array of MS12 audio capabilities |
| result.MS12Capabilities[#] | string | MS12 audio capability (must be one of the following: *none*, *Dolby Volume*, *Inteligent Equalizer*, *Dialogue Enhancer*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.ms12capabilities",
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
        "MS12Capabilities": [
            "Dolby Volume"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.ms12capabilities",
    "params":{"audioPort":"HDMI0"}}'
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
    function ms12capabilities(audioPort) {
      thunderJS.ms12capabilities({ audioPort: audioPort })
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
    <button onclick="ms12capabilities('HDMI0')">ms12capabilities</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void ms12capabilities(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="supportedms12audioprofiles"></a>
## *supportedms12audioprofiles*


The `supportedms12audioprofiles` API provides a list of audio profiles supported by the MS12 (Dolby MS12) audio processing system on the device. Dolby MS12 is a comprehensive audio solution that enhances the audio experience by supporting advanced features such as Dolby Atmos, Dolby Digital Plus, and other high-quality audio formats. This API is useful for users who want to understand the range of audio profiles their device can handle, ensuring compatibility with various content and audio setups. By knowing the supported MS12 audio profiles, users can optimize their audio settings for the best possible sound quality.

### Related Functions
[audiocapabilities](#audiocapabilities) : Provides a broader overview of the audio capabilities of the device, including supported audio formats and features.
[ms12capabilities](#ms12capabilities) : Offers detailed information about the specific capabilities of the MS12 audio system, complementing the supported audio profiles.

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
| result.supportedMS12AudioProfiles | array | An array of MS12 audio profiles |
| result.supportedMS12AudioProfiles[#] | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.supportedms12audioprofiles",
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
        "supportedMS12AudioProfiles": [
            "Movie"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.supportedms12audioprofiles",
    "params":{"audioPort":"HDMI0"}}'
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
    function supportedms12audioprofiles(audioPort) {
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
    <button onclick="supportedms12audioprofiles('HDMI0')">supportedms12audioprofiles</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void supportedms12audioprofiles(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="Properties"></a>
# Properties

The following properties are provided by the DeviceInfo plugin:

DeviceInfo interface properties:

| Property | Description |
| :-------- | :-------- |
| [systeminfo](#systeminfo) <sup>RO</sup> | System general information |
| [addresses](#addresses) <sup>RO</sup> | Network interface addresses |
| [socketinfo](#socketinfo) <sup>RO</sup> | Socket information |
| [firmwareversion](#firmwareversion) <sup>RO</sup> | Versions maintained in version |
| [serialnumber](#serialnumber) <sup>RO</sup> | Serial number set by manufacturer |
| [releaseversion](#releaseversion) <sup>RO</sup> | Release version of Image |
| [chipset](#chipset) <sup>RO</sup> | Chipset used for this device |
| [modelid](#modelid) <sup>RO</sup> | Device model number or SKU |
| [make](#make) <sup>RO</sup> | Device manufacturer |
| [modelname](#modelname) <sup>RO</sup> | Friendly device model name |
| [devicetype](#devicetype) <sup>RO</sup> | Device type |
| [socname](#socname) <sup>RO</sup> | SOC Name |
| [distributorid](#distributorid) <sup>RO</sup> | Partner ID or distributor ID for device |
| [supportedaudioports](#supportedaudioports) <sup>RO</sup> | Audio ports supported on the device (all ports that are physically present) |
| [supportedvideodisplays](#supportedvideodisplays) <sup>RO</sup> | Video ports supported on the device (all ports that are physically present) |
| [hostedid](#hostedid) <sup>RO</sup> | EDID of the host |


<a name="systeminfo"></a>
## *systeminfo*


The *systeminfo* API provides comprehensive details about the device's hardware and software specifications. It is a centralized source for retrieving essential information such as the device's model, chipset, firmware version, serial number, and other critical identifiers. This API is particularly useful for users who want to understand the technical capabilities of their device, verify compatibility with specific applications, or troubleshoot issues by identifying the device's configuration. By accessing this information, users can ensure their device meets the requirements for certain functionalities or services.

### Related Functions
[firmwareversion](#firmwareversion) : Retrieves the firmware version of the device, which is a key component of the system information.
[serialnumber](#serialnumber) : Provides the unique serial number of the device, often used in conjunction with system information for identification purposes.
[chipset](#chipset) : Offers details about the chipset used in the device, which is a critical part of the system's hardware information.
[modelid](#modelid) : Retrieves the model identifier of the device, complementing the system information for device-specific details.
[make](#make) : Provides the manufacturer details of the device, which is part of the broader system information.
[modelname](#modelname) : Supplies the model name of the device, adding to the overall system details.
[devicetype](#devicetype) : Identifies the type of device, such as a set-top box or smart TV, which is relevant to the system's profile.
[socname](#socname) : Retrieves the name of the System on Chip (SoC) used in the device, a key hardware detail in system information.
[distributorid](#distributorid) : Provides the distributor ID of the device, which is part of the system's identification details.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | System general information |
| (property).version | string | Software version (in form *version#hashtag*) |
| (property).uptime | number | System uptime (in seconds) |
| (property).totalram | number | Total installed system RAM memory (in bytes) |
| (property).freeram | number | Free system RAM memory (in bytes) |
| (property).totalswap | number | Total swap space (in bytes) |
| (property).freeswap | number | Swap space still available (in bytes) |
| (property).devicename | string | Host name |
| (property).cpuload | string | Current CPU load (percentage) |
| (property).cpuloadavg | object | CPU load average |
| (property).cpuloadavg.avg1min | number | 1min cpuload average |
| (property).cpuloadavg.avg5min | number | 5min cpuload average |
| (property).cpuloadavg.avg15min | number | 15min cpuload average |
| (property).serialnumber | string | Device serial number |
| (property).time | string | Current system date and time |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.systeminfo"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "version": "1.0#14452f612c3747645d54974255d11b8f3b4faa54",
        "uptime": 120,
        "totalram": 655757312,
        "freeram": 563015680,
        "totalswap": 789132680,
        "freeswap": 789132680,
        "devicename": "buildroot",
        "cpuload": "2",
        "cpuloadavg": {
            "avg1min": 789132680,
            "avg5min": 789132680,
            "avg15min": 789132680
        },
        "serialnumber": "aplhanumerical string",
        "time": "Mon, 11 Mar 2019 14:38:18"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.systeminfo",
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
    function systeminfo() {
      thunderJS.DeviceInfo.systeminfo()
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
    <button onclick="systeminfo()">systeminfo</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_systeminfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="addresses"></a>
## *addresses*


The `addresses` API provides detailed information about the network addresses associated with the device. This includes data such as IP addresses, MAC addresses, and other relevant network identifiers. It is particularly useful for users who need to verify or troubleshoot network connectivity, configure network settings, or identify the device on a network. By accessing this information, users can ensure proper integration of the device within their network environment and maintain seamless communication between devices.

### Related Functions
[socketinfo](#socketinfo) : Provides details about the network socket configuration, which complements the network address information by offering insights into how the device communicates over the network.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | array | Network interface addresses |
| (property)[#] | object |  |
| (property)[#].name | string | Interface name |
| (property)[#].mac | string | Interface MAC address |
| (property)[#]?.ip | array | <sup>*(optional)*</sup>  |
| (property)[#]?.ip[#] | string | <sup>*(optional)*</sup> Interface IP address |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.addresses"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "name": "lo",
            "mac": "00:00:00:00:00",
            "ip": [
                "127.0.0.1"
            ]
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
    "method":"DeviceInfo.addresses",
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
    function DeviceInfo_addresses() {
      thunderJS.DeviceInfo.addresses()
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
    <button onclick="DeviceInfo_addresses()">DeviceInfo_addresses</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_addresses(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="socketinfo"></a>
## *socketinfo*


The `socketinfo` API provides detailed information about the network socket configuration of the device. This includes data such as the status of network connections, the type of network protocols being used, and other relevant socket-level details. This API is particularly useful for users who want to understand the network connectivity of their device, troubleshoot network-related issues, or verify the current network setup. By accessing this information, users can ensure that their device is properly connected to the network and functioning optimally.

### Related Functions
[addresses](#addresses) : Provides detailed information about the network addresses associated with the device, which complements the socket-level details provided by `socketinfo`.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Socket information |
| (property)?.total | number | <sup>*(optional)*</sup>  |
| (property)?.open | number | <sup>*(optional)*</sup>  |
| (property)?.link | number | <sup>*(optional)*</sup>  |
| (property)?.exception | number | <sup>*(optional)*</sup>  |
| (property)?.shutdown | number | <sup>*(optional)*</sup>  |
| (property).runs | number | Number of runs |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.socketinfo"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "total": 0,
        "open": 0,
        "link": 0,
        "exception": 0,
        "shutdown": 0,
        "runs": 1
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.socketinfo",
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
    function socketinfo() {
      thunderJS.DeviceInfo.socketinfo()
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
    <button onclick="socketinfo()">socketinfo</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void socketinfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="firmwareversion"></a>
## *firmwareversion*


The *firmwareversion* API provides information about the current firmware version installed on the device. Firmware is the software programmed into the hardware of a device, and knowing the firmware version is essential for troubleshooting, compatibility checks, and ensuring the device is up-to-date with the latest features and security patches. This API is particularly useful for users who want to verify if their device is running the latest firmware or need to provide firmware details for support purposes.

### Related Functions
[releaseversion](#releaseversion) : Provides information about the release version of the software, which complements the firmware version details.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Versions maintained in version.txt |
| (property).imagename | string |  |
| (property)?.sdk | string | <sup>*(optional)*</sup>  |
| (property)?.mediarite | string | <sup>*(optional)*</sup>  |
| (property)?.yocto | string | <sup>*(optional)*</sup> Yocto version (must be one of the following: *kirkstone*, *dunfell*, *morty*, *daisy*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.firmwareversion"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "imagename": "alphanumerical string",
        "sdk": "17.3",
        "mediarite": "8.3.53",
        "yocto": "dunfell"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.firmwareversion",
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
    function firmwareversion() {
      thunderJS.DeviceInfo.firmwareversion()
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
    <button onclick="firmwareversion()">firmwareversion</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_firmwareversion(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="serialnumber"></a>
## *serialnumber*


The *serialnumber* API provides the unique serial number of the device. This serial number is a hardware-specific identifier that is typically assigned during the manufacturing process. It is used to uniquely identify a device for purposes such as warranty claims, device registration, or inventory management. This information is particularly useful for users who need to verify the authenticity of their device, troubleshoot issues with customer support, or manage multiple devices in a networked environment.

### Related Functions
[systeminfo](#systeminfo) : Provides general system information about the device, which may complement the serial number for detailed device identification.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Serial number set by manufacturer |
| (property).serialnumber | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.serialnumber"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "serialnumber": "alphanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.serialnumber"}'
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
    function DeviceInfo_serialnumber() {
      thunderJS.DeviceInfo.serialnumber()
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
    <button onclick="DeviceInfo_serialnumber()">DeviceInfo_serialnumber</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void DeviceInfo_serialnumber(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="releaseversion"></a>
## *releaseversion*


The *releaseversion* API provides information about the current software release version installed on the device. This is particularly useful for users who want to verify the version of the software running on their device, ensuring compatibility with applications, features, or updates. Knowing the release version can also help users troubleshoot issues or confirm whether their device is up-to-date with the latest firmware or software enhancements.

### Related Functions
[firmwareversion](#firmwareversion) : Provides details about the firmware version of the device, which complements the software release version information.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Release version of Image.  If unable to find the Release version default value is 99.99.0.0 |
| (property).releaseversion | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.releaseversion"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "releaseversion": "8.2.0.0"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.releaseversion"}'
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
    function releaseVersion() {
      thunderJS.DeviceInfo.releaseversion()
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
    <button onclick="releaseVersion()">releaseVersion</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_releaseversion(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="chipset"></a>
## *chipset*


The *chipset* API provides information about the chipset used in the device. A chipset is a critical component of the hardware that determines the device's processing capabilities, performance, and compatibility with various software and hardware features. This API is useful for users who want to understand the underlying hardware specifications of their device, which can be helpful for troubleshooting, compatibility checks, or simply gaining insight into the device's technical details.

### Related Functions
[socname](#socname) : Provides the name of the System on Chip (SoC) used in the device, which complements the chipset information by offering more specific details about the hardware architecture.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Chipset used for this device |
| (property).chipset | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.chipset"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "chipset": "T962X3"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.chipset",
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
    function deviceInfoChipset() {
      thunderJS.deviceInfoChipset()
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
    <button onclick="deviceInfoChipset()">deviceInfoChipset</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_chipset(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="modelid"></a>
## *modelid*


The `modelid` API provides the unique identifier for the specific model of the device. This identifier is crucial for distinguishing between different models within a product line or across various product categories. It is particularly useful for users who need to verify the exact model of their device for compatibility checks, firmware updates, or when seeking customer support. The `modelid` serves as a key reference point for identifying the device's technical specifications and supported features.

### Related Functions
[modelname](#modelname) : Provides the name of the device model, which complements the `modelid` by offering a more user-friendly representation of the device.
[make](#make) : Identifies the manufacturer of the device, which can be used alongside `modelid` to get a complete understanding of the device's origin.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Device model number or SKU |
| (property).sku | string | Device model number or SKU |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.modelid"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "sku": "alphanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.modelid",
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
    function deviceInfoModelId() {
      thunderJS.DeviceInfo.modelid()
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
    <button onclick="deviceInfoModelId()">deviceInfoModelId</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void DeviceInfo_modelid(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="make"></a>
## *make*


The *make* API provides information about the manufacturer of the device. This function is particularly useful for users who want to identify the brand or company responsible for producing the hardware. It can be helpful in scenarios where users need to verify the authenticity of the device, check compatibility with other products, or simply understand the origin of the device. This API is often used in conjunction with other device identification functions to provide a comprehensive profile of the hardware.

### Related Functions
[modelname](#modelname) : Provides the specific model name of the device, complementing the manufacturer information.
[modelid](#modelid) : Offers the unique identifier for the device model, which can be used alongside the manufacturer details for precise identification.
[chipset](#chipset) : Gives details about the chipset used in the device, which can be relevant when considering the manufacturer's hardware specifications.
[distributorid](#distributorid) : Provides information about the distributor, which can be useful in understanding the supply chain associated with the manufacturer.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Device manufacturer |
| (property).make | string | Device manufacturer |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.make"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "make": "alphanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.make",
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
    function deviceInfoMake() {
      thunderJS.deviceInfoMake()
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
    <button onclick="deviceInfoMake()">deviceInfoMake</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_make(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="modelname"></a>
## *modelname*


The *modelname* API provides the name of the device model. This information is useful for identifying the specific model of the device in use, which can be helpful for compatibility checks, troubleshooting, or when referencing device-specific features. Users can leverage this API to confirm the exact model of their device, ensuring they are working with the correct hardware specifications.

### Related Functions
[modelid](#modelid) : Provides the unique identifier for the device model, complementing the *modelname* API by offering a more specific reference to the device.
[make](#make) : Offers information about the manufacturer of the device, which can be used alongside *modelname* to get a complete understanding of the device's origin.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Friendly device model name |
| (property).model | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.modelname"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "model": "alphanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.modelname",
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
    function deviceInfoModelname() {
      thunderJS.deviceInfoModelname()
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
    <button onclick="deviceInfoModelname()">deviceInfoModelname</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_modelname(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="devicetype"></a>
## *devicetype*


The *devicetype* API provides information about the type of device being used. This could include details such as whether the device is a set-top box, a smart TV, a streaming stick, or any other type of hardware. This information is particularly useful for users who want to understand the category or classification of their device, which can help in troubleshooting, compatibility checks, or when seeking support. Knowing the device type can also assist in determining the capabilities and limitations of the hardware.

### Related Functions
[modelid](#modelid) : Provides the unique identifier for the device model, which complements the device type information by offering more specific details about the hardware.
[modelname](#modelname) : Gives the name of the device model, which can be used alongside the device type to identify the device more precisely.
[make](#make) : Indicates the manufacturer of the device, which is often relevant when understanding the device type.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Device type |
| (property).devicetype | string | Device type (must be one of the following: *tv*, *IpStb*, *QamIpStb*) |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.devicetype"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "devicetype": "IpStb"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.devicetype"}'
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
    function devicetype() {
      thunderJS.DeviceInfo.devicetype()
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
    <button onclick="devicetype()">devicetype</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_devicetype(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="socname"></a>
## *socname*


The *socname* API provides information about the System on Chip (SoC) used in the device. This API is useful for users who want to understand the hardware capabilities of their device, as the SoC plays a critical role in determining the device's performance, features, and compatibility with various software and hardware standards. Knowing the SoC name can help users identify the underlying architecture and assess whether the device meets their requirements for specific applications, such as gaming, streaming, or professional workloads.

### Related Functions
[chipset](#chipset) : Provides additional details about the chipset used in the device, which complements the information provided by the *socname* API.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | SOC Name |
| (property).socname | string | SOC Name |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.socname"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "socname": "alphanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.socname",
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
    function socname() {
      thunderJS.DeviceInfo.socname()
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
    <button onclick="socname()">socname</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_socname(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="distributorid"></a>
## *distributorid*


The *distributorid* API provides information about the distributor or operator associated with the device. This identifier is typically used to distinguish devices based on the organization or entity responsible for their distribution. It is particularly useful for users who need to verify the origin of their device or for troubleshooting purposes when interacting with customer support. The distributor ID can also help in identifying region-specific configurations or services tied to the device.

### Related Functions
[systeminfo](#systeminfo) : Provides general information about the system, which may include details related to the distributor.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Partner ID or distributor ID for device |
| (property).distributorid | string | Partner ID or distributor ID for device |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.distributorid"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "distributorid": "aplhanumerical string"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.distributorid"}'
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
    function DeviceInfo_distributorid() {
      thunderJS.DeviceInfo.distributorid()
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
    <button onclick="DeviceInfo_distributorid()">DeviceInfo_distributorid</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_distributorid(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="supportedaudioports"></a>
## *supportedaudioports*


The `supportedaudioports` API provides information about the audio output ports supported by the device. This function is particularly useful for users who want to understand the available audio connectivity options on their device, such as HDMI, optical, or analog ports. By retrieving this information, users can ensure compatibility with their audio equipment, such as soundbars, home theater systems, or external speakers. This API helps users make informed decisions about how to connect their device to external audio systems for optimal sound quality and performance.

### Related Functions
[audiocapabilities](#audiocapabilities) : Provides detailed information about the audio capabilities of the device, including supported audio formats and features.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Audio ports supported on the device (all ports that are physically present) |
| (property).supportedAudioPorts | array |  |
| (property).supportedAudioPorts[#] | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.supportedaudioports"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedAudioPorts": [
            "HDMI0"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.supportedaudioports",
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
    function supportedaudioports() {
      thunderJS.DeviceInfo.supportedaudioports()
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
    <button onclick="supportedaudioports()">supportedaudioports</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void DeviceInfo_supportedaudioports(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="supportedvideodisplays"></a>
## *supportedvideodisplays*


The *supportedvideodisplays* API provides a comprehensive list of video display types that are supported by the device. This information is particularly useful for users who want to understand the compatibility of their device with various video output options, such as HDMI, DisplayPort, or other display interfaces. By knowing the supported video displays, users can make informed decisions about connecting their device to external monitors, TVs, or projectors, ensuring optimal performance and compatibility.

### Related Functions
[supportedresolutions](#supportedresolutions) : Provides details about the resolutions supported by the device, which complements the information about supported video displays.
[defaultresolution](#defaultresolution) : Offers the default resolution setting of the device, which is relevant when considering supported video displays.
[supportedaudioports](#supportedaudioports) : Lists the audio ports supported by the device, which can be useful when pairing audio capabilities with video display options.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | Video ports supported on the device (all ports that are physically present) |
| (property).supportedVideoDisplays | array |  |
| (property).supportedVideoDisplays[#] | string |  |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.supportedvideodisplays"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "supportedVideoDisplays": [
            "HDMI0"
        ]
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.supportedvideodisplays",
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
    function callDeviceInfoSupportedVideoDisplays() {
      thunderJS.DeviceInfo.supportedvideodisplays()
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
    <button onclick="callDeviceInfoSupportedVideoDisplays()">callDeviceInfoSupportedVideoDisplays</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void supportedvideodisplays(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="hostedid"></a>
## *hostedid*


The *hostedid* API provides a unique identifier for the device. This identifier is typically used to distinguish the device within a network or system, enabling seamless communication and management. It is particularly useful in scenarios where multiple devices are connected, and a unique reference is required to identify and interact with a specific device. This API ensures that each device can be uniquely recognized, which is essential for tasks such as device registration, authentication, and tracking.

### Related Functions
[systeminfo](#systeminfo) : Provides detailed information about the system, which may include the hosted ID as part of the broader system details.

> This property is **read-only**.

### Events

No Events

### Value

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| (property) | object | EDID of the host |
| (property).EDID | string | A base64 encoded byte array string representing the EDID |

### Errors

| Code | Message | Description |
| :-------- | :-------- | :-------- |
| 1 | ```ERROR_GENERAL``` | General error |

### Example

#### Get Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "DeviceInfo.hostedid"
}
```

#### Get Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "EDID": "AP///////wAQrMLQVEJTMQUdAQOANR546q11qVRNnSYPUFSlSwCBALMA0QBxT6lAgYDRwAEBVl4AoKCgKVAwIDUADighAAAaAAAA/wBNWTNORDkxVjFTQlQKAAAA/ABERUxMIFAyNDE4RAogAAAA/QAxVh1xHAAKICAgICAgARsCAxuxUJAFBAMCBxYBBhESFRMUHyBlAwwAEAACOoAYcTgtQFgsRQAOKCEAAB4BHYAYcRwWIFgsJQAOKCEAAJ6/FgCggDgTQDAgOgAOKCEAABp+OQCggDgfQDAgOgAOKCEAABoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA2A"
    }
}
```


<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
    '{"jsonrpc":"2.0",
    "id":3,
    "method":"DeviceInfo.hostedid",
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
    function hostedid() {
      thunderJS.DeviceInfo.hostedid()
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
    <button onclick="hostedid()">hostedid</button>
    </body>
    </html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void DeviceInfo_hostedid(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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
