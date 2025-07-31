<!-- Generated automatically, DO NOT EDIT! -->
<a name="USBMassStorage_Plugin"></a>
# USBMassStorage Plugin

A org.rdk.UsbMassStorage plugin for Thunder framework.

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


The USBMassStorage service is a plugin designed to manage USB mass storage devices. It handles the mounting of devices and partitions, tracks their mount information, and provides details about the file system, partition size, and mount flags. This service facilitates interaction with USB storage devices, ensuring proper access and management of their data.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.UsbMassStorage*) |
| classname | string | Class name: *org.rdk.UsbMassStorage* |
| locator | string | Library name: *libWPEFrameworkUSBMassStorage.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.UsbMassStorage plugin:

org.rdk.UsbMassStorage interface methods:

| Method | Description | Events |
| :-------- | :-------- | :-------- |
| [getDeviceList](#getDeviceList) | Retrieve the list of connected USB storage devices | NA |
| [getMountPoints](#getMountPoints) | Retrieve the mount info list by given USB storage device name | NA |
| [getPartitionInfo](#getPartitionInfo) | Get the partition information for the given mount path | NA |


<a name="getDeviceList"></a>
## *getDeviceList*


Retrieves a comprehensive list of devices, including connected, discovered, and paired devices. This API is essential for managing and monitoring devices across various states, ensuring seamless integration and accessibility for applications requiring device information.

### Related Functions  
[getMountPoints](#getMountPoints) : Provides information about the mount points of storage devices.  
[getPartitionInfo](#getPartitionInfo) : Retrieves detailed partition information for storage devices.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | array | On success, a list of USB storage devices will be returned |
| result[#] | object | Information about a USB storage device |
| result[#].devicePath | string | The path to the USB device |
| result[#].deviceName | string | The name of the USB device |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UsbMassStorage.getDeviceList"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "devicePath": "/dev/sda",
            "deviceName": "001/006"
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
"method": "getDeviceList"
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


<a name="getMountPoints"></a>
## *getMountPoints*


Retrieves detailed information about the mount points for a specified USB storage device. This API is essential for identifying the paths where the device's partitions are mounted, enabling efficient management and access to the device's storage. It ensures accurate retrieval of mount point data by validating the device name and iterating through the associated mount points.

### Related Functions  
[getDeviceList](#getDeviceList) : Retrieves a list of connected USB storage devices.  
[getPartitionInfo](#getPartitionInfo) : Provides detailed information about the partitions of a specified USB storage device.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceName | string | Name of the USB storage device |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | array | On success, mount info list of a USB storage device will be returned |
| result[#] | object |  |
| result[#].partitionName | string | The name of the partition being mounted |
| result[#].mountFlags | string | Flags indicating how the partition is mounted |
| result[#].mountPath | string | The mount point path in the file system |
| result[#]?.fileSystem | string | <sup>*(optional)*</sup> File system |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UsbMassStorage.getMountPoints",
    "params": {
        "deviceName": "001/006"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": [
        {
            "partitionName": "/dev/sda1",
            "mountFlags": "READ_ONLY",
            "mountPath": "/tmp/media/usb2",
            "fileSystem": "VFAT"
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
"method": "org.rdk.UsbMassStorage.getMountPoints",
"params": {
"deviceName": "001/006"
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
function getMountPoints(deviceName) {
  thunderJS.getMountPoints(deviceName)
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getMountPoints('001/006')">getMountPoints</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getMountPoints(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["deviceName"] = "001/006";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
```
</details>


<a name="getPartitionInfo"></a>
## *getPartitionInfo*


Retrieves detailed information about a specific partition based on its mount path. This API provides essential data such as the file system type, partition size, sector details, total space, used space, and available space, enabling users to understand and manage storage partitions effectively.

### Related Functions  
[getDeviceList](#getDeviceList) : Provides a list of connected storage devices.  
[getMountPoints](#getMountPoints) : Retrieves the mount points of storage partitions.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.mountPath | string | Name of the USB storage device |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.fileSystem | string | The file system of the partition |
| result.size | integer | Total size of the partition in MB |
| result.startSector | integer | The starting sector of the partition |
| result.numSectors | integer | The number of sectors in the partition |
| result.sectorSize | integer | The size of each sector in bytes |
| result.totalSpace | integer | Total space of the partition in MB |
| result.usedSpace | integer | Used space of the partition in MB |
| result.availableSpace | integer | Available space in the partition in MB |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.UsbMassStorage.getPartitionInfo",
    "params": {
        "mountPath": "/tmp/media/usb2"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "fileSystem": "VFAT",
        "size": 1024,
        "startSector": 2048,
        "numSectors": 4096,
        "sectorSize": 512,
        "totalSpace": 1024,
        "usedSpace": 512,
        "availableSpace": 512
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
"method": "org.rdk.UsbMassStorage.getPartitionInfo",
"params": {
"mountPath": "/tmp/media/usb2"
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
function getPartitionInfo(mountPath) {
  thunderJS.getPartitionInfo({ mountPath: mountPath })
    .then(function(result) {
      log('Success', result)
    })
    .catch(function(error) {
      log('Error', error)
    })
}
function log(msg, content) {
  var el = document.getElementById('log')
  var entry = '<p class="font-bold">' + msg + '</p>'
  if (content) {
    entry += '<pre class="border mt-4 mb-8 text-sm">' + JSON.stringify(content, null, 2) + '</pre>'
  }
  entry += '<hr class="border-b" />'
  el.innerHTML += entry
}
</script>
<button onclick="getPartitionInfo('/tmp/media/usb2')">getPartitionInfo</button>
</body>
</html>
```
</details>

<details>
<summary><kbd>CPP</kbd></summary>

```cpp
    void getPartitionInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["mountPath"] = "/tmp/media/usb2";
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

The following events are provided by the org.rdk.UsbMassStorage plugin:

org.rdk.UsbMassStorage interface events:

| Event | Description |
| :-------- | :-------- |
| [onDeviceMounted](#onDeviceMounted) | Triggered after the device partitions are mounted |
| [onDeviceUnmounted](#onDeviceUnmounted) | Triggered after the device partitions are unmounted |


<a name="onDeviceMounted"></a>
## *onDeviceMounted*


The *onDeviceMounted* event is triggered when a USB storage device is successfully connected and mounted to the system. This event provides users with detailed information about the mounted device, including its name, device path, and a list of mount points associated with it. It ensures users are notified whenever a new device becomes available for use, making it easier to access and manage external storage devices.

### Related Functions  
[getDeviceList](#getDeviceList) : This function retrieves the list of connected USB devices, enabling the identification of newly mounted devices that trigger the *onDeviceMounted* event.  

[getMountPoints](#getMountPoints) : This function provides information about the mount points associated with a device, which is included in the event payload when *onDeviceMounted* is triggered.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceinfo | object |  |
| params.deviceinfo.devicePath | string | The device path |
| params.deviceinfo.deviceName | string | The name of the device |
| params.mountPoints | array | mount info list of a USB storage device will be returned |
| params.mountPoints[#] | object |  |
| params.mountPoints[#].partitionName | string | The name of the partition being mounted |
| params.mountPoints[#].mountFlags | string | Flags indicating how the partition is mounted |
| params.mountPoints[#].mountPath | string | The mount point path in the file system |
| params.mountPoints[#]?.fileSystem | string | <sup>*(optional)*</sup> File system |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceMounted",
    "params": {
        "deviceinfo": {
            "devicePath": "/dev/sda",
            "deviceName": "001/022"
        },
        "mountPoints": [
            {
                "partitionName": "/dev/sda1",
                "mountFlags": "READ_ONLY",
                "mountPath": "/tmp/media/usb2",
                "fileSystem": "VFAT"
            }
        ]
    }
}
```

<a name="onDeviceUnmounted"></a>
## *onDeviceUnmounted*


This event is triggered when a USB mass storage device is successfully unmounted from the system. It provides users with information about the device that was unmounted, including its name and device path, as well as details about the mount points that were associated with the device. This event is useful for tracking the removal of external storage devices and ensuring that all related resources are properly released.

### Related Functions  
[getMountPoints](#getMountPoints) : This function retrieves information about the mount points associated with the device. It is directly related to the event as it helps identify the specific mount points that were unmounted when the device was removed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.deviceinfo | object |  |
| params.deviceinfo.devicePath | string | The device path |
| params.deviceinfo.deviceName | string | The name of the device |
| params.mountPoints | array | mount info list of a USB storage device will be returned |
| params.mountPoints[#] | object |  |
| params.mountPoints[#].partitionName | string | The name of the partition being mounted |
| params.mountPoints[#].mountFlags | string | Flags indicating how the partition is mounted |
| params.mountPoints[#].mountPath | string | The mount point path in the file system |
| params.mountPoints[#]?.fileSystem | string | <sup>*(optional)*</sup> File system |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceUnmounted",
    "params": {
        "deviceinfo": {
            "devicePath": "/dev/sda",
            "deviceName": "001/022"
        },
        "mountPoints": [
            {
                "partitionName": "/dev/sda1",
                "mountFlags": "READ_ONLY",
                "mountPath": "/tmp/media/usb2",
                "fileSystem": "VFAT"
            }
        ]
    }
}
```
