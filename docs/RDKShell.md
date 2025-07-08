<!-- Generated automatically, DO NOT EDIT! -->
<a name="RDKShell_Plugin"></a>
# RDKShell Plugin

**Version: [1.0.0]()**

A org.rdk.RDKShell plugin for Thunder framework.

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


RDKShell is a lightweight and efficient framework designed for managing graphical user interfaces and applications within RDK-based platforms. It provides tools for window management, rendering, and application lifecycle control, enabling seamless integration and performance optimization for set-top boxes and connected devices.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#Thunder)].

<a name="Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: *org.rdk.RDKShell*) |
| classname | string | Class name: *org.rdk.RDKShell* |
| locator | string | Library name: *libWPEFrameworkRDKShell.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a name="Methods"></a>
# Methods

The following methods are provided by the org.rdk.RDKShell plugin:

RDKShell interface methods:

| Method | Description |
| :-------- | :-------- |
| [addAnimation](#addAnimation) | Performs the set of animations |
| [addKeyIntercept](#addKeyIntercept) | Adds a key intercept to the client application specified |
| [addKeyIntercepts](#addKeyIntercepts) | Adds the list of key intercepts |
| [addKeyListener](#addKeyListener) | Adds a key listener to an application |
| [addKeyMetadataListener](#addKeyMetadataListener) | Adds the key metadata listeners |
| [createDisplay](#createDisplay) |  Creates a display for the specified client using the configuration parameters |
| [destroy](#destroy) | Destroys an application |
| [enableInactivityReporting](#enableInactivityReporting) | Enables or disables inactivity reporting and events |
| [enableKeyRepeats](#enableKeyRepeats) | Enables or disables key repeats |
| [enableLogsFlushing](#enableLogsFlushing) | Enables or disables flushing all logs |
| [enableVirtualDisplay](#enableVirtualDisplay) | Enables or disables a virtual display for the specified client |
| [generateKey](#generateKey) | Triggers the key events (key press and release) |
| [getAvailableTypes](#getAvailableTypes) | Returns the list of application types available on the firmware |
| [getBounds](#getBounds) | Gets the bounds of the specified client |
| [getClients](#getClients) | Gets a list of clients |
| [getCursorSize](#getCursorSize) | Returns the currently set cursor size |
| [getHolePunch](#getHolePunch) | Returns whether video hole punching is enabled or disabled for the specified client |
| [getKeyRepeatsEnabled](#getKeyRepeatsEnabled) | Returns whether key repeating is enabled or disabled |
| [getLastWakeupKey](#getLastWakeupKey) | Returns the last key press prior to a device wakeup |
| [getLogLevel](#getLogLevel) | Returns the currently set logging level |
| [getLogsFlushingEnabled](#getLogsFlushingEnabled) | Returns whether log flushing is enabled or disabled |
| [getOpacity](#getOpacity) | Gets the opacity of the specified client |
| [getScale](#getScale) | Returns the scale of an application |
| [getScreenResolution](#getScreenResolution) | Gets the screen resolution |
| [getScreenshot](#getScreenshot) | Captures a screenshot |
| [getState](#getState) | Returns the state of all applications |
| [getSystemMemory](#getSystemMemory) | Gets the information of System Memory |
| [getSystemResourceInfo](#getSystemResourceInfo) | Returns system resource information about each application |
| [getVirtualDisplayEnabled](#getVirtualDisplayEnabled) | Returns whether virtual display is enabled or disabled for the specified client |
| [getVirtualResolution](#getVirtualResolution) | Returns the virtual display resolution for the specified client |
| [getVisibility](#getVisibility) | Gets the visibility of the specified client |
| [getZOrder](#getZOrder) | Returns an array of clients in Z order, starting with the top most application client first |
| [getGraphicsFrameRate](#getGraphicsFrameRate) | Returns the current Graphics Frame Rate |
| [hideAllClients](#hideAllClients) | Hides/Unhides all the clients |
| [hideCursor](#hideCursor) | Hides the cursor from showing on the display |
| [hideFullScreenImage](#hideFullScreenImage) | Hides the Full Screen Image |
| [hideSplashLogo](#hideSplashLogo) | Removes the splash screen |
| [ignoreKeyInputs](#ignoreKeyInputs) | Blocks user key inputs |
| [injectKey](#injectKey) | Injects the keys |
| [kill](#kill) | Kills the specified client |
| [launch](#launch) | Launches an application |
| [launchApplication](#launchApplication) | Launches an application |
| [launchResidentApp](#launchResidentApp) | Launches the Resident application |
| [moveBehind](#moveBehind) | Moves the specified client behind the specified target client |
| [moveToBack](#moveToBack) | Moves the specified client to the back or bottom of the Z order |
| [moveToFront](#moveToFront) | Moves the specified client to the front or top of the Z order |
| [removeAllKeyIntercepts](#removeAllKeyIntercepts) | Removes all key intercepts |
| [removeAllKeyListeners](#removeAllKeyListeners) | Removes all key listeners |
| [removeAnimation](#removeAnimation) | Removes the current animation for the specified client |
| [removeKeyIntercept](#removeKeyIntercept) | Removes a key intercept |
| [removeKeyListener](#removeKeyListener) | Removes a key listener for an application |
| [removeKeyMetadataListener](#removeKeyMetadataListener) | Removes the key metadata listeners |
| [resetInactivityTime](#resetInactivityTime) | Resets the inactivity notification interval |
| [resumeApplication](#resumeApplication) | Resumes an application |
| [scaleToFit](#scaleToFit) | Scales the specified client to fit the current bounds |
| [setBounds](#setBounds) | Sets the bounds of the specified client |
| [setCursorSize](#setCursorSize) | Sets the cursor size |
| [setFocus](#setFocus) | Sets focus to the specified client |
| [setHolePunch](#setHolePunch) | Enables or disables video hole punching for the specified client |
| [setInactivityInterval](#setInactivityInterval) | Sets the inactivity notification interval |
| [setLogLevel](#setLogLevel) | Sets the logging level |
| [setMemoryMonitor](#setMemoryMonitor) | Enables or disables RAM memory monitoring on the device |
| [setOpacity](#setOpacity) | Sets the opacity of the specified client |
| [setScale](#setScale) | Scales an application |
| [setScreenResolution](#setScreenResolution) | Sets the screen resolution |
| [setTopmost](#setTopmost) | Sets whether the specified client appears above all other clients on the display |
| [setVirtualResolution](#setVirtualResolution) | Sets the virtual resolution for the specified client |
| [setVisibility](#setVisibility) | Sets whether the specified client should be visible |
| [setGraphicsFrameRate](#setGraphicsFrameRate) | Set Graphics Frame Rate |
| [showCursor](#showCursor) | Shows the cursor on the display using the current cursor size |
| [showFullScreenImage](#showFullScreenImage) | Shows the Full Screen Image |
| [showSplashLogo](#showSplashLogo) | Displays the splash screen |
| [showWatermark](#showWatermark) | Sets whether a watermark shows on the display |
| [suspend](#suspend) | Suspends an application |
| [suspendApplication](#suspendApplication) | Suspends an application |
| [keyRepeatConfig](#keyRepeatConfig) | Customizes key repeats |
| [setAVBlocked](#setAVBlocked) | adds/removes the list of applications with the given callsigns to/from the blacklist |
| [getBlockedAVApplications](#getBlockedAVApplications) | Gets a list of blacklisted clients |


<a name="addAnimation"></a>
## *addAnimation*


The *addAnimation* API is designed to enhance the visual experience by allowing users to add animations to specific elements or components within an application or display. This function is particularly useful for creating dynamic and engaging user interfaces, improving the overall aesthetic appeal, and providing visual feedback for user interactions. By using *addAnimation*, users can define and apply animations such as transitions, movements, or effects to elements, making the application more interactive and visually appealing. This API is ideal for scenarios where smooth and visually captivating animations are required to improve user engagement or highlight specific actions or states within the application.

### Related Functions  
[destroy](#destroy) : This function can be used to remove or clean up elements or components, including those with animations, ensuring proper resource management and preventing unnecessary clutter.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.animations | array | A list of animations to perform |
| params.animations[#] | object |  |
| params.animations[#].client | string | The client name |
| params.animations[#]?.x | number | <sup>*(optional)*</sup> The x location |
| params.animations[#]?.y | number | <sup>*(optional)*</sup> The y location |
| params.animations[#]?.w | number | <sup>*(optional)*</sup> The width |
| params.animations[#]?.h | number | <sup>*(optional)*</sup> The height |
| params.animations[#]?.sx | number | <sup>*(optional)*</sup> The x scale factor |
| params.animations[#]?.sy | number | <sup>*(optional)*</sup> The y scale factor |
| params.animations[#]?.a | number | <sup>*(optional)*</sup> The alpha/opacity level to animate to (between 0 and 100) |
| params.animations[#]?.duration | number | <sup>*(optional)*</sup> The duration of the animation in seconds |
| params.animations[#]?.tween | string | <sup>*(optional)*</sup> The animation tween type. The default is `linear` (must be one of the following: *linear*, *exp1*, *exp2*, *exp3*, *inquad*, *incubic*, *nback*, *inelastic*, *outelastic*, *outbounce*) |
| params.animations[#]?.delay | number | <sup>*(optional)*</sup> Set delay for an animation |

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
    "method": "org.rdk.RDKShell.addAnimation",
    "params": {
        "animations": [
            {
                "client": "org.rdk.Netflix",
                "x": 0,
                "y": 0,
                "w": 1920,
                "h": 1080,
                "sx": 0.5,
                "sy": 0.5,
                "a": 0,
                "duration": 2,
                "tween": "exp1",
                "delay": 0
            }
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
        "success": true
    }
}
```



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.addAnimation", 
    "params":{"animations":[{"client":"org.rdk.Netflix","x":0,"y":0,"w":1920,"h":1080,"sx":0.5,"sy":0.5,"a":0,"duration":2,"tween":"exp1","delay":0}]}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function addAnimation(params) {
      thunderJS.org.rdk.RDKShell.addAnimation(params)
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
    <button onclick="addAnimation({animations: [{client: 'org.rdk.Netflix', x: 0, y: 0, w: 1920, h: 1080, sx: 0.5, sy: 0.5, a: 0, duration: 2, tween: 'exp1', delay: 0}]})">addAnimation</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void addAnimation(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["animations"] = JsonArray();
        JsonObject animation;
        animation["client"] = "org.rdk.Netflix";
        animation["x"] = 0;
        animation["y"] = 0;
        animation["w"] = 1920;
        animation["h"] = 1080;
        animation["sx"] = 0.5;
        animation["sy"] = 0.5;
        animation["a"] = 0;
        animation["duration"] = 2;
        animation["tween"] = "exp1";
        animation["delay"] = 0;
        parameters["animations"].Add(animation);
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="addKeyIntercept"></a>
## *addKeyIntercept*


The *addKeyIntercept* API is designed to allow users to intercept specific key events before they are processed by the system or application. This function is particularly useful for scenarios where you need to customize or override the default behavior of certain keys. For example, you can use this API to block specific key inputs, remap keys to different actions, or implement custom shortcuts. By intercepting key events, you gain greater control over how the application responds to user input, enabling a more tailored and interactive experience.

### Related Functions  
[addKeyIntercepts](#addKeyIntercepts) : Allows you to intercept multiple key events at once, providing a more efficient way to handle bulk key interception.  
[addKeyListener](#addKeyListener) : Enables you to listen for key events, which can complement *addKeyIntercept* by allowing you to monitor key activity alongside interception.  
[addKeyMetadataListener](#addKeyMetadataListener) : Provides metadata about key events, which can be useful for understanding intercepted keys and their context.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.modifiers[#] | string |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.addKeyIntercept",
    "params": {
        "keyCode": 10,
        "modifiers": [
            "shift"
        ],
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.addKeyIntercept", 
    "params":{"keyCode":13,"modifiers":["ctrl","shift"]}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function addKeyIntercept(params) {
      thunderJS.org.rdk.RDKShell.addKeyIntercept(params)
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
    <button onclick="addKeyIntercept({keyCode: 13, modifiers: ['ctrl', 'shift']})">addKeyIntercept</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void addKeyIntercept(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["keyCode"] = 13;
        parameters["modifiers"] = JsonArray({ "ctrl", "shift" });
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="addKeyIntercepts"></a>
## *addKeyIntercepts*


The `addKeyIntercepts` function is designed to allow users to specify a list of keys that should be intercepted by the system. When a key is intercepted, it prevents the default behavior associated with that key from being executed. This is particularly useful in scenarios where you want to override or customize the behavior of specific keys, such as in gaming applications, custom user interfaces, or specialized workflows. By using this function, you can ensure that the specified keys are handled exclusively by your application, providing greater control over user interactions.

### Related Functions  
[addKeyIntercept](#addKeyIntercept) : Allows interception of a single key, providing a more granular approach compared to `addKeyIntercepts`.  
[addKeyListener](#addKeyListener) : Enables listening for key events, which can complement the use of `addKeyIntercepts` by allowing you to define custom actions for intercepted keys.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.intercepts | array | A list of intercepts |
| params.intercepts[#] | object |  |
| params.intercepts[#].client | string | The client name |
| params.intercepts[#].keys | array | A list of keys to simulate |
| params.intercepts[#].keys[#] | object |  |
| params.intercepts[#].keys[#].keycode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.intercepts[#].keys[#].modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.intercepts[#].keys[#].modifiers[#] | string |  |

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
    "method": "org.rdk.RDKShell.addKeyIntercepts",
    "params": {
        "intercepts": [
            {
                "client": "searchanddiscovery",
                "keys": [
                    {
                        "keycode": 10,
                        "modifiers": [
                            "shift"
                        ]
                    }
                ]
            }
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
        "success": true
    }
}
```



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.addKeyIntercepts", 
    "params":{"keys":[{"keyCode":13,"modifiers":["ctrl","shift"]}]}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function addKeyIntercepts(params) {
      thunderJS.addKeyIntercepts(params)
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
    <button onclick="addKeyIntercepts({ keys: [{ keyCode: 13, modifiers: ['ctrl', 'shift'] }] })">addKeyIntercepts</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void addKeyIntercepts(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["keys"] = JsonArray();
        JsonObject keyObject;
        keyObject["keyCode"] = 13;
        keyObject["modifiers"] = JsonArray();
        keyObject["modifiers"].Add("ctrl");
        keyObject["modifiers"].Add("shift");
        parameters["keys"].Add(keyObject);
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="addKeyListener"></a>
## *addKeyListener*


The `addKeyListener` function is designed to allow users to monitor and respond to specific key events. By using this function, you can attach a listener that will be triggered whenever a particular key or set of keys is pressed or released. This is particularly useful for creating interactive applications, such as games, remote controls, or any system that requires real-time key input handling. The function ensures that your application can react dynamically to user input, enhancing the overall user experience. 

### Related Functions  
[addKeyIntercept](#addKeyIntercept) : Allows you to intercept specific key events before they are processed by the system, enabling you to override default behaviors.  
[addKeyIntercepts](#addKeyIntercepts) : Similar to `addKeyIntercept`, but allows you to intercept multiple key events at once.  
[addKeyMetadataListener](#addKeyMetadataListener) : Enables you to listen for metadata associated with key events, providing additional context about the key actions.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.keys | array | A list of keys on which to add a listener for the specified application |
| params.keys[#] | object |  |
| params.keys[#].keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.keys[#]?.nativekeyCode | number | <sup>*(optional)*</sup> The native key code |
| params.keys[#].modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.keys[#].modifiers[#] | string |  |
| params.keys[#].activate | boolean | Activate an application on key  The default is `false` |
| params.keys[#].propagate | boolean | Propagate to the next application in the z-order. The default is `true` |

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
    "method": "org.rdk.RDKShell.addKeyListener",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "keys": [
            {
                "keyCode": 10,
                "nativekeyCode": 10,
                "modifiers": [
                    "shift"
                ],
                "activate": false,
                "propagate": true
            }
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
        "success": true
    }
}
```



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.addKeyListener", 
    "params":{"keyCode":13, "client":"HtmlApp", "activate":true}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function addKeyListener(params) {
      thunderJS.org.rdk.RDKShell.addKeyListener(params)
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
    <button onclick="addKeyListener({keyCode: 13, client: 'HtmlApp', activate: true})">addKeyListener</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void addKeyListener(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["keyCode"] = 13;
        parameters["client"] = "HtmlApp";
        parameters["activate"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
    
    ```

<a name="addKeyMetadataListener"></a>
## *addKeyMetadataListener*


The `addKeyMetadataListener` function is designed to allow users to monitor and respond to metadata associated with key events. This function is particularly useful in scenarios where additional context or information about key inputs is required, such as tracking specific attributes or properties of a key press. By using this function, users can enhance their interaction handling by accessing detailed metadata, enabling more informed decision-making or customized responses to key events. This is ideal for applications that require advanced input handling or need to process key events with supplementary data.

### Related Functions  
[addKeyListener](#addKeyListener) : Provides a way to listen for key events, focusing on the key press or release actions without metadata.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.addKeyMetadataListener",
    "params": {
        "client": "searchanddiscovery",
        "callsign": "searchanddiscovery"
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.addKeyMetadataListener", 
    "params":{"client":"searchanddiscovery", "callsign":"searchanddiscovery"}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function addKeyMetadataListener(params) {
      thunderJS.addKeyMetadataListener(params)
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
    <button onclick="addKeyMetadataListener({client: 'searchanddiscovery', callsign: 'searchanddiscovery'})">addKeyMetadataListener</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void addKeyMetadataListener(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["client"] = "searchanddiscovery";
        parameters["callsign"] = "searchanddiscovery";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="createDisplay"></a>
## *createDisplay*


The `createDisplay` function is used to initialize and set up a display environment for rendering visual content. This function is essential for applications that require a graphical interface or need to present information visually to users. By invoking `createDisplay`, users can create a virtual or physical display instance that serves as the foundation for rendering animations, graphics, or other visual elements. It is particularly useful in scenarios where multiple displays are needed or when working with virtual environments. This function ensures that the display is properly configured and ready for use, enabling seamless integration with other graphical or interactive components.

### Related Functions  
[destroy](#destroy) : Used to terminate or remove the display created by `createDisplay`.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.displayName | string | A name for the display |
| params.displayWidth | number | The width of the display |
| params.displayHeight | number | The height of the display |
| params.virtualDisplay | boolean | Whether to create a virtual display (`true`) or not (`false`) |
| params.virtualWidth | number | The width of the virtual display |
| params.virtualHeight | number | The height of the virtual display |
| params?.topmost | boolean | <sup>*(optional)*</sup> Whether to set topmost (true) or not (false) |
| params?.focus | boolean | <sup>*(optional)*</sup> Whether to setfocus (true) or not (false) |

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
    "method": "org.rdk.RDKShell.createDisplay",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "displayName": "test",
        "displayWidth": 1920,
        "displayHeight": 1080,
        "virtualDisplay": true,
        "virtualWidth": 1920,
        "virtualHeight": 1080,
        "topmost": false,
        "focus": false
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.createDisplay", 
    "params":{}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function createDisplay() {
      thunderJS.org.rdk.RDKShell.createDisplay()
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
    <button onclick="createDisplay()">createDisplay</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void createDisplay(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

<a name="destroy"></a>
## *destroy*


The `destroy` function is used to terminate or dismantle a specific resource, object, or instance that was previously created. This function ensures that all associated resources, such as memory, connections, or other dependencies, are properly released and cleaned up. It is particularly useful for preventing resource leaks and maintaining optimal system performance. Users should call this function when the resource is no longer needed to ensure efficient resource management. Once the `destroy` function is invoked, the associated resource becomes inaccessible and cannot be reused.

### Related Functions  
[createDisplay](#createDisplay) : The `createDisplay` function is used to initialize or create a display resource. It is often paired with the `destroy` function to ensure proper lifecycle management of the display resource.

### Events

| Event | Description |
| :-------- | :-------- |
| [onDestroyed](#onDestroyed) | Triggers when a runtime is successfully destroyed |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.callsign | string | The application callsign |

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
    "method": "org.rdk.RDKShell.destroy",
    "params": {
        "callsign": "Cobalt"
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.suspend", 
    "params":{"callsign":"Cobalt"}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function suspend(params) {
      thunderJS.org.rdk.RDKShell.suspend(params)
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
    <button onclick="suspend({callsign: 'Cobalt'})">suspend</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void suspend(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["callsign"] = "Cobalt";
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }
    
    ```

<a name="enableInactivityReporting"></a>
## *enableInactivityReporting*


The `enableInactivityReporting` function is designed to monitor and report periods of inactivity within a system or application. When enabled, this function tracks user inactivity, such as the absence of input or interaction, and triggers notifications or logs based on predefined thresholds. This feature is particularly useful for applications that require user engagement tracking, session management, or security measures, such as locking the system after prolonged inactivity. By enabling inactivity reporting, users can ensure better control over idle states, improve resource management, and enhance user experience by implementing appropriate actions during inactivity.

### Related Functions  
None

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | boolean | Whether to enable (`true`) or disable (`false`) inactivity reporting |

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
    "method": "org.rdk.RDKShell.enableInactivityReporting",
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.enableInactivityReporting", 
    "params":{"enable":true}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function enableInactivityReporting(enable) {
      thunderJS.enableInactivityReporting(enable)
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
    <button onclick="enableInactivityReporting(true)">enableInactivityReporting</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void enableInactivityReporting(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

<a name="enableKeyRepeats"></a>
## *enableKeyRepeats*


The `enableKeyRepeats` function is used to control whether key repeat events are enabled or disabled for a system or application. When key repeats are enabled, holding down a key will generate repeated key press events at regular intervals, which can be useful for scenarios like text input, gaming, or any application where continuous key press actions are required. Disabling key repeats ensures that only a single key press event is registered, regardless of how long the key is held down. This function is particularly useful for customizing user input behavior based on the application's requirements, enhancing usability and responsiveness.

### Related Functions  
[addKeyListener](#addKeyListener) : Allows you to add a listener for key press events, which can be used in conjunction with `enableKeyRepeats` to handle repeated key presses effectively.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | boolean | Whether to enable (`true`) or disable (`false`) key repeats |

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
    "method": "org.rdk.RDKShell.enableKeyRepeats",
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.enableKeyRepeats", 
    "params":{"enable":true}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function enableKeyRepeats(enable) {
      thunderJS.org.rdk.RDKShell.enableKeyRepeats(enable)
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
    <button onclick="enableKeyRepeats(true)">enableKeyRepeats</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void org_rdk_RDKShell_enableKeyRepeats(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

<a name="enableLogsFlushing"></a>
## *enableLogsFlushing*


The `enableLogsFlushing` function is designed to ensure that log data is consistently written and stored, preventing any loss of critical information during application runtime. This function is particularly useful in scenarios where real-time monitoring or debugging is required, as it forces the system to flush logs to their designated storage or output location immediately. By enabling log flushing, users can maintain a reliable record of application events, errors, and other operational details, which can be crucial for troubleshooting, performance analysis, or compliance purposes. This function is ideal for applications that handle sensitive or high-priority data, where missing logs could lead to significant issues.

### Related Functions  
None

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | boolean | Whether to enable (`true`) or disable (`false`) log flushing |

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
    "method": "org.rdk.RDKShell.enableLogsFlushing",
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.enableLogsFlushing", 
    "params":{"enable":true}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function enableLogsFlushing(enable) {
      thunderJS.org.rdk.RDKShell.enableLogsFlushing({ enable: enable })
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
    <button onclick="enableLogsFlushing(true)">enableLogsFlushing</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void enableLogsFlushing(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
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

<a name="enableVirtualDisplay"></a>
## *enableVirtualDisplay*


The *enableVirtualDisplay* function is designed to activate a virtual display environment, allowing users to simulate or emulate a display without relying on physical hardware. This is particularly useful in scenarios where testing, debugging, or running applications in a controlled environment is required. By enabling a virtual display, users can create a flexible and customizable workspace that mimics the behavior of a real display, making it ideal for remote operations, automation, or scenarios where physical displays are unavailable or impractical. This function enhances accessibility and efficiency by providing a virtual alternative to traditional display setups.

### Related Functions  
[createDisplay](#createDisplay) : Used to create a new display instance, which can complement the virtual display setup.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.enable | boolean | Whether to enable (`true`) or disable (`false`) a virtual display |

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
    "method": "org.rdk.RDKShell.enableVirtualDisplay",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
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



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.enableVirtualDisplay", 
    "params":{"client":"org.rdk.Netflix","callsign":"org.rdk.Netflix","enable":true}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function enableVirtualDisplay(params) {
      thunderJS.enableVirtualDisplay(params)
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
    <button onclick="enableVirtualDisplay({client: 'org.rdk.Netflix', callsign: 'org.rdk.Netflix', enable: true})">enableVirtualDisplay</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void enableVirtualDisplay(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["client"] = "org.rdk.Netflix";
        parameters["callsign"] = "org.rdk.Netflix";
        parameters["enable"] = true;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="generateKey"></a>
## *generateKey*


The *generateKey* API is used to create a unique key or identifier that can be utilized for various purposes, such as authentication, encryption, or tracking within a system. This function is particularly useful when there is a need to generate secure and distinct keys dynamically, ensuring that no two keys are identical. It is designed to simplify the process of key generation, making it accessible for users who require a reliable method to produce unique identifiers without delving into complex algorithms or manual processes. The generated key can be used in scenarios like securing data, managing access control, or identifying specific entities within an application.

### Related Functions  
None

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.keys | array | A list of keys to simulate |
| params.keys[#] | object |  |
| params.keys[#].keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.keys[#].modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.keys[#].modifiers[#] | string |  |
| params.keys[#].delay | number | The amount of time to wait (in seconds) before sending the key event |
| params.keys[#]?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.keys[#]?.client | string | <sup>*(optional)*</sup> The client name can be used instead of callsign |

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
    "method": "org.rdk.RDKShell.generateKey",
    "params": {
        "keys": [
            {
                "keyCode": 10,
                "modifiers": [
                    "shift"
                ],
                "delay": 1.0,
                "callsign": "Cobalt",
                "client": "Cobalt"
            }
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
        "success": true
    }
}
```



=== "CURL"

    ```bash
    curl -H 'content-type:text/plain;' --data-binary 
    '{"jsonrpc":"2.0", 
    "id":3, 
    "method":"org.rdk.RDKShell.generateKey", 
    "params":{"input":"keyboard", 
    "enabled":true, 
    "initialDelay":500, 
    "repeatInterval":100}}'
    http://127.0.0.1:9998/jsonrpc

    ```
=== "JS"

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
    function generateKey(params) {
      thunderJS.org.rdk.RDKShell.generateKey(params)
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
    <button onclick="generateKey({input: 'keyboard', enabled: true, initialDelay: 500, repeatInterval: 100})">generateKey</button>
    </body>
    </html>

    ```
=== "CPP"

    ```cpp
    void generateKey(std::string methodName, JSONRPC::LinkType<Core::JSON::IElement> *remoteObject)
    {
        printf("[%llu] Inside (%s)", TimeStamp(), __FUNCTION__);
        JsonObject parameters, response;
        parameters["input"] = "keyboard";
        parameters["enabled"] = true;
        parameters["initialDelay"] = 500;
        parameters["repeatInterval"] = 100;
        std::string result;
        if (invokeJSONRPC(remoteObject, methodName, parameters, response)) {
            response.ToString(result);
            printf("Response: '%s'", result.c_str());
        }
    }

    ```

<a name="getAvailableTypes"></a>
## *getAvailableTypes*

Returns the list of application types available on the firmware.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.types | array | application types |
| result.types[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getAvailableTypes"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "types": [
            "HtmlBrowser"
        ],
        "success": true
    }
}
```

<a name="getBounds"></a>
## *getBounds*

Gets the bounds of the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.bounds | object |  |
| result.bounds.x | number | The x location |
| result.bounds.y | number | The y location |
| result.bounds.w | number | The width |
| result.bounds.h | number | The height |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getBounds",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "bounds": {
            "x": 0,
            "y": 0,
            "w": 1920,
            "h": 1080
        },
        "success": true
    }
}
```

<a name="getClients"></a>
## *getClients*

Gets a list of clients.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.clients | array | A list of clients |
| result.clients[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getClients"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "clients": [
            "org.rdk.Netflix"
        ],
        "success": true
    }
}
```

<a name="getCursorSize"></a>
## *getCursorSize*

Returns the currently set cursor size.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.width | number | The cursor width |
| result.height | number | The cursor height |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getCursorSize"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "width": 255,
        "height": 255,
        "success": true
    }
}
```

<a name="getHolePunch"></a>
## *getHolePunch*

Returns whether video hole punching is enabled or disabled for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.holePunch | boolean | Whether hole punching is enabled (`true`) or disabled (`false`) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getHolePunch",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "holePunch": true,
        "success": true
    }
}
```

<a name="getKeyRepeatsEnabled"></a>
## *getKeyRepeatsEnabled*

Returns whether key repeating is enabled or disabled.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.keyRepeat | boolean | `true` if enabled, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getKeyRepeatsEnabled"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "keyRepeat": true,
        "success": true
    }
}
```

<a name="getLastWakeupKey"></a>
## *getLastWakeupKey*

Returns the last key press prior to a device wakeup.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| result.modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| result.modifiers[#] | string |  |
| result.timestampInSeconds | boolean | The time, in seconds, of the last wakeup |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getLastWakeupKey"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "keyCode": 10,
        "modifiers": [
            "shift"
        ],
        "timestampInSeconds": true,
        "success": true
    }
}
```

<a name="getLogLevel"></a>
## *getLogLevel*

Returns the currently set logging level.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.logLevel | string | The log level (must be one of the following: *DEBUG*, *INFO*, *WARN*, *ERROR*, *FATAL*) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getLogLevel"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "logLevel": "INFO",
        "success": true
    }
}
```

<a name="getLogsFlushingEnabled"></a>
## *getLogsFlushingEnabled*

Returns whether log flushing is enabled or disabled.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enabled | boolean | `true` if enabled, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getLogsFlushingEnabled"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enabled": true,
        "success": true
    }
}
```

<a name="getOpacity"></a>
## *getOpacity*

Gets the opacity of the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.opacity | integer | The opacity level (between 0 and 100) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getOpacity",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "opacity": 100,
        "success": true
    }
}
```

<a name="getScale"></a>
## *getScale*

Returns the scale of an application.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.sx | string | The x scale factor |
| result.sy | string | The y scale factor |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getScale",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "sx": "0.5",
        "sy": "0.5",
        "success": true
    }
}
```

<a name="getScreenResolution"></a>
## *getScreenResolution*

Gets the screen resolution.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.w | number | The width |
| result.h | number | The height |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getScreenResolution"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "w": 1920,
        "h": 1080,
        "success": true
    }
}
```

<a name="getScreenshot"></a>
## *getScreenshot*

Captures a screenshot.

### Events

| Event | Description |
| :-------- | :-------- |
| [onScreenshotComplete](#onScreenshotComplete) | Triggers when a screenshot is captured successfully |
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
    "method": "org.rdk.RDKShell.getScreenshot"
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

<a name="getState"></a>
## *getState*

Returns the state of all applications.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.runtimes | array | A list of apps and their current state |
| result.runtimes[#] | object |  |
| result.runtimes[#].callsign | string | The application callsign |
| result.runtimes[#].state | string | The runtime state of the app |
| result.runtimes[#].uri | string | The URI of the app (empty, if unable to get URI status) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getState"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "runtimes": [
            {
                "callsign": "Cobalt",
                "state": "suspended",
                "uri": "https://..."
            }
        ],
        "success": true
    }
}
```

<a name="getSystemMemory"></a>
## *getSystemMemory*

Gets the information of System Memory.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.freeRam | number | Free RAM memory (kB) |
| result.swapRam | number | Swap memory (kB) |
| result.totalRam | number | Total RAM memory (kB) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getSystemMemory"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "freeRam": 321944,
        "swapRam": 0,
        "totalRam": 624644,
        "success": true
    }
}
```

<a name="getSystemResourceInfo"></a>
## *getSystemResourceInfo*

Returns system resource information about each application.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.types | array | A list of apps and their system resource information |
| result.types[#] | object |  |
| result.types[#].callsign | string | The application callsign |
| result.types[#].ram | integer | The amount of memory the runtime is consuming in kb |
| result.types[#].vram | integer | The amount of graphics memory the runtime is consuming in kb (if supported) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getSystemResourceInfo"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "types": [
            {
                "callsign": "Cobalt",
                "ram": 123,
                "vram": 50
            }
        ],
        "success": true
    }
}
```

<a name="getVirtualDisplayEnabled"></a>
## *getVirtualDisplayEnabled*

Returns whether virtual display is enabled or disabled for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.enabled | boolean | `true` if a virtual display is enabled, otherwise `false` |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getVirtualDisplayEnabled",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "enabled": true,
        "success": true
    }
}
```

<a name="getVirtualResolution"></a>
## *getVirtualResolution*

Returns the virtual display resolution for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.w | number | The width |
| result.h | number | The height |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getVirtualResolution",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "w": 1920,
        "h": 1080,
        "success": true
    }
}
```

<a name="getVisibility"></a>
## *getVisibility*

Gets the visibility of the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.visible | boolean | Whether the client is visible (`true`) or not (`false`) |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getVisibility",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "visible": true,
        "success": true
    }
}
```

<a name="getZOrder"></a>
## *getZOrder*

Returns an array of clients in Z order, starting with the top most application client first.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.clients | array | A list of clients |
| result.clients[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getZOrder"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "clients": [
            "org.rdk.Netflix"
        ],
        "success": true
    }
}
```

<a name="getGraphicsFrameRate"></a>
## *getGraphicsFrameRate*

Returns the current Graphics Frame Rate.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.frameRate | number | display the current Graphics framerate |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getGraphicsFrameRate"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "frameRate": 40,
        "success": true
    }
}
```

<a name="hideAllClients"></a>
## *hideAllClients*

Hides/Unhides all the clients.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.hide | boolean | true to hide all the clients, and false to unhide all the clients |

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
    "method": "org.rdk.RDKShell.hideAllClients",
    "params": {
        "hide": true
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

<a name="hideCursor"></a>
## *hideCursor*

Hides the cursor from showing on the display. The cursor is hidden by default.

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
    "method": "org.rdk.RDKShell.hideCursor"
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

<a name="hideFullScreenImage"></a>
## *hideFullScreenImage*

Hides the Full Screen Image.

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
    "method": "org.rdk.RDKShell.hideFullScreenImage"
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

<a name="hideSplashLogo"></a>
## *hideSplashLogo*

Removes the splash screen.

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
    "method": "org.rdk.RDKShell.hideSplashLogo"
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

<a name="ignoreKeyInputs"></a>
## *ignoreKeyInputs*

Blocks user key inputs.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ignore | boolean | Whether key inputs are ignored |

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
    "method": "org.rdk.RDKShell.ignoreKeyInputs",
    "params": {
        "ignore": false
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

<a name="injectKey"></a>
## *injectKey*

Injects the keys.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.keycode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.modifiers[#] | string |  |

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
    "method": "org.rdk.RDKShell.injectKey",
    "params": {
        "keycode": 10,
        "modifiers": [
            "shift"
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
        "success": true
    }
}
```

<a name="kill"></a>
## *kill*

Kills the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.kill",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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

<a name="launch"></a>
## *launch*

Launches an application.

### Events

| Event | Description |
| :-------- | :-------- |
| [onLaunched](#onLaunched) | Triggers when the runtime of an application is launched successfull |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.callsign | string | The application callsign |
| params.type | string | The ID of the runtime package or the callsign of the plugin desired to be cloned |
| params?.version | string | <sup>*(optional)*</sup> The version of the package. Defaults to the latest version |
| params.uri | string | The URI of the app (empty, if unable to get URI status) |
| params?.x | number | <sup>*(optional)*</sup> The x location |
| params?.y | number | <sup>*(optional)*</sup> The y location |
| params?.w | number | <sup>*(optional)*</sup> The width |
| params?.h | number | <sup>*(optional)*</sup> The height |
| params?.suspend | boolean | <sup>*(optional)*</sup> Whether to suspend the app on launch (`true`) or not (`false`). Default is `false` |
| params?.visible | boolean | <sup>*(optional)*</sup> Whether the app is visible on launch (`true`) or not (`false`). Default is `true`. The value will be `false` if the `suspend` argument is `true` |
| params?.focused | boolean | <sup>*(optional)*</sup> Whether the app is focused on launch (`true`) or not (`false`). Default is `true`. The app cannot be focused if the `visible` argument is set to `false` |
| params?.configuration | string | <sup>*(optional)*</sup> The plugin configuration overrides. Empty by default |
| params?.behind | string | <sup>*(optional)*</sup> The client to put behind. Defaults to top of z-order |
| params?.displayName | string | <sup>*(optional)*</sup> A name for the display |
| params?.scaleToFit | boolean | <sup>*(optional)*</sup> Whether the app can be scaled to fit the current bounds. Default is `false` |
| params?.holePunch | boolean | <sup>*(optional)*</sup> Whether the video hole punching can be enabled for the client. Default is `true` |
| params?.topmost | boolean | <sup>*(optional)*</sup> Whether the app appears above all other apps on the display. Default is `false` |
| params?.focus | boolean | <sup>*(optional)*</sup> Whether the app should be under focus. Default is `false` |
| params?.autodestroy | boolean | <sup>*(optional)*</sup> Whether the application can be automatically destroyed. Default is `true` |

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.launchType | string | The launch type of client |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.launch",
    "params": {
        "callsign": "Cobalt",
        "type": "HtmlApp",
        "version": "1.0",
        "uri": "https://...",
        "x": 0,
        "y": 0,
        "w": 1920,
        "h": 1080,
        "suspend": false,
        "visible": true,
        "focused": true,
        "configuration": "...",
        "behind": "...",
        "displayName": "test",
        "scaleToFit": false,
        "holePunch": false,
        "topmost": false,
        "focus": false,
        "autodestroy": false
    }
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "launchType": "activate",
        "success": true
    }
}
```

<a name="launchApplication"></a>
## *launchApplication*

Launches an application.

### Events

| Event | Description |
| :-------- | :-------- |
| [onApplicationLaunched](#onApplicationLaunched) | Triggers when an application is launched successfully |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params.uri | string | The client uri |
| params.mimeType | string | The mime type |
| params?.topmost | boolean | <sup>*(optional)*</sup> true to put the application at the top, otherwise false |
| params?.focus | boolean | <sup>*(optional)*</sup> true to put the application above all other applications, otherwise false |

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
    "method": "org.rdk.RDKShell.launchApplication",
    "params": {
        "client": "HtmlApp",
        "uri": "https://x1box-app.xumo.com/3.0.70/index.html%22",
        "mimeType": "application/native",
        "topmost": true,
        "focus": true
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

<a name="launchResidentApp"></a>
## *launchResidentApp*

Launches the Resident application.

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
    "method": "org.rdk.RDKShell.launchResidentApp"
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

<a name="moveBehind"></a>
## *moveBehind*

Moves the specified client behind the specified target client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params.target | string | The target in which the client moves behind |

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
    "method": "org.rdk.RDKShell.moveBehind",
    "params": {
        "client": "org.rdk.Netflix",
        "target": "org.rdk.RDKBrowser2"
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

<a name="moveToBack"></a>
## *moveToBack*

Moves the specified client to the back or bottom of the Z order.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.moveToBack",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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

<a name="moveToFront"></a>
## *moveToFront*

Moves the specified client to the front or top of the Z order.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.moveToFront",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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

<a name="removeAllKeyIntercepts"></a>
## *removeAllKeyIntercepts*

Removes all key intercepts.

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
    "method": "org.rdk.RDKShell.removeAllKeyIntercepts"
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

<a name="removeAllKeyListeners"></a>
## *removeAllKeyListeners*

Removes all key listeners.

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
    "method": "org.rdk.RDKShell.removeAllKeyListeners"
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

<a name="removeAnimation"></a>
## *removeAnimation*

Removes the current animation for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.removeAnimation",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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

<a name="removeKeyIntercept"></a>
## *removeKeyIntercept*

Removes a key intercept.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.modifiers[#] | string |  |
| params.client | string | The client name |

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
    "method": "org.rdk.RDKShell.removeKeyIntercept",
    "params": {
        "keyCode": 10,
        "modifiers": [
            "shift"
        ],
        "client": "org.rdk.Netflix"
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

<a name="removeKeyListener"></a>
## *removeKeyListener*

Removes a key listener for an application.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.keys | array | A list of keys for which to remove a listener for the specified application (only symbol * (string data type) is acceptable) |
| params.keys[#] | object |  |
| params.keys[#].keyCode | number | The key code of the key to intercept (only symbol * (string data type) is acceptable) |
| params.keys[#].modifiers | array | A list of modifiers that need to be present to intercept (`ctrl`, `alt`, and `shift` are supported) |
| params.keys[#].modifiers[#] | string |  |

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
    "method": "org.rdk.RDKShell.removeKeyListener",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "keys": [
            {
                "keyCode": 10,
                "modifiers": [
                    "shift"
                ]
            }
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
        "success": true
    }
}
```

<a name="removeKeyMetadataListener"></a>
## *removeKeyMetadataListener*

Removes the key metadata listeners.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.removeKeyMetadataListener",
    "params": {
        "client": "searchanddiscovery",
        "callsign": "searchanddiscovery"
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

<a name="resetInactivityTime"></a>
## *resetInactivityTime*

Resets the inactivity notification interval.

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
    "method": "org.rdk.RDKShell.resetInactivityTime"
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

<a name="resumeApplication"></a>
## *resumeApplication*

Resumes an application.

### Events

| Event | Description |
| :-------- | :-------- |
| [onApplicationResumed](#onApplicationResumed) | Triggers when an application resumes from a suspended state |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

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
    "method": "org.rdk.RDKShell.resumeApplication",
    "params": {
        "client": "HtmlApp"
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

<a name="scaleToFit"></a>
## *scaleToFit*

Scales the specified client to fit the current bounds.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.x | number | The x location |
| params.y | number | The y location |
| params.w | number | The width |
| params.h | number | The height |

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
    "method": "org.rdk.RDKShell.scaleToFit",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "x": 0,
        "y": 0,
        "w": 1920,
        "h": 1080
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

<a name="setBounds"></a>
## *setBounds*

Sets the bounds of the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.x | number | The x location |
| params.y | number | The y location |
| params.w | number | The width |
| params.h | number | The height |

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
    "method": "org.rdk.RDKShell.setBounds",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "x": 0,
        "y": 0,
        "w": 1920,
        "h": 1080
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

<a name="setCursorSize"></a>
## *setCursorSize*

Sets the cursor size.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.width | number | The cursor width |
| params.height | number | The cursor height |

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
    "method": "org.rdk.RDKShell.setCursorSize",
    "params": {
        "width": 255,
        "height": 255
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

<a name="setFocus"></a>
## *setFocus*

Sets focus to the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |

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
    "method": "org.rdk.RDKShell.setFocus",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix"
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

<a name="setHolePunch"></a>
## *setHolePunch*

Enables or disables video hole punching for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.holePunch | boolean | Whether hole punching is enabled (`true`) or disabled (`false`) |

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
    "method": "org.rdk.RDKShell.setHolePunch",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "holePunch": true
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

<a name="setInactivityInterval"></a>
## *setInactivityInterval*

Sets the inactivity notification interval.

### Events

| Event | Description |
| :-------- | :-------- |
| [onUserInactivity](#onUserInactivity) | Triggers only if the device is inactive for the specified time interval |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.interval | integer | The inactivity event interval in minutes |

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
    "method": "org.rdk.RDKShell.setInactivityInterval",
    "params": {
        "interval": 15
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

<a name="setLogLevel"></a>
## *setLogLevel*

Sets the logging level.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.logLevel | string | The log level (must be one of the following: *DEBUG*, *INFO*, *WARN*, *ERROR*, *FATAL*) |

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
    "method": "org.rdk.RDKShell.setLogLevel",
    "params": {
        "logLevel": "INFO"
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

<a name="setMemoryMonitor"></a>
## *setMemoryMonitor*

Enables or disables RAM memory monitoring on the device. Upon enabling, triggers possible events are onDeviceLowRamWarning, onDeviceCriticallyLowRamWarning, onDeviceLowRamWarningCleared, and onDeviceCriticallyLowRamWarningCleared.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | boolean | `true` to enable memory monitoring or `false` to disable memory monitoring |
| params.interval | number | The duration, in seconds, between memory checks |
| params.lowRam | number | The threshold, in Megabytes, after which a `onDeviceLowRamWarning` event is generated |
| params.criticallyLowRam | number | The threshold, in Megabytes, after which a critically `onDeviceCriticallyLowRamWarning` event is generated |

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
    "method": "org.rdk.RDKShell.setMemoryMonitor",
    "params": {
        "enable": true,
        "interval": 300,
        "lowRam": 128,
        "criticallyLowRam": 64
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

<a name="setOpacity"></a>
## *setOpacity*

Sets the opacity of the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params.opacity | integer | The opacity level (between 0 and 100) |

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
    "method": "org.rdk.RDKShell.setOpacity",
    "params": {
        "client": "org.rdk.Netflix",
        "opacity": 100
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

<a name="setScale"></a>
## *setScale*

Scales an application.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.sx | number | The x scale factor |
| params.sy | number | The y scale factor |

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
    "method": "org.rdk.RDKShell.setScale",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "sx": 0.5,
        "sy": 0.5
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

<a name="setScreenResolution"></a>
## *setScreenResolution*

Sets the screen resolution.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.w | number | The width |
| params.h | number | The height |

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
    "method": "org.rdk.RDKShell.setScreenResolution",
    "params": {
        "w": 1920,
        "h": 1080
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

<a name="setTopmost"></a>
## *setTopmost*

Sets whether the specified client appears above all other clients on the display.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params.topmost | boolean | `true` to set the client as the top most client |
| params?.focus | boolean | <sup>*(optional)*</sup> `true' to set focus for the client |

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
    "method": "org.rdk.RDKShell.setTopmost",
    "params": {
        "client": "org.rdk.Netflix",
        "topmost": true,
        "focus": true
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

<a name="setVirtualResolution"></a>
## *setVirtualResolution*

Sets the virtual resolution for the specified client.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.width | number | <sup>*(optional)*</sup> The width of the virtual resolution |
| params?.height | number | <sup>*(optional)*</sup> The height of the virtual resolution |

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
    "method": "org.rdk.RDKShell.setVirtualResolution",
    "params": {
        "client": "org.rdk.Netflix",
        "width": 1920,
        "height": 1080
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

<a name="setVisibility"></a>
## *setVisibility*

Sets whether the specified client should be visible.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params?.callsign | string | <sup>*(optional)*</sup> The application callsign |
| params.visible | boolean | Whether the client is visible (`true`) or not (`false`) |

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
    "method": "org.rdk.RDKShell.setVisibility",
    "params": {
        "client": "org.rdk.Netflix",
        "callsign": "org.rdk.Netflix",
        "visible": true
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

<a name="setGraphicsFrameRate"></a>
## *setGraphicsFrameRate*

Set Graphics Frame Rate.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.framerate | number | Graphics Framerate to be set |

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
    "method": "org.rdk.RDKShell.setGraphicsFrameRate",
    "params": {
        "framerate": 60
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

<a name="showCursor"></a>
## *showCursor*

Shows the cursor on the display using the current cursor size. See `setCursorSize`. The cursor automatically disappears after 5 seconds of inactivity.

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
    "method": "org.rdk.RDKShell.showCursor"
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

<a name="showFullScreenImage"></a>
## *showFullScreenImage*

Shows the Full Screen Image.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.path | string | The image path |

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
    "method": "org.rdk.RDKShell.showFullScreenImage",
    "params": {
        "path": "/tmp/netflix.png"
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

<a name="showSplashLogo"></a>
## *showSplashLogo*

Displays the splash screen.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.displayTime | number | The amount of the time to show the splash screen |

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
    "method": "org.rdk.RDKShell.showSplashLogo",
    "params": {
        "displayTime": 5
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

<a name="showWatermark"></a>
## *showWatermark*

Sets whether a watermark shows on the display.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.show | boolean | `true` to show the watermark or `false` to hide the watermark |

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
    "method": "org.rdk.RDKShell.showWatermark",
    "params": {
        "show": true
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

<a name="suspend"></a>
## *suspend*

Suspends an application.

### Events

| Event | Description |
| :-------- | :-------- |
| [onSuspended](#onSuspended) | Triggers when the runtime of an application is suspended |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.callsign | string | The application callsign |

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
    "method": "org.rdk.RDKShell.suspend",
    "params": {
        "callsign": "Cobalt"
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

<a name="suspendApplication"></a>
## *suspendApplication*

Suspends an application.

### Events

| Event | Description |
| :-------- | :-------- |
| [onApplicationSuspended](#onApplicationSuspended) | Triggers when an application is suspended |
### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

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
    "method": "org.rdk.RDKShell.suspendApplication",
    "params": {
        "client": "HtmlApp"
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

<a name="keyRepeatConfig"></a>
## *keyRepeatConfig*

Customizes key repeats.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params?.input | string | <sup>*(optional)*</sup> input type, can be 'default' or 'keyboard'. If 'input' prop not specified 'default'('keyboard') is assumed |
| params.enabled | boolean | `true` to enable key repeats, false to disable key repeats |
| params.initialDelay | number | number of miliseconds until first key repeat event will be sent |
| params.repeatInterval | number | number of miliseconds until following key repeat events will be sent |

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
    "method": "org.rdk.RDKShell.keyRepeatConfig",
    "params": {
        "input": "default",
        "enabled": true,
        "initialDelay": 500,
        "repeatInterval": 250
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

<a name="setAVBlocked"></a>
## *setAVBlocked*

adds/removes the list of applications with the given callsigns to/from the blacklist.

### Events

No Events

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.callsign | string | The application callsign |
| params.blocked | boolean | Whether to block (`true`) or unblock (`false`) AV for the callsign |

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
    "method": "org.rdk.RDKShell.setAVBlocked",
    "params": {
        "callsign": "searchanddiscovery",
        "blocked": true
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

<a name="getBlockedAVApplications"></a>
## *getBlockedAVApplications*

Gets a list of blacklisted clients.

### Events

No Events

### Parameters

This method takes no parameters.

### Result

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.clients | array | A list of clients |
| result.clients[#] | string |  |
| result.success | boolean | Whether the request succeeded |

### Example

#### Request

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "method": "org.rdk.RDKShell.getBlockedAVApplications"
}
```

#### Response

```json
{
    "jsonrpc": "2.0",
    "id": 42,
    "result": {
        "clients": [
            "org.rdk.Netflix"
        ],
        "success": true
    }
}
```

<a name="Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#Thunder)] for information on how to register for a notification.

The following events are provided by the org.rdk.RDKShell plugin:

RDKShell interface events:

| Event | Description |
| :-------- | :-------- |
| [onApplicationActivated](#onApplicationActivated) | Triggered when an application is activated |
| [onApplicationConnected](#onApplicationConnected) | Triggered when a connection to an application succeeds |
| [onApplicationDisconnected](#onApplicationDisconnected) | Triggered when an attempt to disconnect from an application succeeds |
| [onApplicationFirstFrame](#onApplicationFirstFrame) | Triggered when the first frame of an application is loaded |
| [onApplicationLaunched](#onApplicationLaunched) | Triggered when an application launches successfully |
| [onApplicationResumed](#onApplicationResumed) | Triggered when an application resumes from a suspended state |
| [onApplicationSuspended](#onApplicationSuspended) | Triggered when an application is suspended |
| [onApplicationTerminated](#onApplicationTerminated) | Triggered when an application terminates |
| [onDestroyed](#onDestroyed) | Triggered when a runtime is destroyed |
| [onDeviceCriticallyLowRamWarning](#onDeviceCriticallyLowRamWarning) | Triggered when the RAM memory on the device exceeds the configured `criticallyLowRam` threshold value |
| [onDeviceCriticallyLowRamWarningCleared](#onDeviceCriticallyLowRamWarningCleared) | Triggered when the RAM memory on the device no longer exceeds the configured `criticallyLowRam` threshold value |
| [onDeviceLowRamWarning](#onDeviceLowRamWarning) | Triggered when the RAM memory on the device exceeds the configured `lowRam` threshold value |
| [onDeviceLowRamWarningCleared](#onDeviceLowRamWarningCleared) | Triggered when the RAM memory on the device no longer exceeds the configured `lowRam` threshold value |
| [onLaunched](#onLaunched) | Triggered when a runtime is launched |
| [onSuspended](#onSuspended) | Triggered when a runtime is suspended |
| [onUserInactivity](#onUserInactivity) | Triggered when a device has been inactive for a period of time |
| [onWillDestroy](#onWillDestroy) | Triggered when an application is set to be destroyed |
| [onPluginSuspended](#onPluginSuspended) | Triggered when a plugin is suspended |
| [onScreenshotComplete](#onScreenshotComplete) | Triggered when a screenshot is captured successfully using `getScreenshot` method |
| [onBlur](#onBlur) | Triggered when the focused client is blurred |
| [onFocus](#onFocus) | Triggered when a client is set to focus |


<a name="onApplicationActivated"></a>
## *onApplicationActivated*


The *onApplicationActivated* event is triggered when an application becomes active or is brought to the foreground. This event is particularly useful for scenarios where you need to perform specific actions or updates when the application gains focus, such as refreshing data, resuming paused processes, or updating the user interface to reflect the current state. It ensures that the application is ready to interact with the user and provides a seamless experience by handling tasks that are relevant only when the application is actively being used. This event is essential for maintaining application responsiveness and ensuring that the user receives the most up-to-date information or functionality when they return to the app.

### Related Functions  
[addAnimation](#addAnimation) : This function can trigger *onApplicationActivated* when animations are added to the application, ensuring they are properly initialized or resumed when the app becomes active.  

[addKeyIntercept](#addKeyIntercept) : This function may invoke *onApplicationActivated* when key intercepts are set up, allowing the application to handle specific key inputs upon activation.  

[addKeyIntercepts](#addKeyIntercepts) : Similar to *addKeyIntercept*, this function can trigger *onApplicationActivated* when multiple key intercepts are configured, ensuring the app is ready to process these inputs when active.  

[addKeyListener](#addKeyListener) : This function can trigger *onApplicationActivated* by setting up key listeners that become active when the application is brought to the foreground.  

[addKeyMetadataListener](#addKeyMetadataListener) : This function may invoke *onApplicationActivated* when metadata listeners for keys are added, ensuring the app processes relevant metadata upon activation.  

[createDisplay](#createDisplay) : This function can trigger *onApplicationActivated* when a new display is created, ensuring the display is properly initialized and ready for interaction when the app becomes active.  

[destroy](#destroy) : While primarily used for cleanup, this function can indirectly trigger *onApplicationActivated* when the application transitions between states, ensuring proper handling of resources.  

[enableInactivityReporting](#enableInactivityReporting) : This function may invoke *onApplicationActivated* to resume inactivity reporting when the application becomes active, ensuring accurate tracking of user engagement.  

[enableKeyRepeats](#enableKeyRepeats) : This function can trigger *onApplicationActivated* by enabling key repeat functionality, ensuring the app handles repeated key inputs correctly upon activation.  

[enableLogsFlushing](#enableLogsFlushing) : This function may invoke *onApplicationActivated* to resume log flushing processes, ensuring that logs are updated and maintained when the app is active.  

[enableVirtualDisplay](#enableVirtualDisplay) : This function can trigger *onApplicationActivated* when virtual displays are enabled, ensuring they are properly initialized and ready for use upon activation.  

[generateKey](#generateKey) : This function may invoke *onApplicationActivated* when keys are generated, ensuring the application processes these keys correctly when it becomes active.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationActivated",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationConnected"></a>
## *onApplicationConnected*


The `onApplicationConnected` event is triggered when the application successfully establishes a connection with the underlying system or platform. This event signifies that the application is now ready to interact with the system's features and services. For users, this means that the application has completed its initialization process and is fully operational. This event is particularly useful in scenarios where the application needs to notify users or perform specific actions upon successfully connecting to the system, such as updating the user interface, enabling certain features, or starting background processes.

### Related Functions  
[createDisplay](#createDisplay) : The `createDisplay` function is responsible for initializing and setting up a display for the application. This function triggers the `onApplicationConnected` event once the display is successfully created, signaling that the application is ready to interact with the display and other system components.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationConnected",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationDisconnected"></a>
## *onApplicationDisconnected*


The `onApplicationDisconnected` event is triggered when an application loses its connection to the system or platform it is interacting with. This event is particularly useful for monitoring the application's lifecycle and ensuring that appropriate actions are taken when the connection is disrupted. For example, it can be used to clean up resources, notify users, or attempt reconnection. This event is essential for maintaining a seamless user experience and ensuring that the application handles disconnections gracefully.

### Related Functions  
[destroy](#destroy) : The `destroy` function is responsible for terminating or cleaning up resources associated with an application or display. When this function is called, it can trigger the `onApplicationDisconnected` event to indicate that the application has been disconnected as part of the destruction process.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationDisconnected",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationFirstFrame"></a>
## *onApplicationFirstFrame*

Triggered when the first frame of an application is loaded.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationFirstFrame",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationLaunched"></a>
## *onApplicationLaunched*

Triggered when an application launches successfully.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationLaunched",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationResumed"></a>
## *onApplicationResumed*

Triggered when an application resumes from a suspended state.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationResumed",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationSuspended"></a>
## *onApplicationSuspended*

Triggered when an application is suspended.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationSuspended",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onApplicationTerminated"></a>
## *onApplicationTerminated*

Triggered when an application terminates.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onApplicationTerminated",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onDestroyed"></a>
## *onDestroyed*

Triggered when a runtime is destroyed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDestroyed",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onDeviceCriticallyLowRamWarning"></a>
## *onDeviceCriticallyLowRamWarning*

Triggered when the RAM memory on the device exceeds the configured `criticallyLowRam` threshold value. See `setMemoryMonitor`.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ram | integer | The amount of free memory remaining in Kilobytes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceCriticallyLowRamWarning",
    "params": {
        "ram": 65536
    }
}
```

<a name="onDeviceCriticallyLowRamWarningCleared"></a>
## *onDeviceCriticallyLowRamWarningCleared*

Triggered when the RAM memory on the device no longer exceeds the configured `criticallyLowRam` threshold value. See `setMemoryMonitor`.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ram | integer | The amount of free memory remaining in Kilobytes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceCriticallyLowRamWarningCleared",
    "params": {
        "ram": 65536
    }
}
```

<a name="onDeviceLowRamWarning"></a>
## *onDeviceLowRamWarning*

Triggered when the RAM memory on the device exceeds the configured `lowRam` threshold value. See `setMemoryMonitor`.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ram | integer | The amount of free memory remaining in Kilobytes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceLowRamWarning",
    "params": {
        "ram": 65536
    }
}
```

<a name="onDeviceLowRamWarningCleared"></a>
## *onDeviceLowRamWarningCleared*

Triggered when the RAM memory on the device no longer exceeds the configured `lowRam` threshold value. See `setMemoryMonitor`.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.ram | integer | The amount of free memory remaining in Kilobytes |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onDeviceLowRamWarningCleared",
    "params": {
        "ram": 65536
    }
}
```

<a name="onLaunched"></a>
## *onLaunched*

Triggered when a runtime is launched.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |
| params.launchType | string | The launch type of an application (must be one of the following: *create*, *active*, *suspend*, *resume*) |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onLaunched",
    "params": {
        "client": "org.rdk.Netflix",
        "launchType": "create"
    }
}
```

<a name="onSuspended"></a>
## *onSuspended*

Triggered when a runtime is suspended.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onSuspended",
    "params": {
        "client": "org.rdk.Netflix"
    }
}
```

<a name="onUserInactivity"></a>
## *onUserInactivity*

Triggered when a device has been inactive for a period of time. This event is broadcasted at the frequency specified by `setInactivityInterval` if the device is not active. The default frequency is 15 minutes.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.minutes | number | The number of minutes that the device has been inactive |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onUserInactivity",
    "params": {
        "minutes": 5
    }
}
```

<a name="onWillDestroy"></a>
## *onWillDestroy*

Triggered when an application is set to be destroyed.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.callsign | string | The application callsign |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onWillDestroy",
    "params": {
        "callsign": "Cobalt"
    }
}
```

<a name="onPluginSuspended"></a>
## *onPluginSuspended*

Triggered when a plugin is suspended.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onPluginSuspended",
    "params": {
        "client": "searchanddiscovery"
    }
}
```

<a name="onScreenshotComplete"></a>
## *onScreenshotComplete*

Triggered when a screenshot is captured successfully using `getScreenshot` 

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.imageData | string | Base64 encoded image data |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onScreenshotComplete",
    "params": {
        "imageData": "AAAAAAAAAA"
    }
}
```

<a name="onBlur"></a>
## *onBlur*

Triggered when the focused client is blurred.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onBlur",
    "params": {
        "client": "searchanddiscovery"
    }
}
```

<a name="onFocus"></a>
## *onFocus*

Triggered when a client is set to focus.

### Parameters

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.client | string | The client name |

### Example

```json
{
    "jsonrpc": "2.0",
    "method": "client.events.onFocus",
    "params": {
        "client": "HtmlApp"
    }
}
```
