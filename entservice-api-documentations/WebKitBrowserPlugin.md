<!-- Generated automatically, DO NOT EDIT! -->
<a id="head.WebKitBrowser_Plugin"></a>
# WebKitBrowser Plugin

**Version: [1.0.0](https://github.com/rdkcentral/rdkservices/blob/main/WebKitBrowser/CHANGELOG.md)**

A WebKitBrowser plugin for Thunder framework.

### Table of Contents

- [Abbreviation, Acronyms and Terms](#head.Abbreviation,_Acronyms_and_Terms)
- [Description](#head.Description)
- [Configuration](#head.Configuration)
- [Methods](#head.Methods)
- [Notifications](#head.Notifications)

<a id="head.Abbreviation,_Acronyms_and_Terms"></a>
# Abbreviation, Acronyms and Terms

[[Refer to this link](userguide/aat.md)]

<a id="head.Description"></a>
# Description

The `WebKitBrowser` plugin provides an interface for WebKitBrowser.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].

<a id="head.Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: org.rdk.WebKitBrowser) |
| classname | string | Class name: *WebKitBrowser* |
| locator | string | Library name: *libWPEFrameworkWebKitBrowser.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a id="head.Methods"></a>
# Methods

The following methods are provided by the WebKitBrowser plugin:

WebKitBrowser interface methods:

| Method | Description |
| :-------- | :-------- |
| [contentLink](#method.contentLink) | URI of the associated application-specific content |
| [identifier](#method.identifier) |  |
| [language](#method.language) |  |
| [launchPoint](#method.launchPoint) |  |
| [reset](#method.reset) | Resets application data |
| [visible](#method.visible) |  |
| [addUserScript](#method.addUserScript) | Add user script to be executed at document start. |
| [bridgeEvent](#method.bridgeEvent) | Send legacy $badger event. |
| [bridgeReply](#method.bridgeReply) | Response for legacy $badger. |
| [collectGarbage](#method.collectGarbage) | Initiate garbage collection |
| [setcoookiejar](#method.setcoookiejar) |  |
| [cookieJarChanged](#method.cookieJarChanged) | Notifies that cookies were added, removed or modified. |
| [fPS](#method.fPS) | Current framerate the browser is rendering at |
| [getFPS](#method.getFPS) |  |
| [getURL](#method.getURL) |  |
| [hTTPCookieAcceptPolicy](#method.hTTPCookieAcceptPolicy) |  |
| [hide](#method.hide) |  |
| [loadFailed](#method.loadFailed) | Browser failed to load page |
| [loadFinished](#method.loadFinished) | Initial HTML document has been completely loaded and parsed |
| [localStorageEnabled](#method.localStorageEnabled) |  |
| [mixedContentPolicy](#method.mixedContentPolicy) |  |
| [pageClosure](#method.pageClosure) | Notifies that the web page requests to close its window |
| [removeAllUserScripts](#method.removeAllUserScripts) | Remove all user scripts. |
| [runJavaScript](#method.runJavaScript) | Run javascript in main frame. |
| [securityProfile](#method.securityProfile) |  |
| [setURL](#method.setURL) |  |
| [uRL](#method.uRL) |  |
| [uRLChange](#method.uRLChange) | Signals a URL change in the browser |
| [userAgent](#method.userAgent) |  |
| [userScripts](#method.userScripts) |  |
| [userStyleSheets](#method.userStyleSheets) |  |
| [visibility](#method.visibility) |  |
| [visibilityChange](#method.visibilityChange) | Signals a visibility change of the browser |
| [allocated](#method.allocated) |  |
| [isOperational](#method.isOperational) |  |
| [name](#method.name) |  |
| [process](#method.process) |  |
| [processes](#method.processes) |  |
| [resident](#method.resident) |  |
| [shared](#method.shared) |  |

<a id="method.contentLink"></a>
## *contentLink [<sup>method</sup>](#head.Methods)*

URI of the associated application-specific content

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.link | string | Content URI (e.g. https://youtube.com) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.WebKitBrowser.contentLink",
    "params": {
        "link": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.WebKitBrowser.contentLink", "params": {"link": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": null
}
```

<a id="method.identifier"></a>
## *identifier [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "method": "org.rdk.WebKitBrowser.identifier"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 1, "method": "org.rdk.WebKitBrowser.identifier"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "result": null
}
```

<a id="method.language"></a>
## *language [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.WebKitBrowser.language"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.WebKitBrowser.language"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": null
}
```

<a id="method.launchPoint"></a>
## *launchPoint [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.WebKitBrowser.launchPoint"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.WebKitBrowser.launchPoint"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": null
}
```

<a id="method.reset"></a>
## *reset [<sup>method</sup>](#head.Methods)*

Resets application data

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.type | resettype | Type of reset to perform |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "method": "org.rdk.WebKitBrowser.reset",
    "params": {
        "type": "FACTORY"
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 4, "method": "org.rdk.WebKitBrowser.reset", "params": {"type": "FACTORY"}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "result": null
}
```

<a id="method.visible"></a>
## *visible [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "method": "org.rdk.WebKitBrowser.visible"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 5, "method": "org.rdk.WebKitBrowser.visible"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "result": null
}
```

<a id="method.addUserScript"></a>
## *addUserScript [<sup>method</sup>](#head.Methods)*

Add user script to be executed at document start.

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.script | string | Utf8 encoded JS code string. |
| params.topFrameOnly | bool |  |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.WebKitBrowser.addUserScript",
    "params": {
        "script": "",
        "topFrameOnly": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.WebKitBrowser.addUserScript", "params": {"script": "", "topFrameOnly": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": null
}
```

<a id="method.bridgeEvent"></a>
## *bridgeEvent [<sup>method</sup>](#head.Methods)*

Send legacy $badger event.

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.payload | string | base64 encoded JSON string response to be delivered to $badger.callback |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "method": "org.rdk.WebKitBrowser.bridgeEvent",
    "params": {
        "payload": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 1, "method": "org.rdk.WebKitBrowser.bridgeEvent", "params": {"payload": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "result": null
}
```

<a id="method.bridgeReply"></a>
## *bridgeReply [<sup>method</sup>](#head.Methods)*

Response for legacy $badger.

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.payload | string | base64 encoded JSON string response to be delivered to $badger.callback |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.WebKitBrowser.bridgeReply",
    "params": {
        "payload": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.WebKitBrowser.bridgeReply", "params": {"payload": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": null
}
```

<a id="method.collectGarbage"></a>
## *collectGarbage [<sup>method</sup>](#head.Methods)*

Initiate garbage collection

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.WebKitBrowser.collectGarbage"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.WebKitBrowser.collectGarbage"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": null
}
```

<a id="method.cookieJar"></a>
## *cookieJar [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.version | uint32_t |  |
| params.checksum | uint32_t |  |
| params.payload | string | base64 encoded JSON string response to be delivered to $badger.callback |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "method": "org.rdk.WebKitBrowser.cookieJar",
    "params": {
        "version": 0,
        "checksum": 0,
        "payload": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 4, "method": "org.rdk.WebKitBrowser.cookieJar", "params": {"version": 0, "checksum": 0, "payload": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "result": null
}
```

<a id="method.cookieJarChanged"></a>
## *cookieJarChanged [<sup>method</sup>](#head.Methods)*

Notifies that cookies were added, removed or modified.

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "method": "org.rdk.WebKitBrowser.cookieJarChanged"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 5, "method": "org.rdk.WebKitBrowser.cookieJarChanged"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "result": null
}
```

<a id="method.fPS"></a>
## *fPS [<sup>method</sup>](#head.Methods)*

Current framerate the browser is rendering at

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.fps | uint8_t | Current FPS |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "method": "org.rdk.WebKitBrowser.fPS"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 6, "method": "org.rdk.WebKitBrowser.fPS"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "result": {
        "fps": ""
    }
}
```

<a id="method.getFPS"></a>
## *getFPS [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "method": "org.rdk.WebKitBrowser.getFPS"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 7, "method": "org.rdk.WebKitBrowser.getFPS"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "result": null
}
```

<a id="method.getURL"></a>
## *getURL [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 8,
    "method": "org.rdk.WebKitBrowser.getURL"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 8, "method": "org.rdk.WebKitBrowser.getURL"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 8,
    "result": null
}
```

<a id="method.hTTPCookieAcceptPolicy"></a>
## *hTTPCookieAcceptPolicy [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.policy | HTTPCookieAcceptPolicyType | HTTP Cookie Accept Policy Type (e.g. always) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 9,
    "method": "org.rdk.WebKitBrowser.hTTPCookieAcceptPolicy",
    "params": {
        "policy": "ALWAYS"
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 9, "method": "org.rdk.WebKitBrowser.hTTPCookieAcceptPolicy", "params": {"policy": "ALWAYS"}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 9,
    "result": null
}
```

<a id="method.hide"></a>
## *hide [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hidden | bool | hidden (true) or visible (false) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 10,
    "method": "org.rdk.WebKitBrowser.hide",
    "params": {
        "hidden": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 10, "method": "org.rdk.WebKitBrowser.hide", "params": {"hidden": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 10,
    "result": null
}
```

<a id="method.loadFailed"></a>
## *loadFailed [<sup>method</sup>](#head.Methods)*

Browser failed to load page

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 11,
    "method": "org.rdk.WebKitBrowser.loadFailed",
    "params": {
        "URL": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 11, "method": "org.rdk.WebKitBrowser.loadFailed", "params": {"URL": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 11,
    "result": null
}
```

<a id="method.loadFinished"></a>
## *loadFinished [<sup>method</sup>](#head.Methods)*

Initial HTML document has been completely loaded and parsed

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |
| params.httpstatus | int32_t | The response code of main resource request (e.g. 200) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 12,
    "method": "org.rdk.WebKitBrowser.loadFinished",
    "params": {
        "URL": "",
        "httpstatus": 0
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 12, "method": "org.rdk.WebKitBrowser.loadFinished", "params": {"URL": "", "httpstatus": 0}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 12,
    "result": null
}
```

<a id="method.localStorageEnabled"></a>
## *localStorageEnabled [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enabled | bool |  |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 13,
    "method": "org.rdk.WebKitBrowser.localStorageEnabled",
    "params": {
        "enabled": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 13, "method": "org.rdk.WebKitBrowser.localStorageEnabled", "params": {"enabled": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 13,
    "result": null
}
```

<a id="method.mixedContentPolicy"></a>
## *mixedContentPolicy [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.policy | MixedContentPolicyType | Mixed content policy type |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 14,
    "method": "org.rdk.WebKitBrowser.mixedContentPolicy",
    "params": {
        "policy": "ALLOWED"
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 14, "method": "org.rdk.WebKitBrowser.mixedContentPolicy", "params": {"policy": "ALLOWED"}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 14,
    "result": null
}
```

<a id="method.pageClosure"></a>
## *pageClosure [<sup>method</sup>](#head.Methods)*

Notifies that the web page requests to close its window

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 15,
    "method": "org.rdk.WebKitBrowser.pageClosure"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 15, "method": "org.rdk.WebKitBrowser.pageClosure"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 15,
    "result": null
}
```

<a id="method.removeAllUserScripts"></a>
## *removeAllUserScripts [<sup>method</sup>](#head.Methods)*

Remove all user scripts.

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 16,
    "method": "org.rdk.WebKitBrowser.removeAllUserScripts"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 16, "method": "org.rdk.WebKitBrowser.removeAllUserScripts"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 16,
    "result": null
}
```

<a id="method.runJavaScript"></a>
## *runJavaScript [<sup>method</sup>](#head.Methods)*

Run javascript in main frame.

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.script | string | Utf8 encoded JS code string. |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 17,
    "method": "org.rdk.WebKitBrowser.runJavaScript",
    "params": {
        "script": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 17, "method": "org.rdk.WebKitBrowser.runJavaScript", "params": {"script": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 17,
    "result": null
}
```

<a id="method.securityProfile"></a>
## *securityProfile [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.profile | string | Security profile for secure connections (e.g. compatible) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 18,
    "method": "org.rdk.WebKitBrowser.securityProfile",
    "params": {
        "profile": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 18, "method": "org.rdk.WebKitBrowser.securityProfile", "params": {"profile": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 18,
    "result": null
}
```

<a id="method.setURL"></a>
## *setURL [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 19,
    "method": "org.rdk.WebKitBrowser.setURL",
    "params": {
        "URL": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 19, "method": "org.rdk.WebKitBrowser.setURL", "params": {"URL": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 19,
    "result": null
}
```

<a id="method.uRL"></a>
## *uRL [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.url | string | Loaded URL (e.g. https://example.com) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 20,
    "method": "org.rdk.WebKitBrowser.uRL",
    "params": {
        "url": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 20, "method": "org.rdk.WebKitBrowser.uRL", "params": {"url": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 20,
    "result": null
}
```

<a id="method.uRLChange"></a>
## *uRLChange [<sup>method</sup>](#head.Methods)*

Signals a URL change in the browser

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |
| params.loaded | bool | loaded (true) or not (false) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 21,
    "method": "org.rdk.WebKitBrowser.uRLChange",
    "params": {
        "URL": "",
        "loaded": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 21, "method": "org.rdk.WebKitBrowser.uRLChange", "params": {"URL": "", "loaded": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 21,
    "result": null
}
```

<a id="method.userAgent"></a>
## *userAgent [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.useragent | string | UserAgent value (e.g. Mozilla/5.0 (Linux; x86_64 GNU/Linux) AppleWebKit/601.1 (KHTML, like Gecko) Version/8.0 Safari/601.1 WP) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 22,
    "method": "org.rdk.WebKitBrowser.userAgent",
    "params": {
        "useragent": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 22, "method": "org.rdk.WebKitBrowser.userAgent", "params": {"useragent": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 22,
    "result": null
}
```

<a id="method.userScripts"></a>
## *userScripts [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.uris | IStringIterator | JSON array containing URIs pointing to user scripts, supported protocols: file:// |
| params.uris[#] | string |  |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 23,
    "method": "org.rdk.WebKitBrowser.userScripts",
    "params": [
        ""
    ]
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 23, "method": "org.rdk.WebKitBrowser.userScripts", "params": [""]}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 23,
    "result": null
}
```

<a id="method.userStyleSheets"></a>
## *userStyleSheets [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.uris | IStringIterator | JSON array containing URIs pointing to user scripts, supported protocols: file:// |
| params.uris[#] | string |  |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 24,
    "method": "org.rdk.WebKitBrowser.userStyleSheets",
    "params": [
        ""
    ]
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 24, "method": "org.rdk.WebKitBrowser.userStyleSheets", "params": [""]}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 24,
    "result": null
}
```

<a id="method.visibility"></a>
## *visibility [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.visible | VisibilityType | Visiblity state (e.g. ) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 25,
    "method": "org.rdk.WebKitBrowser.visibility",
    "params": {
        "visible": "HIDDEN"
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 25, "method": "org.rdk.WebKitBrowser.visibility", "params": {"visible": "HIDDEN"}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 25,
    "result": null
}
```

<a id="method.visibilityChange"></a>
## *visibilityChange [<sup>method</sup>](#head.Methods)*

Signals a visibility change of the browser

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hidden | bool | hidden (true) or visible (false) |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 26,
    "method": "org.rdk.WebKitBrowser.visibilityChange",
    "params": {
        "hidden": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 26, "method": "org.rdk.WebKitBrowser.visibilityChange", "params": {"hidden": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 26,
    "result": null
}
```

<a id="method.allocated"></a>
## *allocated [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.WebKitBrowser.allocated"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.WebKitBrowser.allocated"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": null
}
```

<a id="method.isOperational"></a>
## *isOperational [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.WebKitBrowser.isOperational"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.WebKitBrowser.isOperational"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": null
}
```

<a id="method.name"></a>
## *name [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.WebKitBrowser.name"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.WebKitBrowser.name"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": null
}
```

<a id="method.process"></a>
## *process [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.processname | string |  |
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.process | IProcessMemory |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "method": "org.rdk.WebKitBrowser.process",
    "params": {
        "processname": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 4, "method": "org.rdk.WebKitBrowser.process", "params": {"processname": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "result": {
        "process": ""
    }
}
```

<a id="method.processes"></a>
## *processes [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.processnames | IStringIterator |  |
| result.processnames[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "method": "org.rdk.WebKitBrowser.processes"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 5, "method": "org.rdk.WebKitBrowser.processes"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "result": [
        ""
    ]
}
```

<a id="method.resident"></a>
## *resident [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "method": "org.rdk.WebKitBrowser.resident"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 6, "method": "org.rdk.WebKitBrowser.resident"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "result": null
}
```

<a id="method.shared"></a>
## *shared [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "method": "org.rdk.WebKitBrowser.shared"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 7, "method": "org.rdk.WebKitBrowser.shared"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "result": null
}
```



<a id="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the WebKitBrowser plugin:

WebKitBrowser interface events:

| Event | Description |
| :-------- | :-------- |
| [visibilityChange](#event.visibilityChange) | Application visibility changes |
| [closure](#event.closure) |  |
| [hidden](#event.hidden) |  |
| [loadFinished](#event.loadFinished) |  |
| [uRLChanged](#event.uRLChanged) |  |

<a id="event.visibilityChange"></a>
## *visibilityChange [<sup>event</sup>](#head.Notifications)*

Application visibility changes

### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hidden | bool | hidden (true) or visible (false) |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "method": "org.rdk.WebKitBrowser.visibilityChange",
    "params": {
        "hidden": true
    }
}
```

<a id="event.closure"></a>
## *closure [<sup>event</sup>](#head.Notifications)*



### Parameters
This method takes no parameters.

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 27,
    "method": "org.rdk.WebKitBrowser.closure"
}
```

<a id="event.hidden"></a>
## *hidden [<sup>event</sup>](#head.Notifications)*



### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hidden | bool | hidden (true) or visible (false) |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 28,
    "method": "org.rdk.WebKitBrowser.hidden",
    "params": {
        "hidden": true
    }
}
```

<a id="event.loadFinished"></a>
## *loadFinished [<sup>event</sup>](#head.Notifications)*



### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 29,
    "method": "org.rdk.WebKitBrowser.loadFinished",
    "params": {
        "URL": ""
    }
}
```

<a id="event.uRLChanged"></a>
## *uRLChanged [<sup>event</sup>](#head.Notifications)*



### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.URL | string | The URL that has been loaded (e.g. https://example.com) |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 30,
    "method": "org.rdk.WebKitBrowser.uRLChanged",
    "params": {
        "URL": ""
    }
}
```
