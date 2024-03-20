---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Design Amazon Kindle Payments ^rdtQrWCB

Functional Requirements:
1.  Consistency
2. User can make payments
3. User receives notification

Non-functional Req:
1.  High Consistency 
2. Scalability
3. Low latency
 ^ynwwKS0U

Estimations:
* DAU = 10M
* 2 purchases/DAU daily
* RPS = 2 * 10^6 * 0.5KB / 3600 * 24
       = 
* Storage = 2 * 10^6 * 0.5KB = ~10GB / day ^2rGjOPWj

API:
1. POST /api/v1/payments
* Params:
  userId
  method
  amount
  currency     
    
2. GET /api/v1/payments

 ^ma8Js1i6

Kindle ^H008T04i

Payments Service ^hqfJT5oF

API 
Gateway ^dSZ5Qusi

Payments 
DB ^bNHTPvSx

Kafka ^kraizP5n

Payments 
Service
Provider (PSP) ^xrjRSxud

Bank ^U4AcrOsi

events ^6TFn445s

txn ^8wG5p3TB

ws ^dTLlmJzp

ws ^LtJbzrYa

Notification
Service ^PtpyuxpE

SES ^nm1OmJ8h

Twilio ^vWHbsEhp

purchase ^d8tXYo5J

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.24",
	"elements": [
		{
			"type": "text",
			"version": 452,
			"versionNonce": 900803867,
			"isDeleted": false,
			"id": "rdtQrWCB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -472.46744791666674,
			"y": -406.0073784722222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 552.0958251953125,
			"height": 45,
			"seed": 1026740763,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454448323,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Design Amazon Kindle Payments",
			"rawText": "Design Amazon Kindle Payments",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Design Amazon Kindle Payments",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "rectangle",
			"version": 490,
			"versionNonce": 1491967029,
			"isDeleted": false,
			"id": "1TZ0cUCK1lx516uyTiuTF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -814.2705346963265,
			"y": -433.24488933134785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 310.515625,
			"height": 257.109375,
			"seed": 991713333,
			"groupIds": [
				"4V17-Hq7sqCdz-qT7YAhb"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710453649238,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 757,
			"versionNonce": 1639337365,
			"isDeleted": false,
			"id": "ynwwKS0U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -798.9541284463265,
			"y": -417.54957683134785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 280.6197509765625,
			"height": 250,
			"seed": 351385237,
			"groupIds": [
				"4V17-Hq7sqCdz-qT7YAhb"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710453649238,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Functional Requirements:\n1.  Consistency\n2. User can make payments\n3. User receives notification\n\nNon-functional Req:\n1.  High Consistency \n2. Scalability\n3. Low latency\n",
			"rawText": "Functional Requirements:\n1.  Consistency\n2. User can make payments\n3. User receives notification\n\nNon-functional Req:\n1.  High Consistency \n2. Scalability\n3. Low latency\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Functional Requirements:\n1.  Consistency\n2. User can make payments\n3. User receives notification\n\nNon-functional Req:\n1.  High Consistency \n2. Scalability\n3. Low latency\n",
			"lineHeight": 1.25,
			"baseline": 243
		},
		{
			"type": "rectangle",
			"version": 1059,
			"versionNonce": 262051445,
			"isDeleted": false,
			"id": "jMbigXn9CiK2bwZ0vqU9v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -820.7605401408545,
			"y": -128.8395552358436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 497.675164712972,
			"height": 185.49530316188086,
			"seed": 1773546037,
			"groupIds": [
				"zaBsWuwuvoMUKz-aZDaxK"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710453665855,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1376,
			"versionNonce": 80609237,
			"isDeleted": false,
			"id": "2rGjOPWj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -808.3245701008101,
			"y": -115.01272840366755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 468.999755859375,
			"height": 150,
			"seed": 641538965,
			"groupIds": [
				"zaBsWuwuvoMUKz-aZDaxK"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710453665855,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Estimations:\n* DAU = 10M\n* 2 purchases/DAU daily\n* RPS = 2 * 10^6 * 0.5KB / 3600 * 24\n       = \n* Storage = 2 * 10^6 * 0.5KB = ~10GB / day",
			"rawText": "Estimations:\n* DAU = 10M\n* 2 purchases/DAU daily\n* RPS = 2 * 10^6 * 0.5KB / 3600 * 24\n       = \n* Storage = 2 * 10^6 * 0.5KB = ~10GB / day",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Estimations:\n* DAU = 10M\n* 2 purchases/DAU daily\n* RPS = 2 * 10^6 * 0.5KB / 3600 * 24\n       = \n* Storage = 2 * 10^6 * 0.5KB = ~10GB / day",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "rectangle",
			"version": 768,
			"versionNonce": 1041425877,
			"isDeleted": false,
			"id": "oUy4BdybViLHDgF7VzzYA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -811.4792441809188,
			"y": 110.38974233829725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 310.515625,
			"height": 257.109375,
			"seed": 1819687995,
			"groupIds": [
				"7Ial4rn7PmEbMF7461TDg"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710453668872,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1170,
			"versionNonce": 851534645,
			"isDeleted": false,
			"id": "ma8Js1i6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -796.1628379309188,
			"y": 126.08505483829725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 248.0198211669922,
			"height": 275,
			"seed": 2088303835,
			"groupIds": [
				"7Ial4rn7PmEbMF7461TDg"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710453668872,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "API:\n1. POST /api/v1/payments\n* Params:\n  userId\n  method\n  amount\n  currency     \n    \n2. GET /api/v1/payments\n\n",
			"rawText": "API:\n1. POST /api/v1/payments\n* Params:\n  userId\n  method\n  amount\n  currency     \n    \n2. GET /api/v1/payments\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API:\n1. POST /api/v1/payments\n* Params:\n  userId\n  method\n  amount\n  currency     \n    \n2. GET /api/v1/payments\n\n",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "ellipse",
			"version": 928,
			"versionNonce": 700782619,
			"isDeleted": false,
			"id": "wHkfj_zx4sU7yCEiIuREs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -435.60666898661816,
			"y": -323.72314641319184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.578993055555543,
			"height": 29.001736111111114,
			"seed": 1867968149,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "q5zJoRL1wRXfARGQGaaoZ",
					"type": "arrow"
				}
			],
			"updated": 1710454527823,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 908,
			"versionNonce": 2104994299,
			"isDeleted": false,
			"id": "ns2BjsDMcFUkukhJB8hmo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.5736828755071,
			"y": -294.04866724652516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.2821180555556566,
			"height": 44.52256944444446,
			"seed": 1826078517,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710454527824,
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
					0.2821180555556566,
					44.52256944444446
				]
			]
		},
		{
			"type": "line",
			"version": 900,
			"versionNonce": 1317450395,
			"isDeleted": false,
			"id": "14wcgcA4yedqsCSgd_SWG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.6344467643959,
			"y": -289.46533391319184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.533854166666742,
			"height": 9.700520833333343,
			"seed": 1031150459,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710454527824,
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
					-15.533854166666742,
					9.700520833333343
				]
			]
		},
		{
			"type": "line",
			"version": 905,
			"versionNonce": 99329851,
			"isDeleted": false,
			"id": "jRur4WNOwVsvu3zrR8_0O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -418.4712523199514,
			"y": -288.4193269687474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 18.012152777777715,
			"height": 10.694444444444429,
			"seed": 1170629589,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710454527824,
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
					18.012152777777715,
					10.694444444444429
				]
			]
		},
		{
			"type": "line",
			"version": 901,
			"versionNonce": 973670363,
			"isDeleted": false,
			"id": "sL59PtHfFYIxCHXmNhEG-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -418.0545856532848,
			"y": -258.81429224652516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.508680555555543,
			"height": 17.009548611111086,
			"seed": 387935995,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710454527824,
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
					-22.508680555555543,
					17.009548611111086
				]
			]
		},
		{
			"type": "line",
			"version": 934,
			"versionNonce": 284251259,
			"isDeleted": false,
			"id": "xCLePvhLAnqckfQ-_w1DD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.0354884310626,
			"y": -258.64502141319184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.8064236111112,
			"height": 16.384548611111143,
			"seed": 2003666357,
			"groupIds": [
				"2Aw4h9i87i66RM_vLpUmZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710454527824,
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
					23.8064236111112,
					16.384548611111143
				]
			]
		},
		{
			"type": "rectangle",
			"version": 477,
			"versionNonce": 232112187,
			"isDeleted": false,
			"id": "Voim3OXs-cgZy0Tty5fAI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -254.76465509772902,
			"y": -342.06516030208087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 87.71267361111109,
			"height": 98.50694444444443,
			"seed": 776238939,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "H008T04i"
				},
				{
					"id": "q5zJoRL1wRXfARGQGaaoZ",
					"type": "arrow"
				},
				{
					"id": "Fs8CtFW4s4vhr-gb_6Hnc",
					"type": "arrow"
				}
			],
			"updated": 1710454531073,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 1330118875,
			"isDeleted": false,
			"id": "H008T04i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -237.68829418328676,
			"y": -305.31168807985864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.55995178222656,
			"height": 25,
			"seed": 1212060699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454531073,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kindle",
			"rawText": "Kindle",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Voim3OXs-cgZy0Tty5fAI",
			"originalText": "Kindle",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 884,
			"versionNonce": 1924429019,
			"isDeleted": false,
			"id": "q5zJoRL1wRXfARGQGaaoZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -416.40548064768643,
			"y": -285.11688002484277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.30575610551273,
			"height": 0.9962384278520631,
			"seed": 1132134075,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "d8tXYo5J"
				}
			],
			"updated": 1710455304953,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wHkfj_zx4sU7yCEiIuREs",
				"gap": 9.995715208482316,
				"focus": 1.660341521661361
			},
			"endBinding": {
				"elementId": "Voim3OXs-cgZy0Tty5fAI",
				"gap": 7.3350694444446844,
				"focus": -0.18211883620410954
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					154.30575610551273,
					0.9962384278520631
				]
			]
		},
		{
			"id": "d8tXYo5J",
			"type": "text",
			"x": -373.20457555635585,
			"y": -294.61876081091674,
			"width": 67.90394592285156,
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
			"seed": 941199157,
			"version": 9,
			"versionNonce": 583054395,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710455304018,
			"link": null,
			"locked": false,
			"text": "purchase",
			"rawText": "purchase",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "q5zJoRL1wRXfARGQGaaoZ",
			"originalText": "purchase",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 345,
			"versionNonce": 1306722203,
			"isDeleted": false,
			"id": "tH8wuMdmS5OTC1xkBxR_j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -38.29330093106262,
			"y": -128.38894502430298,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 144.0451388888888,
			"height": 123.82378472222223,
			"seed": 1237205851,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "hqfJT5oF"
				},
				{
					"id": "DgQAKhr7kE2cO5L6__AtU",
					"type": "arrow"
				},
				{
					"id": "w0jDdaWLMQq9UfhxfPn1u",
					"type": "arrow"
				},
				{
					"id": "bC00VeXzdCNZwKHGOtbFK",
					"type": "arrow"
				},
				{
					"id": "V8B8PfXxNuy9WA0oDg4SF",
					"type": "arrow"
				}
			],
			"updated": 1710454919170,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 1312183355,
			"isDeleted": false,
			"id": "hqfJT5oF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -11.790689982711967,
			"y": -91.47705266319187,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 91.0399169921875,
			"height": 50,
			"seed": 1209261307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454919170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payments\nService",
			"rawText": "Payments Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tH8wuMdmS5OTC1xkBxR_j",
			"originalText": "Payments Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"id": "xCN05KukF4qUJEJcHQxP4",
			"type": "diamond",
			"x": -46.46485456373648,
			"y": -334.09641030208087,
			"width": 159.53125,
			"height": 100,
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
			"seed": 1139819061,
			"version": 483,
			"versionNonce": 1839023195,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Fs8CtFW4s4vhr-gb_6Hnc",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "dSZ5Qusi"
				}
			],
			"updated": 1710454558988,
			"link": null,
			"locked": false
		},
		{
			"id": "dSZ5Qusi",
			"type": "text",
			"x": -1.086024607681793,
			"y": -304.09641030208087,
			"width": 69.00796508789062,
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
			"seed": 529648277,
			"version": 337,
			"versionNonce": 801767675,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710454558988,
			"link": null,
			"locked": false,
			"text": "API \nGateway",
			"rawText": "API \nGateway",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 34,
			"containerId": "xCN05KukF4qUJEJcHQxP4",
			"originalText": "API \nGateway",
			"lineHeight": 1.25
		},
		{
			"id": "Fs8CtFW4s4vhr-gb_6Hnc",
			"type": "arrow",
			"x": -164.22527123040288,
			"y": -287.29427260539524,
			"width": 116.91711120094399,
			"height": 1.4650196905588473,
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
			"seed": 702490581,
			"version": 840,
			"versionNonce": 1234576955,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "dTLlmJzp"
				}
			],
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					116.91711120094399,
					1.4650196905588473
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Voim3OXs-cgZy0Tty5fAI",
				"gap": 2.8267102562150512,
				"focus": 0.09903934704361735
			},
			"endBinding": {
				"elementId": "xCN05KukF4qUJEJcHQxP4",
				"gap": 1.9161287008584154,
				"focus": 0.014455588444511723
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dTLlmJzp",
			"type": "text",
			"x": -114.98270378714675,
			"y": -296.5617627644236,
			"width": 18.431976318359375,
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
			"seed": 1328152667,
			"version": 3,
			"versionNonce": 392010485,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710454888959,
			"link": null,
			"locked": false,
			"text": "ws",
			"rawText": "ws",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "Fs8CtFW4s4vhr-gb_6Hnc",
			"originalText": "ws",
			"lineHeight": 1.25
		},
		{
			"id": "DgQAKhr7kE2cO5L6__AtU",
			"type": "arrow",
			"x": 33.69573571404135,
			"y": -237.3516186354142,
			"width": 0.6190524419452075,
			"height": 106.72743055555557,
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
			"seed": 1886016539,
			"version": 203,
			"versionNonce": 1174075163,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "LtJbzrYa"
				}
			],
			"updated": 1710455203453,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6190524419452075,
					106.72743055555557
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "tH8wuMdmS5OTC1xkBxR_j",
				"gap": 2.2352430555556566,
				"focus": 0.01322977166358023
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "LtJbzrYa",
			"type": "text",
			"x": 24.78927377583426,
			"y": -193.9879033576364,
			"width": 18.431976318359375,
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
			"seed": 1932768693,
			"version": 3,
			"versionNonce": 708214267,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710454931841,
			"link": null,
			"locked": false,
			"text": "ws",
			"rawText": "ws",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "DgQAKhr7kE2cO5L6__AtU",
			"originalText": "ws",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 404,
			"versionNonce": 166078555,
			"isDeleted": false,
			"id": "ss7oV-ggmCMmK6Mo1biQB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.64018015848598,
			"y": 51.67832928125242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 144.0451388888888,
			"height": 123.82378472222223,
			"seed": 526197147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "bNHTPvSx"
				},
				{
					"id": "w0jDdaWLMQq9UfhxfPn1u",
					"type": "arrow"
				}
			],
			"updated": 1710454937954,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 352,
			"versionNonce": 425092347,
			"isDeleted": false,
			"id": "bNHTPvSx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 192.14279110683663,
			"y": 88.59022164236353,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.0399169921875,
			"height": 50,
			"seed": 1880897083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454937954,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payments \nDB",
			"rawText": "Payments \nDB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ss7oV-ggmCMmK6Mo1biQB",
			"originalText": "Payments \nDB",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"id": "w0jDdaWLMQq9UfhxfPn1u",
			"type": "arrow",
			"x": 107.20268015848565,
			"y": -56.15333797625046,
			"width": 146.97889376684657,
			"height": 106.83166725750287,
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
			"seed": 884674741,
			"version": 390,
			"versionNonce": 1108059867,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					136.61024305555546,
					10.142865174169593
				],
				[
					146.97889376684657,
					106.83166725750287
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "tH8wuMdmS5OTC1xkBxR_j",
				"gap": 1.4508422006594373,
				"focus": 0.07238480024468681
			},
			"endBinding": {
				"elementId": "ss7oV-ggmCMmK6Mo1biQB",
				"gap": 1,
				"focus": 0.23220064018003528
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "rectangle",
			"version": 530,
			"versionNonce": 1185176085,
			"isDeleted": false,
			"id": "hw1pl4HziTVmAWmD3KmF_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -236.33464623040294,
			"y": 47.78075983680796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.44704861111109,
			"height": 71.55815972222223,
			"seed": 129170357,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "kraizP5n"
				},
				{
					"id": "bC00VeXzdCNZwKHGOtbFK",
					"type": "arrow"
				},
				{
					"id": "1Hn0-3eXwdC6wD2aVJa_v",
					"type": "arrow"
				}
			],
			"updated": 1710455183320,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 471,
			"versionNonce": 506115637,
			"isDeleted": false,
			"id": "kraizP5n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -202.81110361430052,
			"y": 71.05983969791907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.39996337890625,
			"height": 25,
			"seed": 1604566293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710455183320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kafka",
			"rawText": "Kafka",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hw1pl4HziTVmAWmD3KmF_",
			"originalText": "Kafka",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "bC00VeXzdCNZwKHGOtbFK",
			"type": "arrow",
			"x": -45.106347619291924,
			"y": -88.71070404599337,
			"width": 140.73630595822124,
			"height": 135.49146388280133,
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
			"seed": 389157845,
			"version": 790,
			"versionNonce": 1565004667,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "6TFn445s"
				}
			],
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-121.43663194444433,
					10.573495132801355
				],
				[
					-140.73630595822124,
					135.49146388280133
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "tH8wuMdmS5OTC1xkBxR_j",
				"gap": 6.813046688229292,
				"focus": 0.4267620262533215
			},
			"endBinding": {
				"elementId": "hw1pl4HziTVmAWmD3KmF_",
				"gap": 1,
				"focus": -0.26246887525488677
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "6TFn445s",
			"type": "text",
			"x": -177.89927991774027,
			"y": -111.76134085763647,
			"width": 51.07197570800781,
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
			"seed": 522333237,
			"version": 7,
			"versionNonce": 1762593275,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710454824935,
			"link": null,
			"locked": false,
			"text": "events",
			"rawText": "events",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "bC00VeXzdCNZwKHGOtbFK",
			"originalText": "events",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 515,
			"versionNonce": 958205621,
			"isDeleted": false,
			"id": "Z8LpAaKkcL7TQY6dpfsrp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.4361871029302,
			"y": -275.2227123854142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.09288194444423,
			"height": 93.20746527777777,
			"seed": 1600763701,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xrjRSxud"
				},
				{
					"id": "P2rXWh655LgwnsbDbPYsB",
					"type": "arrow"
				},
				{
					"id": "V8B8PfXxNuy9WA0oDg4SF",
					"type": "arrow"
				}
			],
			"updated": 1710454868369,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 486,
			"versionNonce": 1521796853,
			"isDeleted": false,
			"id": "xrjRSxud",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.5546724477109,
			"y": -258.61897974652527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.85591125488281,
			"height": 60,
			"seed": 402065557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454808320,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Payments \nService\nProvider (PSP)",
			"rawText": "Payments \nService\nProvider (PSP)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Z8LpAaKkcL7TQY6dpfsrp",
			"originalText": "Payments \nService\nProvider (PSP)",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "rectangle",
			"version": 522,
			"versionNonce": 345008059,
			"isDeleted": false,
			"id": "C7PPkxBFNM7v6si8Z6XXT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 174.4986871029302,
			"y": -430.0751429409698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.84809027777771,
			"height": 85,
			"seed": 1061501173,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "U4AcrOsi"
				},
				{
					"id": "P2rXWh655LgwnsbDbPYsB",
					"type": "arrow"
				}
			],
			"updated": 1710454819457,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 482,
			"versionNonce": 1853306875,
			"isDeleted": false,
			"id": "U4AcrOsi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 200.94274414367453,
			"y": -400.0751429409698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 46.95997619628906,
			"height": 25,
			"seed": 2088522325,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710454814905,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bank",
			"rawText": "Bank",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "C7PPkxBFNM7v6si8Z6XXT",
			"originalText": "Bank",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "P2rXWh655LgwnsbDbPYsB",
			"type": "arrow",
			"x": 231.0525065473749,
			"y": -279.6085630798587,
			"width": 3.1197699623605786,
			"height": 64.46657986111109,
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
			"seed": 1922411157,
			"version": 80,
			"versionNonce": 472046555,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-3.1197699623605786,
					-64.46657986111109
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Z8LpAaKkcL7TQY6dpfsrp",
				"gap": 4.385850694444457,
				"focus": 0.09389241781473207
			},
			"endBinding": {
				"elementId": "C7PPkxBFNM7v6si8Z6XXT",
				"gap": 1,
				"focus": -0.027026967871805124
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "V8B8PfXxNuy9WA0oDg4SF",
			"type": "arrow",
			"x": 235.08462460293026,
			"y": -179.0616880798587,
			"width": 126.50173611111109,
			"height": 84.41713065895557,
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
			"seed": 1941267739,
			"version": 173,
			"versionNonce": 457541275,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "8wG5p3TB"
				}
			],
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-16.124131944444343,
					57.096354166666686
				],
				[
					-126.50173611111109,
					84.41713065895557
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Z8LpAaKkcL7TQY6dpfsrp",
				"gap": 2.9535590277777146,
				"focus": -0.2871668391152936
			},
			"endBinding": {
				"elementId": "tH8wuMdmS5OTC1xkBxR_j",
				"gap": 2.8310505339929932,
				"focus": -0.12089017724372558
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "8wG5p3TB",
			"type": "text",
			"x": 206.20850138651326,
			"y": -131.965333913192,
			"width": 25.503982543945312,
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
			"seed": 633823125,
			"version": 4,
			"versionNonce": 883186363,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710454879340,
			"link": null,
			"locked": false,
			"text": "txn",
			"rawText": "txn",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "V8B8PfXxNuy9WA0oDg4SF",
			"originalText": "txn",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 661,
			"versionNonce": 194412891,
			"isDeleted": false,
			"id": "3NpUL1zBl2cYWzmkslWws",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -245.84853511929185,
			"y": 194.4430862256968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 144.0451388888888,
			"height": 78.52864583333331,
			"seed": 394384571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PtpyuxpE"
				},
				{
					"id": "1Hn0-3eXwdC6wD2aVJa_v",
					"type": "arrow"
				},
				{
					"id": "84yqgaEUn01AfUxwHD3_Y",
					"type": "arrow"
				},
				{
					"id": "sM34tHNbwU748WiN5Fqcj",
					"type": "arrow"
				}
			],
			"updated": 1710455223602,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 622,
			"versionNonce": 967103061,
			"isDeleted": false,
			"id": "PtpyuxpE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -230.43590525004277,
			"y": 208.70740914236345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.21987915039062,
			"height": 50,
			"seed": 1669170523,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710455202320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notification\nService",
			"rawText": "Notification\nService",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "3NpUL1zBl2cYWzmkslWws",
			"originalText": "Notification\nService",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"id": "1Hn0-3eXwdC6wD2aVJa_v",
			"type": "arrow",
			"x": -173.81634375188096,
			"y": 120.33891955903022,
			"width": 0.9905247007441744,
			"height": 72.83897569444446,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1486728571,
			"version": 195,
			"versionNonce": 1729880347,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710455203454,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.9905247007441744,
					72.83897569444446
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "hw1pl4HziTVmAWmD3KmF_",
				"gap": 1,
				"focus": -0.004665878658488701
			},
			"endBinding": {
				"elementId": "3NpUL1zBl2cYWzmkslWws",
				"gap": 1.2651909722221575,
				"focus": -0.021115355352250346
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "rectangle",
			"version": 533,
			"versionNonce": 244710485,
			"isDeleted": false,
			"id": "40jBHBniKDiqGqKjR_STY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -396.1892469248474,
			"y": 323.5489890034746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.44704861111109,
			"height": 71.55815972222223,
			"seed": 1876412571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "nm1OmJ8h"
				},
				{
					"id": "84yqgaEUn01AfUxwHD3_Y",
					"type": "arrow"
				}
			],
			"updated": 1710455220616,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 477,
			"versionNonce": 1636259797,
			"isDeleted": false,
			"id": "nm1OmJ8h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -352.3657088863817,
			"y": 346.8280688645857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 37.79997253417969,
			"height": 25,
			"seed": 1219099963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710455207823,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SES",
			"rawText": "SES",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "40jBHBniKDiqGqKjR_STY",
			"originalText": "SES",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 551,
			"versionNonce": 1728325275,
			"isDeleted": false,
			"id": "RzajHLhirrMl5k2XMFmBv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.23959414706974,
			"y": 323.9569751145857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.44704861111109,
			"height": 71.55815972222223,
			"seed": 1272578325,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "vWHbsEhp"
				},
				{
					"id": "sM34tHNbwU748WiN5Fqcj",
					"type": "arrow"
				}
			],
			"updated": 1710455223602,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 497,
			"versionNonce": 1798476027,
			"isDeleted": false,
			"id": "vWHbsEhp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -76.19603962911185,
			"y": 347.2360549756968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.35993957519531,
			"height": 25,
			"seed": 126031477,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710455210584,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Twilio",
			"rawText": "Twilio",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "RzajHLhirrMl5k2XMFmBv",
			"originalText": "Twilio",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "84yqgaEUn01AfUxwHD3_Y",
			"type": "arrow",
			"x": -173.95617400818082,
			"y": 280.2829299756969,
			"width": 92.01388888888891,
			"height": 78.19010416666663,
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
			"seed": 827903547,
			"version": 211,
			"versionNonce": 266441915,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710455253271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-10.125868055555543,
					65.19965277777771
				],
				[
					-92.01388888888891,
					78.19010416666663
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "3NpUL1zBl2cYWzmkslWws",
				"focus": -0.09092652105591047,
				"gap": 7.311197916666799
			},
			"endBinding": {
				"elementId": "40jBHBniKDiqGqKjR_STY",
				"focus": 0.21544722731299454,
				"gap": 4.772135416666572
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "sM34tHNbwU748WiN5Fqcj",
			"type": "arrow",
			"x": -170.36242400818082,
			"y": 279.636228586808,
			"width": 49.7439236111112,
			"height": 74.33593749999989,
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
			"seed": 1604168117,
			"version": 394,
			"versionNonce": 2063697525,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710455247253,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.2855902777778283,
					67.03559027777771
				],
				[
					49.7439236111112,
					74.33593749999989
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "3NpUL1zBl2cYWzmkslWws",
				"focus": -0.016396194077033535,
				"gap": 6.664496527777885
			},
			"endBinding": {
				"elementId": "RzajHLhirrMl5k2XMFmBv",
				"focus": -0.11852602610916158,
				"gap": 8.378906249999886
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 841.2435003970702,
		"scrollY": 472.59901446874784,
		"zoom": {
			"value": 0.9
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