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
| [GetDeviceInfo](#method.GetDeviceInfo) | Returns device info | NA |
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
| [SetAuthIdToken](#method.SetAuthIdToken) | Sets authorization ID token | NA |
| [Ready](#method.Ready) | Device's keys and certificates status | NA |
| [GetBootstrapProperty](#method.GetBootstrapProperty) | Returns bootstrap property | NA |
| [ActivationStarted](#method.ActivationStarted) | Lets Auth Service know device's activation | NA |
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

This API returns the STB Auth Service info. It provides details such as version, host, auth service path, auth service mode, minimum and maximum renewal times, and success status. This information is crucial for understanding the configuration and status of the STB Auth Service.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| version | string | The version of the STB Auth Service |
| host | string | The host of the STB Auth Service |
| aspath | string | The path to the auth service |
| asmode | string | The mode of the auth service |
| minRenew | integer | The minimum renewal time |
| maxRenew | integer | The maximum renewal time |
| success | boolean | The success status of the STB Auth Service |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.GetInfo"
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

This API returns device information. Please note that this API is deprecated and may be removed in future versions. The device information is returned as a string of hexadecimal characters.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceInfo | string | The device information returned as a string of hexadecimal characters. |
| success | boolean | Indicates whether the operation was successful. |

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

This API returns the device (receiver) id. It is a virtual method that retrieves the unique identifier of the device. This identifier is used to distinguish between different devices in a network or system.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceId | string | The unique identifier of the device |
| partnerId | string | The partner identifier, in this case "comcast" |
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

This API sets the device id. It takes a string as an input parameter and returns a success message. The device id is used to uniquely identify a device in the system.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| deviceId | string | The unique identifier for the device |

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
<button onclick="setPartnerId('partner123')">setPartnerId</button>
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
    parameters["partnerId"] = "example_partner_id";
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

This method returns the authorization token. It provides a new token if the `forceNew` parameter is set to true. If the `recoverRenewal` parameter is set to true, it recovers the renewal process of the token.

This method triggers the [AuthTokenChanged](#event.AuthTokenChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| forceNew | bool | If set to true, a new token is generated |
| recoverRenewal | bool | If set to true, the renewal process of the token is recovered |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the token generation process |
| token | string | The generated authorization token |
| expires | int | The expiration time of the token |
| clientId | string | The client ID associated with the token |
| messageId | string | The message ID associated with the token generation process |
| success | bool | Indicates whether the token generation process was successful or not |

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
    parameters["forceNew"] = true;
    parameters["recoverRenewal"] = true;
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

This API returns the session token. It is a virtual method that retrieves the session token and other related information such as the token's expiration time, client ID, message ID, and status. The method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the session token retrieval, "0" indicates success |
| token | string | The actual session token |
| expires | integer | The expiration time of the session token |
| clientId | string | The client ID associated with the session token |
| messageId | string | The message ID associated with the session token |
| success | boolean | Indicates whether the session token retrieval was successful |
| message | string | Any additional message or information related to the session token retrieval |

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

This API sets the session token. It takes in several parameters including status, token, expiration time, client ID, and message ID. Upon successful execution, it triggers the [SessionTokenChanged](#event.SessionTokenChanged) event.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The status of the session |
| token | string | The session token |
| expires | uint32_t | The expiration time of the session token |
| clientId | string | The client ID |
| messageId | string | The message ID |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The status of the operation, 0 indicates success |
| token | string | The session token |
| expires | uint32_t | The expiration time of the session token |
| clientId | string | The client ID |
| messageId | string | The message ID |

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

This API returns the service access token. It is a crucial method for authenticating and authorizing the service. The access token is a key to access the service and its features.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The status of the request, "0" indicates success |
| token | string | The service access token |
| expires | integer | The expiration time of the token in seconds |
| success | boolean | Indicates whether the token retrieval was successful |
| message | string | Any additional message related to the token retrieval |

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

This API sets the service access token. It takes in a status, a token, and an expiration time. The status is used to determine the state of the service, the token is the access token for the service, and the expiration time is the time at which the token will expire.

This method triggers the [ServiceAccessTokenChanged](#event.ServiceAccessTokenChanged)

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | int32_t | The status of the service |
| token | string | The access token for the service |
| expires | uint32_t | The expiration time for the token |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | bool | Indicates whether the operation was successful |
| message | string | Provides additional information about the operation |

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

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| serviceAccountId | string | The unique identifier for the service account |
| success | boolean | Indicates whether the operation was successful or not |

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

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetServiceAccountId"}'http://127.0.0.1:9998/jsonrpc

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

This method does not return a value. However, it does update the status of the operation in a `SuccessMsgResult` object passed as an output parameter. The `SuccessMsgResult` object has the following structure:

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | bool | Indicates whether the operation was successful |
| message | string | Contains any message returned by the operation |

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
<button onclick="setServiceAccountId('your_service_account_id')">Set Service Account ID</button>
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
    std::string result;
    parameters["serviceAccountId"] = "your_service_account_id";
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

This API sets the authorization ID token. It is used to authenticate the user and grant them access to the system. The ID token is a string that is passed as an input parameter to the method.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| authIdToken | string | The authorization ID token |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| setStat | SuccessMsgResult | The result of setting the authorization ID token. It returns "success": true, if the operation is successful. |

Note: The `SuccessMsgResult` is a user-defined type that contains two fields: "success" and "message". The "success" field is a boolean that indicates whether the operation was successful or not, and the "message" field is a string that contains a message about the operation.

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

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetAuthIdToken", "params":{"authIdToken":"your_auth_id_token"}}'http://127.0.0.1:9998/jsonrpc

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
    std::string result;
    parameters["authIdToken"] = "your_auth_id_token_value";
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
| success | boolean | Returns true if the device is ready |
| message | string | Returns an empty string |

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

This API returns the bootstrap property associated with the current partnerId. It is a virtual method that takes a string parameter and returns a set of properties.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| bootstrapProperty | string | The bootstrap property associated with the current partnerId |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| ntpHost | string | The NTP host, for example "ntp.ccp.xcal.tv" |
| success | boolean | The status of the operation, true if successful |
| message | string | A message associated with the operation, typically used for providing information on failures |

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
    parameters["bootstrapProperty"] = "ntpHost";
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
        "ntpHost": "ntp.ccp.xcal.tv",
        "success": true,
        "message": " "
    }
}
```

<a name="method.ActivationStarted"></a>
## ActivationStarted<div align="right">[<sup>methods & notifications</sup>](#head.Methods)</div>

This API lets the auth service know that the device's activation has started. It is used to initiate the activation process and ensure that the device is ready for use. The API communicates with the authentication service to confirm the start of the activation process.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| successResult | SuccessResult | The result of the activation process, returns "success": true if the activation has started successfully |

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
function startActivation() {
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
<button onclick="startActivation()">Start Activation</button>
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

This API lets the auth service know that the device's activation is completed. It is used to signal the completion of the device activation process. The API returns a success result indicating the status of the operation.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| successResult | SuccessResult | "success": true |

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

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.ActivationComplete"}'http://127.0.0.1:9998/jsonrpc

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

This API returns the stored Lost and Found access token (LFAT) if one is available. It is a virtual method that retrieves the LFAT from the system. The LFAT is a unique identifier used for lost and found operations.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| lostAndFoundAccessToken | string | The Lost and Found access token. |
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
| lostAndFoundAccessToken | string | The access token for the lost and found service in opaque JSON string format |

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
<button onclick="setLostAndFoundAccessToken('your_token_here')">Set Lost and Found Access Token</button>
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

This API returns the xDevice ID. It is a unique identifier for the xDevice. The method is used to retrieve the ID when required for various operations.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xDeviceId | string | The unique identifier for the xDevice |
| success | boolean | Indicates whether the operation was successful |
| message | string | Provides additional information about the operation |

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

This API sets the xDevice ID. It takes a string as an input parameter and returns a success message. This method is used to assign a unique identifier to the xDevice.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xDeviceId | string | The unique identifier for the xDevice |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns an empty string if the operation was successful |

### Example
#### Request

```json
{
"jsonrpc":"2.0",
"id":3,
"method":"org.rdk.AuthService.1.SetXDeviceId",
"params":{"xDeviceId":"your_value"}
}
```

<details>
 <summary><kbd>CURL</kbd></summary>

 ```bash

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetXDeviceId", "params":{"xDeviceId":"your_device_id"}}' http://127.0.0.1:9998/jsonrpc

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

This API returns the experience. It is a virtual method that retrieves the experience data and returns it in a structured format. The method is designed to be overridden in a derived class and it is used to implement the functionality to get the experience.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| experience | string | The experience value |
| success | boolean | The status of the operation, true if successful |

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

This API sets the experience. It takes a string as input and returns a success message. The experience can be any valid string value. The success message indicates whether the operation was successful or not.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| experience | string | The experience to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Indicates whether the operation was successful |
| message | string | The message returned by the API |

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
    parameters["experience"] = "5 years"; // replace "5 years" with actual experience value
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

This API returns the xifaId. It is a virtual method that can be overridden in a derived class. The method is designed to return a unique identifier, known as xifaId, which is used for various purposes within the system.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| xifaIdResult | GetxifaIdResult | This is the result of the API call, which contains the xifaId. |
| success | boolean | This indicates whether the API call was successful. If true, the xifaId was successfully retrieved. |

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
<button onclick="setXifaId('your_xifaId')">setXifaId</button>
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
| advtOptOutResult | AdvtOptOutResult | The advertisement opt-out status of the user |
| success | boolean | The status of the operation, returns true if the operation is successful |

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

This API sets the advertisement opt-out status. It takes a boolean value as input and returns a success message upon successful execution.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| advtOptOut | bool | The advertisement opt-out status to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| setStat | SuccessMsgResult | The success message result indicating the status of the operation |

Note: This method does not trigger any event.

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
    parameters["advtOptOut"] = true; // replace with actual value
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

This API returns the activation status. It checks whether the system is activated or not and returns the status as "not-activated" or "activated". The success of the operation is also returned.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| status | string | The activation status of the system. Possible values are "not-activated" and "activated". |
| success | boolean | Indicates the success of the operation. Returns true if the operation was successful, false otherwise. |

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
    if (invokeJSONRPC(remoteObject, "AuthService.GetActivationStatus", parameters, response)) {
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

This API is used to set the activation status. It takes a string as an input parameter and returns a success message. The activation status can be any string value. The method triggers the OnActivationStatusChanged event.

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
<button onclick="setActivationStatus('active')">Set Activation Status</button>
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

This API clears the authorization token. It is used when the user wants to log out or when the token is expired and needs to be refreshed. 

This method does not trigger any event.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the operation was successful |
| message | string | Returns an empty string as there is no specific message associated with this operation |
| setStat | SuccessMsgResult | User-defined type that holds the status of the operation |

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

This API clears the session token. It is used when a session is no longer needed or when a session needs to be reset. The API returns a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | Returns true if the session token is successfully cleared |

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

This API clears the service access token. It is used when there is a need to invalidate the current service access token and generate a new one. The method returns a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | bool | Indicates the success or failure of the operation |
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
| success | bool | Indicates the success or failure of the operation |
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

This API clears the service account ID. It is used when there is a need to reset or remove the existing service account ID from the system. The operation will return a success message upon successful execution.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | bool | Indicates the success of the operation |
| message | string | Provides additional information about the operation |

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
| setStat | SuccessMsgResult | User-defined type indicating the status of the operation |

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

This API returns the custom properties. It is a virtual method that retrieves the custom properties of an object. The properties are returned as a string and a success flag indicates whether the operation was successful or not.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| customProperties | string | The custom properties of the object |
| success | bool | A flag indicating whether the operation was successful or not |

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

This API sets the custom properties. It takes a JSON string as input and returns a success status. This method is useful when you want to add or modify custom properties in your application.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| customProperties | JSON string | The custom properties to be set |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| success | boolean | The success status of setting the custom properties |

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

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.SetCustomProperties", "params":{"customProperties":"your_custom_properties_here"}}' http://127.0.0.1:9998/jsonrpc

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

curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc":"2.0", "id":3, "method":"org.rdk.AuthService.1.GetAlternateIds"}' http://127.0.0.1:9998/jsonrpc

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
<button onclick="getAlternateIds()">Get Alternate IDs</button>
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
| success | boolean | Returns true if the operation was successful, false otherwise |
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

This API returns the transition data. It provides a mechanism to retrieve the data related to a specific transition. The transition data is returned as a string, and the success of the operation is indicated by a boolean value.

This method does not trigger any events.

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| transitionData | string | The transition data returned by the API |
| message | string | A message indicating the status or result of the operation |
| success | boolean | A boolean value indicating the success of the operation |

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
| params | Object | The new session token |

### Example
        
        
```json
{
  "jsonrpc": "2.0",
  "method": "client.events.SessionTokenChanged",
  "params": {"token": "new_token_value"}
}
```

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


