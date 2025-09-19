<!-- Generated automatically, DO NOT EDIT! -->
<a id="head.DisplayInfo_Plugin"></a>
# DisplayInfo Plugin

**Version: [1.0.0](https://github.com/rdkcentral/rdkservices/blob/main/DisplayInfo/CHANGELOG.md)**

A DisplayInfo plugin for Thunder framework.

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

The `DisplayInfo` plugin provides an interface for DisplayInfo.

The plugin is designed to be loaded and executed within the Thunder framework. For more information about the framework refer to [[Thunder](#ref.Thunder)].

<a id="head.Configuration"></a>
# Configuration

The table below lists configuration options of the plugin.

| Name | Type | Description |
| :-------- | :-------- | :-------- |
| callsign | string | Plugin instance name (default: org.rdk.DisplayInfo) |
| classname | string | Class name: *DisplayInfo* |
| locator | string | Library name: *libWPEFrameworkDisplayInfo.so* |
| autostart | boolean | Determines if the plugin shall be started automatically along with the framework |

<a id="head.Methods"></a>
# Methods

The following methods are provided by the DisplayInfo plugin:

DisplayInfo interface methods:

| Method | Description |
| :-------- | :-------- |
| [configure](#method.configure) |  |
| [colorSpace](#method.colorSpace) | Provides access to the display's Colour space (chroma subsampling format) |
| [colorimetry](#method.colorimetry) | Provides access to display's colorimetry |
| [colourDepth](#method.colourDepth) | Provides access to display's colour Depth |
| [connected](#method.connected) | Current HDMI connection status |
| [eDID](#method.eDID) | TV's Extended Display Identification Data |
| [eOTF](#method.eOTF) | Provides access to display's Electro optical transfer function |
| [frameRate](#method.frameRate) | Provides access to Frame Rate |
| [freeGpuRam](#method.freeGpuRam) | Free GPU DRAM memory (in bytes) |
| [hDCPProtection](#method.hDCPProtection) |  |
| [hDRSetting](#method.hDRSetting) | HDR format in use |
| [height](#method.height) | Vertical resolution of TV |
| [heightInCentimeters](#method.heightInCentimeters) | Vertical size in centimeters |
| [isAudioPassthrough](#method.isAudioPassthrough) | Current audio passthrough status on HDMI |
| [portName](#method.portName) | Video output port on the STB used for connection to TV |
| [quantizationRange](#method.quantizationRange) | Provides access to display's Qauntization Range |
| [sTBCapabilities](#method.sTBCapabilities) | HDR formats supported by STB |
| [tVCapabilities](#method.tVCapabilities) | HDR formats supported by TV |
| [totalGpuRam](#method.totalGpuRam) | Total GPU DRAM memory (in bytes) |
| [verticalFreq](#method.verticalFreq) | Vertical Frequency |
| [width](#method.width) | Horizontal resolution of TV |
| [widthInCentimeters](#method.widthInCentimeters) | Horizontal size in centimeters |

<a id="method.configure"></a>
## *configure [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.framework | PluginHost::IShell |  |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.DisplayInfo.configure",
    "params": {
        "framework": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.DisplayInfo.configure", "params": {"framework": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": null
}
```

<a id="method.colorSpace"></a>
## *colorSpace [<sup>method</sup>](#head.Methods)*

Provides access to the display's Colour space (chroma subsampling format)

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.cs | ColourSpaceType | colour space |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "method": "org.rdk.DisplayInfo.colorSpace"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 0, "method": "org.rdk.DisplayInfo.colorSpace"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 0,
    "result": {
        "cs": "FORMAT_UNKNOWN"
    }
}
```

<a id="method.colorimetry"></a>
## *colorimetry [<sup>method</sup>](#head.Methods)*

Provides access to display's colorimetry

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.colorimetry | IColorimetryIterator | display colorimetry |
| result.colorimetry[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "method": "org.rdk.DisplayInfo.colorimetry"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 1, "method": "org.rdk.DisplayInfo.colorimetry"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 1,
    "result": [
        "COLORIMETRY_UNKNOWN"
    ]
}
```

<a id="method.colourDepth"></a>
## *colourDepth [<sup>method</sup>](#head.Methods)*

Provides access to display's colour Depth

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.colour | ColourDepthType | colour depth |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "method": "org.rdk.DisplayInfo.colourDepth"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 2, "method": "org.rdk.DisplayInfo.colourDepth"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 2,
    "result": {
        "colour": "COLORDEPTH_UNKNOWN"
    }
}
```

<a id="method.connected"></a>
## *connected [<sup>method</sup>](#head.Methods)*

Current HDMI connection status

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.isconnected | bool | connected/disconnected |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "method": "org.rdk.DisplayInfo.connected"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 3, "method": "org.rdk.DisplayInfo.connected"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 3,
    "result": {
        "isconnected": true
    }
}
```

<a id="method.eDID"></a>
## *eDID [<sup>method</sup>](#head.Methods)*

TV's Extended Display Identification Data

### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.length | uint16_t |  |
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.length | uint16_t |  |
| result.data[] | uint8_t |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "method": "org.rdk.DisplayInfo.eDID",
    "params": {
        "length": ""
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 4, "method": "org.rdk.DisplayInfo.eDID", "params": {"length": ""}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 4,
    "result": {
        "length": "",
        "data[]": ""
    }
}
```

<a id="method.eOTF"></a>
## *eOTF [<sup>method</sup>](#head.Methods)*

Provides access to display's Electro optical transfer function

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.eotf | EotfType | display's EOTF |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "method": "org.rdk.DisplayInfo.eOTF"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 5, "method": "org.rdk.DisplayInfo.eOTF"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 5,
    "result": {
        "eotf": "EOTF_UNKNOWN"
    }
}
```

<a id="method.frameRate"></a>
## *frameRate [<sup>method</sup>](#head.Methods)*

Provides access to Frame Rate

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.rate | FrameRateType | frame rate |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "method": "org.rdk.DisplayInfo.frameRate"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 6, "method": "org.rdk.DisplayInfo.frameRate"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 6,
    "result": {
        "rate": "FRAMERATE_UNKNOWN"
    }
}
```

<a id="method.freeGpuRam"></a>
## *freeGpuRam [<sup>method</sup>](#head.Methods)*

Free GPU DRAM memory (in bytes)

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.free | uint64_t |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "method": "org.rdk.DisplayInfo.freeGpuRam"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 7, "method": "org.rdk.DisplayInfo.freeGpuRam"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 7,
    "result": {
        "free": 0
    }
}
```

<a id="method.hDCPProtection"></a>
## *hDCPProtection [<sup>method</sup>](#head.Methods)*



### Events
Event details are missing in the header file documentation 
### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.value | HDCPProtectionType | protocol |
### Results
This method returns no results.

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 8,
    "method": "org.rdk.DisplayInfo.hDCPProtection",
    "params": {
        "value": "HDCP_Unencrypted"
    }
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 8, "method": "org.rdk.DisplayInfo.hDCPProtection", "params": {"value": "HDCP_Unencrypted"}}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 8,
    "result": null
}
```

<a id="method.hDRSetting"></a>
## *hDRSetting [<sup>method</sup>](#head.Methods)*

HDR format in use

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.type | HDRType | HDR format |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 9,
    "method": "org.rdk.DisplayInfo.hDRSetting"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 9, "method": "org.rdk.DisplayInfo.hDRSetting"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 9,
    "result": {
        "type": "HDR_OFF"
    }
}
```

<a id="method.height"></a>
## *height [<sup>method</sup>](#head.Methods)*

Vertical resolution of TV

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.height | uint32_t | height of TV in pixels |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 10,
    "method": "org.rdk.DisplayInfo.height"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 10, "method": "org.rdk.DisplayInfo.height"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 10,
    "result": {
        "height": 0
    }
}
```

<a id="method.heightInCentimeters"></a>
## *heightInCentimeters [<sup>method</sup>](#head.Methods)*

Vertical size in centimeters

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.height | uint8_t |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 11,
    "method": "org.rdk.DisplayInfo.heightInCentimeters"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 11, "method": "org.rdk.DisplayInfo.heightInCentimeters"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 11,
    "result": {
        "height": ""
    }
}
```

<a id="method.isAudioPassthrough"></a>
## *isAudioPassthrough [<sup>method</sup>](#head.Methods)*

Current audio passthrough status on HDMI

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.passthru | bool | enabled/disabled |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 12,
    "method": "org.rdk.DisplayInfo.isAudioPassthrough"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 12, "method": "org.rdk.DisplayInfo.isAudioPassthrough"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 12,
    "result": {
        "passthru": true
    }
}
```

<a id="method.portName"></a>
## *portName [<sup>method</sup>](#head.Methods)*

Video output port on the STB used for connection to TV

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.name | string | video output port name |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 13,
    "method": "org.rdk.DisplayInfo.portName"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 13, "method": "org.rdk.DisplayInfo.portName"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 13,
    "result": {
        "name": ""
    }
}
```

<a id="method.quantizationRange"></a>
## *quantizationRange [<sup>method</sup>](#head.Methods)*

Provides access to display's Qauntization Range

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.qr | QuantizationRangeType | quantization range |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 14,
    "method": "org.rdk.DisplayInfo.quantizationRange"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 14, "method": "org.rdk.DisplayInfo.quantizationRange"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 14,
    "result": {
        "qr": "QUANTIZATIONRANGE_UNKNOWN"
    }
}
```

<a id="method.sTBCapabilities"></a>
## *sTBCapabilities [<sup>method</sup>](#head.Methods)*

HDR formats supported by STB

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.type | IHDRIterator |  |
| result.type[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 15,
    "method": "org.rdk.DisplayInfo.sTBCapabilities"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 15, "method": "org.rdk.DisplayInfo.sTBCapabilities"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 15,
    "result": [
        "HDR_OFF"
    ]
}
```

<a id="method.tVCapabilities"></a>
## *tVCapabilities [<sup>method</sup>](#head.Methods)*

HDR formats supported by TV

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.type | IHDRIterator |  |
| result.type[#] | string |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 16,
    "method": "org.rdk.DisplayInfo.tVCapabilities"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 16, "method": "org.rdk.DisplayInfo.tVCapabilities"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 16,
    "result": [
        "HDR_OFF"
    ]
}
```

<a id="method.totalGpuRam"></a>
## *totalGpuRam [<sup>method</sup>](#head.Methods)*

Total GPU DRAM memory (in bytes)

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.total | uint64_t |  |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 17,
    "method": "org.rdk.DisplayInfo.totalGpuRam"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 17, "method": "org.rdk.DisplayInfo.totalGpuRam"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 17,
    "result": {
        "total": 0
    }
}
```

<a id="method.verticalFreq"></a>
## *verticalFreq [<sup>method</sup>](#head.Methods)*

Vertical Frequency

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.vf | uint32_t | vertical freq |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 18,
    "method": "org.rdk.DisplayInfo.verticalFreq"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 18, "method": "org.rdk.DisplayInfo.verticalFreq"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 18,
    "result": {
        "vf": 0
    }
}
```

<a id="method.width"></a>
## *width [<sup>method</sup>](#head.Methods)*

Horizontal resolution of TV

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.width | uint32_t | width of TV in pixels |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 19,
    "method": "org.rdk.DisplayInfo.width"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 19, "method": "org.rdk.DisplayInfo.width"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 19,
    "result": {
        "width": 0
    }
}
```

<a id="method.widthInCentimeters"></a>
## *widthInCentimeters [<sup>method</sup>](#head.Methods)*

Horizontal size in centimeters

### Events
Event details are missing in the header file documentation 
### Parameters
This method takes no parameters.
### Results
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| result | object |  |
| result.width | uint8_t | width in cm |

### Examples


#### Request

```json
{
    "jsonrpc": 2.0,
    "id": 20,
    "method": "org.rdk.DisplayInfo.widthInCentimeters"
}
```


#### CURL Command

```curl
curl -H 'content-type:text/plain;' --data-binary '{"jsonrpc": 2.0, "id": 20, "method": "org.rdk.DisplayInfo.widthInCentimeters"}' http://127.0.0.1:9998/jsonrpc
```


#### Response

```json
{
    "jsonrpc": 2.0,
    "id": 20,
    "result": {
        "width": ""
    }
}
```



<a id="head.Notifications"></a>
# Notifications

Notifications are autonomous events, triggered by the internals of the implementation, and broadcasted via JSON-RPC to all registered observers. Refer to [[Thunder](#ref.Thunder)] for information on how to register for a notification.

The following events are provided by the DisplayInfo plugin:

DisplayInfo interface events:

| Event | Description |
| :-------- | :-------- |
| [updated](#event.updated) |  |

<a id="event.updated"></a>
## *updated [<sup>event</sup>](#head.Notifications)*



### Parameters
| Name | Type | Description |
| :-------- | :-------- | :-------- |
| params | object |  |
| params.event | Source |  |

### Examples

```json
{
    "jsonrpc": 2.0,
    "id": 21,
    "method": "org.rdk.DisplayInfo.updated",
    "params": {
        "event": "PRE_RESOLUTION_CHANGE"
    }
}
```
