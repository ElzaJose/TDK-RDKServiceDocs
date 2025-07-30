<!-- Generated automatically, DO NOT EDIT! -->
<a name="Bluetooth_Plugin"></a>
# Bluetooth Plugin

A org.rdk.Bluetooth plugin for Thunder framework.

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


The **Bluetooth** RDK service is a plugin designed to manage and interact with Bluetooth hardware and devices. It provides functionalities such as starting and stopping device discovery, retrieving discovered devices, and managing device connection states. The service is implemented as a JSON-RPC-based plugin, enabling seamless integration and communication within the RDK framework.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.Bluetooth*) |
| classname | string | Class name: *org.rdk.Bluetooth* |
| locator | string | Library name: *libWPEFrameworkBluetooth.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.Bluetooth plugin:

Bluetooth interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [connect](#connect) | Initiates the connection with the given Bluetooth device | [onStatusChanged](#onStatusChanged) |
| [disable](#disable) | Disables the Bluetooth stack | NA |
| [disconnect](#disconnect) | Disconnects the given device from this device ID and triggers `onStatusChanged` Event | [onStatusChanged](#onStatusChanged) |
| [enable](#enable) | Enables the Bluetooth stack | NA |
| [getAudioInfo](#getAudioInfo) | Provides information on the currently playing song/audio from an external source | NA |
| [getConnectedDevices](#getConnectedDevices) | Returns a list of devices connected to this device | NA |
| [getDeviceInfo](#getDeviceInfo) | Returns information for the given device ID | NA |
| [getDiscoveredDevices](#getDiscoveredDevices) | This method should be called after getting at least one event `onDiscoveredDevice` event and it returns an array of discovered devices | NA |
| [getName](#getName) | Returns the name of this device as seen by other Bluetooth devices | NA |
| [getPairedDevices](#getPairedDevices) | Returns a list of devices that have paired with this device | NA |
| [isDiscoverable](#isDiscoverable) | Returns `true`, if this device can be discovered by other Bluetooth devices | NA |
| [pair](#pair) | Pairs this device with device ID of Bluetooth | [onStatusChanged](#onStatusChanged), [onRequestFailed](#onRequestFailed) |
| [respondToEvent](#respondToEvent) | Provides the ability to respond the client Bluetooth event | NA |
| [sendAudioPlaybackCommand](#sendAudioPlaybackCommand) | Provides control over the connected source | NA |
| [setAudioStream](#setAudioStream) | Sets the primary or secondary audio-out to the given Bluetooth device | NA |
| [setDiscoverable](#setDiscoverable) | When true, this device can be discovered by other Bluetooth devices | NA |
| [setName](#setName) | Sets the name of this device as seen by other Bluetooth devices | NA |
| [startScan](#startScan) | Starts scanning for other Bluetooth devices that match the given profile | [onStatusChanged](#onStatusChanged), [onDiscoveredDevice](#onDiscoveredDevice) |
| [stopScan](#stopScan) | Stops scanning for Bluetooth devices  if already scan is in-progress and triggers `onStatusChanged` event | [onStatusChanged](#onStatusChanged) |
| [unpair](#unpair) | Unpairs the given device ID from this device | [onStatusChanged](#onStatusChanged) |
| [getDeviceVolumeMuteInfo](#getDeviceVolumeMuteInfo) | Gets the volume information of the given Bluetooth device ID | NA |
| [setDeviceVolumeMuteInfo](#setDeviceVolumeMuteInfo) | Sets the volume of the connected Bluetooth device ID | [onDeviceMediaStatus](#onDeviceMediaStatus) |
| [getApiVersionNumber](#getApiVersionNumber) | Provides the current API version number | NA |


<a name="connect"></a>
## *connect*


The `connect` API establishes a Bluetooth connection with a specified device, enabling seamless communication and data exchange. This function is essential for pairing and interacting with Bluetooth-enabled devices, such as headphones, speakers, or other peripherals, ensuring a smooth user experience.

### Related Functions  
[disconnect](#disconnect) : Terminates an active Bluetooth connection with a specified device.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggers `onStatusChanged` event once it is  connected to the given deviceID. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.connectedProfile | string | Profile of the connected device. See [startscan](#startscan) for supported profiles |

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
    "method": "org.rdk.Bluetooth.connect",
    "params": {
        "deviceID": "61579454946360",
        "deviceType": "TV",
        "connectedProfile": "SMARTPHONE"
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
"method": "org.rdk.Bluetooth.connect",
"params": {
"deviceID": "61579454946360",
"deviceType": "TV",
"connectedProfile": "SMARTPHONE"
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
function connect(params) {
  thunderJS.connect(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="connect({deviceID: '61579454946360', deviceType: 'TV', connectedProfile: 'SMARTPHONE'})">connect</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void connect(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["deviceType"] = "TV";
        parameters["connectedProfile"] = "SMARTPHONE";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="disable"></a>
## *disable*


Disables the Bluetooth functionality on the device, ensuring that no Bluetooth operations, such as pairing or connecting, can occur. This is useful for conserving power or restricting Bluetooth usage when not needed.

### Related Functions  
[enable](#enable) : Enables the Bluetooth functionality on the device.

### Events

No Events

### Parameters

This method takes no parameters.

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
    "method": "org.rdk.Bluetooth.disable"
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
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.Bluetooth.disable"}' http://127.0.0.1:9998/jsonrpc
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
function disable() {
  thunderJS.disable()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="disable()">disable</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void disable(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="disconnect"></a>
## *disconnect*


Disconnect allows users to terminate the connection between a device and the system, ensuring the device is no longer actively linked or communicating. This function is essential for managing device connections, freeing up resources, and maintaining control over connected devices.

### Related Functions  
[connect](#connect) : Establishes a connection with a device.  
[unpair](#unpair) : Removes the pairing information of a device, preventing future connections.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggers `onStatusChanged` event once it is disconnected from given deviceID. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |

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
    "method": "org.rdk.Bluetooth.disconnect",
    "params": {
        "deviceID": "61579454946360",
        "deviceType": "TV"
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
"method": "org.rdk.Bluetooth.disconnect",
"params": {
"deviceID": "61579454946360",
"deviceType": "TV"
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
function disconnect(params) {
  thunderJS.disconnect(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="disconnect({deviceID: '61579454946360', deviceType: 'TV'})">disconnect</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void disconnect(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["deviceType"] = "TV";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="enable"></a>
## *enable*


Enables Bluetooth functionality on the device, allowing it to perform operations such as pairing, connecting, and streaming audio. This API is essential for activating Bluetooth capabilities and ensuring the device is ready for wireless communication.

### Related Functions  
[disable](#disable) : Disables Bluetooth functionality on the device.

### Events

No Events

### Parameters

This method takes no parameters.

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
    "method": "org.rdk.Bluetooth.enable"
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
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.Bluetooth.enable"}' http://127.0.0.1:9998/jsonrpc
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
function enable() {
  thunderJS.enable()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="enable()">enable</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void enable(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getAudioInfo"></a>
## *getAudioInfo*


Provides detailed information about the audio properties of a connected device, including volume levels, mute status, and audio stream details. This API is essential for users who want to monitor or adjust audio settings for their devices seamlessly.

### Related Functions  
[getDeviceVolumeMuteInfo](#getDeviceVolumeMuteInfo) : Retrieves the volume and mute status of a specific device.  
[setAudioStream](#setAudioStream) : Configures the audio stream for a connected device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.trackInfo | object | An object that contains information about the currently playing audio selection |
| result.trackInfo.album | string | Name of the album |
| result.trackInfo.genre | string | Genre of the album |
| result.trackInfo.title | string | Title of the track |
| result.trackInfo.artist | string | name of the artist |
| result.trackInfo.ui32Duration | string | Duration of the track in milliseconds |
| result.trackInfo.ui32TrackNumber | string | Currently playing track |
| result.trackInfo.ui32NumberOfTracks | string | Number of total tracks |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getAudioInfo",
    "params": {
        "deviceID": "61579454946360"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "trackInfo": {
            "album": "Spacebound Apes",
            "genre": "Jazz",
            "title": "Grace",
            "artist": "Neil Cowley Trio",
            "ui32Duration": "217292",
            "ui32TrackNumber": "1",
            "ui32NumberOfTracks": "10"
        },
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary
'[json data]'
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
function getAudioInfo() {
  thunderJS.getAudioInfo()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getAudioInfo()">getAudioInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getConnectedDevices"></a>
## *getConnectedDevices*


Retrieves a list of currently connected Bluetooth devices, including details such as device ID, name, type, connection status, and pairing status. This API helps users monitor and manage their active Bluetooth connections efficiently. It is particularly useful for identifying connected devices and their properties in real-time.

### Related Functions  
[getDiscoveredDevices](#getDiscoveredDevices) : Retrieves a list of Bluetooth devices that are currently discoverable.  
[getPairedDevices](#getPairedDevices) : Retrieves a list of Bluetooth devices that are paired with the system.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.connectedDevices | array | An array of objects where each object represents a connected device |
| result.connectedDevices[#] | object |  |
| result.connectedDevices[#].deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| result.connectedDevices[#].name | string | Name of the Bluetooth Device |
| result.connectedDevices[#].deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| result.connectedDevices[#].activeState | string | for devices that support low power mode this parameter indicates if the device is in `STANDBY` mode (`0`), `LOW_POWER` mode (`1`), or `ACTIVE` mode (`2`) |
| result.connectedDevices[#].rawDeviceType | string | Bluetooth device class |
| result.connectedDevices[#].rawBleDeviceType | string | Bluetooth device appearance |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getConnectedDevices"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "connectedDevices": [
            {
                "deviceID": "61579454946360",
                "name": "[TV] UE32J5530",
                "deviceType": "TV",
                "activeState": "0",
                "rawDeviceType": "2360344",
                "rawBleDeviceType": "180"
            }
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
"method": "org.rdk.Bluetooth.getConnectedDevices"
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
function getConnectedDevices() {
  thunderJS.getConnectedDevices()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getConnectedDevices()">getConnectedDevices</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getConnectedDevices(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getDeviceInfo"></a>
## *getDeviceInfo*


Retrieves detailed information about a specific Bluetooth device, including its name, type, firmware revision, and unique identifier. This API helps users understand the properties and capabilities of a device, making it easier to manage and interact with connected or discovered devices. It is essential for identifying and troubleshooting Bluetooth devices in your network.

### Related Functions  
[getConnectedDevices](#getConnectedDevices) : Provides a list of currently connected Bluetooth devices.  
[getDiscoveredDevices](#getDiscoveredDevices) : Retrieves a list of Bluetooth devices discovered during a scan.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.deviceInfo | object | An object that contains information about the device |
| result.deviceInfo.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| result.deviceInfo.name | string | Name of the Bluetooth Device |
| result.deviceInfo.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| result.deviceInfo.supportedProfile | string | Bluetooth profile supported by the device |
| result.deviceInfo.manufacturer | string | Manufacturer of the device |
| result.deviceInfo.MAC | string | MAC address of the device |
| result.deviceInfo.rssi | string | Received signal strength of the device |
| result.deviceInfo.signalStrength | string | Bluetooth signal strength |
| result.deviceInfo?.batteryLevel | string | <sup>*(optional)*</sup> Battery level of the connected bluetooth device, 0 if no battery level found |
| result.deviceInfo?.modalias | string | <sup>*(optional)*</sup> The modalias for the device - if no modalias is present it will be an empty string |
| result.deviceInfo?.firmwareRevision | string | <sup>*(optional)*</sup> The firmware revision for a particular device creaded from the modalias - if no modalias is present it will be an empty string |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getDeviceInfo",
    "params": {
        "deviceID": "61579454946360"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "deviceInfo": {
            "deviceID": "61579454946360",
            "name": "[TV] UE32J5530",
            "deviceType": "TV",
            "supportedProfile": "SMARTPHONE",
            "manufacturer": "640",
            "MAC": "E8:FB:E9:0C:XX:80",
            "rssi": "0",
            "signalStrength": "0",
            "batteryLevel": "53",
            "modalias": "v:0B13p:045Ed:0517",
            "firmwareRevision": "5.1.7"
        },
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
"method": "getDeviceInfo"
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
function getDeviceInfo() {
  thunderJS.DeviceInfo.make()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getDeviceInfo()">getDeviceInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDeviceInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getDiscoveredDevices"></a>
## *getDiscoveredDevices*


Retrieves a list of Bluetooth devices that have been discovered during a scan, including details such as device ID, name, type, connection status, and pairing status. This function is essential for identifying nearby devices and managing Bluetooth connections effectively.

### Related Functions  
[getPairedDevices](#getPairedDevices) : Provides a list of devices that are already paired with the system.  
[getConnectedDevices](#getConnectedDevices) : Retrieves information about devices currently connected to the system.  
[startScan](#startScan) : Initiates a scan to discover nearby Bluetooth devices.  
[stopScan](#stopScan) : Stops an ongoing scan for Bluetooth devices.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.discoveredDevices | array | An array of objects where each object represents a discovered device |
| result.discoveredDevices[#] | object |  |
| result.discoveredDevices[#].deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| result.discoveredDevices[#].name | string | Name of the Bluetooth Device |
| result.discoveredDevices[#].deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| result.discoveredDevices[#].connected | boolean | Whether the device is connected |
| result.discoveredDevices[#].paired | boolean | Whether paired or not |
| result.discoveredDevices[#].rawDeviceType | string | Bluetooth device class |
| result.discoveredDevices[#].rawBleDeviceType | string | Bluetooth device appearance |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getDiscoveredDevices"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "discoveredDevices": [
            {
                "deviceID": "61579454946360",
                "name": "[TV] UE32J5530",
                "deviceType": "TV",
                "connected": true,
                "paired": true,
                "rawDeviceType": "2360344",
                "rawBleDeviceType": "180"
            }
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.Bluetooth.getDiscoveredDevices"}' http://127.0.0.1:9998/jsonrpc
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
function getDiscoveredDevices() {
  thunderJS.getDiscoveredDevices()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getDiscoveredDevices()">getDiscoveredDevices</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDiscoveredDevices(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getName"></a>
## *getName*


Retrieves the friendly name of the Bluetooth adapter, allowing users to identify the device in a network or pairing scenario. This function is essential for ensuring a seamless and user-friendly Bluetooth experience by providing clear identification of the device.

### Related Functions  
[setName](#setName) : Updates the friendly name of the Bluetooth adapter.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.name | string | The name of the device |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getName"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "name": "RDK Bluetooth Device",
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
"method": "org.rdk.Bluetooth.getName"
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
function getName() {
  thunderJS.getName()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getName()">getName</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getName(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getPairedDevices"></a>
## *getPairedDevices*


Retrieves a list of all Bluetooth devices that have been paired with the system, including detailed information such as device name, type, connection status, and unique identifiers. This API is essential for managing and interacting with previously paired devices, enabling users to view and organize their Bluetooth connections effortlessly.

### Related Functions  
[getConnectedDevices](#getConnectedDevices) : Provides information about currently connected Bluetooth devices.  
[getDiscoveredDevices](#getDiscoveredDevices) : Lists Bluetooth devices discovered during a scan, including pairing status.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.pairedDevices | array | An array of objects where each object represents a paired device |
| result.pairedDevices[#] | object |  |
| result.pairedDevices[#].deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| result.pairedDevices[#].name | string | Name of the Bluetooth Device |
| result.pairedDevices[#].deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| result.pairedDevices[#].connected | boolean | Whether the device is connected |
| result.pairedDevices[#].rawDeviceType | string | Bluetooth device class |
| result.pairedDevices[#].rawBleDeviceType | string | Bluetooth device appearance |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getPairedDevices"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "pairedDevices": [
            {
                "deviceID": "61579454946360",
                "name": "[TV] UE32J5530",
                "deviceType": "TV",
                "connected": true,
                "rawDeviceType": "2360344",
                "rawBleDeviceType": "180"
            }
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
"method": "org.rdk.Bluetooth.getPairedDevices"
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
function getPairedDevices() {
  thunderJS.getPairedDevices()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getPairedDevices()">getPairedDevices</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPairedDevices(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="isDiscoverable"></a>
## *isDiscoverable*


Checks whether the Bluetooth adapter is currently discoverable, allowing other devices to find and connect to it. This function is useful for confirming the discoverability status of your device, ensuring seamless pairing and connectivity.

### Related Functions  
[setDiscoverable](#setDiscoverable) : Enables or disables the discoverable mode for the Bluetooth adapter, optionally with a timeout.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.discoverable | boolean | Whether the device is discoverable |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.isDiscoverable"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "discoverable": true,
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
"method": "org.rdk.Bluetooth.isDiscoverable"
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
function isDiscoverable() {
  thunderJS.isDiscoverable()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="isDiscoverable()">isDiscoverable</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void isDiscoverable(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="pair"></a>
## *pair*


The *pair* API establishes a secure connection between your device and a specified Bluetooth device, enabling seamless communication and functionality. This is essential for creating a trusted link to share data or use features like audio playback and device control.  

### Related Functions  
[unpair](#unpair) : Removes the pairing between your device and a previously connected Bluetooth device.  
[getPairedDevices](#getPairedDevices) : Retrieves a list of all devices currently paired with your device.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggers onStatusChanged event when the device gets paired to given device ID. |
| [onRequestFailed](#onRequestFailed) | Triggers onRequestFailed event, when the device is unable to pair (BluetoothState: PAIRING_FAILED) |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |

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
    "method": "org.rdk.Bluetooth.pair",
    "params": {
        "deviceID": "61579454946360"
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
"method": "org.rdk.Bluetooth.pair",
"params": {
"deviceID": "61579454946360"
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
function pair(deviceID) {
  thunderJS.pair(deviceID)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="pair('61579454946360')">pair</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void pair(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["deviceID"] = "61579454946360";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="respondToEvent"></a>
## *respondToEvent*


Allows users to respond to specific Bluetooth events, such as pairing requests or playback requests, by providing a device ID, event type, and response value. This function is essential for managing real-time interactions with Bluetooth devices, ensuring seamless communication and control.  

### Related Functions  
[getDeviceInfo](#getDeviceInfo) : Retrieve detailed information about a specific Bluetooth device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.eventType | string | Name of a request-time event (for example, `onPairingRequest`, `onConnectionRequest`, `onPlaybackRequest`) |
| params.responseValue | string | one of `ACCEPTED` or `REJECTED` |

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
    "method": "org.rdk.Bluetooth.respondToEvent",
    "params": {
        "deviceID": "61579454946360",
        "eventType": "onPairingRequest",
        "responseValue": "ACCEPTED"
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
  "method": "respondToEvent",
  "params": {
    "eventId": "12345",
    "response": "accepted",
    "comments": "Looking forward to it!"
  },
  "id": 1
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
function respondToEvent(params) {
  thunderJS.respondToEvent(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="respondToEvent({eventId: '12345', response: 'accepted', comments: 'Looking forward to it!'})">respondToEvent</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void respondToEvent(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["eventId"] = "12345";
        parameters["response"] = "accepted";
        parameters["comments"] = "Looking forward to it!";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="sendAudioPlaybackCommand"></a>
## *sendAudioPlaybackCommand*


This API allows users to control audio playback on a connected Bluetooth device by sending commands such as play, pause, stop, resume, skip, and volume adjustments. It ensures seamless interaction with Bluetooth audio devices, enhancing the user experience for managing playback remotely.

### Related Functions  
[getAudioInfo](#getAudioInfo) : Retrieve detailed information about the audio capabilities of connected Bluetooth devices.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.command | string | Command to send to the connected source |

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
    "method": "org.rdk.Bluetooth.sendAudioPlaybackCommand",
    "params": {
        "deviceID": "61579454946360",
        "command": "PLAY"
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
"method": "org.rdk.Bluetooth.sendAudioPlaybackCommand",
"params": {
"deviceID": "61579454946360",
"command": "PLAY"
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
function sendAudioPlaybackCommand(params) {
  thunderJS.sendAudioPlaybackCommand(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendAudioPlaybackCommand({deviceID: '61579454946360', command: 'PLAY'})">sendAudioPlaybackCommand</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendAudioPlaybackCommand(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["command"] = "PLAY";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setAudioStream"></a>
## *setAudioStream*


Allows you to configure the audio output stream for a specific Bluetooth device, selecting between "PRIMARY" or "AUXILIARY" streams. This function is essential for optimizing audio playback based on user preferences or device capabilities, ensuring a tailored listening experience.

### Related Functions  
[getAudioInfo](#getAudioInfo) : Retrieve detailed information about the current audio configuration.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.audioStreamName | string | The audio out to set. Either `PRIMARY` or `AUXILIARY` |

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
    "method": "org.rdk.Bluetooth.setAudioStream",
    "params": {
        "deviceID": "61579454946360",
        "audioStreamName": "PRIMARY"
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
"method": "org.rdk.Bluetooth.setAudioStream",
"params": {
"deviceID": "61579454946360",
"audioStreamName": "PRIMARY"
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
function setAudioStream(params) {
  thunderJS.setAudioStream(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setAudioStream({deviceID: '61579454946360', audioStreamName: 'PRIMARY'})">setAudioStream</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setAudioStream(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["audioStreamName"] = "PRIMARY";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDiscoverable"></a>
## *setDiscoverable*


Enables or disables the Bluetooth device's discoverable mode, allowing it to be visible to other devices for pairing. Users can specify an optional timeout to limit how long the device remains discoverable. This function is essential for managing device visibility and ensuring secure and controlled connectivity.

### Related Functions  
[isDiscoverable](#isDiscoverable) : Checks if the Bluetooth device is currently in discoverable mode.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.timeout | integer | <sup>*(optional)*</sup> Discoverable window timeout |
| params.discoverable | boolean | Whether the device is discoverable |

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
    "method": "org.rdk.Bluetooth.setDiscoverable",
    "params": {
        "timeout": 5,
        "discoverable": true
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
"method": "org.rdk.Bluetooth.setDiscoverable",
"params": {
"timeout": 5,
"discoverable": true
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
function setDiscoverable(params) {
  thunderJS.setDiscoverable(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setDiscoverable({timeout: 5, discoverable: true})">setDiscoverable</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDiscoverable(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["timeout"] = 5;
        parameters["discoverable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setName"></a>
## *setName*


Updates the Bluetooth adapter's name to a user-specified value, making it easier to identify the device during discovery or pairing. This function is essential for personalizing your Bluetooth device and ensuring it stands out in environments with multiple devices.

### Related Functions  
[getName](#getName) : Retrieves the current name of the Bluetooth adapter.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.name | string | Name of the Bluetooth Device |

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
    "method": "org.rdk.Bluetooth.setName",
    "params": {
        "name": "RDK Bluetooth Device"
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
"method": "org.rdk.Bluetooth.setName",
"params": {
"name": "RDK Bluetooth Device"
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
function setName(name) {
  thunderJS.setName(name)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setName('RDK Bluetooth Device')">setName</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setName(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["name"] = "RDK Bluetooth Device";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="startScan"></a>
## *startScan*


Initiates a Bluetooth device discovery process to identify nearby devices within range. This function allows users to specify a timeout duration and target device profiles, making it easier to find compatible devices for pairing or connection. It is particularly useful for setting up new devices or managing connections in dynamic environments.

### Related Functions  
[stopScan](#stopScan) : Stops the ongoing Bluetooth device discovery process.
 Supported profiles include:
* For Audio-Out: `LOUDSPEAKER`, `HEADPHONES`, `WEARABLE HEADSET`, `HIFI AUDIO DEVICE`
* For Audio-In: `SMARTPHONE`, `TABLET`
* For HID: `KEYBOARD`, `MOUSE`, `JOYSTICK`
* For HandsFree: `HandsFree`.

 The method returns one of the following statuses:
* `AVAILABLE` - Bluetooth stack is initialized, not software disabled, and hardware is running
* `NO_BLUETOOTH_HARDWARE` - Bluetooth is supported in RDK software, but no Bluetooth hardware was found.
* This method sends both `onStatusChanged` and `onDiscoveredDevice` events.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggered onStatusChangedevent when device starts scanning the other available Bluetooth devices or when timeout (timeout param) is completed or the StopScan method called. |
| [onDiscoveredDevice](#onDiscoveredDevice) | Triggered onDiscoveredDevice event when device is in scanning mode and at least one device is discovered or when the scanned device is lost. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.timeout | integer | Discoverable window timeout |
| params?.profile | string | <sup>*(optional)*</sup> List of Profiles to scan |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.status | string | Discovery status |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.startScan",
    "params": {
        "timeout": 5,
        "profile": "SMARTPHONE, HEADSET"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "AVAIlABLE",
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
"method": "org.rdk.Bluetooth.startScan",
"params": {
"timeout": 5,
"profile": "SMARTPHONE, HEADSET"
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
function startScan(params) {
  thunderJS.startScan(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="startScan({timeout: 5, profile: 'SMARTPHONE, HEADSET'})">startScan</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void startScan(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["timeout"] = 5;
        parameters["profile"] = "SMARTPHONE, HEADSET";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="stopScan"></a>
## *stopScan*


Stops the ongoing Bluetooth device discovery process, ensuring no further devices are scanned or detected. This function is useful for conserving resources or ending a scan once the desired devices have been found.

### Related Functions  
[startScan](#startScan) : Initiates the Bluetooth device discovery process to detect nearby devices.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggered onStatusChanged event when scan is stopped. |
### Parameters

This method takes no parameters.

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
    "method": "org.rdk.Bluetooth.stopScan"
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
"method": "org.rdk.Bluetooth.stopScan"
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
function stopScan() {
  thunderJS.stopScan()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="stopScan()">stopScan</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void stopScan(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="unpair"></a>
## *unpair*


The *unpair* API allows users to disconnect and remove a previously paired Bluetooth device from the system. This is useful for managing device connections and ensuring only desired devices remain paired, enhancing security and convenience.

### Related Functions  
[pair](#pair) : Use this function to establish a new Bluetooth pairing with a device.

### Events

| Event | Description |
| :-------- | :-------- |
| [onStatusChanged](#onStatusChanged) | Triggers onStatusChanged event when device is unpaired. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |

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
    "method": "org.rdk.Bluetooth.unpair",
    "params": {
        "deviceID": "61579454946360"
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
"method": "org.rdk.Bluetooth.unpair",
"params": {
"deviceID": "61579454946360"
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
function unpair(deviceID) {
  thunderJS.unpair(deviceID)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="unpair('61579454946360')">unpair</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void unpair(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["deviceID"] = "61579454946360";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="getDeviceVolumeMuteInfo"></a>
## *getDeviceVolumeMuteInfo*


Retrieves the current volume level and mute status of a specified Bluetooth device. This API is useful for monitoring audio settings and ensuring the device's sound configuration aligns with user preferences.

### Related Functions  
[setDeviceVolumeMuteInfo](#setDeviceVolumeMuteInfo) : Allows users to adjust the volume level and mute status of a Bluetooth device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.deviceProfile | string | Profile of the Bluetooth device |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.volumeInfo | object | An object which represents current device volume and mute information |
| result.volumeInfo.volume | string | Volume value is in between 0 and 255 |
| result.volumeInfo.mute | boolean | Mute value of the device is either true or false |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getDeviceVolumeMuteInfo",
    "params": {
        "deviceID": "61579454946360",
        "deviceProfile": "SMARTPHONE"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "volumeInfo": {
            "volume": "50",
            "mute": false
        },
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
"method": "org.rdk.Bluetooth.getDeviceVolumeMuteInfo",
"params": {
"deviceID": "61579454946360",
"deviceProfile": "SMARTPHONE"
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
function getDeviceVolumeMuteInfo(params) {
  thunderJS.getDeviceVolumeMuteInfo(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getDeviceVolumeMuteInfo({deviceID: '61579454946360', deviceProfile: 'SMARTPHONE'})">getDeviceVolumeMuteInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDeviceVolumeMuteInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["deviceProfile"] = "SMARTPHONE";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDeviceVolumeMuteInfo"></a>
## *setDeviceVolumeMuteInfo*


Allows users to adjust the volume level and mute status of a connected Bluetooth device, ensuring a personalized audio experience. This API is essential for managing audio output settings on devices like headphones or speakers.

### Related Functions  
[getDeviceVolumeMuteInfo](#getDeviceVolumeMuteInfo) : Retrieves the current volume level and mute status of a connected Bluetooth device.

### Events

| Event | Description |
| :-------- | :-------- |
| [onDeviceMediaStatus](#onDeviceMediaStatus) | Triggers onDeviceMediaStatus event once volume of connected given deviceID is increased or decreased or when connected given deviceID is muted or unmuted or when unknown key is pressed on connected given deviceID. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.deviceProfile | string | Profile of the Bluetooth device |
| params.volume | string | Volume value is in between 0 and 255 |
| params.mute | string | Mute value of the device is either 1 or 0 |

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
    "method": "org.rdk.Bluetooth.setDeviceVolumeMuteInfo",
    "params": {
        "deviceID": "61579454946360",
        "deviceProfile": "SMARTPHONE",
        "volume": "50",
        "mute": "1"
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
"method": "org.rdk.Bluetooth.setDeviceVolumeMuteInfo",
"params": {
"deviceID": "61579454946360",
"deviceProfile": "SMARTPHONE",
"volume": "50",
"mute": "1"
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
function setDeviceVolumeMuteInfo(params) {
  thunderJS.setDeviceVolumeMuteInfo(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setDeviceVolumeMuteInfo({deviceID: '61579454946360', deviceProfile: 'SMARTPHONE', volume: '50', mute: '1'})">setDeviceVolumeMuteInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDeviceVolumeMuteInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceID"] = "61579454946360";
        parameters["deviceProfile"] = "SMARTPHONE";
        parameters["volume"] = "50";
        parameters["mute"] = "1";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getApiVersionNumber"></a>
## *getApiVersionNumber*


Provides the current version number of the API, helping users identify compatibility and ensure they are using the correct version for their needs. This function is essential for maintaining seamless integration and troubleshooting across different API versions.

### Related Functions  
None

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.version | integer | API Version Number |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.Bluetooth.getApiVersionNumber"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "version": 1,
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.Bluetooth.getApiVersionNumber"}' http://127.0.0.1:9998/jsonrpc
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
function getApiVersionNumber() {
  thunderJS.getApiVersionNumber()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getApiVersionNumber()">getApiVersionNumber</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getApiVersionNumber(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

The following events are provided by the org.rdk.Bluetooth plugin:

Bluetooth interface events:

| Event | Description |
| :-------- | :-------- |
| [onConnectionRequest](#onConnectionRequest) | Triggered when a connection is requested by third party device that has already been paired to the set-top box |
| [onDiscoveredDevice](#onDiscoveredDevice) | Triggered during device discovery when a new device is discovered or a discovered device has been lost in real time |
| [onPairingRequest](#onPairingRequest) | Triggered when pairing is requested by a third party device that supports A2DP profile |
| [onPlaybackChange](#onPlaybackChange) | Triggered when playback is interrupted or changed |
| [onPlaybackNewTrack](#onPlaybackNewTrack) | Triggered whenever the user plays a new track or when the music player selects a next track automatically from its playlist |
| [onPlaybackProgress](#onPlaybackProgress) | Triggered in one second intervals as long as the status of the playback is playing |
| [onPlaybackRequest](#onPlaybackRequest) | Triggered when playback is requested by third party device that has already been paired to the set-top box |
| [onRequestFailed](#onRequestFailed) | Triggered when the previous request to pair or connect failed |
| [onStatusChanged](#onStatusChanged) | Triggered when the Bluetooth functionality status changes |
| [onDeviceFound](#onDeviceFound) | Triggered when the new device got discovered |
| [onDeviceLost](#onDeviceLost) | Triggered when any discovered device lost or out of range |
| [onDeviceMediaStatus](#onDeviceMediaStatus) | Triggered when any change occurs to Device Media like volume or mute |


<a name="onConnectionRequest"></a>
## *onConnectionRequest*


The *onConnectionRequest* event is triggered when a device requests to establish a connection. This event typically occurs when a discovered or paired device attempts to connect to the system, signaling its intent to interact or exchange data. Users may encounter this event when a Bluetooth-enabled device, such as headphones, speakers, or smartphones, initiates a connection request. The event provides information about the requesting device, including whether it is already connected or paired.

### Related Functions  
[connect](#connect) : Initiates the connection process for a device, which can trigger the *onConnectionRequest* event when a device attempts to connect.  

[pair](#pair) : Establishes a pairing relationship between devices, which may lead to a connection request and trigger the *onConnectionRequest* event.  

[enable](#enable) : Activates Bluetooth functionality, allowing devices to discover and connect, potentially triggering the *onConnectionRequest* event.  

[setDiscoverable](#setDiscoverable) : Makes the device discoverable to others, enabling connection requests that can trigger the *onConnectionRequest* event.  

[respondToEvent](#respondToEvent) : Handles incoming events, such as *onConnectionRequest*, by allowing users to accept or reject the connection request.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.supportedProfile | string | Bluetooth profile supported by the device |
| params.manufacturer | string | Manufacturer of the device |
| params.MAC | string | MAC address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onConnectionRequest",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "supportedProfile": "SMARTPHONE",
        "manufacturer": "640",
        "MAC": "E8:FB:E9:0C:XX:80"
    }
}
```

<a name="onDiscoveredDevice"></a>
## *onDiscoveredDevice*


The *onDiscoveredDevice* event is triggered whenever a new Bluetooth device is discovered or an existing device is no longer discoverable during a scanning process. This event provides information about the device, such as its name, type, connection status, and pairing status. It helps users stay updated on the availability of nearby devices in real-time. 

This event is particularly useful when searching for devices to connect or pair with, ensuring that users can easily identify and interact with devices in their vicinity.

### Related Functions
[startScan](#startScan) : Initiates the scanning process to discover nearby Bluetooth devices, which can trigger the *onDiscoveredDevice* event when a device is found or lost.

[stopScan](#stopScan) : Stops the scanning process, which may indirectly trigger the *onDiscoveredDevice* event if the discovery state changes during the stop action.

[getDiscoveredDevices](#getDiscoveredDevices) : Retrieves the list of devices discovered during the scanning process, which is updated as the *onDiscoveredDevice* event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.discoveryType | string | either `DISCOVERED` or `LOST` |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.rawDeviceType | string | Bluetooth device class |
| params.rawBleDeviceType | string | Bluetooth device appearance |
| params.lastConnectedState | boolean | Whether the device was last to connect. Only the last connected device has a value of `true` |
| params.paired | boolean | Whether the device is paired. 1. `true` if the device is paired when the PAIRING_CHANGE status is sent 2. `false` if the device is unpaired. **Note** The set-top box does not retain/store all paired devices across previous power cycles. In addition, if the device is unpaired as part of a previous operation and the same device gets detected in a new discovery cycle, the device will not be a paired device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDiscoveredDevice",
    "params": {
        "deviceID": "61579454946360",
        "discoveryType": "DISCOVERED",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "rawDeviceType": "2360344",
        "rawBleDeviceType": "180",
        "lastConnectedState": true,
        "paired": true
    }
}
```

<a name="onPairingRequest"></a>
## *onPairingRequest*


The **onPairingRequest** event is triggered when an external device sends a request to pair with your device. This event notifies users that a pairing request has been received, providing details such as the requesting device's name, type, and unique identifier. It allows users to decide whether to accept or reject the pairing request, facilitating secure and controlled device connections.

### Related Functions  
[pair](#pair) : This function initiates the pairing process with the device that triggered the event, enabling a secure connection between the devices.  

[respondToEvent](#respondToEvent) : This function allows users to respond to the pairing request by either accepting or rejecting it, based on their preference.

 **Note** : External pairing (process initiated by an external device) is not recommended for usage in the current edition, as it might lead to unexpected results. This warning will be removed when this scenario is fully supported.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.supportedProfile | string | Bluetooth profile supported by the device |
| params.manufacturer | string | Manufacturer of the device |
| params.MAC | string | MAC address of the device |
| params.pinRequired | boolean | Whether a pin is required to complete pairing. If `true`, the pin is displayed on the TV screen |
| params.pinValue | string | Pin that is used for paring |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPairingRequest",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "supportedProfile": "SMARTPHONE",
        "manufacturer": "640",
        "MAC": "E8:FB:E9:0C:XX:80",
        "pinRequired": true,
        "pinValue": "0601"
    }
}
```

<a name="onPlaybackChange"></a>
## *onPlaybackChange*


The **onPlaybackChange** event notifies users about changes in the playback state of a connected Bluetooth device. This event is triggered whenever playback starts, pauses, stops, or ends. It helps users stay informed about the current playback status, ensuring a seamless audio experience.  

### Related Functions  
[sendAudioPlaybackCommand](#sendAudioPlaybackCommand) : This function can trigger the **onPlaybackChange** event by sending commands to control playback (e.g., play, pause, stop) on a connected Bluetooth device.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.action | string | Current playback state. Either `started`, `paused`, `stopped` or `ended`. If the state is `ended`, then `position` and `Duration` are omitted |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.position | string | Current track's position in milliseconds |
| params.Duration | string | Current track's duration in milliseconds |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPlaybackChange",
    "params": {
        "action": "started",
        "deviceID": "61579454946360",
        "position": "217000",
        "Duration": "217292"
    }
}
```

<a name="onPlaybackNewTrack"></a>
## *onPlaybackNewTrack*


This event is triggered whenever a new audio track begins playback on a connected device. It provides users with updated information about the currently playing track, including details such as the track's title, artist, album, genre, and its position within the playlist. This event ensures that users are always informed about the media content being played, enhancing their listening experience.

### Related Functions  
[getAudioInfo](#getAudioInfo) : This function retrieves detailed information about the audio currently being played, including track metadata, which aligns with the data provided by the `onPlaybackNewTrack` event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.album | string | Name of the album |
| params.genre | string | Genre of the album |
| params.title | string | Title of the track |
| params.artist | string | name of the artist |
| params.ui32Duration | string | Duration of the track in milliseconds |
| params.ui32TrackNumber | string | Currently playing track |
| params.ui32NumberOfTracks | string | Number of total tracks |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPlaybackNewTrack",
    "params": {
        "deviceID": "61579454946360",
        "album": "Spacebound Apes",
        "genre": "Jazz",
        "title": "Grace",
        "artist": "Neil Cowley Trio",
        "ui32Duration": "217292",
        "ui32TrackNumber": "1",
        "ui32NumberOfTracks": "10"
    }
}
```

<a name="onPlaybackProgress"></a>
## *onPlaybackProgress*


This event provides real-time updates about the current playback position of an audio track. It is triggered periodically during audio playback to inform users about the progress of the track. The event includes details such as the device ID and the current playback position in the track. This is particularly useful for tracking playback progress or synchronizing other actions with the audio timeline.

### Related Functions
[sendAudioPlaybackCommand](#sendAudioPlaybackCommand) : This function can trigger the event by initiating or controlling audio playback, which results in updates about the playback position being sent.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.position | string | Current track's position in milliseconds |
| params.Duration | string | Current track's duration in milliseconds |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPlaybackProgress",
    "params": {
        "deviceID": "61579454946360",
        "position": "217000",
        "Duration": "217292"
    }
}
```

<a name="onPlaybackRequest"></a>
## *onPlaybackRequest*


The *onPlaybackRequest* event is triggered when a playback-related action is requested by a connected device or system. This event typically occurs when a device sends a command to initiate, pause, resume, or stop audio playback. It serves as a notification to inform users that a playback action is being requested, allowing the system to respond accordingly.

### Related Functions  
[respondToEvent](#respondToEvent) : This function is used to handle and respond to the *onPlaybackRequest* event, ensuring that the system processes the playback request appropriately.  

[sendAudioPlaybackCommand](#sendAudioPlaybackCommand) : This function can trigger the *onPlaybackRequest* event by sending playback commands (e.g., play, pause, stop) to the system, which may result in this event being generated.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.supportedProfile | string | Bluetooth profile supported by the device |
| params.manufacturer | string | Manufacturer of the device |
| params.MAC | string | MAC address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPlaybackRequest",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "supportedProfile": "SMARTPHONE",
        "manufacturer": "640",
        "MAC": "E8:FB:E9:0C:XX:80"
    }
}
```

<a name="onRequestFailed"></a>
## *onRequestFailed*


This event indicates that a requested operation has failed. It is triggered when an attempt to perform an action, such as connecting to a device, pairing, unpairing, or scanning for devices, encounters an error. The event provides details about the failure, including the device involved (if applicable) and the type of operation that was unsuccessful. Users may encounter this event when a device is out of range, pairing fails, or a connection cannot be established.  

### Related Functions  
- [connect](#connect) : This function may trigger the event if the connection attempt to a device fails due to issues such as device unavailability or signal interference.  
- [pair](#pair) : The event is triggered if the pairing process with a device fails, possibly due to compatibility issues or incorrect pairing protocols.  
- [unpair](#unpair) : This function can trigger the event if the unpairing process fails, such as when the device is not properly recognized or is already disconnected.  
- [startScan](#startScan) : The event may occur if the scanning process fails, for example, due to hardware limitations or Bluetooth module errors.  
- [disconnect](#disconnect) : This function can trigger the event if the disconnection process fails, such as when the device is already disconnected or unreachable.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.newStatus | string | Bluetooth status on the device |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.rawDeviceType | string | Bluetooth device class |
| params.rawBleDeviceType | string | Bluetooth device appearance |
| params.lastConnectedState | boolean | Whether the device was last to connect. Only the last connected device has a value of `true` |
| params.paired | boolean | Whether paired or not |
| params.connected | boolean | Whether the device is connected. `true` if the device is connected when the `CONNECTION_CHANGE` status is sent. `false` if the device is disconnected |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onRequestFailed",
    "params": {
        "newStatus": "DISCOVERY_COMPLETED",
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "rawDeviceType": "2360344",
        "rawBleDeviceType": "180",
        "lastConnectedState": true,
        "paired": true,
        "connected": true
    }
}
```

<a name="onStatusChanged"></a>
## *onStatusChanged*


The *onStatusChanged* event provides real-time updates about changes in the status of Bluetooth-related activities. This event is triggered whenever there is a significant change in the state of a Bluetooth operation, such as device discovery starting or completing, connection status changes, pairing failures, or connection failures. It helps users stay informed about the progress or outcome of Bluetooth operations, ensuring a seamless and transparent experience.  

### Related Functions  
- [connect](#connect) : Triggers the event when a device successfully connects or fails to connect.  
- [disconnect](#disconnect) : Triggers the event when a device disconnects or fails to disconnect.  
- [startScan](#startScan) : Triggers the event when device discovery starts or completes.  
- [stopScan](#stopScan) : Triggers the event when device discovery is stopped.  
- [pair](#pair) : Triggers the event when a pairing attempt succeeds or fails.  
- [unpair](#unpair) : Triggers the event when a device is successfully unpaired.
* `PAIRING_CHANGE` - Pairing status changed. Applications get the device which got paired/unpaired as part of this message, but it's up to the application to obtain an updated list of paired devices by calling [getPairedDevices](#getpaireddevices).
* `CONNECTION_CHANGE` - one or more Bluetooth connections changed status. Applications get the device that got connected/disconnected as part of this message, but it's up to the application to obtain an updated list of connected devices by calling [getConnectedDevices](#getconnecteddevices).
* `DISCOVERY_COMPLETED` - Bluetooth device discovery is complete, at least one device is available. Applications should obtain an updated list of discovered devices by calling [getDiscoveredDevices](#getdiscovereddevices)
* `DISCOVERY_STARTED`- The Bluetooth device discovery will be triggered, after startScan method started.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.newStatus | string | Bluetooth status on the device |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.rawDeviceType | string | Bluetooth device class |
| params.rawBleDeviceType | string | Bluetooth device appearance |
| params.lastConnectedState | boolean | Whether the device was last to connect. Only the last connected device has a value of `true` |
| params.paired | boolean | Whether paired or not |
| params.connected | boolean | Whether device connected or not |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onStatusChanged",
    "params": {
        "newStatus": "DISCOVERY_COMPLETED",
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "rawDeviceType": "2360344",
        "rawBleDeviceType": "180",
        "lastConnectedState": true,
        "paired": true,
        "connected": false
    }
}
```

<a name="onDeviceFound"></a>
## *onDeviceFound*


The *onDeviceFound* event is triggered when a new device is discovered during a scanning process. This event provides information about the discovered device, such as its name, type, connection status, pairing status, and unique identifiers. It helps users identify and interact with nearby devices that are available for pairing or connection.  

### Related Functions  
[startScan](#startScan) : Initiates the scanning process to discover nearby devices, which can trigger the *onDeviceFound* event when a device is detected.  

[stopScan](#stopScan) : Stops the scanning process, which may prevent further *onDeviceFound* events from being triggered.  

[getDiscoveredDevices](#getDiscoveredDevices) : Retrieves a list of devices discovered during the scanning process, including those that triggered the *onDeviceFound* event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.rawDeviceType | string | Bluetooth device class |
| params.rawBleDeviceType | string | Bluetooth device appearance |
| params.lastConnectedState | boolean | Whether the device was last to connect. Only the last connected device has a value of `true` |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceFound",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "rawDeviceType": "2360344",
        "rawBleDeviceType": "180",
        "lastConnectedState": true
    }
}
```

<a name="onDeviceLost"></a>
## *onDeviceLost*


The *onDeviceLost* event is triggered when a previously connected or paired device becomes unavailable. This can occur if the device moves out of range, is powered off, or is otherwise disconnected unexpectedly. Users may experience this event when a device they were using is no longer accessible, and it serves as a notification to take appropriate action, such as reconnecting or troubleshooting the device.

### Related Functions  
[getConnectedDevices](#getConnectedDevices) : This function retrieves the list of currently connected devices. It can help confirm if a device has been lost by checking its absence from the connected devices list.  

[getPairedDevices](#getPairedDevices) : This function provides a list of paired devices. It can be used to verify if the lost device is still paired but not currently connected.  

[disconnect](#disconnect) : This function can trigger the *onDeviceLost* event if a device is manually disconnected, leading to its unavailability.  

[startScan](#startScan) : Scanning for devices can help detect if a lost device is still nearby and available for reconnection.  

[stopScan](#stopScan) : Stopping an ongoing scan may indirectly lead to the *onDeviceLost* event if the device was temporarily discovered but not connected.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.rawDeviceType | string | Bluetooth device class |
| params.rawBleDeviceType | string | Bluetooth device appearance |
| params.lastConnectedState | boolean | Whether the device was last to connect. Only the last connected device has a value of `true` |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceLost",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "rawDeviceType": "2360344",
        "rawBleDeviceType": "180",
        "lastConnectedState": true
    }
}
```

<a name="onDeviceMediaStatus"></a>
## *onDeviceMediaStatus*


The **onDeviceMediaStatus** event provides real-time updates about the media status of a connected device. This event is triggered whenever there is a change in the media-related properties of a device, such as its volume level, mute status, or other media-specific attributes. It helps users stay informed about the current state of their connected devices, ensuring a seamless and interactive experience. 

### Related Functions
[getDeviceInfo](#getDeviceInfo) : Retrieves detailed information about a specific device, including its media-related properties, which can trigger this event when updated.

[getDeviceVolumeMuteInfo](#getDeviceVolumeMuteInfo) : Fetches the current volume and mute status of a device. Changes in these properties can trigger the **onDeviceMediaStatus** event.

[setDeviceVolumeMuteInfo](#setDeviceVolumeMuteInfo) : Updates the volume or mute status of a device. Any modifications made using this function can result in the **onDeviceMediaStatus** event being triggered.
* `MUTE` - BT audio device muted using remote or external BT device.
* `UNMUTE` - BT audio device unmuted using remote or external BT device.
* `VOLUME_UP` - BT audio device volume increased using remote or external BT device.
* `VOLUME_DOWN`- BT audio device volume decreased using remote or external BT device.
* `CMD_UNKNOWN`- Unknown Media control other than MUTE, UNMUTE, VOLUME_UP, VOLUME_DOWN was performed on external BT device. .

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceID | string | ID that is derived from the Bluetooth MAC address. 6 byte MAC value is packed into 8 byte with leading zeros for first 2 bytes |
| params.name | string | Name of the Bluetooth Device |
| params.deviceType | string | Device class (for example: `headset`, `speakers`, etc.) |
| params.volume | string | Volume value is in between 0 and 255 |
| params.mute | boolean | Mute value of the device is either true or false |
| params.command | string | Command to send to the connected source |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceMediaStatus",
    "params": {
        "deviceID": "61579454946360",
        "name": "[TV] UE32J5530",
        "deviceType": "TV",
        "volume": "50",
        "mute": false,
        "command": "PLAY"
    }
}
```
