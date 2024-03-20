---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Client ^tu5lamUT

Product Service ^19auiMKM

cart service ^WDYmNIea

order service ^PvnGeT5U

LB ^nIYcjhWY

MongoDB ^m4W63Nox

MongoDB
(read replica) ^WoxE3c3D

MongoDB
(read replica) ^yhnmpeiT

Kafka Queue ^5OKpimZz

Document based
search Indexing ^iYt2tgAn

Product Search 
    cache ^I7hwYkj6


Elastic-
search ^iIEWut4G


Elastic-
search ^DB4ubCAK


Elastic-
search ^9avjwUB7

 
Riak
DB ^D0WiroDj

 
Riak
DB ^HKG0apFK

 
Riak
DB ^NdorRWdJ

In order to handle concurrency
in adding data to cart
we opt for: ^YsItrLj2

* Set based CRDT for
Leaderless replication using 
Riak. 
* It uses consistent hashing
to add data to shards (based 
on accnt Id)  ^OqN9iGRR

Kafka Queue ^vc7bAJgN

Spark Streaming 
consumers ^3GyLHIWW

MYSQL 
Orders DB ^sWscjZvl

    Functional requirements:
1. Search for Items with text
2. Add Products to cart with 
   concurrency
3. Complete an Order with list of
   items

  ^SOGkPXy8

Capacity Estimate:
 ^TMPNOM0W

1.  1 billion users around the globe
2. 100M products, each of size 1kb
3. 100M order / day ^kZ0lY9OG

API Design ^4zMsCDMl

1. /searchProduct(queryString)
2. addToCart(userId,productId)
3. placeOrder(userId, productIdList) ^TBQCijFf

Database Schema ^VpNZwVrI

1. Accounts(email, pw_hash, addr)
2. Cart(accntId, productsSet)
3. Products(id, name, metadata)
4. Orders(accntId, productIds, price) ^4HooKrpr

Breaks order into individual
products, partitioned on 
productID.  ^ZGFkZTxa

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
			"version": 262,
			"versionNonce": 279236853,
			"isDeleted": false,
			"id": "3e4rDfzmBol-EPaUyshmE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -526.0736853435161,
			"y": 102.14321199988439,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 1826314875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "tu5lamUT"
				},
				{
					"id": "zEzrSd8MLQG8CyerUohFN",
					"type": "arrow"
				}
			],
			"updated": 1710463238482,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 774433365,
			"isDeleted": false,
			"id": "tu5lamUT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -513.9107672526958,
			"y": 120.60219637488439,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.099945068359375,
			"height": 25,
			"seed": 402424315,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463238482,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Client",
			"rawText": "Client",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "3e4rDfzmBol-EPaUyshmE",
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 461,
			"versionNonce": 366024597,
			"isDeleted": false,
			"id": "f58S1OE5PztB6yiaaJ4kx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -332.77582386831455,
			"y": 102.95479521882379,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 65.67968750000001,
			"height": 60,
			"seed": 106797973,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "nIYcjhWY"
				},
				{
					"id": "zEzrSd8MLQG8CyerUohFN",
					"type": "arrow"
				},
				{
					"id": "y1I-vTfsFGAGj3XrCD2G7",
					"type": "arrow"
				}
			],
			"updated": 1710463235517,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 1599298805,
			"isDeleted": false,
			"id": "nIYcjhWY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -310.4638960729044,
			"y": 122.95479521882379,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.215988159179688,
			"height": 20,
			"seed": 250047093,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463235517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "LB",
			"rawText": "LB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "f58S1OE5PztB6yiaaJ4kx",
			"originalText": "LB",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 300,
			"versionNonce": 2064481659,
			"isDeleted": false,
			"id": "c_09YY7dWL1KB86nd406c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.6455078125,
			"y": -327.974609375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 67.31640625,
			"seed": 1299809467,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "19auiMKM"
				},
				{
					"id": "Ydc_6SgONoeu225ZWDcr6",
					"type": "arrow"
				},
				{
					"id": "C1IxYq0HiX3Bytug4Ch5Q",
					"type": "arrow"
				},
				{
					"id": "AJ8-5-VKgALdC5XaUnIEm",
					"type": "arrow"
				}
			],
			"updated": 1710461078928,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 1341239509,
			"isDeleted": false,
			"id": "19auiMKM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -141.22459411621094,
			"y": -314.31640625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 61.583953857421875,
			"height": 40,
			"seed": 1593783643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460743494,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Product\nService",
			"rawText": "Product Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "c_09YY7dWL1KB86nd406c",
			"originalText": "Product Service",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 607,
			"versionNonce": 1607257723,
			"isDeleted": false,
			"id": "Y5xwY5DPmf8AQh_YNnlXT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -120.16703823871376,
			"y": 115.05782969733531,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 910431733,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WDYmNIea"
				},
				{
					"id": "y1I-vTfsFGAGj3XrCD2G7",
					"type": "arrow"
				},
				{
					"id": "KE5lVtU4WgVKs4fHav5Ox",
					"type": "arrow"
				}
			],
			"updated": 1710463204883,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 551,
			"versionNonce": 1673742107,
			"isDeleted": false,
			"id": "WDYmNIea",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.44213131732704,
			"y": 126.01681407233531,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.97596740722656,
			"height": 40,
			"seed": 1234669397,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "cart\nservice",
			"rawText": "cart service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Y5xwY5DPmf8AQh_YNnlXT",
			"originalText": "cart service",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 498,
			"versionNonce": 1040210651,
			"isDeleted": false,
			"id": "o0PJ936vQm_AXjYo4z8QD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -97.31313063909806,
			"y": 406.5002288585272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 60,
			"seed": 2042620507,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PvnGeT5U"
				},
				{
					"id": "XKq0keTm_8tEcDwE7xn9O",
					"type": "arrow"
				},
				{
					"id": "E5bjYQ2MKUuHKPnm8KpYx",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 452,
			"versionNonce": 1619412859,
			"isDeleted": false,
			"id": "PvnGeT5U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -84.58822371771134,
			"y": 416.5002288585272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.97596740722656,
			"height": 40,
			"seed": 749201147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463162367,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "order\nservice",
			"rawText": "order service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "o0PJ936vQm_AXjYo4z8QD",
			"originalText": "order service",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 833,
			"versionNonce": 1678644660,
			"isDeleted": false,
			"id": "zEzrSd8MLQG8CyerUohFN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -444.5932165935161,
			"y": 135.77647494948548,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 111.40627822310364,
			"height": 0.9205240316956633,
			"seed": 85397653,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938379,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3e4rDfzmBol-EPaUyshmE",
				"gap": 3.0546875,
				"focus": 0.07432254269241186
			},
			"endBinding": {
				"elementId": "f58S1OE5PztB6yiaaJ4kx",
				"gap": 3.0401829284229294,
				"focus": -0.13389828855919436
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
					111.40627822310364,
					0.9205240316956633
				]
			]
		},
		{
			"type": "arrow",
			"version": 495,
			"versionNonce": 1696727604,
			"isDeleted": false,
			"id": "Ydc_6SgONoeu225ZWDcr6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.2373253218493,
			"y": -14.150447475883993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 77.59181750934931,
			"height": 286.16819552855645,
			"seed": 1263242907,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "c_09YY7dWL1KB86nd406c",
				"gap": 1,
				"focus": 0.4885507101962229
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
					18.97457678436274,
					-257.099552524116
				],
				[
					77.59181750934931,
					-286.16819552855645
				]
			]
		},
		{
			"type": "arrow",
			"version": 1031,
			"versionNonce": 2098602420,
			"isDeleted": false,
			"id": "y1I-vTfsFGAGj3XrCD2G7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -267.7317709524573,
			"y": 137.63279720154253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 143.5334827137435,
			"height": 5.138396680045872,
			"seed": 581459061,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938379,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "f58S1OE5PztB6yiaaJ4kx",
				"gap": 3.0250973213347088,
				"focus": 0.11750380600953785
			},
			"endBinding": {
				"elementId": "Y5xwY5DPmf8AQh_YNnlXT",
				"gap": 4.03125,
				"focus": 0.05245256411231063
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
					143.5334827137435,
					5.138396680045872
				]
			]
		},
		{
			"type": "arrow",
			"version": 967,
			"versionNonce": 1914015284,
			"isDeleted": false,
			"id": "XKq0keTm_8tEcDwE7xn9O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -227.27237033936092,
			"y": -20.75088596436092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.70849336477613,
			"height": 461.5558210272553,
			"seed": 1906584283,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "o0PJ936vQm_AXjYo4z8QD",
				"gap": 8.102399085954573,
				"focus": -0.4916092583371476
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
					-2.8516527504678493,
					415.104286376446
				],
				[
					121.85684061430828,
					461.5558210272553
				]
			]
		},
		{
			"type": "arrow",
			"version": 575,
			"versionNonce": 1741870132,
			"isDeleted": false,
			"id": "C1IxYq0HiX3Bytug4Ch5Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -69.4716796875,
			"y": -297.95520754800543,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.2861328125,
			"height": 0.6848319858132754,
			"seed": 785368603,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938381,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "c_09YY7dWL1KB86nd406c",
				"gap": 1.748046875,
				"focus": -0.1155757374770315
			},
			"endBinding": {
				"elementId": "M-OQA4s-JjMkak4DdRHPD",
				"gap": 8.46307313423631,
				"focus": -0.06115978483188686
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
					99.2861328125,
					0.6848319858132754
				]
			]
		},
		{
			"type": "rectangle",
			"version": 593,
			"versionNonce": 1050927285,
			"isDeleted": false,
			"id": "M-OQA4s-JjMkak4DdRHPD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 38.27752625923631,
			"y": -349.96191406250045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 85.369140625,
			"height": 99.9403229111415,
			"seed": 1742618933,
			"groupIds": [
				"aJuqBWD5T5IK6DfpdJI5P"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "m4W63Nox"
				},
				{
					"id": "C1IxYq0HiX3Bytug4Ch5Q",
					"type": "arrow"
				},
				{
					"id": "Fn7jRCjHioQr05v3WaRpE",
					"type": "arrow"
				},
				{
					"id": "ru8klIlNsmgUdWTEFF30Q",
					"type": "arrow"
				},
				{
					"id": "7Gj48b_b7CvBZhVpxw11S",
					"type": "arrow"
				}
			],
			"updated": 1710460821860,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 428,
			"versionNonce": 980660379,
			"isDeleted": false,
			"id": "m4W63Nox",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 54.73260438423631,
			"y": -307.6664499036338,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 52.458984375,
			"height": 15.349394593408201,
			"seed": 1967805077,
			"groupIds": [
				"aJuqBWD5T5IK6DfpdJI5P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460803758,
			"link": null,
			"locked": false,
			"fontSize": 12.791162161173501,
			"fontFamily": 3,
			"text": "MongoDB",
			"rawText": "MongoDB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "M-OQA4s-JjMkak4DdRHPD",
			"originalText": "MongoDB",
			"lineHeight": 1.2,
			"baseline": 12
		},
		{
			"type": "ellipse",
			"version": 614,
			"versionNonce": 1561885947,
			"isDeleted": false,
			"id": "Fvu1rcYjFxANJKJjZ1Y4B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 43.314670928663276,
			"y": -347.5592667732839,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 78.70499510450577,
			"height": 24.785999529598165,
			"seed": 300759029,
			"groupIds": [
				"aJuqBWD5T5IK6DfpdJI5P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710460803758,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 723,
			"versionNonce": 775736437,
			"isDeleted": false,
			"id": "WDMAG9ZK4cCKXgN46e3cw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -27.358034884445708,
			"y": -195.30219270557092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1497311643,
			"groupIds": [
				"zCW9RjA3lGCmK3qdyblbn"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WoxE3c3D"
				}
			],
			"updated": 1710460798342,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 691,
			"versionNonce": 1580561877,
			"isDeleted": false,
			"id": "WoxE3c3D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -18.076875406354812,
			"y": -175.65354754234139,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 43.6875,
			"height": 33.57760289718236,
			"seed": 813514299,
			"groupIds": [
				"zCW9RjA3lGCmK3qdyblbn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460798342,
			"link": null,
			"locked": false,
			"fontSize": 9.32711191588399,
			"fontFamily": 3,
			"text": "MongoDB\n(read\nreplica)",
			"rawText": "MongoDB\n(read replica)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "WDMAG9ZK4cCKXgN46e3cw",
			"originalText": "MongoDB\n(read replica)",
			"lineHeight": 1.2,
			"baseline": 31
		},
		{
			"type": "ellipse",
			"version": 748,
			"versionNonce": 1343353653,
			"isDeleted": false,
			"id": "IiMJO71lxbfmjD5659rmQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -23.68502914217987,
			"y": -193.46467477800599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1817165531,
			"groupIds": [
				"zCW9RjA3lGCmK3qdyblbn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "Fn7jRCjHioQr05v3WaRpE",
					"type": "arrow"
				}
			],
			"updated": 1710460798342,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 214,
			"versionNonce": 1521112884,
			"isDeleted": false,
			"id": "Fn7jRCjHioQr05v3WaRpE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 82.9163792310526,
			"y": -248.54492187500028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.02767874012827,
			"height": 55.24386833391489,
			"seed": 1411509627,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938381,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "M-OQA4s-JjMkak4DdRHPD",
				"gap": 1.4766692763586775,
				"focus": -0.6121389712719488
			},
			"endBinding": {
				"elementId": "IiMJO71lxbfmjD5659rmQ",
				"gap": 1,
				"focus": 0.1176722169502726
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
					-64.02767874012827,
					55.24386833391489
				]
			]
		},
		{
			"type": "arrow",
			"version": 136,
			"versionNonce": 1774802612,
			"isDeleted": false,
			"id": "ru8klIlNsmgUdWTEFF30Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 98.7689958753042,
			"y": -249.02159115135896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 50.805668787289875,
			"height": 55.588973963858734,
			"seed": 1171171285,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "M-OQA4s-JjMkak4DdRHPD",
				"gap": 1,
				"focus": 0.32570226658211465
			},
			"endBinding": {
				"elementId": "H2eRjlWLiN6k89MqOnuHv",
				"gap": 4.68071745067931,
				"focus": 0.5785107329705728
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
					50.805668787289875,
					55.588973963858734
				]
			]
		},
		{
			"type": "rectangle",
			"version": 743,
			"versionNonce": 1718758357,
			"isDeleted": false,
			"id": "H2eRjlWLiN6k89MqOnuHv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 118.7580855311453,
			"y": -188.75189973682092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1331066939,
			"groupIds": [
				"1JVc3uNDZG2ZwEHuvG_dC"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yhnmpeiT"
				},
				{
					"id": "ru8klIlNsmgUdWTEFF30Q",
					"type": "arrow"
				}
			],
			"updated": 1710460979454,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 711,
			"versionNonce": 1531439413,
			"isDeleted": false,
			"id": "yhnmpeiT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 128.0392450092362,
			"y": -169.10325457359139,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 43.6875,
			"height": 33.57760289718236,
			"seed": 267499739,
			"groupIds": [
				"1JVc3uNDZG2ZwEHuvG_dC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460979454,
			"link": null,
			"locked": false,
			"fontSize": 9.32711191588399,
			"fontFamily": 3,
			"text": "MongoDB\n(read\nreplica)",
			"rawText": "MongoDB\n(read replica)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "H2eRjlWLiN6k89MqOnuHv",
			"originalText": "MongoDB\n(read replica)",
			"lineHeight": 1.2,
			"baseline": 31
		},
		{
			"type": "ellipse",
			"version": 767,
			"versionNonce": 951523669,
			"isDeleted": false,
			"id": "Sn8i2ykkMd1m6i_nLnD5U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 122.43109127341114,
			"y": -186.91438180925599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1755047291,
			"groupIds": [
				"1JVc3uNDZG2ZwEHuvG_dC"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710460979455,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 79,
			"versionNonce": 1560523700,
			"isDeleted": false,
			"id": "7Gj48b_b7CvBZhVpxw11S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 126.6505731342362,
			"y": -294.96093750000034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.99902343750023,
			"height": 2.607421875,
			"seed": 540327451,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "M-OQA4s-JjMkak4DdRHPD",
				"gap": 3.0039062499998863,
				"focus": 0.11366934959640432
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					163.99902343750023,
					-2.607421875
				]
			]
		},
		{
			"type": "rectangle",
			"version": 101,
			"versionNonce": 1981987381,
			"isDeleted": false,
			"id": "ma_1E8bJCg59Xvvho73OW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 286.5187371967364,
			"y": -322.75390625000034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.15820312500014,
			"height": 50.4833984375,
			"seed": 1001634363,
			"groupIds": [
				"7Um-vWo9JXtuXXb1bEcL3"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "_bsv7gUyTrntltU-gYJmn",
					"type": "arrow"
				}
			],
			"updated": 1710460925115,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 841445621,
			"isDeleted": false,
			"id": "5OKpimZz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 315.0587762592364,
			"y": -305.54199218750034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.67996215820312,
			"height": 20,
			"seed": 879818613,
			"groupIds": [
				"7Um-vWo9JXtuXXb1bEcL3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460925115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Kafka Queue",
			"rawText": "Kafka Queue",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kafka Queue",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 191,
			"versionNonce": 1477892725,
			"isDeleted": false,
			"id": "_bsv7gUyTrntltU-gYJmn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 441.4601434467366,
			"y": -297.83284677227533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.49319450704542,
			"height": 49.63429127211043,
			"seed": 985192123,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710461015713,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ma_1E8bJCg59Xvvho73OW",
				"focus": -0.03344831173242622,
				"gap": 2.783203125000057
			},
			"endBinding": {
				"elementId": "EVg5qRRJV06Vz8BEjBDXb",
				"focus": 0.06170401597984452,
				"gap": 3.82099666130868
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
					124.65332031250017,
					0.8553077097749906
				],
				[
					168.49319450704542,
					49.63429127211043
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1476819387,
			"isDeleted": false,
			"id": "iYt2tgAn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 504.26287782173654,
			"y": -356.26953125000034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.19993591308594,
			"height": 40,
			"seed": 729163451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710460900579,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Document based\nsearch Indexing",
			"rawText": "Document based\nsearch Indexing",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Document based\nsearch Indexing",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 248,
			"versionNonce": 1245454325,
			"isDeleted": false,
			"id": "6MbABXOcOPGwFXGSDwtlV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 294.81347486688094,
			"y": -112.92716413809057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.15820312500014,
			"height": 65.1220703125,
			"seed": 1585367579,
			"groupIds": [
				"noCbdQyTO8bKjrlF8J6Ia"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "AJ8-5-VKgALdC5XaUnIEm",
					"type": "arrow"
				}
			],
			"updated": 1710463226184,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 1408394933,
			"isDeleted": false,
			"id": "I7hwYkj6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 309.98925611688094,
			"y": -104.11368757559057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.5519256591797,
			"height": 40,
			"seed": 502582971,
			"groupIds": [
				"noCbdQyTO8bKjrlF8J6Ia"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "F8U7J1fPoWJhbUBzV7S9h",
					"type": "arrow"
				},
				{
					"id": "eptiLPbbfvDAKdzcZ2zyv",
					"type": "arrow"
				},
				{
					"id": "QtT_T_r03_Q8Rp4LgNFpE",
					"type": "arrow"
				}
			],
			"updated": 1710463226184,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Product Search \n    cache",
			"rawText": "Product Search \n    cache",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Product Search \n    cache",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 792,
			"versionNonce": 1554834907,
			"isDeleted": false,
			"id": "7elwo0DDAXUpr9NNaKpHl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 586.8244917811459,
			"y": -246.74506379932092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1288093045,
			"groupIds": [
				"gyMwTQvWkXxGMCS8quuKW"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "iIEWut4G"
				},
				{
					"id": "F8U7J1fPoWJhbUBzV7S9h",
					"type": "arrow"
				}
			],
			"updated": 1710461044113,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 781,
			"versionNonce": 1651616955,
			"isDeleted": false,
			"id": "iIEWut4G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 596.1056512592368,
			"y": -227.09641863609139,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 43.6875,
			"height": 33.57760289718236,
			"seed": 1482245845,
			"groupIds": [
				"gyMwTQvWkXxGMCS8quuKW"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710461024308,
			"link": null,
			"locked": false,
			"fontSize": 9.32711191588399,
			"fontFamily": 3,
			"text": "\nElastic-\nsearch",
			"rawText": "\nElastic-\nsearch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "7elwo0DDAXUpr9NNaKpHl",
			"originalText": "\nElastic-\nsearch",
			"lineHeight": 1.2,
			"baseline": 31
		},
		{
			"type": "ellipse",
			"version": 816,
			"versionNonce": 1956005141,
			"isDeleted": false,
			"id": "EVg5qRRJV06Vz8BEjBDXb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 590.4974975234118,
			"y": -244.90754587175599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1469293621,
			"groupIds": [
				"gyMwTQvWkXxGMCS8quuKW"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "_bsv7gUyTrntltU-gYJmn",
					"type": "arrow"
				}
			],
			"updated": 1710461015713,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 821,
			"versionNonce": 1525229109,
			"isDeleted": false,
			"id": "k7e3qe-jd7XitMYvtjH2C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 591.3606245936459,
			"y": -154.82611848682086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1584658235,
			"groupIds": [
				"VaeM70Yw2Mm-5clnyKpDA"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DB4ubCAK"
				},
				{
					"id": "eptiLPbbfvDAKdzcZ2zyv",
					"type": "arrow"
				}
			],
			"updated": 1710461051229,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 811,
			"versionNonce": 484318709,
			"isDeleted": false,
			"id": "DB4ubCAK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 600.6417840717368,
			"y": -135.17747332359133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 43.6875,
			"height": 33.57760289718236,
			"seed": 2097633243,
			"groupIds": [
				"VaeM70Yw2Mm-5clnyKpDA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710461031878,
			"link": null,
			"locked": false,
			"fontSize": 9.32711191588399,
			"fontFamily": 3,
			"text": "\nElastic-\nsearch",
			"rawText": "\nElastic-\nsearch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "k7e3qe-jd7XitMYvtjH2C",
			"originalText": "\nElastic-\nsearch",
			"lineHeight": 1.2,
			"baseline": 31
		},
		{
			"type": "ellipse",
			"version": 845,
			"versionNonce": 1605408597,
			"isDeleted": false,
			"id": "jvgQJQ6P4pKMWILFwD4p3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 595.0336303359117,
			"y": -152.98860055925593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 2141561979,
			"groupIds": [
				"VaeM70Yw2Mm-5clnyKpDA"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710461031878,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1051,
			"versionNonce": 1980724315,
			"isDeleted": false,
			"id": "XyOhAYtnRVd6PUjmuVJJV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 599.941894841999,
			"y": -54.142042781385896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1778054875,
			"groupIds": [
				"eha8HwnKVA4W63_S-GrDl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9avjwUB7"
				},
				{
					"id": "QtT_T_r03_Q8Rp4LgNFpE",
					"type": "arrow"
				}
			],
			"updated": 1710463211717,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 1042,
			"versionNonce": 1732026005,
			"isDeleted": false,
			"id": "9avjwUB7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 609.2230543200899,
			"y": -34.49339761815636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 43.6875,
			"height": 33.57760289718236,
			"seed": 1791845243,
			"groupIds": [
				"eha8HwnKVA4W63_S-GrDl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710512120019,
			"link": null,
			"locked": false,
			"fontSize": 9.32711191588399,
			"fontFamily": 3,
			"text": "\nElastic-\nsearch",
			"rawText": "\nElastic-\nsearch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "XyOhAYtnRVd6PUjmuVJJV",
			"originalText": "\nElastic-\nsearch",
			"lineHeight": 1.2,
			"baseline": 31
		},
		{
			"type": "ellipse",
			"version": 1075,
			"versionNonce": 1281569461,
			"isDeleted": false,
			"id": "8a_zcgIaWbtTLfP_hVsut",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 603.6149005842648,
			"y": -52.304524853820965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1273576475,
			"groupIds": [
				"eha8HwnKVA4W63_S-GrDl"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463211567,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 218,
			"versionNonce": 1170356660,
			"isDeleted": false,
			"id": "F8U7J1fPoWJhbUBzV7S9h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 582.8517450092368,
			"y": -191.5354476827689,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 135.9288951423557,
			"height": 92.03735806234835,
			"seed": 1469993877,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7elwo0DDAXUpr9NNaKpHl",
				"gap": 3.972746771909101,
				"focus": 0.08680657604735768
			},
			"endBinding": {
				"elementId": "I7hwYkj6",
				"gap": 7.381668090820426,
				"focus": 0.5241717060035932
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
					-135.9288951423557,
					92.03735806234835
				]
			]
		},
		{
			"type": "arrow",
			"version": 225,
			"versionNonce": 756964532,
			"isDeleted": false,
			"id": "eptiLPbbfvDAKdzcZ2zyv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 588.3644403217368,
			"y": -105.29853985981244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 138.4533092048557,
			"height": 5.450579237020889,
			"seed": 2067374171,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "k7e3qe-jd7XitMYvtjH2C",
				"gap": 2.996184271909101,
				"focus": -0.31189602003376693
			},
			"endBinding": {
				"elementId": "I7hwYkj6",
				"gap": 10.369949340820426,
				"focus": -0.5665593334563498
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
					-138.4533092048557,
					5.450579237020889
				]
			]
		},
		{
			"type": "arrow",
			"version": 244,
			"versionNonce": 269336500,
			"isDeleted": false,
			"id": "QtT_T_r03_Q8Rp4LgNFpE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 592.9591668842368,
			"y": -15.912522954500169,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 142.9601451423557,
			"height": 74.01701289250406,
			"seed": 1193637461,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XyOhAYtnRVd6PUjmuVJJV",
				"gap": 6.982727957762222,
				"focus": -0.40953807174727175
			},
			"endBinding": {
				"elementId": "I7hwYkj6",
				"gap": 10.457839965820426,
				"focus": -0.8361960847585245
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
					-142.9601451423557,
					-74.01701289250406
				]
			]
		},
		{
			"type": "arrow",
			"version": 585,
			"versionNonce": 360136372,
			"isDeleted": false,
			"id": "AJ8-5-VKgALdC5XaUnIEm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 287.71068036872725,
			"y": -76.74154824310472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 399.6055538379136,
			"height": 173.88551283615757,
			"seed": 1268403413,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938379,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6MbABXOcOPGwFXGSDwtlV",
				"focus": -0.18785780027371832,
				"gap": 7.102794498153685
			},
			"endBinding": {
				"elementId": "c_09YY7dWL1KB86nd406c",
				"gap": 10.03114204573771,
				"focus": 0.17441818397051467
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
					-376.82027767736383,
					-13.632423204048735
				],
				[
					-399.6055538379136,
					-173.88551283615757
				]
			]
		},
		{
			"type": "ellipse",
			"version": 370,
			"versionNonce": 780821371,
			"isDeleted": false,
			"id": "71F6jou1DH8HoVMJgbU0g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 147.22279270802244,
			"y": 36.21407969733508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 175.69335937500023,
			"height": 170.34179687500017,
			"seed": 643615413,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "KE5lVtU4WgVKs4fHav5Ox",
					"type": "arrow"
				}
			],
			"updated": 1710463204883,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1090,
			"versionNonce": 1371406523,
			"isDeleted": false,
			"id": "wy6y3FaEYLegH0GoNkcYj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.63987541743154,
			"y": 36.64675027301436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 1544866261,
			"groupIds": [
				"juc_sl2jWzBN1V0t_bI3a"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "D0WiroDj"
				}
			],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 1104,
			"versionNonce": 1565798747,
			"isDeleted": false,
			"id": "D0WiroDj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 149.01478489552244,
			"y": 44.28419688483508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 37.5,
			"height": 57.599999999999994,
			"seed": 2129053493,
			"groupIds": [
				"juc_sl2jWzBN1V0t_bI3a"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": " \nRiak\nDB",
			"rawText": " \nRiak\nDB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wy6y3FaEYLegH0GoNkcYj",
			"originalText": " \nRiak\nDB",
			"lineHeight": 1.2,
			"baseline": 53
		},
		{
			"type": "ellipse",
			"version": 1113,
			"versionNonce": 1142640123,
			"isDeleted": false,
			"id": "DdHHYjIyyWPPyMb7_dqwY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.61561553469733,
			"y": 38.796768200579294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1699879061,
			"groupIds": [
				"juc_sl2jWzBN1V0t_bI3a"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1092,
			"versionNonce": 1226167963,
			"isDeleted": false,
			"id": "Bgf6Z4p1db8tjB1o7OthD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 283.28050041743177,
			"y": 51.87135964801436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 959143515,
			"groupIds": [
				"MVkHNG0dDAbv8JQwiUczs"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "HKG0apFK"
				}
			],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 1107,
			"versionNonce": 720784187,
			"isDeleted": false,
			"id": "HKG0apFK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 295.65540989552267,
			"y": 59.50880625983508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 37.5,
			"height": 57.599999999999994,
			"seed": 1451547387,
			"groupIds": [
				"MVkHNG0dDAbv8JQwiUczs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": " \nRiak\nDB",
			"rawText": " \nRiak\nDB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Bgf6Z4p1db8tjB1o7OthD",
			"originalText": " \nRiak\nDB",
			"lineHeight": 1.2,
			"baseline": 53
		},
		{
			"type": "ellipse",
			"version": 1115,
			"versionNonce": 773794779,
			"isDeleted": false,
			"id": "uRzVket5eemjJbbtvs7xn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 287.25624053469755,
			"y": 54.021377575579294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 1355137947,
			"groupIds": [
				"MVkHNG0dDAbv8JQwiUczs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1092,
			"versionNonce": 1721956475,
			"isDeleted": false,
			"id": "QqDs6j9aYZbOKqhYCTaeB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 209.53050041743165,
			"y": 175.62135964801453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 62.24981895618179,
			"height": 72.87489322364144,
			"seed": 69924053,
			"groupIds": [
				"nRtdqnfO3XcOpi3q11qBM"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "NdorRWdJ"
				}
			],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			}
		},
		{
			"type": "text",
			"version": 1106,
			"versionNonce": 1111765275,
			"isDeleted": false,
			"id": "NdorRWdJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 221.90540989552255,
			"y": 183.25880625983524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 37.5,
			"height": 57.599999999999994,
			"seed": 956273205,
			"groupIds": [
				"nRtdqnfO3XcOpi3q11qBM"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": " \nRiak\nDB",
			"rawText": " \nRiak\nDB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "QqDs6j9aYZbOKqhYCTaeB",
			"originalText": " \nRiak\nDB",
			"lineHeight": 1.2,
			"baseline": 53
		},
		{
			"type": "ellipse",
			"version": 1115,
			"versionNonce": 1383421371,
			"isDeleted": false,
			"id": "bMmQOSg--n87EFaLuH8G4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 213.50624053469744,
			"y": 177.77137757557946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 57.390430082037135,
			"height": 18.073556463957818,
			"seed": 404325269,
			"groupIds": [
				"nRtdqnfO3XcOpi3q11qBM"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463204883,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 837,
			"versionNonce": 1050166452,
			"isDeleted": false,
			"id": "KE5lVtU4WgVKs4fHav5Ox",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -40.30650416697779,
			"y": 140.27815329396276,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.76885093966533,
			"height": 1.1849517615744958,
			"seed": 833820795,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938381,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Y5xwY5DPmf8AQh_YNnlXT",
				"gap": 1.4347528217359695,
				"focus": -0.1922965366555358
			},
			"endBinding": {
				"elementId": "71F6jou1DH8HoVMJgbU0g",
				"gap": 7.0371822520757235,
				"focus": -0.24278325153935193
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
					182.76885093966533,
					1.1849517615744958
				]
			]
		},
		{
			"type": "text",
			"version": 631,
			"versionNonce": 1141263109,
			"isDeleted": false,
			"id": "YsItrLj2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 425.5648781162429,
			"y": 173.55782969733514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.1197509765625,
			"height": 75,
			"seed": 123785627,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710730922303,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In order to handle concurrency\nin adding data to cart\nwe opt for:",
			"rawText": "In order to handle concurrency\nin adding data to cart\nwe opt for:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order to handle concurrency\nin adding data to cart\nwe opt for:",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 390,
			"versionNonce": 539553429,
			"isDeleted": false,
			"id": "kDgvrdZYrg_GbTUsZUubh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 385.55510682175884,
			"y": 96.84131568607125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 116.9002527410072,
			"height": 54.32128906250006,
			"seed": 2065655963,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463270435,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					104.94140625000011,
					2.5048828125
				],
				[
					116.9002527410072,
					54.32128906250006
				]
			]
		},
		{
			"type": "rectangle",
			"version": 934,
			"versionNonce": 931897035,
			"isDeleted": false,
			"id": "rqxuuYJxxdxeD3gRf6G32",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 390.99936271148476,
			"y": 265.9814283022952,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 359.3674538352276,
			"height": 164.45712002840915,
			"seed": 1634278491,
			"groupIds": [
				"4dwcxlhG8QThXUGbTMOm8"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710730951097,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1119,
			"versionNonce": 1642302827,
			"isDeleted": false,
			"id": "OqN9iGRR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 424.0853002114849,
			"y": 273.4650145501793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 320.1197509765625,
			"height": 150,
			"seed": 1817893115,
			"groupIds": [
				"4dwcxlhG8QThXUGbTMOm8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710730951097,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Set based CRDT for\nLeaderless replication using \nRiak. \n* It uses consistent hashing\nto add data to shards (based \non accnt Id) ",
			"rawText": "* Set based CRDT for\nLeaderless replication using \nRiak. \n* It uses consistent hashing\nto add data to shards (based \non accnt Id) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Set based CRDT for\nLeaderless replication using \nRiak. \n* It uses consistent hashing\nto add data to shards (based \non accnt Id) ",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "rectangle",
			"version": 311,
			"versionNonce": 11179355,
			"isDeleted": false,
			"id": "hAJmby3rRTc52oK2L_rbE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.07377062013808,
			"y": 408.5231780772772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.15820312500014,
			"height": 50.4833984375,
			"seed": 963510075,
			"groupIds": [
				"_BTGdDkXMbOgALVq9v-jJ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "E5bjYQ2MKUuHKPnm8KpYx",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 1294154395,
			"isDeleted": false,
			"id": "vc7bAJgN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 117.61380968263808,
			"y": 425.7350921397772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.67996215820312,
			"height": 20,
			"seed": 2072010715,
			"groupIds": [
				"_BTGdDkXMbOgALVq9v-jJ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Dt2iBi3xrg-yLs6TLvo_q",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Kafka Queue",
			"rawText": "Kafka Queue",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kafka Queue",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 523,
			"versionNonce": 721850676,
			"isDeleted": false,
			"id": "E5bjYQ2MKUuHKPnm8KpYx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.874471567362058,
			"y": 430.6617324552113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.94824218750009,
			"height": 0.7864458682705617,
			"seed": 1138419067,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938381,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "o0PJ936vQm_AXjYo4z8QD",
				"gap": 1.012877821735998,
				"focus": -0.18288897488785558
			},
			"endBinding": {
				"elementId": "hAJmby3rRTc52oK2L_rbE",
				"gap": 1.0000000000000142,
				"focus": 0.17289269899980045
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
					105.94824218750009,
					-0.7864458682705617
				]
			]
		},
		{
			"type": "rectangle",
			"version": 213,
			"versionNonce": 863689851,
			"isDeleted": false,
			"id": "RNBZTX_XZOvBCkwzWgA5r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 78.96146593263802,
			"y": 551.8117522960273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 204.24804687500023,
			"height": 138.3300781250001,
			"seed": 399477781,
			"groupIds": [
				"57Ru9LYqxJyyE7zZnBFLA"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "w5AoruIWxOYEvqmpl7s9l",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 839600731,
			"isDeleted": false,
			"id": "3GyLHIWW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 116.23685655763802,
			"y": 565.1076507335273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 133.15191650390625,
			"height": 40,
			"seed": 588222549,
			"groupIds": [
				"57Ru9LYqxJyyE7zZnBFLA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Dt2iBi3xrg-yLs6TLvo_q",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Spark Streaming \nconsumers",
			"rawText": "Spark Streaming \nconsumers",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Spark Streaming \nconsumers",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 257,
			"versionNonce": 1805299611,
			"isDeleted": false,
			"id": "tzaRA6ntiOLTzanBJYt6-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 131.48587999513813,
			"y": 616.3283538585274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 43.4814453125,
			"height": 41.30859375,
			"seed": 229502683,
			"groupIds": [
				"57Ru9LYqxJyyE7zZnBFLA"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 262,
			"versionNonce": 964166715,
			"isDeleted": false,
			"id": "41ef1Xj1BFrZ8bjXnT55y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 220.03324327638825,
			"y": 594.1457366710274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 43.4814453125,
			"height": 41.30859375,
			"seed": 456040821,
			"groupIds": [
				"57Ru9LYqxJyyE7zZnBFLA"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "w5AoruIWxOYEvqmpl7s9l",
					"type": "arrow"
				}
			],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 261,
			"versionNonce": 1442956507,
			"isDeleted": false,
			"id": "vcHCClNXG3NEty7haxzVI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 186.23929796388825,
			"y": 643.4230804210274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 43.4814453125,
			"height": 41.30859375,
			"seed": 975241627,
			"groupIds": [
				"57Ru9LYqxJyyE7zZnBFLA"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710463162367,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 267,
			"versionNonce": 1458917397,
			"isDeleted": false,
			"id": "f-mRUIiBJ2Wv0mD4sWDrK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 454.4247838618205,
			"y": 549.7507064571405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120.46875000000023,
			"height": 130.8349609375001,
			"seed": 1435561147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "sWscjZvl"
				},
				{
					"id": "w5AoruIWxOYEvqmpl7s9l",
					"type": "arrow"
				}
			],
			"updated": 1710463175135,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 183,
			"versionNonce": 1348240757,
			"isDeleted": false,
			"id": "sWscjZvl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 472.6431905390667,
			"y": 595.1681869258905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 84.03193664550781,
			"height": 40,
			"seed": 1025892475,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463175135,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "MYSQL \nOrders DB",
			"rawText": "MYSQL \nOrders DB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "f-mRUIiBJ2Wv0mD4sWDrK",
			"originalText": "MYSQL \nOrders DB",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 504,
			"versionNonce": 85701941,
			"isDeleted": false,
			"id": "Dt2iBi3xrg-yLs6TLvo_q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 167.12076301065383,
			"y": 460.2883147960272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.6400431938077134,
			"height": 91.97265625000011,
			"seed": 700903573,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463162635,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vc7bAJgN",
				"focus": 0.034710237359475586,
				"gap": 14.55322265625
			},
			"endBinding": {
				"elementId": "3GyLHIWW",
				"focus": -0.2011918297109795,
				"gap": 12.8466796875
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
					1.6400431938077134,
					91.97265625000011
				]
			]
		},
		{
			"type": "arrow",
			"version": 539,
			"versionNonce": 314598068,
			"isDeleted": false,
			"id": "w5AoruIWxOYEvqmpl7s9l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 284.92826280763813,
			"y": 626.0052510958319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165.80511480418238,
			"height": 10.550220618506728,
			"seed": 1282209691,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739938382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RNBZTX_XZOvBCkwzWgA5r",
				"gap": 1.7187499999998863,
				"focus": 0.1537867647272498
			},
			"endBinding": {
				"elementId": "f-mRUIiBJ2Wv0mD4sWDrK",
				"gap": 3.69140625,
				"focus": 0.054595788962303465
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
					165.80511480418238,
					-10.550220618506728
				]
			]
		},
		{
			"type": "ellipse",
			"version": 162,
			"versionNonce": 1802358389,
			"isDeleted": false,
			"id": "sVfpbTzJMnV9nFlyt6L1X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 460.017417371741,
			"y": 554.5429877951806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.45117187500023,
			"height": 18.984375,
			"seed": 681035573,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710463179650,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 260,
			"versionNonce": 632099957,
			"isDeleted": false,
			"id": "L0UQOp4iVuTxk-yGQskWZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1158.1574982867503,
			"y": -433.94238514074243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 543.1201019324112,
			"height": 243.59839548940397,
			"seed": 1605891989,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710463115932,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 672534293,
			"isDeleted": false,
			"id": "SOGkPXy8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1126.2631154507649,
			"y": -422.37352379327797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 463.51177978515625,
			"height": 280,
			"seed": 1263656251,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463103543,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "    Functional requirements:\n1. Search for Items with text\n2. Add Products to cart with \n   concurrency\n3. Complete an Order with list of\n   items\n\n ",
			"rawText": "    Functional requirements:\n1. Search for Items with text\n2. Add Products to cart with \n   concurrency\n3. Complete an Order with list of\n   items\n\n ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    Functional requirements:\n1. Search for Items with text\n2. Add Products to cart with \n   concurrency\n3. Complete an Order with list of\n   items\n\n ",
			"lineHeight": 1.25,
			"baseline": 270
		},
		{
			"type": "rectangle",
			"version": 342,
			"versionNonce": 1976204245,
			"isDeleted": false,
			"id": "UsYXhumC9LUugMTifFJ3C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1158.4098272648832,
			"y": -103.87445354491581,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.9849030640969,
			"height": 226.3535121838711,
			"seed": 2020498901,
			"groupIds": [
				"ZK9zROwZt3FOyftuURgM7"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710463121566,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 2065054005,
			"isDeleted": false,
			"id": "TMPNOM0W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1033.5502394853993,
			"y": -82.22462722112164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 262.6678771972656,
			"height": 70,
			"seed": 128134843,
			"groupIds": [
				"ZK9zROwZt3FOyftuURgM7"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463121566,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Capacity Estimate:\n",
			"rawText": "Capacity Estimate:\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Capacity Estimate:\n",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 348,
			"versionNonce": 1321421461,
			"isDeleted": false,
			"id": "kZ0lY9OG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1125.9603206770053,
			"y": -22.41545000427311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 483.75579833984375,
			"height": 105,
			"seed": 1358967413,
			"groupIds": [
				"ZK9zROwZt3FOyftuURgM7"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463121566,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "1.  1 billion users around the globe\n2. 100M products, each of size 1kb\n3. 100M order / day",
			"rawText": "1.  1 billion users around the globe\n2. 100M products, each of size 1kb\n3. 100M order / day",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1.  1 billion users around the globe\n2. 100M products, each of size 1kb\n3. 100M order / day",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "rectangle",
			"version": 479,
			"versionNonce": 530364219,
			"isDeleted": false,
			"id": "40BG55ymoSecgyOsODb8O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1172.1869894709343,
			"y": 188.00168486066764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 626.9221602700017,
			"height": 226.3535121838711,
			"seed": 746486389,
			"groupIds": [
				"H9RE5a6jnMZu7qGWN2BDc"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710463128049,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 564,
			"versionNonce": 454563803,
			"isDeleted": false,
			"id": "4zMsCDMl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -939.0205948774776,
			"y": 209.41360100507939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.73194885253906,
			"height": 35,
			"seed": 1141990357,
			"groupIds": [
				"H9RE5a6jnMZu7qGWN2BDc"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463128049,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "API Design",
			"rawText": "API Design",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Design",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 564,
			"versionNonce": 496919675,
			"isDeleted": false,
			"id": "TBQCijFf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1140.1628374461943,
			"y": 269.46068840131034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 590.625,
			"height": 100.80000000000001,
			"seed": 809509173,
			"groupIds": [
				"H9RE5a6jnMZu7qGWN2BDc"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710463128049,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 3,
			"text": "1. /searchProduct(queryString)\n2. addToCart(userId,productId)\n3. placeOrder(userId, productIdList)",
			"rawText": "1. /searchProduct(queryString)\n2. addToCart(userId,productId)\n3. placeOrder(userId, productIdList)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. /searchProduct(queryString)\n2. addToCart(userId,productId)\n3. placeOrder(userId, productIdList)",
			"lineHeight": 1.2,
			"baseline": 94
		},
		{
			"type": "rectangle",
			"version": 639,
			"versionNonce": 827018133,
			"isDeleted": false,
			"id": "pjJhWZNnXNNMcb2Dcnyvt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1179.24138675959,
			"y": 492.6144694836347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 657.6558298065764,
			"height": 226.3535121838711,
			"seed": 1277043925,
			"groupIds": [
				"OG2AgMXB_3UfU4Q9l1xo1"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598212385,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 753,
			"versionNonce": 1969688821,
			"isDeleted": false,
			"id": "VpNZwVrI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -975.9074867808051,
			"y": 513.5649840680323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.05992126464844,
			"height": 35,
			"seed": 2064433717,
			"groupIds": [
				"OG2AgMXB_3UfU4Q9l1xo1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598212385,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Database Schema",
			"rawText": "Database Schema",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Database Schema",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 820,
			"versionNonce": 1084435029,
			"isDeleted": false,
			"id": "4HooKrpr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1147.2172347348499,
			"y": 574.0734730242774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 607.03125,
			"height": 134.4,
			"seed": 16823189,
			"groupIds": [
				"OG2AgMXB_3UfU4Q9l1xo1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598212385,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 3,
			"text": "1. Accounts(email, pw_hash, addr)\n2. Cart(accntId, productsSet)\n3. Products(id, name, metadata)\n4. Orders(accntId, productIds, price)",
			"rawText": "1. Accounts(email, pw_hash, addr)\n2. Cart(accntId, productsSet)\n3. Products(id, name, metadata)\n4. Orders(accntId, productIds, price)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Accounts(email, pw_hash, addr)\n2. Cart(accntId, productsSet)\n3. Products(id, name, metadata)\n4. Orders(accntId, productIds, price)",
			"lineHeight": 1.2,
			"baseline": 128
		},
		{
			"type": "rectangle",
			"version": 996,
			"versionNonce": 1521609573,
			"isDeleted": false,
			"id": "Wjsuc9YfaSJ_m3jWrtoY-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 7.640351612311235,
			"y": 717.5356587037227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.1472833806821,
			"height": 102.11716157608016,
			"seed": 1856197419,
			"groupIds": [
				"-ke8wXoiaUFXrRiL5Uzo2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710730897409,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1375,
			"versionNonce": 1379969387,
			"isDeleted": false,
			"id": "ZGFkZTxa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 30.91417231972747,
			"y": 732.1137153935687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.53680419921875,
			"height": 71.46284605967239,
			"seed": 1489352139,
			"groupIds": [
				"-ke8wXoiaUFXrRiL5Uzo2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710730897409,
			"link": null,
			"locked": false,
			"fontSize": 19.05675894924597,
			"fontFamily": 1,
			"text": "Breaks order into individual\nproducts, partitioned on \nproductID. ",
			"rawText": "Breaks order into individual\nproducts, partitioned on \nproductID. ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Breaks order into individual\nproducts, partitioned on \nproductID. ",
			"lineHeight": 1.25,
			"baseline": 64
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
		"currentItemOpacity": 40,
		"currentItemFontFamily": 3,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1308.5281941973478,
		"scrollY": 570.9531108275273,
		"zoom": {
			"value": 0.55
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