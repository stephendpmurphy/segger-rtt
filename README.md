## Integrating the Segger RTT source as a submodule
The project can be integrated using CMake an a simple ```include_subdirectory``` statement which will compile a static library that can be linked against in your application.

## Example C API
To view examples of implementing the C API, check out the included ```Examples``` folder.

## Example Cortex-Debug / launch.json config
Add the following config to print ASCII messages over RTT
```json
"rttConfig":{
	"enabled":true,
	"address":"auto",
	"decoders":[
		{
			"port":0,
			"type":"terminal",
		},
	]
},
```

To print data in binary format (viewing raw hex and binary values) use the following config
```json
"rttConfig":{
	"enabled":true,
	"address":"auto",
	"decoders":[
		{
			"port":0,
			"type":"binary",
			"encoding": "unsigned",
			"scale":1
		},
	]
},
```

To plot a data point sent over RTT use the following config
```json
	"rttConfig":{
		"enabled":true,
		"address":"auto",
		"decoders":[
			{
				"port":0,
				"type":"graph",
				"encoding": "unsigned",
				"graphId":"1",
				"scale":1
			},
		]
	},
	"graphConfig": [
		{
			"label": "Graph 1",
			"timespan": 30,
			"type": "realtime",
			"annotate": false,
			"maximum": 10,
			"minimum": 0,
			"plots": [
				{
					"graphId": "1",
					"label": "data 1",
					"color": "#53753c"
				},
			]
		},
	]
```
