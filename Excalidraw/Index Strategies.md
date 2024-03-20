---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Hash Index ^Kqj5ClUJ

B-Tree ^qxQVgDjl

LSM Tree ^0kUbO3e7

1. O(1) reads and writes
    in memory ^wbvNF0sb

1. Keys need to fit in
   memory

2. No range queries ^B4g6OZhx

1. Fast range queries
2. Number of keys limited 
   by memory ^RS3k8GNP

1. Slow writes to b-tree 
   on disk ^q4Y5jgkQ

1. Number of keys not limited 
   by memory
2. Fast writes to memory compared
   to b-trees, slow compared
   to hash-tables.
3. Supports range queries, reads 
   are slow compared to b-trees
   on reads, since it checks
   all the SSTables on disk

 ^RN1xoOjM

1. Extra CPU Usage for 
   Compaction ^MCn7uzC1

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.24",
	"elements": [
		{
			"type": "rectangle",
			"version": 120,
			"versionNonce": 1756096045,
			"isDeleted": false,
			"id": "V65lMhzerK0u28sHG6A-y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -324.5625,
			"y": -254.41796875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 758.36328125,
			"height": 430.1171875,
			"seed": 1270078723,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 61,
			"versionNonce": 890150691,
			"isDeleted": false,
			"id": "2mYw2EZkfuwKlaXNrUKmS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -96.28515625,
			"y": -255.30078125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6484375,
			"height": 429.28515625,
			"seed": 1258040195,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6484375,
					429.28515625
				]
			]
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 1611176077,
			"isDeleted": false,
			"id": "_kleltdQvb-RYwZ2xNGik",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 137.796875,
			"y": -253.1875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.9140625,
			"height": 432.1953125,
			"seed": 981183053,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.9140625,
					432.1953125
				]
			]
		},
		{
			"type": "line",
			"version": 128,
			"versionNonce": 1960100547,
			"isDeleted": false,
			"id": "uZZnbs6TphftrW52J5cWr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -325.1015625,
			"y": -197.40234375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 754.6796875,
			"height": 6.61328125,
			"seed": 241588291,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					754.6796875,
					-6.61328125
				]
			]
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 31457005,
			"isDeleted": false,
			"id": "Kqj5ClUJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -271.03515625,
			"y": -237.515625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.171875,
			"height": 23,
			"seed": 1222721859,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 2,
			"text": "Hash Index",
			"rawText": "Hash Index",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hash Index",
			"lineHeight": 1.15,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 190149219,
			"isDeleted": false,
			"id": "qxQVgDjl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -35.49609375,
			"y": -238.44921875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.390625,
			"height": 23,
			"seed": 1321887491,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 2,
			"text": "B-Tree",
			"rawText": "B-Tree",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B-Tree",
			"lineHeight": 1.15,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 68,
			"versionNonce": 347838797,
			"isDeleted": false,
			"id": "0kUbO3e7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 191.7109375,
			"y": -239.87890625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.0703125,
			"height": 23,
			"seed": 1136493027,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 2,
			"text": "LSM Tree",
			"rawText": "LSM Tree",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LSM Tree",
			"lineHeight": 1.15,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 1499409923,
			"isDeleted": false,
			"id": "wbvNF0sb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -306.75390625,
			"y": -170.8828125,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 194.0625,
			"height": 33.12499999999994,
			"seed": 1328858691,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. O(1) reads and writes\n    in memory",
			"rawText": "1. O(1) reads and writes\n    in memory",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. O(1) reads and writes\n    in memory",
			"lineHeight": 1.2,
			"baseline": 30
		},
		{
			"type": "text",
			"version": 404,
			"versionNonce": 1375004589,
			"isDeleted": false,
			"id": "B4g6OZhx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -307.59375,
			"y": -98.16433189655174,
			"strokeColor": "#da0b0b",
			"backgroundColor": "transparent",
			"width": 177.890625,
			"height": 66.24999999999989,
			"seed": 696186957,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. Keys need to fit in\n   memory\n\n2. No range queries",
			"rawText": "1. Keys need to fit in\n   memory\n\n2. No range queries",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Keys need to fit in\n   memory\n\n2. No range queries",
			"lineHeight": 1.2,
			"baseline": 63
		},
		{
			"type": "text",
			"version": 412,
			"versionNonce": 569406883,
			"isDeleted": false,
			"id": "RS3k8GNP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -77.69921875,
			"y": -173.12109375,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 210.234375,
			"height": 49.687499999999915,
			"seed": 1454504547,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. Fast range queries\n2. Number of keys limited \n   by memory",
			"rawText": "1. Fast range queries\n2. Number of keys limited \n   by memory",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Fast range queries\n2. Number of keys limited \n   by memory",
			"lineHeight": 1.2,
			"baseline": 46
		},
		{
			"type": "text",
			"version": 467,
			"versionNonce": 196438541,
			"isDeleted": false,
			"id": "q4Y5jgkQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -82.9453125,
			"y": -99.66015624999994,
			"strokeColor": "#da0b0b",
			"backgroundColor": "transparent",
			"width": 202.1484375,
			"height": 33.12499999999994,
			"seed": 677680291,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. Slow writes to b-tree \n   on disk",
			"rawText": "1. Slow writes to b-tree \n   on disk",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Slow writes to b-tree \n   on disk",
			"lineHeight": 1.2,
			"baseline": 30
		},
		{
			"type": "text",
			"version": 746,
			"versionNonce": 1144506691,
			"isDeleted": false,
			"id": "RN1xoOjM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 167.421875,
			"y": -169.57031249999994,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 266.8359375,
			"height": 182.1874999999997,
			"seed": 1089424109,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. Number of keys not limited \n   by memory\n2. Fast writes to memory compared\n   to b-trees, slow compared\n   to hash-tables.\n3. Supports range queries, reads \n   are slow compared to b-trees\n   on reads, since it checks\n   all the SSTables on disk\n\n",
			"rawText": "1. Number of keys not limited \n   by memory\n2. Fast writes to memory compared\n   to b-trees, slow compared\n   to hash-tables.\n3. Supports range queries, reads \n   are slow compared to b-trees\n   on reads, since it checks\n   all the SSTables on disk\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Number of keys not limited \n   by memory\n2. Fast writes to memory compared\n   to b-trees, slow compared\n   to hash-tables.\n3. Supports range queries, reads \n   are slow compared to b-trees\n   on reads, since it checks\n   all the SSTables on disk\n\n",
			"lineHeight": 1.2,
			"baseline": 178
		},
		{
			"type": "text",
			"version": 560,
			"versionNonce": 318152813,
			"isDeleted": false,
			"id": "MCn7uzC1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 171.52967834911328,
			"y": 11.65072704792064,
			"strokeColor": "#da0b0b",
			"backgroundColor": "transparent",
			"width": 185.9765625,
			"height": 33.12499999999994,
			"seed": 186676579,
			"groupIds": [
				"y8c3rP--HI92LVZorNxDY"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710618376320,
			"link": null,
			"locked": false,
			"fontSize": 13.802083333333309,
			"fontFamily": 3,
			"text": "1. Extra CPU Usage for \n   Compaction",
			"rawText": "1. Extra CPU Usage for \n   Compaction",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Extra CPU Usage for \n   Compaction",
			"lineHeight": 1.2,
			"baseline": 30
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#da0b0b",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 3,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 505.97368910778334,
		"scrollY": 417.41467537921415,
		"zoom": {
			"value": 1.0499999999999998
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%