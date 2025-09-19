<!-- Generated automatically, DO NOT EDIT! -->
<a id="head.PlayerInfo_Plugin"></a>
# PlayerInfo Plugin

**Version: [1.0.0](https://github.com/rdkcentral/rdkservices/blob/main/PlayerInfo/CHANGELOG.md)**

A PlayerInfo plugin for Thunder framework.

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

The `PlayerInfo` plugin provides an interface for PlayerInfo.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].

<a id="head.Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: org.rdk.PlayerInfo) |
| classname | string | Class name: *PlayerInfo* |
| locator | string | Library name: *libWPEFrameworkPlayerInfo.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a id="head.Methods"></a>
# Methods

The following methods are provided by the PlayerInfo plugin:

PlayerInfo interface methods:

| Method | Description |
| :-------- | :-------- |
| [dolby_atmosmetadata](#method.dolby_atmosmetadata) | Atmos capabilities of Sink |
| [dolby_enableatmosoutput](#method.dolby_enableatmosoutput) | Enable Atmos Audio Output |
| [mode](#method.mode) |  |
| [dolby_soundmode](#method.dolby_soundmode) | Sound Mode - Mono/Stereo/Surround |
| [audioCodecs](#method.audioCodecs) |  |
| [isAudioEquivalenceEnabled](#method.isAudioEquivalenceEnabled) | Checks Loudness Equivalence in platform |
| [resolution](#method.resolution) | Current Video playback resolution |
| [videoCodecs](#method.videoCodecs) |  |

<a id="method.atmosMetadata"></a>
## *atmosMetadata [<sup>method</sup>](#head.Methods)*

Atmos capabilities of Sink

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.supported | bool |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.PlayerInfo.atmosMetadata"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.PlayerInfo.atmosMetadata"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": {
        "supported": true
    }
}
```

<a id="method.enableAtmosOutput"></a>
## *enableAtmosOutput [<sup>method</sup>](#head.Methods)*

Enable Atmos Audio Output

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.enable | bool | enable/disable |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "method": "org.rdk.PlayerInfo.enableAtmosOutput",
    "params": {
        "enable": true
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 1, "method": "org.rdk.PlayerInfo.enableAtmosOutput", "params": {"enable": true}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "result": null
}
```

<a id="method.mode"></a>
## *mode [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mode | Dolby::IOutput::Type | dolby mode type |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.PlayerInfo.mode"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.PlayerInfo.mode"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": {
        "mode": ""
    }
}
```

<a id="method.soundMode"></a>
## *soundMode [<sup>method</sup>](#head.Methods)*

Sound Mode - Mono/Stereo/Surround

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.mode | Dolby::IOutput::SoundModes |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.PlayerInfo.soundMode"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.PlayerInfo.soundMode"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": {
        "mode": ""
    }
}
```

<a id="method.audioCodecs"></a>
## *audioCodecs [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.codec | IAudioCodecIterator |  |
| result.codec[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.PlayerInfo.audioCodecs"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.PlayerInfo.audioCodecs"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": [
        "AUDIO_UNDEFINED"
    ]
}
```

<a id="method.isAudioEquivalenceEnabled"></a>
## *isAudioEquivalenceEnabled [<sup>method</sup>](#head.Methods)*

Checks Loudness Equivalence in platform

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.ae | bool | enabled/disabled |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "method": "org.rdk.PlayerInfo.isAudioEquivalenceEnabled"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 1, "method": "org.rdk.PlayerInfo.isAudioEquivalenceEnabled"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "result": {
        "ae": true
    }
}
```

<a id="method.resolution"></a>
## *resolution [<sup>method</sup>](#head.Methods)*

Current Video playback resolution

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.res | PlaybackResolution | resolution |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.PlayerInfo.resolution"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.PlayerInfo.resolution"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": {
        "res": "RESOLUTION_UNKNOWN"
    }
}
```

<a id="method.videoCodecs"></a>
## *videoCodecs [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.codec | IVideoCodecIterator |  |
| result.codec[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.PlayerInfo.videoCodecs"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.PlayerInfo.videoCodecs"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": [
        "VIDEO_UNDEFINED"
    ]
}
```



<a id="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the PlayerInfo plugin:

PlayerInfo interface events:

| Event | Description |
| :-------- | :-------- |
| [dolby_audiomodechanged](#event.dolby_audiomodechanged) |  |

<a id="event.audioModeChanged"></a>
## *audioModeChanged [<sup>event</sup>](#head.Notifications)*



### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.mode | Dolby::IOutput::SoundModes |  |
| params.enabled | bool |  |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "method": "org.rdk.PlayerInfo.audioModeChanged",
    "params": {
        "mode": "",
        "enabled": true
    }
}
```
