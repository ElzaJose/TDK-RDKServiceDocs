<!-- Generated automatically, DO NOT EDIT! -->
<a name="HdmiCecSinkPlugin"></a>
# HdmiCecSinkPlugin

A org.rdk.HdmiCecSink plugin for Thunder framework.

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


The **HdmiCecSink** service is an RDK plugin designed to manage and interact with HDMI Consumer Electronics Control (CEC) functionality on connected devices. It facilitates communication between HDMI-connected devices, enabling features such as device discovery, active source management, and power status monitoring. The service provides methods to retrieve device information, set active paths, handle routing changes, and manage CEC settings, ensuring seamless integration and control of HDMI devices in the ecosystem.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.HdmiCecSink*) |
| classname | string | Class name: *org.rdk.HdmiCecSink* |
| locator | string | Library name: *libWPEFrameworkHdmiCecSink.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.HdmiCecSink plugin:

HdmiCecSink interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [getActiveRoute](#getActiveRoute) | Gets details for the current route from the source to sink devices | NA |
| [getActiveSource](#getActiveSource) | Gets details for the current active source | NA |
| [getAudioDeviceConnectedStatus](#getAudioDeviceConnectedStatus) | Get status of audio device connection | NA |
| [getDeviceList](#getDeviceList) | Gets the number of connected source devices and system information for each device | NA |
| [getEnabled](#getEnabled) | Returns whether HDMI-CEC is enabled on platform or not | NA |
| [getOSDName](#getOSDName) | Returns the OSD name used by host device | NA |
| [getVendorId](#getVendorId) | Gets the current vendor ID used by host device | NA |
| [printDeviceList](#printDeviceList) | This is a helper debug command for developers | NA |
| [requestActiveSource](#requestActiveSource) | Requests the active source in the network | [onActiveSourceChange](#onActiveSourceChange), [onDeviceAdded](#onDeviceAdded), [onDeviceInfoUpdated](#onDeviceInfoUpdated) |
| [requestShortAudioDescriptor](#requestShortAudioDescriptor) | Sends the CEC Request Short Audio Descriptor (SAD) message as an event | [shortAudiodesciptorEvent](#shortAudiodesciptorEvent) |
| [sendAudioDevicePowerOnMessage](#sendAudioDevicePowerOnMessage) | This message is used to power on the connected audio device | [setSystemAudioModeEvent](#setSystemAudioModeEvent) |
| [sendGetAudioStatusMessage](#sendGetAudioStatusMessage) | Sends the CEC \<Give Audio Status\> message to request the audio status | [reportAudioStatusEvent](#reportAudioStatusEvent) |
| [sendKeyPressEvent](#sendKeyPressEvent) | Sends the CEC \<User Control Pressed\> message when TV remote key is pressed | NA |
| [sendUserControlPressed](#sendUserControlPressed) | Sends the CEC \<User Control Pressed\> message when TV remote key is pressed | NA |
| [sendUserControlReleased](#sendUserControlReleased) | Sends the CEC \<User Control released\> message when TV remote key is released | NA |
| [sendStandbyMessage](#sendStandbyMessage) | Sends a CEC \<Standby\> message to the logical address of the device | NA |
| [setActivePath](#setActivePath) | Sets the source device to active (`setStreamPath`) | NA |
| [setActiveSource](#setActiveSource) | Sets the current active source as TV (physical address 0 | NA |
| [setEnabled](#setEnabled) | Enables or disables HDMI-CEC support in the platform | [reportCecEnabledEvent](#reportCecEnabledEvent) |
| [setMenuLanguage](#setMenuLanguage) | Updates the internal data structure with the new menu Language and also broadcasts the \<Set Menu Language\> CEC message | NA |
| [setOSDName](#setOSDName) | Sets the OSD Name used by host device | NA |
| [setRoutingChange](#setRoutingChange) | Changes routing while switching between HDMI inputs and TV | NA |
| [setupARCRouting](#setupARCRouting) | Enable (or disable) HDMI-CEC Audio Return Channel (ARC) routing | [arcInitiationEvent](#arcInitiationEvent), [arcTerminationEvent](#arcTerminationEvent) |
| [setVendorId](#setVendorId) | Sets a vendor ID used by host device | NA |
| [setLatencyInfo](#setLatencyInfo) | Sets the Current Latency Values such as Video Latency, Latency Flags,Audio Output Compensated value and Audio Output Delay by sending \<Report Current Latency\> message for Dynamic Auto LipSync Feature | NA |


<a name="getActiveRoute"></a>
## *getActiveRoute*


Retrieves the active HDMI CEC route(s) for the sink device, including details such as availability, route length, and the list of active paths. This API helps identify the current active route and its associated devices, ensuring seamless HDMI CEC communication and device management.

### Related Functions  
[getActiveSource](#getActiveSource) : Retrieves the currently active source in the HDMI CEC network.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.available | boolean | If `true`, then there is an active source available and source details are included in the result. If `false`, then there is no active source |
| result.length | integer | The number of devices in the path list |
| result.pathList | array | Object [] of information about each device in the active path |
| result.pathList[#] | object |  |
| result.pathList[#].logicalAddress | integer | Logical address of the device |
| result.pathList[#].physicalAddress | string | Physical address of the device |
| result.pathList[#].deviceType | string | Type of the device |
| result.pathList[#].osdName | string | OSD name of the device if available |
| result.pathList[#].vendorID | string | Vendor ID of the device |
| result.ActiveRoute | string | Gives the route from source to sink with the device type and OSD name as an identifier |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getActiveRoute"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "available": true,
        "length": 1,
        "pathList": [
            {
                "logicalAddress": 4,
                "physicalAddress": "1.0.0.0",
                "deviceType": "Playback Device",
                "osdName": "Fire TV Stick",
                "vendorID": "0ce7"
            }
        ],
        "ActiveRoute": "Playback Device 1(Fire TV Stick)-->HDMI0",
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
"method": "org.rdk.HdmiCecSink.getActiveRoute"
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
function getActiveRoute() {
  thunderJS.getActiveRoute()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getActiveRoute()">getActiveRoute</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getActiveRoute(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getActiveSource"></a>
## *getActiveSource*


Retrieves the current active source in the HDMI-CEC network, including details such as logical address, physical address, device type, CEC version, OSD name, vendor ID, power status, and port. This API is essential for identifying the device currently acting as the active source, enabling better control and monitoring of HDMI-CEC devices.

### Related Functions  
[requestActiveSource](#requestActiveSource) : Requests the active source in the HDMI-CEC network.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.available | boolean | If `true`, then there is an active source available and source details are included in the result. If `false`, then there is no active source |
| result.logicalAddress | integer | Logical address of the device |
| result.physicalAddress | string | Physical address of the device |
| result.deviceType | string | Type of the device |
| result.cecVersion | string | CEC version supported |
| result.osdName | string | OSD name of the device if available |
| result.vendorID | string | Vendor ID of the device |
| result.powerStatus | string | Power status of the device |
| result.port | string | Port of the device |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getActiveSource"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "available": true,
        "logicalAddress": 4,
        "physicalAddress": "1.0.0.0",
        "deviceType": "Playback Device",
        "cecVersion": "Version 1.4",
        "osdName": "Fire TV Stick",
        "vendorID": "0ce7",
        "powerStatus": "Standby",
        "port": "HDMI0",
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
"method": "getActiveSource"
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
function getActiveSource() {
  thunderJS.getActiveSource()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getActiveSource()">getActiveSource</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getActiveSource(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getAudioDeviceConnectedStatus"></a>
## *getAudioDeviceConnectedStatus*


Retrieves the connection status of an audio device, indicating whether it is currently connected or not. This API is essential for monitoring the audio device's availability and ensuring seamless audio functionality in the system.

### Related Functions  
[sendGetAudioStatusMessage](#sendGetAudioStatusMessage) : Sends a request to retrieve the current audio status.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.connected | boolean | `true` if an audio device is connected, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getAudioDeviceConnectedStatus"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "connected": true,
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
"method": "org.rdk.HdmiCecSink.getAudioDeviceConnectedStatus"
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
function getAudioDeviceConnectedStatus() {
  thunderJS.getAudioDeviceConnectedStatus()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getAudioDeviceConnectedStatus()">getAudioDeviceConnectedStatus</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAudioDeviceConnectedStatus(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getDeviceList"></a>
## *getDeviceList*


Retrieve a comprehensive list of devices currently mounted in the system, including detailed information such as vendor ID, power status, and device path. This API is essential for monitoring connected devices and ensuring seamless integration with the system.

### Related Functions  
[printDeviceList](#printDeviceList) : Provides a formatted output of the device list for debugging or display purposes.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.numberofdevices | integer | number of devices in the `devicelist` array |
| result.deviceList | array | Object [] of information about each device |
| result.deviceList[#] | object |  |
| result.deviceList[#].logicalAddress | integer | Logical address of the device |
| result.deviceList[#].physicalAddress | string | Physical address of the device |
| result.deviceList[#].deviceType | string | Type of the device |
| result.deviceList[#].cecVersion | string | CEC version supported |
| result.deviceList[#].osdName | string | OSD name of the device if available |
| result.deviceList[#].vendorID | string | Vendor ID of the device |
| result.deviceList[#].powerStatus | string | Power status of the device |
| result.deviceList[#].portNumber | integer |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getDeviceList"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "numberofdevices": 1,
        "deviceList": [
            {
                "logicalAddress": 4,
                "physicalAddress": "1.0.0.0",
                "deviceType": "Playback Device",
                "cecVersion": "Version 1.4",
                "osdName": "Fire TV Stick",
                "vendorID": "0ce7",
                "powerStatus": "Standby",
                "portNumber": 0
            }
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.HdmiCecSink.getDeviceList"}' http://127.0.0.1:9998/jsonrpc
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
function getDeviceList() {
  thunderJS.getDeviceList()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getDeviceList()">getDeviceList</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDeviceList(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getEnabled"></a>
## *getEnabled*


Retrieves the current status of the HDMI CEC Sink, indicating whether it is enabled or disabled. This API is essential for checking the operational state of the HDMI CEC Sink, which facilitates communication between connected devices over HDMI.

### Related Functions  
[setEnabled](#setEnabled) : Enables or disables the HDMI CEC Sink.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enabled | boolean | Indicates whether HDMI-CEC is enabled (`true`) or disabled (`false`) in the platform |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getEnabled"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enabled": false,
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
"method": "org.rdk.HdmiCecSink.getEnabled"
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
function getEnabled() {
  thunderJS.getEnabled()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getEnabled()">getEnabled</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getEnabled(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getOSDName"></a>
## *getOSDName*


Retrieves the On-Screen Display (OSD) name of the HDMI CEC Sink device. This API is essential for identifying the device's display name, which is used for communication and recognition in HDMI CEC networks. It ensures seamless integration and interaction between connected devices.

### Related Functions  
[setOSDName](#setOSDName) : Allows setting the OSD name of the HDMI CEC Sink device.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.name | string | The OSD Name |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getOSDName"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "name": "Fire TV Stick",
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
"method": "org.rdk.HdmiCecSink.getOSDName"
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
function getOSDName() {
  thunderJS.getOSDName()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getOSDName()">getOSDName</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getOSDName(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getVendorId"></a>
## *getVendorId*


Retrieves the vendor ID of the HDMI CEC Sink, which uniquely identifies the manufacturer of the device. This function ensures accurate communication and compatibility between HDMI devices by providing the vendor ID in a standardized format.

### Related Functions  
[setVendorId](#setVendorId) : Allows setting a custom vendor ID for the HDMI CEC Sink.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.vendorid | string | Vendor ID for this device. The ID can have a maximum of 6 characters |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.getVendorId"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "vendorid": "0019fc",
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
"method": "org.rdk.HdmiCecSink.getVendorId"
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
function getVendorId() {
  thunderJS.getVendorId()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getVendorId()">getVendorId</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getVendorId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="printDeviceList"></a>
## *printDeviceList*


This API is a debugging tool for developers that prints the list of connected devices along with their properties. It helps in identifying and verifying the devices connected to the system, ensuring proper functionality and troubleshooting. The operation indicates whether the device list was successfully printed.

### Related Functions  
[getDeviceList](#getDeviceList) : Retrieves the list of connected devices and their details.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.printed | boolean | Whether device list is printed |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.HdmiCecSink.printDeviceList"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "printed": true,
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
"method": "org.rdk.HdmiCecSink.printDeviceList"
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
function printDeviceList() {
  thunderJS.printDeviceList()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="printDeviceList()">printDeviceList</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void printDeviceList(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="requestActiveSource"></a>
## *requestActiveSource*


Request the active source in the HDMI-CEC network. This API broadcasts a message to identify the currently active source device, ensuring seamless communication and coordination between connected devices. It is essential for managing device interactions and maintaining accurate source status.

### Related Functions  
[getActiveSource](#getActiveSource) : Retrieves detailed information about the current active source, including logical and physical addresses, device type, and more.

### Events

| Event | Description |
| :-------- | :-------- |
| [onActiveSourceChange](#onActiveSourceChange) | Triggered with the active source device changes. |
| [onDeviceAdded](#onDeviceAdded) | Triggered when an HDMI cable is physically connected to the HDMI port on a TV, or the power cable is connected to the source device. |
| [onDeviceInfoUpdated](#onDeviceInfoUpdated) | Triggered when device information changes (physicalAddress, deviceType, vendorID, osdName, cecVersion, powerStatus). |
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
    "method": "org.rdk.HdmiCecSink.requestActiveSource"
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
"method": "org.rdk.HdmiCecSink.requestActiveSource"
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
function requestActiveSource() {
  thunderJS.requestActiveSource()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="requestActiveSource()">requestActiveSource</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void requestActiveSource(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="requestShortAudioDescriptor"></a>
## *requestShortAudioDescriptor*


Sends a CEC Request Short Audio Descriptor (SAD) message to the connected audio device, enabling the retrieval of audio format capabilities and descriptor information. This API is essential for ensuring compatibility and optimizing audio performance between devices in an HDMI-CEC setup.

### Related Functions  
[getActiveSource](#getActiveSource) : Retrieves the currently active source in the HDMI-CEC network.

### Events

| Event | Description |
| :-------- | :-------- |
| [shortAudiodesciptorEvent](#shortAudiodesciptorEvent) | Triggered when SAD is received from the connected audio device. |
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
    "method": "org.rdk.HdmiCecSink.requestShortAudioDescriptor"
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
"method": "org.rdk.HdmiCecSink.requestShortAudioDescriptor"
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
function requestShortAudioDescriptor() {
  thunderJS.requestShortAudioDescriptor()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="requestShortAudioDescriptor()">requestShortAudioDescriptor</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void requestShortAudioDescriptor(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="sendAudioDevicePowerOnMessage"></a>
## *sendAudioDevicePowerOnMessage*


This API is used to power on a connected audio device, typically triggered by the TV when it exits standby mode and detects an audio device in the network. It ensures seamless activation of the audio system, enabling users to enjoy uninterrupted audio functionality.

### Related Functions  
[sendGetAudioStatusMessage](#sendGetAudioStatusMessage) : Retrieves the current audio status of the connected device.

### Events

| Event | Description |
| :-------- | :-------- |
| [setSystemAudioModeEvent](#setSystemAudioModeEvent) | Triggered when CEC <Set System Audio Mode> message of device is received. |
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
    "method": "org.rdk.HdmiCecSink.sendAudioDevicePowerOnMessage"
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
"method": "org.rdk.HdmiCecSink.sendAudioDevicePowerOnMessage"
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
function sendAudioDevicePowerOnMessage() {
  thunderJS.sendAudioDevicePowerOnMessage()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendAudioDevicePowerOnMessage()">sendAudioDevicePowerOnMessage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendAudioDevicePowerOnMessage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="sendGetAudioStatusMessage"></a>
## *sendGetAudioStatusMessage*


Sends a request to the audio system to retrieve the current audio status, including mute status and volume level. This API is essential for ensuring accurate audio state updates and maintaining synchronization between devices in the HDMI-CEC network.

### Related Functions  
[getAudioDeviceConnectedStatus](#getAudioDeviceConnectedStatus) : Retrieves the connection status of the audio device.

### Events

| Event | Description |
| :-------- | :-------- |
| [reportAudioStatusEvent](#reportAudioStatusEvent) | Triggered when CEC <Report Audio Status> message of device is received. |
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
    "method": "org.rdk.HdmiCecSink.sendGetAudioStatusMessage"
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
"method": "org.rdk.HdmiCecSink.sendGetAudioStatusMessage"
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
function sendGetAudioStatusMessage() {
  thunderJS.sendGetAudioStatusMessage()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendGetAudioStatusMessage()">sendGetAudioStatusMessage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendGetAudioStatusMessage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="sendKeyPressEvent"></a>
## *sendKeyPressEvent*


Triggers a key press event on a specified HDMI-CEC device by sending the logical address and key code. This API facilitates remote control functionality, enabling seamless interaction with connected devices in a CEC-enabled ecosystem.

### Related Functions  
[sendUserControlPressed](#sendUserControlPressed) : Sends a "user control pressed" command to a device.  
[sendUserControlReleased](#sendUserControlReleased) : Sends a "user control released" command to a device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |
| params.keyCode | integer | The key code for the pressed key. Possible values : `0x41` (VOLUME_UP), `0x42` (VOLUME_DOWN), `0x43` (MUTE), `0x01` (UP), `0x02` (DOWN), `0x03` (LEFT), `0x04` (RIGHT), `0x00` (SELECT), `0x09` (HOME), `0x0D` (BACK), `0x20` (NUMBER_0), `0x21` (NUMBER_1), `0x22` (NUMBER_2), `0x23` (NUMBER_3), `0x24` (NUMBER_4), `0x25` (NUMBER_5), `0x26` (NUMBER_6), `0x27` (NUMBER_7), `0x28` (NUMBER_8), `0x29` (NUMBER_9) |

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
    "method": "org.rdk.HdmiCecSink.sendKeyPressEvent",
    "params": {
        "logicalAddress": 4,
        "keyCode": 65
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
"method": "org.rdk.HdmiCecSink.sendKeyPressEvent",
"params": {
"logicalAddress": 4,
"keyCode": 65
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
function sendKeyPressEvent(params) {
  thunderJS.sendKeyPressEvent(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendKeyPressEvent({logicalAddress: 4, keyCode: 65})">sendKeyPressEvent</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendKeyPressEvent(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["logicalAddress"] = 4;
        parameters["keyCode"] = 65;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="sendUserControlPressed"></a>
## *sendUserControlPressed*


Sends a user control command, such as directional navigation (e.g., UP, DOWN, LEFT, RIGHT) or numeric input (e.g., 0-9), to a specified logical address. This API facilitates remote control functionality by encoding and transmitting the appropriate user input command to the target device.

### Related Functions  
[sendUserControlReleased](#sendUserControlReleased) : Complements this function by signaling the release of a user control command.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |
| params.keyCode | integer | The key code for the pressed key. Possible values : `0x41` (VOLUME_UP), `0x42` (VOLUME_DOWN), `0x43` (MUTE), `0x01` (UP), `0x02` (DOWN), `0x03` (LEFT), `0x04` (RIGHT), `0x00` (SELECT), `0x09` (HOME), `0x0D` (BACK), `0x20` (NUMBER_0), `0x21` (NUMBER_1), `0x22` (NUMBER_2), `0x23` (NUMBER_3), `0x24` (NUMBER_4), `0x25` (NUMBER_5), `0x26` (NUMBER_6), `0x27` (NUMBER_7), `0x28` (NUMBER_8), `0x29` (NUMBER_9) |

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
    "method": "org.rdk.HdmiCecSink.sendUserControlPressed",
    "params": {
        "logicalAddress": 4,
        "keyCode": 65
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
"method": "org.rdk.HdmiCecSink.sendUserControlPressed",
"params": {
"logicalAddress": 4,
"keyCode": 65
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
function sendUserControlPressed(params) {
  thunderJS.sendUserControlPressed(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendUserControlPressed({logicalAddress: 4, keyCode: 65})">sendUserControlPressed</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendUserControlPressed(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["logicalAddress"] = 4;
        parameters["keyCode"] = 65;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="sendUserControlReleased"></a>
## *sendUserControlReleased*


Sends a "User Control Released" message to a specified logical address over the HDMI-CEC network. This API is used to indicate the release of a user control action, such as releasing a button on a remote control, ensuring proper communication and synchronization between devices.

### Related Functions  
[sendUserControlPressed](#sendUserControlPressed) : Sends a "User Control Pressed" message to indicate the initiation of a user control action.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

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
    "method": "org.rdk.HdmiCecSink.sendUserControlReleased",
    "params": {
        "logicalAddress": 4
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
"method": "org.rdk.HdmiCecSink.sendUserControlReleased",
"params": {
"logicalAddress": 4
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
function sendUserControlReleased(params) {
  thunderJS.sendUserControlReleased(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendUserControlReleased({logicalAddress: 4})">sendUserControlReleased</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendUserControlReleased(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["logicalAddress"] = 4;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="sendStandbyMessage"></a>
## *sendStandbyMessage*


Sends the CEC `<Standby>` message to notify connected HDMI-CEC devices to transition to standby mode. This function ensures proper communication between devices in the HDMI-CEC network, helping to manage power states efficiently and maintain synchronization across devices.

### Related Functions  
[setEnabled](#setEnabled) : Enables or disables the HDMI-CEC functionality.

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
    "method": "org.rdk.HdmiCecSink.sendStandbyMessage"
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
"method": "org.rdk.HdmiCecSink.sendStandbyMessage"
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
function sendStandbyMessage() {
  thunderJS.sendStandbyMessage()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="sendStandbyMessage()">sendStandbyMessage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void sendStandbyMessage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="setActivePath"></a>
## *setActivePath*


Sets the active path for the HDMI CEC device, enabling the specified source device to become active. If the source device is in standby mode, it wakes up to ensure seamless operation. This function is essential for managing HDMI routing and ensuring the correct device is set as the active source.

### Related Functions  
[getActiveRoute](#getActiveRoute) : Retrieves the current active route and associated details, including availability and path information.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.activePath | string | Physical address of the source device |

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
    "method": "org.rdk.HdmiCecSink.setActivePath",
    "params": {
        "activePath": "1.0.0.0"
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
"method": "org.rdk.HdmiCecSink.setActivePath",
"params": {
"activePath": "1.0.0.0"
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
function setActivePath(activePath) {
  thunderJS.setActivePath({ activePath: activePath })
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setActivePath('1.0.0.0')">setActivePath</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setActivePath(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["activePath"] = "1.0.0.0";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setActiveSource"></a>
## *setActiveSource*


Sets the current active source as the TV (physical address 0.0.0.0). This function is used when the TV switches to its internal tuner or applications, ensuring the TV is recognized as the active source in the HDMI-CEC network. It plays a critical role in maintaining proper source management and communication within the HDMI-CEC ecosystem.

### Related Functions  
[getActiveSource](#getActiveSource) : Retrieves the current active source details, including logical and physical addresses.

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
    "method": "org.rdk.HdmiCecSink.setActiveSource"
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
"method": "org.rdk.HdmiCecSink.setActiveSource"
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
function setActiveSource() {
  thunderJS.setActiveSource()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setActiveSource()">setActiveSource</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setActiveSource(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="setEnabled"></a>
## *setEnabled*


Enables or disables the HDMI-CEC (Consumer Electronics Control) functionality. When enabled, it activates CEC communication between connected devices, allowing seamless control and interaction. This setting is persisted for future sessions, ensuring consistent behavior across device restarts.

### Related Functions
[getEnabled](#getEnabled) : Retrieves the current status of the HDMI-CEC functionality (enabled or disabled).

### Events

| Event | Description |
| :-------- | :-------- |
| [reportCecEnabledEvent](#reportCecEnabledEvent) | Triggered when the HDMI-CEC is enabled. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Indicates whether HDMI-CEC is enabled (`true`) or disabled (`false`) in the platform |

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
    "method": "org.rdk.HdmiCecSink.setEnabled",
    "params": {
        "enabled": false
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
"method": "org.rdk.HdmiCecSink.setEnabled",
"params": {
"enabled": false
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
function setEnabled(params) {
  thunderJS.setEnabled(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setEnabled({enabled: false})">setEnabled</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setEnabled(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["enabled"] = false;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setMenuLanguage"></a>
## *setMenuLanguage*


Updates the menu language for the HDMI CEC sink device and broadcasts the `<Set Menu Language>` CEC message to connected devices. This API ensures the internal data structure reflects the new language setting, enabling seamless communication and synchronization across devices.

### Related Functions  
[getOSDName](#getOSDName) : Retrieves the On-Screen Display (OSD) name of the device.  
[getVendorId](#getVendorId) : Fetches the vendor ID of the device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.language | string | 3 byte ASCII defined in ISO_639-2_codes (https://en.wikipedia.org/wiki/List_of_ISO_639-2_codes) |

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
    "method": "org.rdk.HdmiCecSink.setMenuLanguage",
    "params": {
        "language": "chi"
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
"method": "org.rdk.HdmiCecSink.setMenuLanguage",
"params": {
"language": "chi"
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
function setMenuLanguage(language) {
  thunderJS.setMenuLanguage({ language: language })
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setMenuLanguage('chi')">setMenuLanguage</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setMenuLanguage(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["language"] = "chi";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setOSDName"></a>
## *setOSDName*


Sets the On-Screen Display (OSD) name for the HDMI CEC Sink device, enabling identification of the device on connected HDMI systems. This function updates the OSD name in the device's settings and ensures it is broadcasted to other devices in the HDMI network for seamless communication and recognition.

### Related Functions  
[getOSDName](#getOSDName) : Retrieves the current OSD name of the HDMI CEC Sink device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.name | string | The OSD Name |

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
    "method": "org.rdk.HdmiCecSink.setOSDName",
    "params": {
        "name": "Fire TV Stick"
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
"method": "org.rdk.HdmiCecSink.setOSDName",
"params": {
"name": "Fire TV Stick"
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
function setOSDName(params) {
  thunderJS.setOSDName(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setOSDName({name: 'Fire TV Stick'})">setOSDName</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
void setOSDName(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["name"] = "Fire TV Stick";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("Response: '%s'", result.c_str());
    }
}
```
</details>


<a name="setRoutingChange"></a>
## *setRoutingChange*


Changes the routing configuration when switching between HDMI inputs and TV. This API ensures seamless transitions by updating the active route based on the specified old and new port identifiers, validating the ports, and sending the necessary routing change messages.

### Related Functions  
[getActiveRoute](#getActiveRoute) : Retrieves the currently active route configuration.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.oldPort | string | Current active port, such as `TV`, `HDMI0`, `HDMI1`, `HDMI2` |
| params.newPort | string | New port to switch to, such as `TV`, `HDMI0`, `HDMI1`, `HDMI2` |

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
    "method": "org.rdk.HdmiCecSink.setRoutingChange",
    "params": {
        "oldPort": "HDMI0",
        "newPort": "TV"
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
"method": "org.rdk.HdmiCecSink.setRoutingChange",
"params": {
"oldPort": "HDMI0",
"newPort": "TV"
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
function setRoutingChange(params) {
  thunderJS.setRoutingChange(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setRoutingChange({ oldPort: 'HDMI0', newPort: 'TV' })">setRoutingChange</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setRoutingChange(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["oldPort"] = "HDMI0";
        parameters["newPort"] = "TV";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setupARCRouting"></a>
## *setupARCRouting*


Enables and manages Audio Return Channel (ARC) routing for HDMI devices, facilitating seamless audio transmission between connected devices. This API handles ARC initiation, termination, and state transitions, ensuring proper synchronization and communication between devices.

### Related Functions  
[getActiveRoute](#getActiveRoute) : Retrieves the currently active HDMI route.

### Events

| Event | Description |
| :-------- | :-------- |
| [arcInitiationEvent](#arcInitiationEvent) | Triggered when routing though the HDMI ARC port is successfully established. |
| [arcTerminationEvent](#arcTerminationEvent) | Triggered when routing though the HDMI ARC port terminates. |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | boolean | Indicates whether HDMI-CEC ARC is enabled (`true`) or disabled (`false`). If enabled, the CEC \<Request ARC Initiation\> and \<Report ARC Initiated\> messages are sent. If disabled, the CEC \<Request ARC Termination\> and \<Report ARC Terminated\> messages are sent |

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
    "method": "org.rdk.HdmiCecSink.setupARCRouting",
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
"method": "org.rdk.HdmiCecSink.setupARCRouting",
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
function setupARCRouting(params) {
  thunderJS.setupARCRouting(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setupARCRouting({ enabled: true })">setupARCRouting</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setupARCRouting(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="setVendorId"></a>
## *setVendorId*


Sets the vendor ID of the HDMI CEC Sink, which is used to uniquely identify the device in the HDMI-CEC network. This function ensures the vendor ID is correctly configured, defaulting to a predefined value if not provided or invalid. Proper configuration of the vendor ID is essential for seamless communication and device recognition in the HDMI-CEC ecosystem.

### Related Functions  
[getVendorId](#getVendorId) : Retrieves the currently configured vendor ID of the HDMI CEC Sink.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.vendorid | string | Vendor ID for this device. The ID can have a maximum of 6 characters |

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
    "method": "org.rdk.HdmiCecSink.setVendorId",
    "params": {
        "vendorid": "0019fc"
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
"method": "org.rdk.HdmiCecSink.setVendorId",
"params": {
"vendorid": "0019fc"
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
function setVendorId(vendorid) {
  thunderJS.setVendorId(vendorid)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setVendorId('0019fc')">setVendorId</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setVendorId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["vendorid"] = "0019fc";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setLatencyInfo"></a>
## *setLatencyInfo*


Sets the current latency values, including video latency, latency flags, audio output compensated value, and audio output delay, by sending a `<Report Current Latency>` message. This API is essential for enabling the Dynamic Auto LipSync feature, ensuring synchronized audio and video playback for connected HDMI devices.

### Related Functions  
[getAudioDeviceConnectedStatus](#getAudioDeviceConnectedStatus) : Retrieves the connection status of the audio device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.videoLatency | string | Indicates the Video Latency value of the target device |
| params.lowLatencyMode | string | Indicates whether low latency Mode is 0 or 1 |
| params.audioOutputCompensated | string | Indicates whether Audio Output is delay compensated or not. 0 = (NA)Sent by Non-TV, 1 = TV's audio Output is delay compensated, 2 = Not delay compensated, 3 = Partially delayed |
| params.audioOutputDelay | string | Indicates the Audio Output Delay value of the target device |

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
    "method": "org.rdk.HdmiCecSink.setLatencyInfo",
    "params": {
        "videoLatency": "2",
        "lowLatencyMode": "1",
        "audioOutputCompensated": "1",
        "audioOutputDelay": "20"
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
"method": "org.rdk.HdmiCecSink.setLatencyInfo",
"params": {
"videoLatency": "2",
"lowLatencyMode": "1",
"audioOutputCompensated": "1",
"audioOutputDelay": "20"
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
function setLatencyInfo(params) {
  thunderJS.setLatencyInfo(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setLatencyInfo({videoLatency: '2', lowLatencyMode: '1', audioOutputCompensated: '1', audioOutputDelay: '20'})">setLatencyInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setLatencyInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["videoLatency"] = "2";
        parameters["lowLatencyMode"] = "1";
        parameters["audioOutputCompensated"] = "1";
        parameters["audioOutputDelay"] = "20";
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

The following events are provided by the org.rdk.HdmiCecSink plugin:

HdmiCecSink interface events:

| Event | Description |
| :-------- | :-------- |
| [arcInitiationEvent](#arcInitiationEvent) | Triggered when routing though the HDMI ARC port is successfully established |
| [arcTerminationEvent](#arcTerminationEvent) | Triggered when routing though the HDMI ARC port terminates |
| [onActiveSourceChange](#onActiveSourceChange) | Triggered with the active source device changes |
| [onDeviceAdded](#onDeviceAdded) | Triggered when an HDMI cable is physically connected to the HDMI port on a TV, or the power cable is connected to the source device |
| [onDeviceInfoUpdated](#onDeviceInfoUpdated) | Triggered when device information changes (physicalAddress, deviceType, vendorID, osdName, cecVersion, powerStatus) |
| [onDeviceRemoved](#onDeviceRemoved) | Triggered when HDMI cable is physically removed from the HDMI port on a TV or the power cable is removed from the source device |
| [onImageViewOnMsg](#onImageViewOnMsg) | Triggered when an \<Image View ON\> CEC message is received from the source device |
| [onInActiveSource](#onInActiveSource) | Triggered when the source is no longer active |
| [onTextViewOnMsg](#onTextViewOnMsg) | Triggered when a \<Text View ON\> CEC message is received from the source device |
| [onWakeupFromStandby](#onWakeupFromStandby) | Triggered when the TV is in standby mode and it receives \<Image View ON\>/ \<Text View ON\>/ \<Active Source\> CEC message from the connected source device |
| [reportAudioDeviceConnectedStatus](#reportAudioDeviceConnectedStatus) | Triggered when an audio device is added or removed |
| [reportAudioStatusEvent](#reportAudioStatusEvent) | Triggered when CEC \<Report Audio Status\> message of device is received |
| [reportFeatureAbortEvent](#reportFeatureAbortEvent) | Triggered when CEC \<Feature Abort\> message of device is received |
| [reportCecEnabledEvent](#reportCecEnabledEvent) | Triggered when the HDMI-CEC is enabled |
| [setSystemAudioModeEvent](#setSystemAudioModeEvent) | Triggered when CEC \<Set System Audio Mode\> message of device is received |
| [shortAudiodesciptorEvent](#shortAudiodesciptorEvent) | Triggered when SAD is received from the connected audio device |
| [standbyMessageReceived](#standbyMessageReceived) | Triggered when the source device changes status to `STANDBY` |


<a name="arcInitiationEvent"></a>
## *arcInitiationEvent*


The *arcInitiationEvent* is triggered when the Audio Return Channel (ARC) is successfully initiated between connected devices. This event indicates that the ARC setup process has been completed, allowing audio signals to be transmitted from the TV to an external audio device, such as a soundbar or AV receiver, over the HDMI connection. Users can rely on this event to confirm that their ARC-enabled devices are ready for audio playback. The event is typically triggered after the system processes an ARC initiation request and verifies the successful establishment of the ARC state.

### Related Functions
[setupARCRouting](#setupARCRouting) : This function plays a key role in configuring the ARC routing process, which directly leads to the triggering of the *arcInitiationEvent* once the setup is complete.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.status | string | Whether the operation succeeded |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.arcInitiationEvent",
    "params": {
        "status": "success"
    }
}
```

<a name="arcTerminationEvent"></a>
## *arcTerminationEvent*


The *arcTerminationEvent* signifies the end of an Audio Return Channel (ARC) session. This event is triggered when the ARC connection between devices is terminated, either due to user action, device disconnection, or system changes. It ensures that users are informed when the ARC functionality is no longer active, allowing them to take appropriate actions, such as troubleshooting or switching to alternative audio configurations.

### Related Functions  
[setupARCRouting](#setupARCRouting) : This function is directly related to ARC management and can trigger the termination event when ARC routing is disabled or reconfigured.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.status | string | Whether the operation succeeded |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.arcTerminationEvent",
    "params": {
        "status": "success"
    }
}
```

<a name="onActiveSourceChange"></a>
## *onActiveSourceChange*


This event is triggered when the active source device on the HDMI-CEC network changes. The active source is the device currently sending content to the display. This event notifies users about the logical and physical addresses of the new active source, allowing them to identify which device has taken control. It ensures users are aware of changes in the active source, enhancing their ability to manage connected devices.

### Related Functions
[requestActiveSource](#requestActiveSource) : This function can trigger the event by sending a request to identify the current active source on the HDMI-CEC network.

[setActiveSource](#setActiveSource) : This function can trigger the event by setting a device as the active source, which updates the active source status.

[getActiveSource](#getActiveSource) : This function retrieves the current active source, which may be updated when the event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |
| params.physicalAddress | string | Physical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onActiveSourceChange",
    "params": {
        "logicalAddress": 4,
        "physicalAddress": "1.0.0.0"
    }
}
```

<a name="onDeviceAdded"></a>
## *onDeviceAdded*


The *onDeviceAdded* event is triggered whenever a new HDMI-CEC device is detected and added to the system. This event notifies users that a device has been successfully recognized and integrated into the HDMI-CEC network. It provides essential information about the newly added device, such as its logical address, physical address, device type, vendor ID, and other relevant details. This event ensures users are aware of changes in their connected device ecosystem, enabling seamless interaction and management of devices.  

### Related Functions  
[getDeviceList](#getDeviceList) : Retrieves the list of all connected HDMI-CEC devices, including the newly added device, allowing users to view detailed information about their devices.  

[getVendorId](#getVendorId) : Provides the vendor ID of the newly added device, helping users identify the manufacturer of the device.  

[getOSDName](#getOSDName) : Fetches the On-Screen Display (OSD) name of the newly added device, offering a user-friendly way to identify the device.  

[setOSDName](#setOSDName) : Updates the OSD name of the newly added device, ensuring the device is correctly labeled for user convenience.  

[setVendorId](#setVendorId) : Updates the vendor ID of the newly added device, ensuring accurate identification of the device's manufacturer.  

[printDeviceList](#printDeviceList) : Displays the list of all connected devices, including the newly added device, for easy reference and management.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceAdded",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="onDeviceInfoUpdated"></a>
## *onDeviceInfoUpdated*


This event is triggered whenever there is an update to the information of a connected device. It notifies users about changes such as device configuration, vendor details, or other relevant updates. For example, if a new device is added or an existing device's information is modified, this event ensures users are informed promptly.  

### Related Functions  
[getDeviceList](#getDeviceList) : Retrieves the list of connected devices, which may trigger updates to device information.  
[getVendorId](#getVendorId) : Requests the vendor ID of a device, which can lead to updates in device details.  
[getOSDName](#getOSDName) : Requests the On-Screen Display (OSD) name of a device, contributing to updated device information.  
[setVendorId](#setVendorId) : Updates the vendor ID of a device, which directly impacts the device information.  
[setOSDName](#setOSDName) : Updates the OSD name of a device, triggering changes in device details.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceInfoUpdated",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="onDeviceRemoved"></a>
## *onDeviceRemoved*


This event is triggered when a device, such as a USB storage device or an audio device, is disconnected or removed from the system. It provides users with information about the removed device, including its name, device path, and any associated mount points. For audio devices, it also indicates changes in the connection status, such as when an HDMI-CEC audio device is unplugged. This event helps users stay informed about changes in connected devices and ensures that the system can respond appropriately to such changes.

### Related Functions

[getAudioDeviceConnectedStatus](#getAudioDeviceConnectedStatus) : This function monitors the connection status of audio devices. It is relevant to this event as it helps detect when an audio device is removed.

[getDeviceList](#getDeviceList) : This function retrieves the list of connected devices. It is related to this event because the device list is updated when a device is removed.

[printDeviceList](#printDeviceList) : This function displays the current list of connected devices. It is useful for verifying the removal of a device after this event is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceRemoved",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="onImageViewOnMsg"></a>
## *onImageViewOnMsg*


This event is triggered when an "Image View ON" CEC (Consumer Electronics Control) message is received from a source device. The "Image View ON" message is typically sent by a source device, such as a Blu-ray player or streaming device, to signal that it is ready to display video content. This event is used to notify the system that the source device intends to activate the display, potentially bringing the TV or display device out of standby mode.

### Related Functions
[getDeviceList](#getDeviceList) : This function helps manage and retrieve the list of connected devices, which is updated when the "Image View ON" message is received.

[setActiveSource](#setActiveSource) : This function is used to set the active source device, which may be triggered in response to the "Image View ON" message to ensure the correct source is displayed.

[sendStandbyMessage](#sendStandbyMessage) : This function can be used to manage the standby state of devices, which may be relevant if the "Image View ON" message is received while the TV is in standby mode.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onImageViewOnMsg",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="onInActiveSource"></a>
## *onInActiveSource*


This event is triggered when a previously active HDMI source is no longer active. It indicates that the device associated with the specified logical and physical addresses has stopped being the active source. This event is particularly useful for monitoring and managing HDMI-CEC (Consumer Electronics Control) connections, ensuring that the system is aware of changes in the active source status.

### Related Functions  
[setActiveSource](#setActiveSource) : This function can trigger the event by updating the active source. When a source is set as active, other sources may become inactive, leading to the `onInActiveSource` event being triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |
| params.physicalAddress | string | Physical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onInActiveSource",
    "params": {
        "logicalAddress": 4,
        "physicalAddress": "1.0.0.0"
    }
}
```

<a name="onTextViewOnMsg"></a>
## *onTextViewOnMsg*


onTextViewOnMsg is an event that occurs when a specific user interaction or system message related to text input or control is detected. This event is triggered when a user presses or releases a control key, or when a relevant message is processed by the system. It is designed to notify the system or connected devices about user actions or text-related updates, ensuring seamless communication and functionality.

### Related Functions  
[sendUserControlPressed](#sendUserControlPressed) : This function triggers the event by sending a message when a user presses a control key, such as a numeric or navigation button.  

[sendUserControlReleased](#sendUserControlReleased) : This function triggers the event by sending a message when a user releases a control key, signaling the end of the interaction.  

[sendKeyPressEvent](#sendKeyPressEvent) : This function triggers the event by notifying the system about a key press action, enabling the system to respond accordingly.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onTextViewOnMsg",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="onWakeupFromStandby"></a>
## *onWakeupFromStandby*


This event is triggered when the TV is in standby mode and receives a CEC message such as `<Image View ON>`, `<Text View ON>`, or `<Active Source>` from a connected source device. These messages indicate that the source device is requesting the TV to wake up from standby mode and become active. The event ensures seamless communication between devices, allowing the TV to respond appropriately to the source device's request.

### Related Functions  
- [setActiveSource](#setActiveSource) : Activates the source device that sent the wake-up request, ensuring the TV switches to the correct input.  
- [setEnabled](#setEnabled) : Enables or disables CEC functionality, which is necessary for processing wake-up requests.  
- [sendStandbyMessage](#sendStandbyMessage) : Sends a standby message to other devices, ensuring proper communication when transitioning between power states.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onWakeupFromStandby",
    "params": {
        "logicalAddress": 4
    }
}
```

<a name="reportAudioDeviceConnectedStatus"></a>
## *reportAudioDeviceConnectedStatus*


This event is triggered when an audio device is added or removed from the system. It provides information about the connection status of the audio device, helping users understand whether an audio device is currently connected or disconnected. This event ensures seamless monitoring of audio device connectivity, enhancing the overall user experience with audio systems.

### Related Functions  
[getAudioDeviceConnectedStatus](#getAudioDeviceConnectedStatus) : This function retrieves the current connection status of the audio device, directly triggering the event when there is a change in the device's connectivity.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.status | string | The status |
| params.audioDeviceConnected | string | `true` if an audio device is connected, otherwise `false` |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.reportAudioDeviceConnectedStatus",
    "params": {
        "status": "success",
        "audioDeviceConnected": "true"
    }
}
```

<a name="reportAudioStatusEvent"></a>
## *reportAudioStatusEvent*


The *reportAudioStatusEvent* is triggered when a device sends a CEC `<Report Audio Status>` message. This event provides users with real-time information about the audio status of the connected device, including its mute status and current volume level. It ensures that users are informed about the audio settings of their devices, enabling seamless control and monitoring of audio functionality.  

### Related Functions  
[sendGetAudioStatusMessage](#sendGetAudioStatusMessage) : This function initiates a request to retrieve the audio status of a connected device, which subsequently triggers the *reportAudioStatusEvent* when the response is received.  

[requestShortAudioDescriptor](#requestShortAudioDescriptor) : This function requests detailed audio format information from the connected device, which may indirectly lead to the triggering of *reportAudioStatusEvent* as part of the audio status update process.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.muteStatus | integer | The mute status |
| params.volumeLevel | integer | The volume level of device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.reportAudioStatusEvent",
    "params": {
        "muteStatus": 0,
        "volumeLevel": 28
    }
}
```

<a name="reportFeatureAbortEvent"></a>
## *reportFeatureAbortEvent*


The `reportFeatureAbortEvent` is triggered when a connected HDMI-CEC device sends a `<Feature Abort>` message. This event indicates that the device was unable to process a specific CEC command. The event provides details about the logical address of the device, the opcode of the command that was rejected, and the reason for the rejection. It helps users understand why a particular feature or command failed to execute in the HDMI-CEC network.

### Related Functions
No related functions apply.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |
| params.opcode | integer | The opcode send to the device |
| params.FeatureAbortReason | integer | Reason for the feature abort |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.reportFeatureAbortEvent",
    "params": {
        "logicalAddress": 4,
        "opcode": 0,
        "FeatureAbortReason": 0
    }
}
```

<a name="reportCecEnabledEvent"></a>
## *reportCecEnabledEvent*


The *reportCecEnabledEvent* is triggered whenever the HDMI-CEC (Consumer Electronics Control) feature is enabled or disabled on the device. This event notifies users about the current status of HDMI-CEC functionality, which allows connected devices to communicate and control each other via HDMI. For example, enabling HDMI-CEC can allow a TV remote to control other connected devices like soundbars or Blu-ray players. This event ensures users are informed when HDMI-CEC is activated or deactivated.

### Related Functions
[getEnabled](#getEnabled) : This function retrieves the current status of HDMI-CEC (enabled or disabled) and is directly tied to the triggering of this event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.cecEnable | string | Whether the cec is enabled |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.reportCecEnabledEvent",
    "params": {
        "cecEnable": "true"
    }
}
```

<a name="setSystemAudioModeEvent"></a>
## *setSystemAudioModeEvent*


The *setSystemAudioModeEvent* is triggered when the system audio mode is either enabled or disabled. This event indicates whether the audio output is being routed through an external audio system, such as a soundbar or AV receiver, instead of the TV's internal speakers. The event is typically triggered when there is a change in the system audio mode status, such as turning it on or off. For example, when the system audio mode is turned on, the TV routes audio to the connected external audio device, provided the device is powered on and ready to receive audio.

### Related Functions
[setEnabled](#setEnabled) : This function can enable or disable the HDMI-CEC feature, which is a prerequisite for triggering the *setSystemAudioModeEvent*.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.audioMode | string | Audio mode of system |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.setSystemAudioModeEvent",
    "params": {
        "audioMode": "On"
    }
}
```

<a name="shortAudiodesciptorEvent"></a>
## *shortAudiodesciptorEvent*


The **shortAudiodesciptorEvent** is triggered when the Short Audio Descriptor (SAD) information is received from a connected audio device. This event provides users with detailed audio capabilities of the connected device, such as supported audio formats and configurations. It ensures seamless communication between devices, enhancing the audio experience by enabling compatibility and optimal settings. 

This event is particularly useful in scenarios where users need to verify or adjust audio settings based on the capabilities of their connected audio system.

### Related Functions
[requestShortAudioDescriptor](#requestShortAudioDescriptor) : This function sends a request to the connected audio device to retrieve its Short Audio Descriptor (SAD) information. The response to this request triggers the **shortAudiodesciptorEvent**.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ShortAudioDescriptor | array | The SAD information (formatid, audioFormatCode, numberofdescriptor) |
| params.ShortAudioDescriptor[#] | integer |  |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.shortAudiodesciptorEvent",
    "params": {
        "ShortAudioDescriptor": [
            [
                0,
                10,
                2
            ]
        ]
    }
}
```

<a name="standbyMessageReceived"></a>
## *standbyMessageReceived*


This event is triggered when a connected HDMI-CEC device changes its status to "STANDBY." It indicates that the device has entered a low-power mode or is no longer actively functioning as a source. This event is useful for monitoring the power state of devices in an HDMI-CEC network and can help synchronize actions, such as turning off other connected devices or updating the user interface to reflect the standby status.  

### Related Functions  
[sendStandbyMessage](#sendStandbyMessage) : This function sends a "Standby" message to connected HDMI-CEC devices, which can trigger the standbyMessageReceived event when the target device transitions to standby mode.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logicalAddress | integer | Logical address of the device |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.standbyMessageReceived",
    "params": {
        "logicalAddress": 4
    }
}
```
