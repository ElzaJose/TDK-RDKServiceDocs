<!-- Generated automatically, DO NOT EDIT! -->
<a name="DeviceDiagnostics_Plugin"></a>
# DeviceDiagnostics Plugin

A org.rdk.DeviceDiagnostics plugin for Thunder framework.

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


**Overview of DeviceDiagnostics**
The **DeviceDiagnostics** RDK service is a plugin registered within the WPEFramework that provides enhanced diagnostics capabilities for devices. It offers detailed information about device configurations and the status of AV decoders, such as their operational states (e.g., IDLE, PAUSED, ACTIVE). This service is designed to assist in monitoring and troubleshooting device performance and behavior.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.DeviceDiagnostics*) |
| classname | string | Class name: *org.rdk.DeviceDiagnostics* |
| locator | string | Library name: *libWPEFrameworkDeviceDiagnostics.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.DeviceDiagnostics plugin:

DeviceDiagnostics interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [getConfiguration](#getConfiguration) | Gets the values associated with the corresponding property names | NA |
| [getMilestones](#getMilestones) | Returns the list of milestones | NA |
| [logMilestone](#logMilestone) | Log marker string to rdk milestones log | NA |
| [getAVDecoderStatus](#getAVDecoderStatus) | Gets the most active status of audio/video decoder/pipeline | NA |


<a name="getConfiguration"></a>
## *getConfiguration*


Retrieves the values associated with specified property names, enabling users to query and obtain configuration details for a device. This API is essential for accessing key device settings and ensuring proper diagnostics by returning the requested properties and their corresponding values. It also provides a success status to confirm the operation's outcome.

### Related Functions  
[getMilestones](#getMilestones) : Retrieves milestone-related information for diagnostics.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.names | array | String array of property names |
| params.names[#] | string | Property names as represented in the data model like `Device.X_CISCO_COM_LED.RedPwm`, `Device.DeviceInfo.Manufacturer`, `Device.DeviceInfo.UpTime`, `Device.DeviceInfo.ProcessStatus.CPUUsage`, etc |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.paramList | array | An array of JSON objects with the specified properties and their values |
| result.paramList[#] | object |  |
| result.paramList[#].name | string | The property name; Empty, if the property name is not supported |
| result.paramList[#].value | string | The property value; Empty, if the property name is not supported |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DeviceDiagnostics.getConfiguration",
    "params": {
        "names": [
            "Device.X_CISCO_COM_LED.RedPwm"
        ]
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "paramList": [
            {
                "name": "Device.X_CISCO_COM_LED.RedPwm",
                "value": "123"
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
"method": "org.rdk.DeviceDiagnostics.getConfiguration",
"params": {
"names": [
"Device.X_CISCO_COM_LED.RedPwm"
]
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
function getConfiguration(params) {
  thunderJS.getConfiguration(params)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getConfiguration({names: ['Device.X_CISCO_COM_LED.RedPwm']})">getConfiguration</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getConfiguration(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["names"] = JsonArray();
        parameters["names"].Add("Device.X_CISCO_COM_LED.RedPwm");
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getMilestones"></a>
## *getMilestones*


Retrieves a list of milestones, providing a structured overview of key markers or events. This API is essential for tracking progress or significant points in a process, ensuring better monitoring and debugging.

### Related Functions  
[logMilestone](#logMilestone) : Logs a specific milestone marker to the RDK milestones log.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.milestones | array | A string [] of milestones |
| result.milestones[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DeviceDiagnostics.getMilestones"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "milestones": [
            "2020 Jan 28 08:24:06.762355 abcdpq1 systemd[1]: Starting Log RDK Started Service..."
        ],
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DeviceDiagnostics.getMilestones"}' http://127.0.0.1:9998/jsonrpc
```
</details>

<details>
<summary><kbd>JS</kbd></summary>

```javascript
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function getMilestones() {
  thunderJS.getMilestones()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getMilestones()">getMilestones</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMilestones(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="logMilestone"></a>
## *logMilestone*


Logs a specified marker string to the RDK milestones log file, enabling developers to track significant events or checkpoints during system operation. This function ensures the marker is recorded only if it is non-empty, providing a reliable way to document system milestones for debugging or analysis.

### Related Functions  
[getMilestones](#getMilestones) : Retrieves the list of logged milestones.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.marker | string | Milestone marker string |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | boolean | Whether the request succeeded |

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
    "method": "org.rdk.DeviceDiagnostics.logMilestone",
    "params": {
        "marker": "..."
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
'{
"jsonrpc": "2.0",
"id": 42,
"method": "org.rdk.DeviceDiagnostics.logMilestone",
"params": {
"marker": "..."
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
function logMilestone(marker) {
  thunderJS.logMilestone(marker)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="logMilestone('...')">logMilestone</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void logMilestone(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["marker"] = "...";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getAVDecoderStatus"></a>
## *getAVDecoderStatus*


Retrieves the most active status of the audio/video decoder or pipeline, providing insights into the current operational state. This API is essential for monitoring decoder activity and ensuring optimal performance in multimedia applications.

### Related Functions  
[getConfiguration](#getConfiguration) : Provides configuration details that may complement decoder status insights.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.avDecoderStatus | string | The status. If AV decoder status is not supported, the default state will always be IDLE. (must be one of the following: *ACTIVE*, *PAUSED*, *IDLE*) |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.DeviceDiagnostics.getAVDecoderStatus"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "avDecoderStatus": "ACTIVE"
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.DeviceDiagnostics.getAVDecoderStatus"}' http://127.0.0.1:9998/jsonrpc
```
</details>

<details>
<summary><kbd>JS</kbd></summary>

```javascript
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>ThunderJS - Browser example</title>
</head>
<body>
<script>
var thunderJS
var defaultHost = localStorage.getItem('host')
var host = prompt('Please inform the IP address of your STB', defaultHost || '192.168.')
localStorage.setItem('host', host)
thunderJS = ThunderJS({
  host: host,
})
function getAVDecoderStatus() {
  thunderJS.getAVDecoderStatus()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getAVDecoderStatus()">getAVDecoderStatus</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getAVDecoderStatus(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

The following events are provided by the org.rdk.DeviceDiagnostics plugin:

DeviceDiagnostics interface events:

| Event | Description |
| :-------- | :-------- |
| [onAVDecoderStatusChanged](#onAVDecoderStatusChanged) | Triggered when the most active status of audio/video decoder/pipeline changes |


<a name="onAVDecoderStatusChanged"></a>
## *onAVDecoderStatusChanged*


This event is triggered whenever there is a change in the most active status of the audio/video decoder or pipeline. It provides users with real-time updates about the current state of the decoder, ensuring they are informed about any changes that may impact audio or video playback.  

### Related Functions  
[getAVDecoderStatus](#getAVDecoderStatus) : This function retrieves the current status of the most active audio/video decoder. It plays a key role in identifying changes in the decoder's state, which subsequently triggers the `onAVDecoderStatusChanged` event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.avDecoderStatusChange | string | The status. If AV decoder status is not supported, the default state will always be IDLE. (must be one of the following: *ACTIVE*, *PAUSED*, *IDLE*) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onAVDecoderStatusChanged",
    "params": {
        "avDecoderStatusChange": "ACTIVE"
    }
}
```
