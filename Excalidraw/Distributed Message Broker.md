---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Client ^30ZWbrcW

LB ^Ae7KKIES

Auth Service ^j70imNH3

LB ^TAzQF4M7

Queue #1 ^RLJ51Oqw

Queue #2 ^hPyTXPFs

Queue #3 ^eJyn6cIe

Consumer ^kOQJzLQt

Long Poll ^eoWxnWe3

Consistent
Hashing ^wJGCMtks

In-memory or 
Log on disk ^xAWtjoTT

Zookeeper ^efjk2esY

Long polling used as it does
not hold onto connections 
while the consumer is processing
the request, before send ack ^3l5lyfgT

Amazon SQS, RabbitMQ - In-memory store (Faster
writes, but inpersistent)

Apache Kafka - Log based (durable, but slow
writes, provides retries)
 ^ohKrGL7S

API Design:
PublishMessage(userId, msg)
ConsumeMessage(ack?) ^BBnv5sJD

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.24",
	"elements": [
		{
			"id": "z9fup78LfwjnYoicqiHoR",
			"type": "rectangle",
			"x": -491.625,
			"y": -84.23828125,
			"width": 93.921875,
			"height": 63.33203125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 476094445,
			"version": 49,
			"versionNonce": 604218531,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "30ZWbrcW"
				},
				{
					"id": "azEgaBGk_t402oXuRjgIM",
					"type": "arrow"
				}
			],
			"updated": 1710622851038,
			"link": null,
			"locked": false
		},
		{
			"id": "30ZWbrcW",
			"type": "text",
			"x": -471.7140350341797,
			"y": -65.072265625,
			"width": 54.099945068359375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1222685165,
			"version": 7,
			"versionNonce": 1959406787,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622619305,
			"link": null,
			"locked": false,
			"text": "Client",
			"rawText": "Client",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "z9fup78LfwjnYoicqiHoR",
			"originalText": "Client",
			"lineHeight": 1.25
		},
		{
			"id": "UqvpbtkhHM3xY2cBdY66t",
			"type": "diamond",
			"x": -331.79296875,
			"y": -85.38671875,
			"width": 69.59375,
			"height": 62.46875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1988237315,
			"version": 102,
			"versionNonce": 2085015213,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "Ae7KKIES"
				},
				{
					"id": "7TTYjF0qbG9K7cSTZzpdP",
					"type": "arrow"
				}
			],
			"updated": 1710622852701,
			"link": null,
			"locked": false
		},
		{
			"id": "Ae7KKIES",
			"type": "text",
			"x": -307.50252532958984,
			"y": -64.26953125,
			"width": 21.215988159179688,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1880122883,
			"version": 60,
			"versionNonce": 1188340035,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622658795,
			"link": null,
			"locked": false,
			"text": "LB",
			"rawText": "LB",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "UqvpbtkhHM3xY2cBdY66t",
			"originalText": "LB",
			"lineHeight": 1.25
		},
		{
			"id": "VRGxdvQuZNkijnANgIuG8",
			"type": "rectangle",
			"x": -216.4296875,
			"y": -77.7734375,
			"width": 96.21484375,
			"height": 59.9765625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1098509901,
			"version": 89,
			"versionNonce": 20629357,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "j70imNH3"
				},
				{
					"id": "7TTYjF0qbG9K7cSTZzpdP",
					"type": "arrow"
				}
			],
			"updated": 1710622852701,
			"link": null,
			"locked": false
		},
		{
			"id": "j70imNH3",
			"type": "text",
			"x": -195.33025360107422,
			"y": -67.78515625,
			"width": 54.01597595214844,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1789006307,
			"version": 52,
			"versionNonce": 730106445,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622772655,
			"link": null,
			"locked": false,
			"text": "Auth\nService",
			"rawText": "Auth Service",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 34,
			"containerId": "VRGxdvQuZNkijnANgIuG8",
			"originalText": "Auth Service",
			"lineHeight": 1.25
		},
		{
			"id": "MxfiSxbUvTLEUyR2UCyWG",
			"type": "rectangle",
			"x": -223.80859375,
			"y": -80.88671875,
			"width": 98.0625,
			"height": 56.6796875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 282094563,
			"version": 106,
			"versionNonce": 368390979,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "V0MsxOGZzIuHOUOUKBBmI",
					"type": "arrow"
				}
			],
			"updated": 1710622854682,
			"link": null,
			"locked": false
		},
		{
			"type": "diamond",
			"version": 164,
			"versionNonce": 1203116813,
			"isDeleted": false,
			"id": "Px9J8GG3qFEywAhcdr7yM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -49.30859375,
			"y": -82.19921875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.59375,
			"height": 62.46875,
			"seed": 1461965101,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "TAzQF4M7"
				},
				{
					"id": "ov5oWwhDopsOtjc6nxLpq",
					"type": "arrow"
				}
			],
			"updated": 1710622772655,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1303982445,
			"isDeleted": false,
			"id": "TAzQF4M7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.018150329589844,
			"y": -61.08203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.215988159179688,
			"height": 20,
			"seed": 776676237,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710622772655,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "LB",
			"rawText": "LB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Px9J8GG3qFEywAhcdr7yM",
			"originalText": "LB",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"id": "XcIKGqfXIpIlDSwOG5xLr",
			"type": "rectangle",
			"x": 159.34375,
			"y": -189.015625,
			"width": 163.88671875,
			"height": 59.24609375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1361336653,
			"version": 89,
			"versionNonce": 302217773,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "wlrtSw2Yc-OzfhJkDIauB",
					"type": "arrow"
				}
			],
			"updated": 1710622772655,
			"link": null,
			"locked": false
		},
		{
			"id": "RLJ51Oqw",
			"type": "text",
			"x": 204.30859375,
			"y": -169.8125,
			"width": 72.04798889160156,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": null,
			"seed": 2015654509,
			"version": 70,
			"versionNonce": 23237357,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622772655,
			"link": null,
			"locked": false,
			"text": "Queue #1",
			"rawText": "Queue #1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Queue #1",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 128,
			"versionNonce": 785100109,
			"isDeleted": false,
			"id": "rtWAoUeRLf0kpgxdKkCH4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 161.904296875,
			"y": -86.412109375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.88671875,
			"height": 59.24609375,
			"seed": 1007053581,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710622772655,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 136,
			"versionNonce": 1491237805,
			"isDeleted": false,
			"id": "MBGyL-69y8P_rI1x--QHu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 163.181640625,
			"y": 27.365234375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.88671875,
			"height": 59.24609375,
			"seed": 154559363,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "3ZLhx9Hh9g8P9Bfonxceb",
					"type": "arrow"
				}
			],
			"updated": 1710622772655,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 42939501,
			"isDeleted": false,
			"id": "hPyTXPFs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 204.61663055419922,
			"y": -65.484375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 79.10398864746094,
			"height": 20,
			"seed": 599620995,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710622772655,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Queue #2",
			"rawText": "Queue #2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Queue #2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 1961369293,
			"isDeleted": false,
			"id": "eJyn6cIe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 204.87053680419922,
			"y": 47.93359375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.60798645019531,
			"height": 20,
			"seed": 9054307,
			"groupIds": [
				"RZ4Tzv4GDpNicWT9nKSIx"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710622772655,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Queue #3",
			"rawText": "Queue #3",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Queue #3",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"id": "ov5oWwhDopsOtjc6nxLpq",
			"type": "arrow",
			"x": 19.859375,
			"y": -46.37890625,
			"width": 143.1640625,
			"height": 9.03125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1603345123,
			"version": 113,
			"versionNonce": 375252739,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622773983,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.1640625,
					-9.03125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Px9J8GG3qFEywAhcdr7yM",
				"focus": 0.2162417770959149,
				"gap": 3.128320291062188
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "wlrtSw2Yc-OzfhJkDIauB",
			"type": "arrow",
			"x": 17.921875,
			"y": -52.6484375,
			"width": 139.7265625,
			"height": 113.1953125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1869739597,
			"version": 127,
			"versionNonce": 548408995,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622773984,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					139.7265625,
					-113.1953125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "XcIKGqfXIpIlDSwOG5xLr",
				"focus": 0.7729492239296877,
				"gap": 1.6953125
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "3ZLhx9Hh9g8P9Bfonxceb",
			"type": "arrow",
			"x": 13.203125,
			"y": -45.265625,
			"width": 149.46484375,
			"height": 102.64453125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1107151427,
			"version": 111,
			"versionNonce": 1503412803,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622773984,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					149.46484375,
					102.64453125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "MBGyL-69y8P_rI1x--QHu",
				"focus": -0.6637889091733931,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "rectangle",
			"version": 164,
			"versionNonce": 1839389389,
			"isDeleted": false,
			"id": "KewWQvVwevosw1BGoERYG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 398.955078125,
			"y": -189.595703125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.88671875,
			"height": 59.24609375,
			"seed": 1614510179,
			"groupIds": [
				"7-YmCxYYDDOdEbD2RkCrJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "kOQJzLQt"
				},
				{
					"id": "NUO-1x0gJBfu99Ilk8oAA",
					"type": "arrow"
				}
			],
			"updated": 1710622797983,
			"link": null,
			"locked": false
		},
		{
			"id": "kOQJzLQt",
			"type": "text",
			"x": 445.81046295166016,
			"y": -169.97265625,
			"width": 70.17594909667969,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"7-YmCxYYDDOdEbD2RkCrJ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1786599779,
			"version": 44,
			"versionNonce": 1417572013,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622790033,
			"link": null,
			"locked": false,
			"text": "Consumer",
			"rawText": "Consumer",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "KewWQvVwevosw1BGoERYG",
			"originalText": "Consumer",
			"lineHeight": 1.25
		},
		{
			"id": "NUO-1x0gJBfu99Ilk8oAA",
			"type": "arrow",
			"x": 398.16796875,
			"y": -160.46875,
			"width": 75.24609375,
			"height": 2.640625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1433997891,
			"version": 26,
			"versionNonce": 1257336941,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622797983,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-75.24609375,
					-2.640625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "KewWQvVwevosw1BGoERYG",
				"focus": -0.07407009447335346,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "eoWxnWe3",
			"type": "text",
			"x": 328.68359375,
			"y": -203.73046875,
			"width": 69.79196166992188,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1886109635,
			"version": 30,
			"versionNonce": 2112942115,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622806355,
			"link": null,
			"locked": false,
			"text": "Long Poll",
			"rawText": "Long Poll",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Long Poll",
			"lineHeight": 1.25
		},
		{
			"id": "wJGCMtks",
			"type": "text",
			"x": 17.61328125,
			"y": -144.31640625,
			"width": 81.82394409179688,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 674701059,
			"version": 38,
			"versionNonce": 435315811,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622821393,
			"link": null,
			"locked": false,
			"text": "Consistent\nHashing",
			"rawText": "Consistent\nHashing",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Consistent\nHashing",
			"lineHeight": 1.25
		},
		{
			"id": "xAWtjoTT",
			"type": "text",
			"x": 177.609375,
			"y": -242.45703125,
			"width": 106.76792907714844,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1541536579,
			"version": 48,
			"versionNonce": 1119922403,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622838154,
			"link": null,
			"locked": false,
			"text": "In-memory or \nLog on disk",
			"rawText": "In-memory or \nLog on disk",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "In-memory or \nLog on disk",
			"lineHeight": 1.25
		},
		{
			"id": "azEgaBGk_t402oXuRjgIM",
			"type": "arrow",
			"x": -396.19921875,
			"y": -53.64453125,
			"width": 69.83984375,
			"height": 1.640625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1912733613,
			"version": 25,
			"versionNonce": 837565699,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622851038,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					69.83984375,
					-1.640625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "z9fup78LfwjnYoicqiHoR",
				"focus": 0.002021227359376794,
				"gap": 1.50390625
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7TTYjF0qbG9K7cSTZzpdP",
			"type": "arrow",
			"x": -259.8359375,
			"y": -53.27734375,
			"width": 36.546875,
			"height": 0.2421875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 437065795,
			"version": 16,
			"versionNonce": 20082957,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622852701,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					36.546875,
					-0.2421875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "UqvpbtkhHM3xY2cBdY66t",
				"focus": 0.03589799923476061,
				"gap": 2.2297903823884937
			},
			"endBinding": {
				"elementId": "VRGxdvQuZNkijnANgIuG8",
				"focus": 0.20122781270527654,
				"gap": 6.859375
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "V0MsxOGZzIuHOUOUKBBmI",
			"type": "arrow",
			"x": -117.4453125,
			"y": -52.05859375,
			"width": 73.17578125,
			"height": 1.83984375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1588154829,
			"version": 39,
			"versionNonce": 1771249571,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622854682,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					73.17578125,
					1.83984375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "MxfiSxbUvTLEUyR2UCyWG",
				"focus": -0.03223272456383715,
				"gap": 8.30078125
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Kf8b09d_M6WR6bEYRX2gu",
			"type": "rectangle",
			"x": -69.78515625,
			"y": 75.47265625,
			"width": 149.546875,
			"height": 126.328125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 435257549,
			"version": 60,
			"versionNonce": 387009773,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622864638,
			"link": null,
			"locked": false
		},
		{
			"id": "kNxy3YSfwMndHD0YjHxIt",
			"type": "ellipse",
			"x": -54.20703125,
			"y": 101.5234375,
			"width": 42.39453125,
			"height": 12.89453125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"6UiY_XF79-GcVKBvS0mRt"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1385375565,
			"version": 63,
			"versionNonce": 603187491,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622889427,
			"link": null,
			"locked": false
		},
		{
			"id": "IuC0BdwWVDDZo7Fm3iJ_a",
			"type": "rectangle",
			"x": -53.45703125,
			"y": 102.140625,
			"width": 44.02734375,
			"height": 35.9921875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"6UiY_XF79-GcVKBvS0mRt"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1768865421,
			"version": 99,
			"versionNonce": 880078477,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622889427,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 65,
			"versionNonce": 1762703363,
			"isDeleted": false,
			"id": "h9joVpbh2Llo9sqsAqhrf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 15.611328125,
			"y": 106.1015625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 42.39453125,
			"height": 12.89453125,
			"seed": 1854566221,
			"groupIds": [
				"WfIECtutacorNDZIWjRIy"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710622891727,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 101,
			"versionNonce": 383827875,
			"isDeleted": false,
			"id": "6Hq3qRzziokFeP1ksYuuh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 16.361328125,
			"y": 106.71875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.02734375,
			"height": 35.9921875,
			"seed": 2004417965,
			"groupIds": [
				"WfIECtutacorNDZIWjRIy"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710622891727,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 84,
			"versionNonce": 1513018339,
			"isDeleted": false,
			"id": "vxTmQphCBzMALUDyHoU_g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -19.666015625,
			"y": 151.9609375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 42.39453125,
			"height": 12.89453125,
			"seed": 641065165,
			"groupIds": [
				"0a02XmXfAFakkoDJVwdtQ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710622893555,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 120,
			"versionNonce": 428892035,
			"isDeleted": false,
			"id": "kYZ1rec_J2b5AsFA-7wHq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.916015625,
			"y": 152.578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.02734375,
			"height": 35.9921875,
			"seed": 1538932525,
			"groupIds": [
				"0a02XmXfAFakkoDJVwdtQ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710622893555,
			"link": null,
			"locked": false
		},
		{
			"id": "efjk2esY",
			"type": "text",
			"x": -34.30859375,
			"y": 222.23828125,
			"width": 79.29595947265625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 972048995,
			"version": 40,
			"versionNonce": 1358491299,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622901815,
			"link": null,
			"locked": false,
			"text": "Zookeeper",
			"rawText": "Zookeeper",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Zookeeper",
			"lineHeight": 1.25
		},
		{
			"id": "Z1ZtVy1IjtrJSpGvyPMkO",
			"type": "line",
			"x": -9.953125,
			"y": 59.18359375,
			"width": 1.76171875,
			"height": 69.3515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dotted",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1365355907,
			"version": 43,
			"versionNonce": 1555693965,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710622914760,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.76171875,
					-69.3515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "WQerW_wXUAmEORLRvaAaz",
			"type": "rectangle",
			"x": 309.38671875,
			"y": -350.4375,
			"width": 261.78124999999994,
			"height": 117.10156249999999,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"ftaFBF7Phi64y-5xA7fqR"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1413364067,
			"version": 195,
			"versionNonce": 391220557,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710623003491,
			"link": null,
			"locked": false
		},
		{
			"id": "3l5lyfgT",
			"type": "text",
			"x": 318.26953125,
			"y": -334.078125,
			"width": 248.68783569335938,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"ftaFBF7Phi64y-5xA7fqR"
			],
			"frameId": null,
			"roundness": null,
			"seed": 583551363,
			"version": 224,
			"versionNonce": 1783790083,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710623003491,
			"link": null,
			"locked": false,
			"text": "Long polling used as it does\nnot hold onto connections \nwhile the consumer is processing\nthe request, before send ack",
			"rawText": "Long polling used as it does\nnot hold onto connections \nwhile the consumer is processing\nthe request, before send ack",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Long polling used as it does\nnot hold onto connections \nwhile the consumer is processing\nthe request, before send ack",
			"lineHeight": 1.25
		},
		{
			"id": "vsD7Y5MdJFO3VCjofADCM",
			"type": "rectangle",
			"x": -223.3125,
			"y": -392.62890625,
			"width": 420.21484374999994,
			"height": 129.5078125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"8Pm1Ndq-_lR54s7Fn88SJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 583025869,
			"version": 286,
			"versionNonce": 2143468557,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1710623297753,
			"link": null,
			"locked": false
		},
		{
			"id": "ohKrGL7S",
			"type": "text",
			"x": -208.7109375,
			"y": -374.390625,
			"width": 397.1677551269531,
			"height": 120,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"8Pm1Ndq-_lR54s7Fn88SJ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1005778989,
			"version": 370,
			"versionNonce": 2106176109,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710623297753,
			"link": null,
			"locked": false,
			"text": "Amazon SQS, RabbitMQ - In-memory store (Faster\nwrites, but inpersistent)\n\nApache Kafka - Log based (durable, but slow\nwrites, provides retries)\n",
			"rawText": "Amazon SQS, RabbitMQ - In-memory store (Faster\nwrites, but inpersistent)\n\nApache Kafka - Log based (durable, but slow\nwrites, provides retries)\n",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "Amazon SQS, RabbitMQ - In-memory store (Faster\nwrites, but inpersistent)\n\nApache Kafka - Log based (durable, but slow\nwrites, provides retries)\n",
			"lineHeight": 1.25
		},
		{
			"id": "CcCpmnTnVMfM6VyL-jpMl",
			"type": "rectangle",
			"x": -415.4453125,
			"y": -236.51953125,
			"width": 244.8203125,
			"height": 109.703125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"oXeQTZz-Yj2JqjPXgO4pv"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 162431139,
			"version": 200,
			"versionNonce": 1691652877,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710623293773,
			"link": null,
			"locked": false
		},
		{
			"id": "BBnv5sJD",
			"type": "text",
			"x": -401.359375,
			"y": -210.796875,
			"width": 220.14381408691406,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"oXeQTZz-Yj2JqjPXgO4pv"
			],
			"frameId": null,
			"roundness": null,
			"seed": 711174211,
			"version": 125,
			"versionNonce": 1857794115,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710623293773,
			"link": null,
			"locked": false,
			"text": "API Design:\nPublishMessage(userId, msg)\nConsumeMessage(ack?)",
			"rawText": "API Design:\nPublishMessage(userId, msg)\nConsumeMessage(ack?)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "API Design:\nPublishMessage(userId, msg)\nConsumeMessage(ack?)",
			"lineHeight": 1.25
		},
		{
			"id": "rusZpy9w",
			"type": "text",
			"x": -48.85351562500003,
			"y": -319.94921875,
			"width": 8,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1896267725,
			"version": 2,
			"versionNonce": 209820259,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710623194519,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "vsD7Y5MdJFO3VCjofADCM",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 527.05859375,
		"scrollY": 465.1484375,
		"zoom": {
			"value": 1
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