# AuthService Plugin
**Version: [1.0](https://github.com/rdkcentral/rdkservices/blob/main/AuthService/CHANGELOG.md)**
### Table of Contents
- [Abbreviation, Acronyms and Terms](#head.Abbreviation,_Acronyms_and_Terms)
- [Description](#head.Description)
- [Configuration](#head.Configuration)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)
<a name="head.Abbreviation,_Acronyms_and_Terms"></a>
# Abbreviation, Acronyms and Terms
 [[Refer to this link](userguide/aat.md)]
<a name="head.Description"></a>
# Description

 The `AuthService` plugin enables access to ID and security tokens for the set-top device.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].
<a name="head.Configuration"></a>
# Configuration
The table below lists configuration options of the plugin.
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.AuthService*) |
| classname | string | Class name: *org.rdk.AuthService* |
| locator | string | Library name: *libWPEFrameworkAuthService.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="head.Methods"></a>
# Methods and Notifications
The following methods are provided by the org.rdk.AuthService plugin:
| Method | Description |Event|
| :-------- | :-------- | :-------- |
| [GetInfo](#method.GetInfo) | Returns STB Auth Service info | NA |
| [GetDeviceInfo](#method.GetDeviceInfo) | Returns device info - Deprecated | NA |
| [GetDeviceId](#method.GetDeviceId) | Returns the device id | NA |
| [SetDeviceId](#method.SetDeviceId) | Sets device id | NA |
| [SetPartnerId](#method.SetPartnerId) | Sets partner id | NA |
| [GetAuthToken](#method.GetAuthToken) | Returns the authorization token | [AuthTokenChanged](#event.AuthTokenChanged)|
| [GetSessionToken](#method.GetSessionToken) | Returns the session token | NA |
| [SetSessionToken](#method.SetSessionToken) | Sets the session token | [SessionTokenChanged](#event.SessionTokenChanged)|
| [GetServiceAccessToken](#method.GetServiceAccessToken) | Returns the service access token | NA |
| [SetServiceAccessToken](#method.SetServiceAccessToken) | Sets the service access token | [ServiceAccessTokenChanged](#event.ServiceAccessTokenChanged)|
| [GetServiceAccountId](#method.GetServiceAccountId) | Returns the service account ID | NA |
| [SetServiceAccountId](#method.SetServiceAccountId) | Sets the service account ID | [OnServiceAccountIdChanged](#event.OnServiceAccountIdChanged)|
| [SetAuthIdToken](#method.SetAuthIdToken) | Sets the authorization ID token | NA |
| [Ready](#method.Ready) | Device's keys and certificates presence | NA |
| [GetBootstrapProperty](#method.GetBootstrapProperty) | Returns bootstrap property | NA |
| [ActivationStarted](#method.ActivationStarted) | Device's activation started | NA |
| [ActivationComplete](#method.ActivationComplete) | Device's activation completion | NA |
| [GetLostAndFoundAccessToken](#method.GetLostAndFoundAccessToken) | Returns LFAT if available | NA |
| [SetLostAndFoundAccessToken](#method.SetLostAndFoundAccessToken) | Sets Lost and Found token | NA |
| [GetXDeviceId](#method.GetXDeviceId) | Returns the xDevice ID | NA |
| [SetXDeviceId](#method.SetXDeviceId) | Sets the xDevice ID | NA |
| [GetExperience](#method.GetExperience) | Returns the experience | NA |
| [SetExperience](#method.SetExperience) | Sets the experience | NA |
| [GetXifaId](#method.GetXifaId) | Returns xifaId | NA |
| [SetXifaId](#method.SetXifaId) | Sets xifaId | NA |
| [GetAdvtOptOut](#method.GetAdvtOptOut) | Returns advtOptOut | NA |
| [SetAdvtOptOut](#method.SetAdvtOptOut) | Sets advtOptOut | NA |
| [GetActivationStatus](#method.GetActivationStatus) | Returns the activation status | NA |
| [SetActivationStatus](#method.SetActivationStatus) | Sets the activation status | [OnActivationStatusChanged](#event.OnActivationStatusChanged)|
| [ClearAuthToken](#method.ClearAuthToken) | Clears the authorization token | NA |
| [ClearSessionToken](#method.ClearSessionToken) | Clears the session token | NA |
| [ClearServiceAccessToken](#method.ClearServiceAccessToken) | Clears the service access token | NA |
| [ClearLostAndFoundAccessToken](#method.ClearLostAndFoundAccessToken) | Clears Lost and Found token | NA |
| [ClearServiceAccountId](#method.ClearServiceAccountId) | Clears the service account ID | NA |
| [ClearCustomProperties](#method.ClearCustomProperties) | Clears the custom properties | NA |
| [GetCustomProperties](#method.GetCustomProperties) | Returns the custom properties | NA |
| [SetCustomProperties](#method.SetCustomProperties) | Sets the custom properties | NA |
| [GetAlternateIds](#method.GetAlternateIds) | Returns alternate IDs | NA |
| [SetAlternateIds](#method.SetAlternateIds) | Sets alternate IDs | NA |
| [GetTransitionData](#method.GetTransitionData) | Returns the transition data | NA |

<a name="method.GetInfo"></a>
## GetInfo<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the STB Auth Service info. It provides information such as version, host, aspath, asmode, minRenew, maxRenew and success status. This method is essential for retrieving the authentication service details for the Set Top Box (STB).

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| version | string | The version of the STB Auth Service |
| host | string | The host of the STB Auth Service |
| aspath | string | The path of the Auth Service |
| asmode | string | The mode of the Auth Service |
| minRenew | integer | The minimum renewal time for the Auth Service |
| maxRenew | integer | The maximum renewal time for the Auth Service |
| success | boolean | The success status of the Auth Service |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetInfo",
"params":{}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetInfo"}'http://127.0.0.1:9998/jsonrpc

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
function getAuthServiceInfo() {
  thunderJS.AuthService.GetInfo()
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
<button onclick="getAuthServiceInfo()">Get AuthService Info</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "version": "1.0",
        "host": "myHost",
        "aspath": "/opt/www/authService/",
        "asmode": "xre",
        "minRenew": 1000,
        "maxRenew": 2000,
        "success": true
    }
}
```

<a name="method.GetDeviceInfo"></a>
## GetDeviceInfo<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API is used to retrieve device information. Please note that this API is deprecated and may be removed in future versions. The device information is returned as a string of hexadecimal characters.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceInfo | String | The device information returned as a string of hexadecimal characters. |
| success | Boolean | Indicates whether the operation was successful. True if successful, false otherwise. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetDeviceInfo"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetDeviceInfo"}' http://127.0.0.1:9998/jsonrpc

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
  thunderJS.AuthService.GetDeviceInfo()
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
<button onclick="getDeviceInfo()">Get Device Info</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetDeviceInfo(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "deviceInfo": "646576696365547970653D49705374622C6D616B653D41727269732C...",
        "success": true
    }
}
```

<a name="method.GetDeviceId"></a>
## GetDeviceId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method returns the device (receiver) id. It is used to uniquely identify the device in the system. The device id is a unique identifier assigned to each device.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceId | string | The unique identifier of the device |
| partnerId | string | The partner id associated with the device |
| success | boolean | Indicates whether the operation was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetDeviceId"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetDeviceId"}'http://127.0.0.1:9998/jsonrpc

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
function getDeviceId() {
  thunderJS.AuthService.GetDeviceId()
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
<button onclick="getDeviceId()">Get Device Id</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetDeviceId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "deviceId": "c182ae04-84a6-4c51-ad8b-7de7aeb3c823",
        "partnerId": "comcast",
        "success": true
    }
}
```

<a name="method.setDeviceId"></a>
## setDeviceId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the device id. It takes a string as an input parameter and returns a success message. The device id is a unique identifier for a device.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceId | string | Unique identifier for a device |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the device id is successfully set |
| message | string | Returns a message indicating the status of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetDeviceId",
"params":{"deviceId":"your_device_id"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetDeviceId", "params":{"deviceId":"your_device_id"}}'http://127.0.0.1:9998/jsonrpc

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
function setDeviceId(deviceId) {
  thunderJS.AuthService.SetDeviceId(deviceId)
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
<button onclick="setDeviceId('123456')">Set Device Id</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetDeviceId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["deviceId"] = "your_device_id";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetPartnerId"></a>
## SetPartnerId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the partner id. It takes a string as an input parameter and returns a status indicating whether the operation was successful or not.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| partnerId | string | The partner id to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates whether the operation was successful |
| error | string | Contains error message if the operation was unsuccessful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetPartnerId",
"params":{"partnerId":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetPartnerId", "params":{"partnerId":"your_partner_id"}}' http://127.0.0.1:9998/jsonrpc

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
function setPartnerId(partnerId) {
  thunderJS.AuthService.SetPartnerId(partnerId)
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
<button onclick="setPartnerId('partner123')">Set Partner Id</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetPartnerId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    parameters["partnerId"] = "partner123"; // replace "partner123" with actual partnerId
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "error": " "
    }
}
```

<a name="method.GetAuthToken"></a>
## GetAuthToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the authorization token. It provides a mechanism to force a new token or recover a renewal token. The method triggers the [AuthTokenChanged](#event.AuthTokenChanged) event when the authorization token changes.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| forceNew | bool | Forces the generation of a new authorization token |
| recoverRenewal | bool | Recovers a renewal token if available |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the token request |
| token | string | The authorization token |
| expires | int | The expiration time of the token in seconds |
| clientId | string | The client ID associated with the token |
| messageId | string | The message ID associated with the token request |
| success | bool | Indicates whether the token request was successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetAuthToken",
"params":{"forceNew":true, "recoverRenewal":true}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetAuthToken", "params":{"forceNew":true, "recoverRenewal":true}}'http://127.0.0.1:9998/jsonrpc

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
function getAuthToken(forceNew, recoverRenewal) {
  thunderJS.AuthService.GetAuthToken({forceNew: forceNew, recoverRenewal: recoverRenewal})
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
<button onclick="getAuthToken(true, true)">Get Auth Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetAuthToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["forceNew"] = true; // replace with actual value
    parameters["recoverRenewal"] = true; // replace with actual value
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "0",
        "token": "PD94bWwgdmVyc2lvbj0iMS4wI...",
        "expires": 31530812,
        "clientId": "...",
        "messageId": "...",
        "success": true
    }
}
```

<a name="method.GetSessionToken"></a>
## GetSessionToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the session token. It provides a unique token that can be used for session management. The token is a string of characters that represents the session.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | String | The status of the session token request |
| token | String | The session token |
| expires | Integer | The expiration time of the session token |
| clientId | String | The client ID |
| messageId | String | The message ID |
| success | Boolean | The success status of the session token request |
| message | String | Any message related to the session token request |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetSessionToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetSessionToken"}'http://127.0.0.1:9998/jsonrpc

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
function getSessionToken() {
  thunderJS.AuthService.GetSessionToken()
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
<button onclick="getSessionToken()">Get Session Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetSessionToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "0",
        "token": "PD94bWwgdmVyc2lvbj0iMS4wI...",
        "expires": 31530812,
        "clientId": "...",
        "messageId": "...",
        "success": true,
        "message": " "
    }
}
```

<a name="method.setsessiontoken"></a>
## SetSessionToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the session token. It takes in a status, token, expiration time, client ID, and message ID as parameters. The session token is a crucial part of maintaining a secure connection between the client and the server. 

This method triggers the [SessionTokenChanged](#event.sessiontokenchanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The status of the session |
| token | string | The session token |
| expires | uint32_t | The expiration time of the session token |
| clientId | string | The ID of the client |
| messageId | string | The ID of the message |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The status of the session token setting operation |
| token | string | The set session token |
| expires | uint32_t | The expiration time of the set session token |
| clientId | string | The ID of the client for which the session token was set |
| messageId | string | The ID of the message for which the session token was set |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetSessionToken",
"params":{
    "status": 0,
    "token": "PD94bWwgdmVyc2lvbj0iMS4wI...",
    "expires": 31530812,
    "clientId": "...",
    "messageId": "..."
    }
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetSessionToken", "params":{"status":0, "token":"PD94bWwgdmVyc2lvbj0iMS4wI...", "expires":31530812, "clientId":"...", "messageId":"..."}}'http://127.0.0.1:9998/jsonrpc

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
function setSessionToken(status, token, expires, clientId, messageId) {
  thunderJS.AuthService.SetSessionToken({status: status, token: token, expires: expires, clientId: clientId, messageId: messageId})
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
<button onclick="setSessionToken(0, 'PD94bWwgdmVyc2lvbj0iMS4wI...', 31530812, '...', '...')">Set Session Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetSessionToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["status"] = 0;
    parameters["token"] = "PD94bWwgdmVyc2lvbj0iMS4wI...";
    parameters["expires"] = 31530812;
    parameters["clientId"] = "...";
    parameters["messageId"] = "...";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "0",
        "token": "PD94bWwgdmVyc2lvbj0iMS4wI...",
        "expires": 31530812,
        "clientId": "...",
        "messageId": "..."
    }
}
```

<a name="method.GetServiceAccessToken"></a>
## GetServiceAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the service access token. It is a virtual method that retrieves the token required for service access. The token, along with its status, expiry time, success status, and any related message, are returned.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the token retrieval, "0" indicates success |
| token | string | The actual service access token |
| expires | integer | The expiry time of the token in seconds |
| success | boolean | The success status of the token retrieval, "true" indicates success |
| message | string | Any related message to the token retrieval |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetServiceAccessToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetServiceAccessToken"}'http://127.0.0.1:9998/jsonrpc

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
function getServiceAccessToken() {
  thunderJS.AuthService.GetServiceAccessToken()
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
<button onclick="getServiceAccessToken()">Get Service Access Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetServiceAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "0",
        "token": "eyJraWQiOiJzYXQtcHJ...",
        "expires": 31530812,
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetServiceAccessToken"></a>
## SetServiceAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the service access token. It takes in the status, token, and expiration time as parameters. The status is used to determine the current state of the service, the token is the access token for the service, and the expiration time is the time at which the token will expire.

This method triggers the [ServiceAccessTokenChanged](#event.ServiceAccessTokenChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The current status of the service |
| token | string | The access token for the service |
| expires | uint32_t | The expiration time for the token |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | True if the operation was successful, false otherwise |
| message | string | A message describing the result of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetServiceAccessToken",
"params":{
    "status": 1,
    "token": "example_token",
    "expires": 123456
    }
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetServiceAccessToken", "params":{"status":1, "token":"your_token", "expires":12345}}'http://127.0.0.1:9998/jsonrpc

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
function setServiceAccessToken(status, token, expires) {
  thunderJS.AuthService.SetServiceAccessToken({status: status, token: token, expires: expires})
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
<button onclick="setServiceAccessToken(1, 'token123', 3600)">Set Service Access Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetServiceAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["status"] = 1;
    parameters["token"] = "example_token";
    parameters["expires"] = 3600;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetServiceAccountId"></a>
## GetServiceAccountId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the service account ID. It is a unique identifier for the service account. This ID is used to manage the permissions and access control for the service account.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| serviceAccountId | String | The unique identifier for the service account |
| success | Boolean | Indicates whether the operation was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetServiceAccountId"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetServiceAccountId"}' http://127.0.0.1:9998/jsonrpc

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
function getServiceAccountId() {
  thunderJS.AuthService.GetServiceAccountId()
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
<button onclick="getServiceAccountId()">Get Service Account ID</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetServiceAccountId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "serviceAccountId": "7487359890816911506",
        "success": true
    }
}
```

<a name="method.SetServiceAccountId"></a>
## SetServiceAccountId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the service account ID. It is used to update the service account ID in the system. The new service account ID is passed as a parameter to this method.

This method triggers the [OnServiceAccountIdChanged](#event.OnServiceAccountIdChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| serviceAccountId | string | The new service account ID to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the service account ID is successfully set |
| message | string | Returns an empty string if the operation is successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetServiceAccountId",
"params":{"serviceAccountId":"your_service_account_id"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetServiceAccountId", "params":{"serviceAccountId":"your_service_account_id"}}'http://127.0.0.1:9998/jsonrpc

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
function setServiceAccountId(serviceAccountId) {
  thunderJS.AuthService.SetServiceAccountId(serviceAccountId)
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
<button onclick="setServiceAccountId('123456')">Set Service Account ID</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetServiceAccountId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["serviceAccountId"] = "your_service_account_id";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetAuthIdToken"></a>
## SetAuthIdToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the authorization ID token. It is used to authenticate the user and grant them access to the system. The ID token is a string that is passed as an input parameter.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| authIdToken | string | The authorization ID token |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns a message indicating the status of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetAuthIdToken",
"params":{"authIdToken":"your_auth_id_token_here"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetAuthIdToken", "params":{"authIdToken":"your_auth_id_token"}}' http://127.0.0.1:9998/jsonrpc

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
function setAuthIdToken(authIdToken) {
  thunderJS.AuthService.SetAuthIdToken(authIdToken)
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
<button onclick="setAuthIdToken('your_auth_id_token')">SetAuthIdToken</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetAuthIdToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["authIdToken"] = "your_auth_id_token_value";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.Ready"></a>
## Ready<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API lets the Auth Service know that the device's provisioned keys, certificates, and binaries are present on the device. It is used to confirm the readiness of the device for authentication processes. The status of the device's readiness is passed as a parameter to this method.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the device's readiness |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns a message related to the operation's success or failure |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.Ready",
"params":{"status":"value_for_status"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.Ready", "params":{"status":"value"}}'http://127.0.0.1:9998/jsonrpc

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
function ready(status) {
  thunderJS.AuthService.Ready(status)
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
<button onclick="ready('status')">Ready</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void Ready(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["status"] = "status_value";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetBootstrapProperty"></a>
## GetBootstrapProperty<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the bootstrap property associated with the current partnerId. It is a virtual method that takes a string as an input parameter and returns a JSON object containing the bootstrap property.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| bootstrapProperty | string | The bootstrap property associated with the current partnerId |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| ntpHost | string | The NTP host, for example: "ntp.ccp.xcal.tv" |
| success | boolean | Indicates whether the operation was successful |
| message | string | A message providing additional information about the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetBootstrapProperty",
"params":{"bootstrapProperty":"ntp.ccp.xcal.tv"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetBootstrapProperty", "params":{"bootstrapProperty":"ntpHost"}}'http://127.0.0.1:9998/jsonrpc

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
function getBootstrapProperty(bootstrapProperty) {
  thunderJS.AuthService.GetBootstrapProperty(bootstrapProperty)
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
<button onclick="getBootstrapProperty('ntpHost')">getBootstrapProperty</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetBootstrapProperty(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    parameters["bootstrapProperty"] = "ntpHost";
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "ntpHost": "ntp.ccp.xcal.tv",
        "success": true,
        "message": " "
    }
}
```

<a name="method.ActivationStarted"></a>
## ActivationStarted<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This method lets the auth service know that the device's activation is started. It is used to initiate the activation process and communicate the status to the authentication service.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| successResult | boolean | "success": true |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ActivationStarted"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ActivationStarted"}'http://127.0.0.1:9998/jsonrpc

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
function activationStarted() {
  thunderJS.AuthService.ActivationStarted()
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
<button onclick="activationStarted()">Activation Started</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ActivationStarted(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.ActivationComplete"></a>
## ActivationComplete<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API lets the auth service know that the device's activation is completed. It is used to signal the completion of the device activation process to the authentication service. The method returns a success result indicating the status of the operation.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| successResult | boolean | "success": true |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ActivationComplete"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ActivationComplete"}' http://127.0.0.1:9998/jsonrpc

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
function activationComplete() {
  thunderJS.AuthService.ActivationComplete()
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
<button onclick="activationComplete()">Activation Complete</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ActivationComplete(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.GetLostAndFoundAccessToken"></a>
## GetLostAndFoundAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the stored Lost and Found access token (LFAT) if one is available. It provides a secure way to retrieve the LFAT, which is essential for lost and found operations. The method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| lostAndFoundAccessToken | string | The Lost and Found access token, if available. |
| message | string | A message indicating the status of the operation. |
| success | bool | A boolean value indicating whether the operation was successful. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetLostAndFoundAccessToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetLostAndFoundAccessToken"}'http://127.0.0.1:9998/jsonrpc

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
function getLostAndFoundAccessToken() {
  thunderJS.AuthService.GetLostAndFoundAccessToken()
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
<button onclick="getLostAndFoundAccessToken()">Get Lost And Found Access Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetLostAndFoundAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "lostAndFoundAccessToken": {
            "expires": 31530812,
            "version": "31530812",
            "lfat": "UNdybe86vgejbUGVU8dn7djnsdf713jqoNuenUnYbfw==",
            "received": "1646306292",
            "received_usec": "475057"
        },
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetLostAndFoundAccessToken"></a>
## SetLostAndFoundAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the lost and found access token. It is used to update the access token for the lost and found service. The access token is provided in an opaque JSON string format.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| lostAndFoundAccessToken | string (opaque JSON) | The new access token for the lost and found service |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates whether the operation was successful |
| message | string | Provides additional information about the operation result |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetLostAndFoundAccessToken",
"params":{"lostAndFoundAccessToken":"your_token_value_here"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetLostAndFoundAccessToken", "params":{"lostAndFoundAccessToken":"your_token_here"}}'http://127.0.0.1:9998/jsonrpc

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
function setLostAndFoundAccessToken(lostAndFoundAccessToken) {
  thunderJS.AuthService.SetLostAndFoundAccessToken(lostAndFoundAccessToken)
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
<button onclick="setLostAndFoundAccessToken('your_token_here')">SetLostAndFoundAccessToken</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetLostAndFoundAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["lostAndFoundAccessToken"] = "your_token_here";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetXDeviceId"></a>
## GetXDeviceId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the xDevice ID. It is a unique identifier for the xDevice. This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xDeviceId | String | The unique identifier for the xDevice |
| success | Boolean | Indicates whether the operation was successful |
| message | String | A message providing additional information about the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetXDeviceId"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetXDeviceId"}'http://127.0.0.1:9998/jsonrpc

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
function getXDeviceId() {
  thunderJS.AuthService.GetXDeviceId()
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
<button onclick="getXDeviceId()">GetXDeviceId</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetXDeviceId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "xDeviceId": "1360830220996266256",
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetXDeviceId"></a>
## SetXDeviceId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the xDevice ID. It is used to assign a unique identifier to the device for tracking and management purposes. The xDevice ID is a string parameter that is passed into the function.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xDeviceId | string | Unique identifier for the device |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns a message related to the operation status |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetXDeviceId",
"params":{"xDeviceId":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetXDeviceId", "params":{"xDeviceId":"your_device_id"}}'http://127.0.0.1:9998/jsonrpc

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
function setXDeviceId(xDeviceId) {
  thunderJS.AuthService.SetXDeviceId(xDeviceId)
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
<button onclick="setXDeviceId('your_xDeviceId')">setXDeviceId</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetXDeviceId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["xDeviceId"] = "value";
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetExperience"></a>
## GetExperience<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the experience. It is a virtual method that retrieves the experience value and indicates the success of the operation.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| experience | string | The experience value |
| success | boolean | Indicates the success of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetExperience"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetExperience"}'http://127.0.0.1:9998/jsonrpc

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
function getExperience() {
  thunderJS.AuthService.GetExperience()
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
<button onclick="getExperience()">Get Experience</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetExperience(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "experience": "x1",
        "success": true
    }
}
```

<a name="method.SetExperience"></a>
## SetExperience<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the experience. It takes a string as input and returns a success message. The experience can be any valid string value. The success message is a structured message indicating the success status and a message.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| experience | string | The experience to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates if the operation was successful |
| message | string | A message indicating the result of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetExperience",
"params":{"experience":"value_for_experience"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetExperience", "params":{"exp":"value"}}'http://127.0.0.1:9998/jsonrpc

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
function setExperience(experience) {
  thunderJS.AuthService.SetExperience(experience)
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
<button onclick="setExperience('experience_value')">setExperience</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetExperience(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["experience"] = "5 years"; // replace "5 years" with actual value
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetXifaId"></a>
## GetXifaId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the xifaId. It is a virtual method that is used to retrieve the xifaId from the system. The method returns a success status if the operation is successful.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xifaIdResult | GetxifaIdResult | The xifaId retrieved from the system |
| success | boolean | The status of the operation, returns true if the operation is successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetXifaId"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetXifaId"}'http://127.0.0.1:9998/jsonrpc

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
function getXifaId() {
  thunderJS.AuthService.GetXifaId()
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
<button onclick="getXifaId()">GetXifaId</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetXifaId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.SetXifaId"></a>
## SetXifaId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the xifaId. It takes a string as an input parameter and returns a success message if the operation is successful.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xifaId | string | The xifaId to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation is successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetXifaId",
"params":{"xifaId":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetXifaId", "params":{"xifaId":"value"}}'http://127.0.0.1:9998/jsonrpc

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
function setXifaId(xifaId) {
  thunderJS.AuthService.SetXifaId(xifaId)
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
<button onclick="setXifaId('exampleXifaId')">setXifaId</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetXifaId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["xifaId"] = "value_for_xifaId";
    std::string result;
    if (invokeJSONRPC(remoteObject, "AuthService.SetXifaId", parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.GetAdvtOptOut"></a>
## GetAdvtOptOut<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the advertisement opt-out status. It checks whether the user has opted out of advertisements or not. The method returns a success status if the operation is successful.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | True if the operation is successful, false otherwise. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetAdvtOptOut"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetAdvtOptOut"}' http://127.0.0.1:9998/jsonrpc

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
function getAdvtOptOut() {
  thunderJS.AuthService.GetAdvtOptOut()
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
<button onclick="getAdvtOptOut()">Get Advt Opt Out</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetAdvtOptOut(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.SetAdvtOptOut"></a>
## SetAdvtOptOut<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the advertisement opt-out status. It takes a boolean value as input and sets the advertisement opt-out status accordingly. If the operation is successful, it returns a success message.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| advtOptOut | bool | Input parameter to set the advertisement opt-out status |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | bool | Returns true if the operation is successful |

Note: This method does not trigger any events.

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetAdvtOptOut",
"params":{"advtOptOut":true}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetAdvtOptOut", "params":{"advtOptOut":true}}'http://127.0.0.1:9998/jsonrpc

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
function setAdvtOptOut(advtOptOut) {
  thunderJS.AuthService.SetAdvtOptOut(advtOptOut)
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
<button onclick="setAdvtOptOut(true)">setAdvtOptOut</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetAdvtOptOut(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["advtOptOut"] = true;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.GetActivationStatus"></a>
## GetActivationStatus<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the activation status. It provides information about whether the system or service is activated or not. The status is returned as a string, with possible values being "not-activated" or "activated".

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The activation status of the system or service. Possible values are "not-activated" or "activated". |
| success | boolean | Indicates whether the operation was successful. Returns true if the operation was successful, false otherwise. |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetActivationStatus"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetActivationStatus"}'http://127.0.0.1:9998/jsonrpc

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
function getActivationStatus() {
  thunderJS.AuthService.GetActivationStatus()
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
<button onclick="getActivationStatus()">Get Activation Status</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetActivationStatus(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "status": "not-activated",
        "success": true
    }
}
```

<a name="method.SetActivationStatus"></a>
## SetActivationStatus<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API is used to set the activation status. It takes a string as an input parameter and returns a success message. 

This method triggers the [OnActivationStatusChanged](#event.OnActivationStatusChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The activation status to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns a message indicating the result of the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetActivationStatus",
"params":{"status":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetActivationStatus", "params":{"status":"active"}}'http://127.0.0.1:9998/jsonrpc

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
function setActivationStatus(status) {
  thunderJS.AuthService.SetActivationStatus(status)
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
<button onclick="setActivationStatus('active')">setActivationStatus</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetActivationStatus(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["status"] = "active"; // replace "active" with actual status value
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.ClearAuthToken"></a>
## ClearAuthToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the authorization token. It is used when the user wants to log out or when the token is expired and needs to be refreshed. The method returns a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns an empty string as there is no specific message associated with this operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearAuthToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearAuthToken"}'http://127.0.0.1:9998/jsonrpc

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
function clearAuthToken() {
  thunderJS.AuthService.ClearAuthToken()
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
<button onclick="clearAuthToken()">Clear Auth Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearAuthToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.ClearSessionToken"></a>
## ClearSessionToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the session token. It is used when a session is no longer needed or when a session needs to be reset. The method ensures that the session token is completely removed from the system.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | true if the session token was successfully cleared |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearSessionToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearSessionToken"}'http://127.0.0.1:9998/jsonrpc

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
function clearSessionToken() {
  thunderJS.AuthService.ClearSessionToken()
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
<button onclick="clearSessionToken()">Clear Session Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearSessionToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.ClearServiceAccessToken"></a>
## ClearServiceAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the service access token. It is used when there is a need to invalidate the current access token for the service. The method returns a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates the success or failure of the operation |
| message | string | Provides additional information about the operation's result |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearServiceAccessToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearServiceAccessToken"}'http://127.0.0.1:9998/jsonrpc

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
function clearServiceAccessToken() {
  thunderJS.AuthService.ClearServiceAccessToken()
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
<button onclick="clearServiceAccessToken()">Clear Service Access Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearServiceAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.ClearLostAndFoundAccessToken"></a>
## ClearLostAndFoundAccessToken<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the lost and found access token. It is used when there is a need to reset the access token for the lost and found service. The method returns a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates the success or failure of the operation |
| message | string | Provides additional information about the operation result |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearLostAndFoundAccessToken"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearLostAndFoundAccessToken"}'http://127.0.0.1:9998/jsonrpc

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
function clearLostAndFoundAccessToken() {
  thunderJS.AuthService.ClearLostAndFoundAccessToken()
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
<button onclick="clearLostAndFoundAccessToken()">Clear Lost And Found Access Token</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearLostAndFoundAccessToken(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.ClearServiceAccountId"></a>
## ClearServiceAccountId<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the service account ID. It is used when there is a need to reset or remove the existing service account ID from the system. The operation is successful when the return is "success": true.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation is successful |
| message | string | Returns an empty string as there is no specific message associated with this operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearServiceAccountId"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearServiceAccountId"}' http://127.0.0.1:9998/jsonrpc

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
function clearServiceAccountId() {
  thunderJS.AuthService.ClearServiceAccountId()
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
<button onclick="clearServiceAccountId()">Clear Service Account ID</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearServiceAccountId(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.ClearCustomProperties"></a>
## ClearCustomProperties<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API clears the custom properties. It is used when there is a need to reset or remove all the custom properties that have been set previously. The operation is successful when it returns "success": true.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation is successful |
| message | string | Returns an empty string as there is no specific message associated with the success of this operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.ClearCustomProperties"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ClearCustomProperties"}' http://127.0.0.1:9998/jsonrpc

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
function clearCustomProperties() {
  thunderJS.AuthService.ClearCustomProperties()
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
<button onclick="clearCustomProperties()">Clear Custom Properties</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void ClearCustomProperties(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetCustomProperties"></a>
## GetCustomProperties<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the custom properties. It is a virtual method that retrieves the custom properties and indicates the success of the operation.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| customProperties | string | The custom properties of the object |
| success | bool | Indicates whether the operation was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetCustomProperties"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetCustomProperties"}' http://127.0.0.1:9998/jsonrpc

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
function getCustomProperties() {
  thunderJS.AuthService.GetCustomProperties()
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
<button onclick="getCustomProperties()">Get Custom Properties</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetCustomProperties(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "customProperties": {},
        "success": true
    }
}
```

<a name="method.SetCustomProperties"></a>
## SetCustomProperties<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets the custom properties. It takes a JSON string as input and returns a success status. This method is used to customize properties according to user preferences.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| customProperties | JSON string | This is the custom properties to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | This indicates whether the setting of custom properties was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetCustomProperties",
"params":{"customProperties":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetCustomProperties", "params":{"customProperties":"value"}}'http://127.0.0.1:9998/jsonrpc

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
function setCustomProperties(customProperties) {
  thunderJS.AuthService.SetCustomProperties(customProperties)
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
<button onclick="setCustomProperties('customProperties')">Set Custom Properties</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetCustomProperties(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["customProperties"] = "custom value"; // replace "custom value" with actual value
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

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

<a name="method.GetAlternateIds"></a>
## GetAlternateIds<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns alternate IDs as key/value pairs. It is a virtual method that provides a mechanism to retrieve alternate identifiers for a given entity. The alternate IDs are returned as a string in an opaque format.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| alternateIds | string | The alternate IDs returned by the API in an opaque format |
| message | string | A message indicating the status or result of the operation |
| success | bool | A boolean value indicating whether the operation was successful or not |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetAlternateIds"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetAlternateIds"}'http://127.0.0.1:9998/jsonrpc

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
function getAlternateIds() {
  thunderJS.AuthService.GetAlternateIds()
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
<button onclick="getAlternateIds()">Get Alternate Ids</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetAlternateIds(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "alternateIds": {},
        "success": true,
        "message": " "
    }
}
```

<a name="method.SetAlternateIds"></a>
## SetAlternateIds<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API sets alternate IDs as key/value pairs. It takes a JSON string as input and returns a success status and a message. This method is useful when you need to assign alternate identifiers to an object or entity.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| alternateIds | JSON string | A JSON string containing key/value pairs of alternate IDs |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns a message related to the operation's outcome |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetAlternateIds",
"params":{"alternateIds":"value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetAlternateIds", "params":{"alternateIds":"value"}}'http://127.0.0.1:9998/jsonrpc

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
function setAlternateIds(alternateIds) {
  thunderJS.AuthService.SetAlternateIds(alternateIds)
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
<button onclick="setAlternateIds('yourAlternateIds')">setAlternateIds</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void SetAlternateIds(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    parameters["alternateIds"] = "value"; // replace "value" with actual value
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "success": true,
        "message": " "
    }
}
```

<a name="method.GetTransitionData"></a>
## GetTransitionData<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API returns the transition data. It provides a way to retrieve the data related to a specific transition. The transition data is returned as a string, along with a success status and a message.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| transitionData | string | The transition data |
| success | bool | The success status of the operation |
| message | string | A message related to the operation |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetTransitionData"
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetTransitionData"}'http://127.0.0.1:9998/jsonrpc

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
function getTransitionData() {
  thunderJS.AuthService.GetTransitionData()
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
<button onclick="getTransitionData()">Get Transition Data</button>
</body>
</html>

```
</details>


<details>
 <summary><kbd>CPP</kbd></summary>
 
 ```cpp

void GetTransitionData(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
{
    printf("[%llu] Inside (%s)
", TimeStamp(), __FUNCTION__);
    JsonObject parameters, response;
    std::string result;
    if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
        response.ToString(result);
        printf("
Response: '%s'
", result.c_str());
    }
}

```
</details>

#### Response
```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "transitionData": {},
        "success": true,
        "message": " "
    }
}
```
<a name="head.Notifications"></a>
# Notifications
Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.
The following events are provided by the org.rdk.AuthService plugin:
<a name="event.OnActivationStatusChanged"></a>
## OnActivationStatusChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The activation status has changed.

This event is triggered by [SetActivationStatus](#method.SetActivationStatus)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| oldActivationStatus | string | The previous activation status |
| newActivationStatus | string | The new activation status |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnActivationStatusChanged",
  "params": {"oldActivationStatus": "inactive", "newActivationStatus": "active"}
}
```

<a name="event.OnServiceAccountIdChanged"></a>
## OnServiceAccountIdChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This event is triggered when the service account id has changed.

This event is triggered by [SetServiceAccountId](#method.SetServiceAccountId)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| oldServiceAccountId | string | The old service account id |
| newServiceAccountId | string | The new service account id |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.OnServiceAccountIdChanged",
  "params": {"oldServiceAccountId": "oldId", "newServiceAccountId": "newId"}
}
```

<a name="event.AuthTokenChanged"></a>
## AuthTokenChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The auth token has changed.

This event is triggered by [GetAuthToken](#method.GetAuthToken)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | Object | The new auth token |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.AuthTokenChanged",
  "params": {"authToken": "new_auth_token_value"}
}
```

<a name="event.SessionTokenChanged"></a>
## SessionTokenChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The session token has changed.

This event is triggered by [SetSessionToken](#method.SetSessionToken)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | Object | Contains the new session token |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.SessionTokenChanged",
  "params": {"token": "new_session_token"}
}
```

Please note that the actual parameter name and value may vary depending on the implementation.

<a name="event.ServiceAccessTokenChanged"></a>
## ServiceAccessTokenChanged<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

The service access token has changed.

This event is triggered by [SetServiceAccessToken](#method.SetServiceAccessToken)

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | Object | The new service access token |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.ServiceAccessTokenChanged",
  "params": {"token": "new_access_token"}
}
```

