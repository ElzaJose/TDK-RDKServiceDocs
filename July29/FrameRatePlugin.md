<!-- Generated automatically, DO NOT EDIT! -->
<a name="FrameRate_Plugin"></a>
# FrameRate Plugin

A org.rdk.FrameRate plugin for Thunder framework.

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


The **FrameRate** RDK service is designed to monitor and manage the frame rate performance of a device. It collects and reports metrics such as average, minimum, and maximum frames per second (FPS) over a specified time interval. This service also notifies registered clients about changes in display frame rate, ensuring real-time updates for performance monitoring and optimization.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.FrameRate*) |
| classname | string | Class name: *org.rdk.FrameRate* |
| locator | string | Library name: *libWPEFrameworkFrameRate.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.FrameRate plugin:

FrameRate interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [getDisplayFrameRate](#getDisplayFrameRate) | Returns the current display frame rate values | NA |
| [getFrmMode](#getFrmMode) | Returns the current auto framerate mode | NA |
| [setCollectionFrequency](#setCollectionFrequency) | Sets the FPS data collection interval | NA |
| [setDisplayFrameRate](#setDisplayFrameRate) | Sets the display framerate values | [onDisplayFrameRateChanging](#onDisplayFrameRateChanging), [onDisplayFrameRateChanged](#onDisplayFrameRateChanged) |
| [setFrmMode](#setFrmMode) | Sets the auto framerate mode | NA |
| [startFpsCollection](#startFpsCollection) | Starts the FPS data collection | [onFpsEvent](#onFpsEvent) |
| [stopFpsCollection](#stopFpsCollection) | Stops the FPS data collection | [onFpsEvent](#onFpsEvent) |
| [updateFps](#updateFps) | Updates Fps values | NA |


<a name="getDisplayFrameRate"></a>
## *getDisplayFrameRate*


Retrieves the current display frame rate of the system, providing users with real-time information about the refresh rate of their display. This is useful for monitoring or troubleshooting display performance and ensuring optimal viewing experiences.

### Related Functions  
[setDisplayFrameRate](#setDisplayFrameRate) : Allows users to set a specific display frame rate.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.framerate | string | The display framerate setting (width x height x framerate) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.FrameRate.getDisplayFrameRate"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "framerate": "3840x2160px48",
        "success": true
    }
}
```



<details>
<summary><kbd>CURL</kbd></summary>

```bash
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.FrameRate.getDisplayFrameRate"}' http://127.0.0.1:9998/jsonrpc
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
function getDisplayFrameRate() {
  thunderJS.getDisplayFrameRate()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getDisplayFrameRate()">getDisplayFrameRate</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getDisplayFrameRate(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="getFrmMode"></a>
## *getFrmMode*


Retrieves the current frame mode setting, which determines how frames are processed or displayed. This function is useful for understanding the device's frame handling configuration, ensuring compatibility with specific content or display requirements.

### Related Functions  
[setFrmMode](#setFrmMode) : Allows you to configure the frame mode setting.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.auto-frm-mode | integer | `0` for auto framerate mode disabled, `1` for auto framerate mode enabled (must be one of the following: *0*, *1*) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.FrameRate.getFrmMode"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "auto-frm-mode": 0,
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
"method": "org.rdk.FrameRate.getFrmMode"
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
function getFrmMode() {
  thunderJS.getFrmMode()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getFrmMode()">getFrmMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getFrmMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="setCollectionFrequency"></a>
## *setCollectionFrequency*


This API allows you to configure the interval at which FPS (frames per second) data is collected, ensuring precise monitoring of performance metrics. You can set the frequency in milliseconds, with a minimum value of 100ms and a default of 10,000ms. This is useful for optimizing system performance or diagnosing issues by adjusting the data collection rate to suit your needs.

### Related Functions  
[getDisplayFrameRate](#getDisplayFrameRate) : Retrieves the current display frame rate.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.frequency | integer | The amount of time in milliseconds. The default frequency is 10000 milliseconds |

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
    "method": "org.rdk.FrameRate.setCollectionFrequency",
    "params": {
        "frequency": 1000
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
"method": "org.rdk.FrameRate.setCollectionFrequency",
"params": {
"frequency": 1000
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
function setCollectionFrequency(frequency) {
  thunderJS.setCollectionFrequency(frequency)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setCollectionFrequency(1000)">setCollectionFrequency</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setCollectionFrequency(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["frequency"] = 1000;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setDisplayFrameRate"></a>
## *setDisplayFrameRate*


Allows users to adjust the display's frame rate to optimize video playback quality and ensure compatibility with different content formats. This function is essential for achieving smoother visuals and reducing motion artifacts, enhancing the overall viewing experience.

### Related Functions  
[getDisplayFrameRate](#getDisplayFrameRate) : Retrieves the current display frame rate setting.

### Events

| Event | Description |
| :-------- | :-------- |
| [onDisplayFrameRateChanging](#onDisplayFrameRateChanging) | Triggered when the framerate changes started. |
| [onDisplayFrameRateChanged](#onDisplayFrameRateChanged) | Triggered when the framerate changed |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.framerate | string | The display framerate setting (width x height x framerate) |

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
    "method": "org.rdk.FrameRate.setDisplayFrameRate",
    "params": {
        "framerate": "3840x2160px48"
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
"method": "org.rdk.FrameRate.setDisplayFrameRate",
"params": {
"framerate": "3840x2160px48"
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
function setDisplayFrameRate(framerate) {
  thunderJS.setDisplayFrameRate({ framerate: framerate })
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setDisplayFrameRate('3840x2160px48')">setDisplayFrameRate</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setDisplayFrameRate(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["framerate"] = "3840x2160px48";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="setFrmMode"></a>
## *setFrmMode*


Sets the auto frame rate mode to optimize video playback quality. Users can choose between two modes (0 or 1) to adjust how the system handles frame rate synchronization, ensuring smoother visuals or compatibility with specific display settings.

### Related Functions  
[getFrmMode](#getFrmMode) : Retrieves the current auto frame rate mode setting.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.frmmode | integer | `0` for auto framerate mode disabled, `1` for auto framerate mode enabled (must be one of the following: *0*, *1*) |

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
    "method": "org.rdk.FrameRate.setFrmMode",
    "params": {
        "frmmode": 0
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
"method": "org.rdk.FrameRate.setFrmMode",
"params": {
"frmmode": 0
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
function setFrmMode(frmmode) {
  thunderJS.setFrmMode(frmmode)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="setFrmMode(0)">setFrmMode</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void setFrmMode(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["frmmode"] = 0;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="startFpsCollection"></a>
## *startFpsCollection*


Initiates the collection of FPS (Frames Per Second) data to monitor performance metrics over time. This function ensures accurate tracking by starting a timer with a predefined frequency, enabling users to analyze average, minimum, and maximum FPS values during the collection period.

### Related Functions  
[stopFpsCollection](#stopFpsCollection) : Stops the ongoing FPS data collection.  
[updateFps](#updateFps) : Updates the FPS value during the collection process.

### Events

| Event | Description |
| :-------- | :-------- |
| [onFpsEvent](#onFpsEvent) | Triggered at the end of each interval as defined by the setCollectionFrequency |
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
    "method": "org.rdk.FrameRate.startFpsCollection"
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
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": "2.0", "id": 42, "method": "org.rdk.FrameRate.startFpsCollection"}' http://127.0.0.1:9998/jsonrpc
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
function startFpsCollection() {
  thunderJS.startFpsCollection()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="startFpsCollection()">startFpsCollection</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void startFpsCollection(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="stopFpsCollection"></a>
## *stopFpsCollection*


Stops the ongoing FPS data collection process, ensuring that no further updates are recorded. This function is useful for halting performance monitoring when it is no longer needed, helping to conserve system resources.

### Related Functions  
[startFpsCollection](#startFpsCollection) : Initiates the FPS data collection process.

### Events

| Event | Description |
| :-------- | :-------- |
| [onFpsEvent](#onFpsEvent) | Triggered once after the stopFpsCollection method is invoked. |
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
    "method": "org.rdk.FrameRate.stopFpsCollection"
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
"method": "org.rdk.FrameRate.stopFpsCollection"
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
function stopFpsCollection() {
  thunderJS.stopFpsCollection()
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="stopFpsCollection()">stopFpsCollection</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void stopFpsCollection(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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


<a name="updateFps"></a>
## *updateFps*


Updates the current FPS (frames per second) value and recalculates the minimum, maximum, and average FPS based on the new data. This function is essential for tracking real-time performance metrics, ensuring accurate and up-to-date FPS statistics during collection.

### Related Functions  
[startFpsCollection](#startFpsCollection) : Initiates the FPS data collection process.  
[stopFpsCollection](#stopFpsCollection) : Stops the FPS data collection process.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.newFpsValue | integer | New Frames per Second (Fps) value |

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
    "method": "org.rdk.FrameRate.updateFps",
    "params": {
        "newFpsValue": 60
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
"method": "org.rdk.FrameRate.updateFps",
"params": {
"newFpsValue": 60
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
function updateFps(newFpsValue) {
  thunderJS.updateFps(newFpsValue)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="updateFps(60)">updateFps</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void updateFps(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["newFpsValue"] = 60;
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

The following events are provided by the org.rdk.FrameRate plugin:

FrameRate interface events:

| Event | Description |
| :-------- | :-------- |
| [onDisplayFrameRateChanging](#onDisplayFrameRateChanging) | Triggered when the framerate changes started |
| [onDisplayFrameRateChanged](#onDisplayFrameRateChanged) | Triggered when the framerate changed |
| [onFpsEvent](#onFpsEvent) | Triggered at the end of each interval as defined by the `setCollectionFrequency` method and once after the `stopFpsCollection` method is invoked |


<a name="onDisplayFrameRateChanging"></a>
## *onDisplayFrameRateChanging*


The `onDisplayFrameRateChanging` event is triggered when the display's frame rate is about to change. This event notifies users in advance of an impending frame rate adjustment, allowing them to anticipate changes in the visual performance of their display. It provides the new frame rate value that the display is transitioning to.  

This event is particularly useful for scenarios where users need to monitor or adapt to changes in display performance, such as during video playback, gaming, or other dynamic visual applications.  

### Related Functions  
[setDisplayFrameRate](#setDisplayFrameRate) : This function triggers the `onDisplayFrameRateChanging` event when a new display frame rate is set, initiating the transition to the specified frame rate.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.displayFrameRate | string | Video Display FrameRate changing |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDisplayFrameRateChanging",
    "params": {
        "displayFrameRate": "1920x1080x60"
    }
}
```

<a name="onDisplayFrameRateChanged"></a>
## *onDisplayFrameRateChanged*


The `onDisplayFrameRateChanged` event notifies users when the display's frame rate has been successfully updated. This event is triggered after the frame rate change process is completed, ensuring that the new frame rate is now active. It provides users with the updated frame rate value, allowing them to monitor or adjust their settings accordingly.  

This event is particularly useful for scenarios where applications or systems need to adapt to changes in display performance, such as optimizing video playback or adjusting graphical settings.  

### Related Functions  
[setDisplayFrameRate](#setDisplayFrameRate) : This function triggers the event by initiating a change in the display's frame rate. Once the new frame rate is applied, the `onDisplayFrameRateChanged` event is dispatched to confirm the update.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.displayFrameRate | string | Video Display FrameRate changed |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDisplayFrameRateChanged",
    "params": {
        "displayFrameRate": "1920x1080x60"
    }
}
```

<a name="onFpsEvent"></a>
## *onFpsEvent*


The *onFpsEvent* is a notification event that provides users with real-time updates about the performance of the system's frame rate. This event is triggered when the system collects and processes frame rate data, delivering key metrics such as the average frame rate, minimum frame rate, and maximum frame rate. These metrics help users monitor the smoothness and stability of the display performance, making it easier to identify potential issues or optimize settings for a better viewing experience.

### Related Functions  
[startFpsCollection](#startFpsCollection) : This function initiates the collection of frame rate data, which is necessary for triggering the *onFpsEvent*.  

[stopFpsCollection](#stopFpsCollection) : This function halts the collection of frame rate data, effectively stopping the generation of *onFpsEvent* notifications.  

[setCollectionFrequency](#setCollectionFrequency) : This function adjusts how frequently frame rate data is collected, influencing the timing and frequency of *onFpsEvent* notifications.  

[updateFps](#updateFps) : This function updates the frame rate metrics, which are then used to trigger the *onFpsEvent* with the latest data.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.average | integer | The average FPS |
| params.min | integer | The minimum FPS |
| params.max | integer | The maximum FPS |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onFpsEvent",
    "params": {
        "average": 0,
        "min": 0,
        "max": 0
    }
}
```
