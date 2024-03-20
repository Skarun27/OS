---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
         Functional requirements:
1. Make posts including text, images, video
2. Follow other users
3. Browse through my news feed

         Extended requirements:
1. Liking and replying to posts ^m0ygT5wZ

Capacity Estimate:
 ^32n8ZpQ7

1.  200M DAU
2. 100M posts / day
3. Each users follows ~200 users
4. 300Bytes per tweet
5. ~30gb tweets / day
6. 55tb tweets / month
7. 6gb daily cache storage (20% of 
   daily tweets)
8. 30gb cache / month
9. 6tb of cache/day if caching each 
   user's home feed on a seperate 
   server. ( read : write -> 100 : 1 )
10. Write cache estimate : 6gb / day
11. Read cache estimate : 6tb / day ^Vaa1hVBy

API Design ^PluBvPi1

1. POST /createPost(user_id, content, 
   create time, metadata)
2. GET /getFeed(userId, productId)
3. POST /follow(userId1, userId2) ^WrcJXCZI

Database Schema ^r7R1Jynu

Client ^7C9AK02U

LB ^KSW9M6tX

Follow
service ^j91XhfwA

Post service ^xLvSiKQw

Feed
service ^fyZigkfA

UserFollows Cassandra Table ^uBdQUV0n

Log based Message Broker (Kafka) ^tbNqSlzP

Apache Flink Consumer cluster ^JjStc9lJ

changed data ^FPklgbLF

In-memory Message Broker (RabbitMQ) ^dXfiyYmw

Note:
In-memory MQ as persisting
the data is not a priority here, 
rather we need higher throughput
and low latency. ^nNbR7taQ

Note:
Log-based MQ as persisting
the data is a priority here, 
bc the data is already stored in
cassandra and also the order
posts matter. ^OvA7deZM

Note:
Cassandra follows leaderless 
replication. It streams all the changed data
to Kafka (a log-based Message Broker)
as data persistence and order of 
posts matter. ^45T6BmYf

  Posts table
userId: int
content: string
Metadata: json ^9jdLw0Ce

  Users table
userId: int
email: string
pw_hash: string ^yGxyLWp4

  UserFollows table
user1: int
user2: int ^RSuWm24p

Feed
Cache ^cwC6RFJX

Post 
Cache ^wJtcgAsj

Flink ^5GVoK36x

Flink ^EdFOWVbz

Flink ^dRHzbDr0

Post Cassandra DB store ^3in14O1s

 Flink is designed to process large volumes of data
 in real-time, doing all sorts of tasks like sorting, 
analyzing, and aggregating the data as it flows by, 
asynchronously. Here, loading followers for the
users creating the post. ^IkEjt7Rs

Changes in the UserFollows table are sent to Kafka, 
which acts as a buffer and a reliable
 conduit to Flink. This means Flink doesn't 
have to query the database directly, 
which reduces the load on Cassandra and allows 
Flink to process data at its own pace. ^wBUQ9nni

CDN ^LKKOvRkz

S3 ^NRBUnI81

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
			"version": 792,
			"versionNonce": 1613698011,
			"isDeleted": false,
			"id": "m0ygT5wZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -522.4289967860013,
			"y": -408.28457198587165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 415.19964599609375,
			"height": 175,
			"seed": 2064357045,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514424254,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "         Functional requirements:\n1. Make posts including text, images, video\n2. Follow other users\n3. Browse through my news feed\n\n         Extended requirements:\n1. Liking and replying to posts",
			"rawText": "         Functional requirements:\n1. Make posts including text, images, video\n2. Follow other users\n3. Browse through my news feed\n\n         Extended requirements:\n1. Liking and replying to posts",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "         Functional requirements:\n1. Make posts including text, images, video\n2. Follow other users\n3. Browse through my news feed\n\n         Extended requirements:\n1. Liking and replying to posts",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "rectangle",
			"version": 871,
			"versionNonce": 1080590139,
			"isDeleted": false,
			"id": "QLcQlICxr3V1PTFdVqIZS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 603.4638580568644,
			"y": -387.49564175856415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 411.7466218140969,
			"height": 427.2636684338711,
			"seed": 1778552181,
			"groupIds": [
				"EmFj3N7i_VplqVzldy2wf"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514431305,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 995,
			"versionNonce": 1059774427,
			"isDeleted": false,
			"id": "32n8ZpQ7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.2738877632161625,
			"x": 719.9420119148979,
			"y": -371.0200815536669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.61991228376115,
			"height": 50,
			"seed": 2107315925,
			"groupIds": [
				"EmFj3N7i_VplqVzldy2wf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514431305,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Capacity Estimate:\n",
			"rawText": "Capacity Estimate:\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Capacity Estimate:\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 1322,
			"versionNonce": 1142434939,
			"isDeleted": false,
			"id": "Vaa1hVBy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 627.9680521447422,
			"y": -336.13429446792145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 369.2197265625,
			"height": 350,
			"seed": 337343541,
			"groupIds": [
				"EmFj3N7i_VplqVzldy2wf"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514431305,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1.  200M DAU\n2. 100M posts / day\n3. Each users follows ~200 users\n4. 300Bytes per tweet\n5. ~30gb tweets / day\n6. 55tb tweets / month\n7. 6gb daily cache storage (20% of \n   daily tweets)\n8. 30gb cache / month\n9. 6tb of cache/day if caching each \n   user's home feed on a seperate \n   server. ( read : write -> 100 : 1 )\n10. Write cache estimate : 6gb / day\n11. Read cache estimate : 6tb / day",
			"rawText": "1.  200M DAU\n2. 100M posts / day\n3. Each users follows ~200 users\n4. 300Bytes per tweet\n5. ~30gb tweets / day\n6. 55tb tweets / month\n7. 6gb daily cache storage (20% of \n   daily tweets)\n8. 30gb cache / month\n9. 6tb of cache/day if caching each \n   user's home feed on a seperate \n   server. ( read : write -> 100 : 1 )\n10. Write cache estimate : 6gb / day\n11. Read cache estimate : 6tb / day",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1.  200M DAU\n2. 100M posts / day\n3. Each users follows ~200 users\n4. 300Bytes per tweet\n5. ~30gb tweets / day\n6. 55tb tweets / month\n7. 6gb daily cache storage (20% of \n   daily tweets)\n8. 30gb cache / month\n9. 6tb of cache/day if caching each \n   user's home feed on a seperate \n   server. ( read : write -> 100 : 1 )\n10. Write cache estimate : 6gb / day\n11. Read cache estimate : 6tb / day",
			"lineHeight": 1.25,
			"baseline": 343
		},
		{
			"type": "rectangle",
			"version": 273,
			"versionNonce": 511041659,
			"isDeleted": false,
			"id": "jcYEvaBLc_e7fGqgzOh01",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -542.3405728130315,
			"y": -420.90527448734866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 465.8046875,
			"height": 208.8046875,
			"seed": 1290025723,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514424254,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 960,
			"versionNonce": 164164443,
			"isDeleted": false,
			"id": "R1vg9Gjw0oxKE__A9kWCA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3.916342468264702,
			"y": -396.7354343460933,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 470.2091986663851,
			"height": 169.7714809338711,
			"seed": 1643892629,
			"groupIds": [
				"cKvlrY-acC2lWSKfHPf3C"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710597490681,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1105,
			"versionNonce": 1218957307,
			"isDeleted": false,
			"id": "PluBvPi1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 175.15070444064497,
			"y": -387.51857446248084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 108.37996346609933,
			"height": 25,
			"seed": 1164383477,
			"groupIds": [
				"cKvlrY-acC2lWSKfHPf3C"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710597490681,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "API Design",
			"rawText": "API Design",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Design",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1257,
			"versionNonce": 1287788699,
			"isDeleted": false,
			"id": "WrcJXCZI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 19.888794302285646,
			"y": -350.3306402912714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 454.21875,
			"height": 97.9662334402867,
			"seed": 436383317,
			"groupIds": [
				"cKvlrY-acC2lWSKfHPf3C"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710597490681,
			"link": null,
			"locked": false,
			"fontSize": 20.409631966726398,
			"fontFamily": 3,
			"text": "1. POST /createPost(user_id, content, \n   create time, metadata)\n2. GET /getFeed(userId, productId)\n3. POST /follow(userId1, userId2)",
			"rawText": "1. POST /createPost(user_id, content, \n   create time, metadata)\n2. GET /getFeed(userId, productId)\n3. POST /follow(userId1, userId2)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. POST /createPost(user_id, content, \n   create time, metadata)\n2. GET /getFeed(userId, productId)\n3. POST /follow(userId1, userId2)",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "rectangle",
			"version": 1049,
			"versionNonce": 1156401787,
			"isDeleted": false,
			"id": "jF61iOwryQQiQXzc16PF1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -251.71473519964132,
			"y": -173.59078224126404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 617.9847647466187,
			"height": 199.1542934338711,
			"seed": 1258403003,
			"groupIds": [
				"UpCDcnYesZ3kVQ-vUoCC1"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1134,
			"versionNonce": 2139169036,
			"isDeleted": false,
			"id": "r7R1Jynu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -38.311208121730886,
			"y": -159.9326358568537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.5996896044544,
			"height": 24.957805754507003,
			"seed": 1543595355,
			"groupIds": [
				"UpCDcnYesZ3kVQ-vUoCC1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710765706709,
			"link": null,
			"locked": false,
			"fontSize": 19.966244603605602,
			"fontFamily": 1,
			"text": "Database Schema",
			"rawText": "Database Schema",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Database Schema",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 466,
			"versionNonce": 2143348219,
			"isDeleted": false,
			"id": "hrbf_DFgM736i0RESTe4w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -740.1583979838567,
			"y": 699.3389820841236,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 1068712539,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "7C9AK02U"
				},
				{
					"id": "KsTHZWzOgArjZ-E87SV6k",
					"type": "arrow"
				},
				{
					"id": "YW8mKGB2rJ1j6jkyE_Yvq",
					"type": "arrow"
				}
			],
			"updated": 1710593709989,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 395,
			"versionNonce": 321908501,
			"isDeleted": false,
			"id": "7C9AK02U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -727.9954798930364,
			"y": 717.7979664591236,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.099945068359375,
			"height": 25,
			"seed": 175128315,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Client",
			"rawText": "Client",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hrbf_DFgM736i0RESTe4w",
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 664,
			"versionNonce": 760540629,
			"isDeleted": false,
			"id": "gFYHpKTzAZiQXs_yLUNdl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -546.8605365086553,
			"y": 700.150565303063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 65.67968750000001,
			"height": 60,
			"seed": 967092123,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "KSW9M6tX"
				},
				{
					"id": "KsTHZWzOgArjZ-E87SV6k",
					"type": "arrow"
				},
				{
					"id": "e9x8FrX15BU3p5F57Nhk-",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 608,
			"versionNonce": 2088921909,
			"isDeleted": false,
			"id": "KSW9M6tX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.5486087132451,
			"y": 720.150565303063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.215988159179688,
			"height": 20,
			"seed": 595786811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "LB",
			"rawText": "LB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gFYHpKTzAZiQXs_yLUNdl",
			"originalText": "LB",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 541,
			"versionNonce": 1059642197,
			"isDeleted": false,
			"id": "fiDwpdB1mt3e5cDiLbggb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -341.77327583921215,
			"y": 269.60233820061694,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 67.31640625,
			"seed": 871218395,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "j91XhfwA"
				},
				{
					"id": "BYYon07Mw3YRs0Fh1LY-8",
					"type": "arrow"
				},
				{
					"id": "06lv4R_e9rtd34ozOK4jd",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 502,
			"versionNonce": 1484564661,
			"isDeleted": false,
			"id": "j91XhfwA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -329.0483689178254,
			"y": 283.26054132561694,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.97596740722656,
			"height": 40,
			"seed": 913795451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Follow\nservice",
			"rawText": "Follow\nservice",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "fiDwpdB1mt3e5cDiLbggb",
			"originalText": "Follow\nservice",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 841,
			"versionNonce": 1302350267,
			"isDeleted": false,
			"id": "9EHZepHr0ExQvUgRXw2k9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -334.2517508790545,
			"y": 699.225131192071,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 1617068571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xLvSiKQw"
				},
				{
					"id": "e9x8FrX15BU3p5F57Nhk-",
					"type": "arrow"
				},
				{
					"id": "3uQ5Mm3Hz8l66_FBNTkQm",
					"type": "arrow"
				},
				{
					"id": "8rehYCMqb3XjunxICNudL",
					"type": "arrow"
				}
			],
			"updated": 1710593676240,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 797,
			"versionNonce": 346826293,
			"isDeleted": false,
			"id": "xLvSiKQw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -321.5268439576678,
			"y": 710.184115567071,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.97596740722656,
			"height": 40,
			"seed": 446793403,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Post\nservice",
			"rawText": "Post service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "9EHZepHr0ExQvUgRXw2k9",
			"originalText": "Post service",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 705,
			"versionNonce": 331904597,
			"isDeleted": false,
			"id": "Zz6Brb3QV6BBpBsMcIPgB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -311.3978432794388,
			"y": 1003.6959989427664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 60,
			"seed": 198637403,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "fyZigkfA"
				},
				{
					"id": "B8UmouJD8SYb39ooGk0C1",
					"type": "arrow"
				},
				{
					"id": "lAXR_vkEc3BMAzu7Ayr1l",
					"type": "arrow"
				},
				{
					"id": "Ta44X2Y0GMV3gM2bEKNQe",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 662,
			"versionNonce": 1282466741,
			"isDeleted": false,
			"id": "fyZigkfA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.6729363580521,
			"y": 1013.6959989427664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.97596740722656,
			"height": 40,
			"seed": 1649759227,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Feed\nservice",
			"rawText": "Feed\nservice",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Zz6Brb3QV6BBpBsMcIPgB",
			"originalText": "Feed\nservice",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 1500,
			"versionNonce": 1186186892,
			"isDeleted": false,
			"id": "KsTHZWzOgArjZ-E87SV6k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -658.6779292338567,
			"y": 732.9722450339043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 111.406278223149,
			"height": 0.9205240315576475,
			"seed": 1579097243,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912887,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hrbf_DFgM736i0RESTe4w",
				"gap": 3.0546875,
				"focus": 0.074322542699949
			},
			"endBinding": {
				"elementId": "gFYHpKTzAZiQXs_yLUNdl",
				"gap": 3.0401829284229223,
				"focus": -0.13389828855919278
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
					111.406278223149,
					0.9205240315576475
				]
			]
		},
		{
			"type": "arrow",
			"version": 954,
			"versionNonce": 826425868,
			"isDeleted": false,
			"id": "BYYon07Mw3YRs0Fh1LY-8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -442.32203796219005,
			"y": 583.0453226083553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.5487621229779,
			"height": 288.12186296697496,
			"seed": 451334459,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912892,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "fiDwpdB1mt3e5cDiLbggb",
				"gap": 1,
				"focus": 0.48855071019622026
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
					99.5487621229779,
					-288.12186296697496
				]
			]
		},
		{
			"type": "arrow",
			"version": 1758,
			"versionNonce": 771415052,
			"isDeleted": false,
			"id": "e9x8FrX15BU3p5F57Nhk-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -479.66767697984136,
			"y": 732.8655799195978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 141.38467610078686,
			"height": 3.334078882521567,
			"seed": 437187035,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912899,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gFYHpKTzAZiQXs_yLUNdl",
				"gap": 3.025097321334627,
				"focus": 0.11750380601630672
			},
			"endBinding": {
				"elementId": "9EHZepHr0ExQvUgRXw2k9",
				"gap": 4.03125,
				"focus": 0.0524525641123095
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
					141.38467610078686,
					-3.334078882521567
				]
			]
		},
		{
			"type": "arrow",
			"version": 1389,
			"versionNonce": 418632844,
			"isDeleted": false,
			"id": "B8UmouJD8SYb39ooGk0C1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -441.35708297970166,
			"y": 576.4448841198782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.70849336477613,
			"height": 461.55582102725566,
			"seed": 212467323,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912899,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zz6Brb3QV6BBpBsMcIPgB",
				"gap": 8.102399085954573,
				"focus": -0.4916092583371481
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
					461.55582102725566
				]
			]
		},
		{
			"type": "rectangle",
			"version": 394,
			"versionNonce": 742006453,
			"isDeleted": false,
			"id": "y4odxgE3dh7WI1aSWdi-W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 23.332536878596898,
			"y": 270.52167176002627,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 176959355,
			"groupIds": [
				"aqDynuPkQc33vIN-deZtH",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 400,
			"versionNonce": 1296990229,
			"isDeleted": false,
			"id": "81GJW-WYZYl-PQcBycZKK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 30.1544928639903,
			"y": 275.1182238619348,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 1676263227,
			"groupIds": [
				"aqDynuPkQc33vIN-deZtH",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 377,
			"versionNonce": 68138357,
			"isDeleted": false,
			"id": "WCPlH_H-Q5yuofCEhlaPK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 116.12683382370994,
			"y": 270.4796301249477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 1152631189,
			"groupIds": [
				"b1iTTQzfIHgF0w5AC_uNL",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 383,
			"versionNonce": 734215893,
			"isDeleted": false,
			"id": "vokf7VkaI3E9_WbVifG2L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 122.94878980910346,
			"y": 275.0761822268563,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 810600181,
			"groupIds": [
				"b1iTTQzfIHgF0w5AC_uNL",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 395,
			"versionNonce": 452893749,
			"isDeleted": false,
			"id": "KXLHmYhonuQk_4ucUqWw9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 209.0220306930113,
			"y": 267.86183764739746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 1369427733,
			"groupIds": [
				"QntyGqX9eP0nmGNXz6Fuv",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 401,
			"versionNonce": 967265685,
			"isDeleted": false,
			"id": "pLgBxzOc7YkAxYIVwL1o_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 215.8439866784048,
			"y": 272.458389749306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 794764405,
			"groupIds": [
				"QntyGqX9eP0nmGNXz6Fuv",
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 357,
			"versionNonce": 1458754293,
			"isDeleted": false,
			"id": "q7iQQevue0DtpFTMEoIN8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -0.07063998172975516,
			"y": 247.49406683973356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 304.13479370871437,
			"height": 128.439997940279,
			"seed": 938336155,
			"groupIds": [
				"ysxsBxiqGj1GsVURbpIhE"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "06lv4R_e9rtd34ozOK4jd",
					"type": "arrow"
				},
				{
					"id": "lSF4sqH2KcfP9FkMpbk7-",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 363,
			"versionNonce": 474623756,
			"isDeleted": false,
			"id": "06lv4R_e9rtd34ozOK4jd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -257.1131968512575,
			"y": 307.1483442403554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 253.29804857187548,
			"height": 3.8117749137777537,
			"seed": 724946997,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912892,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fiDwpdB1mt3e5cDiLbggb",
				"gap": 6.234297737954648,
				"focus": 0.13348744922626507
			},
			"endBinding": {
				"elementId": "q7iQQevue0DtpFTMEoIN8",
				"gap": 3.74450829765226,
				"focus": 0.16121639211043076
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
					253.29804857187548,
					-3.8117749137777537
				]
			]
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 1587228789,
			"isDeleted": false,
			"id": "uBdQUV0n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1.8357416869239387,
			"y": 205.0824653726123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 291.59979248046875,
			"height": 25,
			"seed": 676679291,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "UserFollows Cassandra Table",
			"rawText": "UserFollows Cassandra Table",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "UserFollows Cassandra Table",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 253,
			"versionNonce": 1025989077,
			"isDeleted": false,
			"id": "rnx1pmXolaR59PJ1KA16W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 426.6679534456366,
			"y": 453.0957034608891,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 239.04215631599055,
			"height": 90.141031135811,
			"seed": 119997109,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "tbNqSlzP"
				},
				{
					"id": "lSF4sqH2KcfP9FkMpbk7-",
					"type": "arrow"
				},
				{
					"id": "jAjUp9mlPdAZzGh287UWq",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 990502011,
			"isDeleted": false,
			"id": "tbNqSlzP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 450.16911125451077,
			"y": 473.1662190287946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 192.0398406982422,
			"height": 50,
			"seed": 2068500411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515798736,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Log based Message\nBroker (Kafka)",
			"rawText": "Log based Message Broker (Kafka)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rnx1pmXolaR59PJ1KA16W",
			"originalText": "Log based Message Broker (Kafka)",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 494,
			"versionNonce": 1804931084,
			"isDeleted": false,
			"id": "lSF4sqH2KcfP9FkMpbk7-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 307.83108423001204,
			"y": 305.5843954154377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 239.5741646118886,
			"height": 146.5113080454512,
			"seed": 2053586805,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "FPklgbLF"
				}
			],
			"updated": 1710739912907,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "q7iQQevue0DtpFTMEoIN8",
				"focus": -0.28603998069777425,
				"gap": 3.7669305030274245
			},
			"endBinding": {
				"elementId": "rnx1pmXolaR59PJ1KA16W",
				"gap": 1.0000000000001705,
				"focus": 0.1846435732248374
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
					168.79996761557277,
					18.39181395897765
				],
				[
					239.5741646118886,
					146.5113080454512
				]
			]
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 1676135893,
			"isDeleted": false,
			"id": "FPklgbLF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 620.6684238789246,
			"y": 401.1394956829219,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.29991149902344,
			"height": 25,
			"seed": 1037362235,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710513353829,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "changed data",
			"rawText": "changed data",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "lSF4sqH2KcfP9FkMpbk7-",
			"originalText": "changed data",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 427,
			"versionNonce": 457938101,
			"isDeleted": false,
			"id": "AVIhqHbKzL9Z5FcR50iIC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 290.54463008671587,
			"y": 658.9389845969876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 304.13479370871437,
			"height": 128.439997940279,
			"seed": 1596447829,
			"groupIds": [
				"N2_4hNgw5OXszWhvpyG_R"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "jAjUp9mlPdAZzGh287UWq",
					"type": "arrow"
				},
				{
					"id": "3_y54UoFo8_fi_rA0ClJc",
					"type": "arrow"
				},
				{
					"id": "JA9mSnPsGrfU-Gyv4qImV",
					"type": "arrow"
				},
				{
					"id": "qaes4RSxVCP0EVtYfuvKS",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 17761173,
			"isDeleted": false,
			"id": "JjStc9lJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 294.5313099536165,
			"y": 805.707334606141,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 293.4597473144531,
			"height": 25,
			"seed": 95051893,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JA9mSnPsGrfU-Gyv4qImV",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Apache Flink Consumer cluster",
			"rawText": "Apache Flink Consumer cluster",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Apache Flink Consumer cluster",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 592,
			"versionNonce": 2126609676,
			"isDeleted": false,
			"id": "jAjUp9mlPdAZzGh287UWq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 544.375907900401,
			"y": 547.7155701203889,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 3.1591033349894815,
			"height": 108.28330279678039,
			"seed": 537772533,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912907,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rnx1pmXolaR59PJ1KA16W",
				"gap": 4.478835523688758,
				"focus": 0.0030417244321392788
			},
			"endBinding": {
				"elementId": "AVIhqHbKzL9Z5FcR50iIC",
				"gap": 2.940111679818301,
				"focus": 0.6278082728980948
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
					-3.1591033349894815,
					108.28330279678039
				]
			]
		},
		{
			"type": "rectangle",
			"version": 430,
			"versionNonce": 1289282133,
			"isDeleted": false,
			"id": "cUjhKv_LVaKKc-U_x7ObY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -136.22644359494598,
			"y": 694.0428697374277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 231.25339792009163,
			"height": 87.5533609910579,
			"seed": 62388603,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dXfiyYmw"
				},
				{
					"id": "3uQ5Mm3Hz8l66_FBNTkQm",
					"type": "arrow"
				},
				{
					"id": "3_y54UoFo8_fi_rA0ClJc",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 392,
			"versionNonce": 1620299701,
			"isDeleted": false,
			"id": "dXfiyYmw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -113.6296594908572,
			"y": 712.8195502329567,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 186.05982971191406,
			"height": 50,
			"seed": 1460736539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In-memory Message\nBroker (RabbitMQ)",
			"rawText": "In-memory Message Broker (RabbitMQ)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "cUjhKv_LVaKKc-U_x7ObY",
			"originalText": "In-memory Message Broker (RabbitMQ)",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 674,
			"versionNonce": 252949013,
			"isDeleted": false,
			"id": "TiQCRI1-I3CTP3NE47LsB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -159.7229308853723,
			"y": 551.3315102976761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 281.99286590074075,
			"height": 128.28222436296736,
			"seed": 1878367611,
			"groupIds": [
				"Zq4gQFigepl6aSmJGtTUp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515481694,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 520,
			"versionNonce": 2053023605,
			"isDeleted": false,
			"id": "nNbR7taQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -143.06822112630647,
			"y": 567.618014114104,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 242.42604064941406,
			"height": 92.78947601410675,
			"seed": 1794024251,
			"groupIds": [
				"Zq4gQFigepl6aSmJGtTUp"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515481694,
			"link": null,
			"locked": false,
			"fontSize": 14.84631616225708,
			"fontFamily": 1,
			"text": "Note:\nIn-memory MQ as persisting\nthe data is not a priority here, \nrather we need higher throughput\nand low latency.",
			"rawText": "Note:\nIn-memory MQ as persisting\nthe data is not a priority here, \nrather we need higher throughput\nand low latency.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note:\nIn-memory MQ as persisting\nthe data is not a priority here, \nrather we need higher throughput\nand low latency.",
			"lineHeight": 1.25,
			"baseline": 87
		},
		{
			"type": "ellipse",
			"version": 883,
			"versionNonce": 718429845,
			"isDeleted": false,
			"id": "hmXCfmeWYDYyFgna_opYe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 98.90833506621192,
			"y": 413.84642375319254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.38346796493596,
			"height": 137.55817459149475,
			"seed": 1100247387,
			"groupIds": [
				"oo0Op5mwI6Kltqj9C0nzn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 925,
			"versionNonce": 1922286581,
			"isDeleted": false,
			"id": "OvA7deZM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 124.79637522971723,
			"y": 426.07087702097533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 252.14759826660156,
			"height": 115.67659636909715,
			"seed": 911445499,
			"groupIds": [
				"oo0Op5mwI6Kltqj9C0nzn"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 15.423546182546286,
			"fontFamily": 1,
			"text": "Note:\nLog-based MQ as persisting\nthe data is a priority here, \nbc the data is already stored in\ncassandra and also the order\nposts matter.",
			"rawText": "Note:\nLog-based MQ as persisting\nthe data is a priority here, \nbc the data is already stored in\ncassandra and also the order\nposts matter.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note:\nLog-based MQ as persisting\nthe data is a priority here, \nbc the data is already stored in\ncassandra and also the order\nposts matter.",
			"lineHeight": 1.25,
			"baseline": 109
		},
		{
			"type": "ellipse",
			"version": 841,
			"versionNonce": 2076278101,
			"isDeleted": false,
			"id": "oYxfMfzSlsvJJ28qsUkxL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 342.92805324988285,
			"y": 148.41566041979996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 329.15797490739664,
			"height": 133.560803546988,
			"seed": 939909461,
			"groupIds": [
				"P8YmkajOnxu4BExed287X"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1122,
			"versionNonce": 2108754613,
			"isDeleted": false,
			"id": "45T6BmYf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 361.43282308940513,
			"y": 168.4834051115691,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 294.61614990234375,
			"height": 99.32790754868108,
			"seed": 2076765877,
			"groupIds": [
				"P8YmkajOnxu4BExed287X"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 13.24372100649081,
			"fontFamily": 1,
			"text": "Note:\nCassandra follows leaderless \nreplication. It streams all the changed data\nto Kafka (a log-based Message Broker)\nas data persistence and order of \nposts matter.",
			"rawText": "Note:\nCassandra follows leaderless \nreplication. It streams all the changed data\nto Kafka (a log-based Message Broker)\nas data persistence and order of \nposts matter.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note:\nCassandra follows leaderless \nreplication. It streams all the changed data\nto Kafka (a log-based Message Broker)\nas data persistence and order of \nposts matter.",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 692,
			"versionNonce": 1500949004,
			"isDeleted": false,
			"id": "3uQ5Mm3Hz8l66_FBNTkQm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -254.63073637756688,
			"y": 732.530450182069,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110.93509272307537,
			"height": 1.2300544524916859,
			"seed": 333676661,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9EHZepHr0ExQvUgRXw2k9",
				"gap": 1.1952332514876218,
				"focus": 0.06046698279426422
			},
			"endBinding": {
				"elementId": "cUjhKv_LVaKKc-U_x7ObY",
				"gap": 7.469200059545528,
				"focus": 0.05979196291641465
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
					110.93509272307537,
					1.2300544524916859
				]
			]
		},
		{
			"type": "arrow",
			"version": 760,
			"versionNonce": 195922060,
			"isDeleted": false,
			"id": "3_y54UoFo8_fi_rA0ClJc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 97.82023652247223,
			"y": 743.1075464897178,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.37435383985212,
			"height": 58.08195008456846,
			"seed": 2081660885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cUjhKv_LVaKKc-U_x7ObY",
				"gap": 2.793282197326562,
				"focus": 0.7263970783634004
			},
			"endBinding": {
				"elementId": "AVIhqHbKzL9Z5FcR50iIC",
				"focus": 0.20275516547394845,
				"gap": 5.350039724391536
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
					75.42865362243059,
					-58.08195008456846
				],
				[
					187.37435383985212,
					-48.717285868357294
				]
			]
		},
		{
			"type": "rectangle",
			"version": 455,
			"versionNonce": 466823099,
			"isDeleted": false,
			"id": "vBxLQCRlU8miWRMcFvpJV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -227.05999539414267,
			"y": -126.20049968887793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 169.54296875,
			"height": 133.09765625,
			"seed": 936542587,
			"groupIds": [
				"FuIZ4MTFZ_L_Uea11Oxie"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 534,
			"versionNonce": 405567579,
			"isDeleted": false,
			"id": "9jdLw0Ce",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -219.58733914414267,
			"y": -109.17315593887793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.9398956298828,
			"height": 100,
			"seed": 916101659,
			"groupIds": [
				"FuIZ4MTFZ_L_Uea11Oxie"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "  Posts table\nuserId: int\ncontent: string\nMetadata: json",
			"rawText": "  Posts table\nuserId: int\ncontent: string\nMetadata: json",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "  Posts table\nuserId: int\ncontent: string\nMetadata: json",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "rectangle",
			"version": 593,
			"versionNonce": 710063355,
			"isDeleted": false,
			"id": "n0MbbsZFqFQmrTYROPY-4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -26.362729769142675,
			"y": -124.12432781387793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 169.54296875,
			"height": 133.09765625,
			"seed": 571907771,
			"groupIds": [
				"VZFZZ4yC1sb2LZ6cmyLR5"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 706,
			"versionNonce": 1640521115,
			"isDeleted": false,
			"id": "yGxyLWp4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.651792269142675,
			"y": -107.09698406387793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.85986328125,
			"height": 100,
			"seed": 350818139,
			"groupIds": [
				"VZFZZ4yC1sb2LZ6cmyLR5"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "  Users table\nuserId: int\nemail: string\npw_hash: string",
			"rawText": "  Users table\nuserId: int\nemail: string\npw_hash: string",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "  Users table\nuserId: int\nemail: string\npw_hash: string",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "rectangle",
			"version": 529,
			"versionNonce": 968880699,
			"isDeleted": false,
			"id": "qu-JnhW24O5-cLiMFSqbW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 164.1971716666801,
			"y": -121.83544654838659,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 189.61328125,
			"height": 133.09765625,
			"seed": 828664827,
			"groupIds": [
				"dUDCX_5JlOh-y-ZeUO8B_"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 719,
			"versionNonce": 589034203,
			"isDeleted": false,
			"id": "RSuWm24p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 151.8573279166801,
			"y": -99.85107154838659,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 192.87985229492188,
			"height": 75,
			"seed": 730543259,
			"groupIds": [
				"dUDCX_5JlOh-y-ZeUO8B_"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710514437088,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "  UserFollows table\nuser1: int\nuser2: int",
			"rawText": "  UserFollows table\nuser1: int\nuser2: int",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "  UserFollows table\nuser1: int\nuser2: int",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 997,
			"versionNonce": 1628547797,
			"isDeleted": false,
			"id": "hPXuUvPFj9ozseWcq_Vfj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -55.784410675685876,
			"y": 1002.4622809719929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 1779181845,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "cwC6RFJX"
				},
				{
					"id": "JA9mSnPsGrfU-Gyv4qImV",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 959,
			"versionNonce": 1939834933,
			"isDeleted": false,
			"id": "cwC6RFJX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39.40350552431869,
			"y": 1013.4212653469929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.663970947265625,
			"height": 40,
			"seed": 1831878261,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Feed\nCache",
			"rawText": "Feed\nCache",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hPXuUvPFj9ozseWcq_Vfj",
			"originalText": "Feed\nCache",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 1166,
			"versionNonce": 357089013,
			"isDeleted": false,
			"id": "Yo12xH7zS91XJ8mQ5n0LM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 249.03283319158334,
			"y": 910.7866635551406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.3211604030976,
			"height": 95.58342859343064,
			"seed": 2006314587,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "wJtcgAsj"
				},
				{
					"id": "kzhuaQ5h4xa45Hkrm7TeI",
					"type": "arrow"
				},
				{
					"id": "Ta44X2Y0GMV3gM2bEKNQe",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1168,
			"versionNonce": 337582165,
			"isDeleted": false,
			"id": "wJtcgAsj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 284.15343536578837,
			"y": 933.578377851856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.0799560546875,
			"height": 50,
			"seed": 152922875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Post \nCache",
			"rawText": "Post \nCache",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Yo12xH7zS91XJ8mQ5n0LM",
			"originalText": "Post \nCache",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1067,
			"versionNonce": 1082431244,
			"isDeleted": false,
			"id": "JA9mSnPsGrfU-Gyv4qImV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 285.9986550706375,
			"y": 774.661501105146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 297.46564172632515,
			"height": 217.06893035709527,
			"seed": 656528245,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AVIhqHbKzL9Z5FcR50iIC",
				"focus": -0.1179694320336723,
				"gap": 4.545975016078387
			},
			"endBinding": {
				"elementId": "hPXuUvPFj9ozseWcq_Vfj",
				"gap": 10.731849509751555,
				"focus": -0.4081166585506936
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
					-171.04315007718935,
					43.04334162749751
				],
				[
					-297.46564172632515,
					217.06893035709527
				]
			]
		},
		{
			"type": "arrow",
			"version": 235,
			"versionNonce": 1730241292,
			"isDeleted": false,
			"id": "lAXR_vkEc3BMAzu7Ayr1l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -54.79436910427876,
			"y": 1034.0585273975669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.89302943518408,
			"height": 4.518767267703197,
			"seed": 540508219,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912899,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zz6Brb3QV6BBpBsMcIPgB",
				"gap": 3.2846634899759692,
				"focus": 0.19279942508371978
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
					-174.89302943518408,
					4.518767267703197
				]
			]
		},
		{
			"type": "rectangle",
			"version": 458,
			"versionNonce": 1998340917,
			"isDeleted": false,
			"id": "K_0oct4kEwFGU-fFOJn9j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 528.1571376992258,
			"y": 914.2897914148792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 1487748891,
			"groupIds": [
				"Zv3lLMo6kXc1YrBsp_qaP",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 464,
			"versionNonce": 829953173,
			"isDeleted": false,
			"id": "qhE-GDr-QguI8z4c3EgVX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 534.9790936846193,
			"y": 918.8863435167876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 344761275,
			"groupIds": [
				"Zv3lLMo6kXc1YrBsp_qaP",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 441,
			"versionNonce": 1192409589,
			"isDeleted": false,
			"id": "FpKT9rnv3U5ubQXbXAoPI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 620.9514346443391,
			"y": 914.2477497798005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 878081115,
			"groupIds": [
				"al57cIdgm3XJ-dHRABlxX",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 447,
			"versionNonce": 284275541,
			"isDeleted": false,
			"id": "nIi7rzBkFBm-ha5Di1gW_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 627.7733906297324,
			"y": 918.8443018817092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 668807419,
			"groupIds": [
				"al57cIdgm3XJ-dHRABlxX",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 459,
			"versionNonce": 728400053,
			"isDeleted": false,
			"id": "1teQDWL83pHHrhICgZA7c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 713.8466315136404,
			"y": 911.6299573022503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63200699390802,
			"height": 83.02382095288579,
			"seed": 1084447131,
			"groupIds": [
				"X_kKa4t3yMQUeLhCMipuq",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 465,
			"versionNonce": 203596309,
			"isDeleted": false,
			"id": "pr7UkD4xPXAeyvxe6Wryo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 720.6685874990337,
			"y": 916.226509404159,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.12720377564415,
			"height": 11.255947098331944,
			"seed": 2077978171,
			"groupIds": [
				"X_kKa4t3yMQUeLhCMipuq",
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 429,
			"versionNonce": 1477416821,
			"isDeleted": false,
			"id": "sihMqVDhycllmh1y_bCca",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 504.7539608388993,
			"y": 891.2621864945864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 304.13479370871437,
			"height": 128.439997940279,
			"seed": 208137947,
			"groupIds": [
				"bzcxKxMzmiWNjue0vy1GI"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "qaes4RSxVCP0EVtYfuvKS",
					"type": "arrow"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 902,
			"versionNonce": 1978531381,
			"isDeleted": false,
			"id": "5zJMtfunVVuismK0gslth",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 303.8695544929576,
			"y": 685.3825703739907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 281843605,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "5GVoK36x"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 865,
			"versionNonce": 73035669,
			"isDeleted": false,
			"id": "5GVoK36x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 327.002458545692,
			"y": 706.3415547489907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.15997314453125,
			"height": 20,
			"seed": 1860099317,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Flink",
			"rawText": "Flink",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "5zJMtfunVVuismK0gslth",
			"originalText": "Flink",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 891,
			"versionNonce": 1660007669,
			"isDeleted": false,
			"id": "cfd_tAzq68Vamj4HsUykW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 400.7591341417758,
			"y": 685.4662512493184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 713835643,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "EdFOWVbz"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 854,
			"versionNonce": 1832472149,
			"isDeleted": false,
			"id": "EdFOWVbz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 423.8920381945102,
			"y": 706.4252356243184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.15997314453125,
			"height": 20,
			"seed": 1394867483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Flink",
			"rawText": "Flink",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "cfd_tAzq68Vamj4HsUykW",
			"originalText": "Flink",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 865,
			"versionNonce": 1913043893,
			"isDeleted": false,
			"id": "0frkk69Wz2zLfEf487Ef4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 502.07736319255946,
			"y": 685.7945377602199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.42578125,
			"height": 61.91796875,
			"seed": 1790188661,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dRHzbDr0"
				}
			],
			"updated": 1710515321630,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 828,
			"versionNonce": 1233091861,
			"isDeleted": false,
			"id": "dRHzbDr0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 525.2102672452938,
			"y": 706.7535221352199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.15997314453125,
			"height": 20,
			"seed": 792905173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Flink",
			"rawText": "Flink",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "0frkk69Wz2zLfEf487Ef4",
			"originalText": "Flink",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 397,
			"versionNonce": 1633402779,
			"isDeleted": false,
			"id": "qaes4RSxVCP0EVtYfuvKS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 599.1266126499163,
			"y": 723.5059250751358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.18948924258711,
			"height": 162.50825988666384,
			"seed": 24149723,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710515321631,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AVIhqHbKzL9Z5FcR50iIC",
				"focus": -0.3175744023906525,
				"gap": 4.447188854486058
			},
			"endBinding": {
				"elementId": "sihMqVDhycllmh1y_bCca",
				"focus": 0.30883523394902557,
				"gap": 5.248001532786816
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
					91.0512293470988,
					17.450681001059365
				],
				[
					101.18948924258711,
					162.50825988666384
				]
			]
		},
		{
			"type": "arrow",
			"version": 234,
			"versionNonce": 343266700,
			"isDeleted": false,
			"id": "kzhuaQ5h4xa45Hkrm7TeI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 505.76450374568685,
			"y": 958.8101095066099,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.41051015100595,
			"height": 1.4573218673184556,
			"seed": 1465124597,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Yo12xH7zS91XJ8mQ5n0LM",
				"gap": 1,
				"focus": -0.040388563583682584
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
					-128.41051015100595,
					-1.4573218673184556
				]
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 185907509,
			"isDeleted": false,
			"id": "3in14O1s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 530.0471365637345,
			"y": 1039.2660526391226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 263.3197937011719,
			"height": 25,
			"seed": 1444553621,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515321630,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Post Cassandra DB store",
			"rawText": "Post Cassandra DB store",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Post Cassandra DB store",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 523,
			"versionNonce": 79381516,
			"isDeleted": false,
			"id": "Ta44X2Y0GMV3gM2bEKNQe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 314.9334860557534,
			"y": 1009.1216265498708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 550.0601414915271,
			"height": 121.91016137184215,
			"seed": 225514651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Yo12xH7zS91XJ8mQ5n0LM",
				"gap": 2.751534401299523,
				"focus": -0.7263066520175399
			},
			"endBinding": {
				"elementId": "Zz6Brb3QV6BBpBsMcIPgB",
				"gap": 2.2706899163467824,
				"focus": 0.4957089573188515
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
					-338.791679250372,
					121.91016137184215
				],
				[
					-550.0601414915271,
					56.845062309242394
				]
			]
		},
		{
			"type": "text",
			"version": 789,
			"versionNonce": 670353915,
			"isDeleted": false,
			"id": "IkEjt7Rs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 682.3984658198423,
			"y": 586.1116177421903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 502.20416259765625,
			"height": 120.4352163778465,
			"seed": 159697461,
			"groupIds": [
				"P_dMLQuKrFs1exn0frN2q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515910460,
			"link": null,
			"locked": false,
			"fontSize": 19.26963462045544,
			"fontFamily": 1,
			"text": " Flink is designed to process large volumes of data\n in real-time, doing all sorts of tasks like sorting, \nanalyzing, and aggregating the data as it flows by, \nasynchronously. Here, loading followers for the\nusers creating the post.",
			"rawText": " Flink is designed to process large volumes of data\n in real-time, doing all sorts of tasks like sorting, \nanalyzing, and aggregating the data as it flows by, \nasynchronously. Here, loading followers for the\nusers creating the post.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " Flink is designed to process large volumes of data\n in real-time, doing all sorts of tasks like sorting, \nanalyzing, and aggregating the data as it flows by, \nasynchronously. Here, loading followers for the\nusers creating the post.",
			"lineHeight": 1.25,
			"baseline": 113
		},
		{
			"type": "rectangle",
			"version": 609,
			"versionNonce": 1818219163,
			"isDeleted": false,
			"id": "dHndBBix986BIUHRikqgw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 670.571763496205,
			"y": 570.6774006847121,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 521.9568562182911,
			"height": 143.79728347465317,
			"seed": 766272443,
			"groupIds": [
				"P_dMLQuKrFs1exn0frN2q"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515910460,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 773,
			"versionNonce": 93323701,
			"isDeleted": false,
			"id": "OJyhjVa-l_Km7du1GPkvn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 701.4884106533807,
			"y": 255.90023009004642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 597.8014840816229,
			"height": 204.62096024504453,
			"seed": 965290843,
			"groupIds": [
				"hbetJMkzl7pAcSNnSMNQZ"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710515948643,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 1479672155,
			"isDeleted": false,
			"id": "wBUQ9nni",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": 729.4017396670972,
			"y": 280.9634075935071,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 555.485107421875,
			"height": 155.10974375301186,
			"seed": 1789625147,
			"groupIds": [
				"hbetJMkzl7pAcSNnSMNQZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710515941526,
			"link": null,
			"locked": false,
			"fontSize": 20.68129916706825,
			"fontFamily": 1,
			"text": "Changes in the UserFollows table are sent to Kafka, \nwhich acts as a buffer and a reliable\n conduit to Flink. This means Flink doesn't \nhave to query the database directly, \nwhich reduces the load on Cassandra and allows \nFlink to process data at its own pace.",
			"rawText": "Changes in the UserFollows table are sent to Kafka, \nwhich acts as a buffer and a reliable\n conduit to Flink. This means Flink doesn't \nhave to query the database directly, \nwhich reduces the load on Cassandra and allows \nFlink to process data at its own pace.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Changes in the UserFollows table are sent to Kafka, \nwhich acts as a buffer and a reliable\n conduit to Flink. This means Flink doesn't \nhave to query the database directly, \nwhich reduces the load on Cassandra and allows \nFlink to process data at its own pace.",
			"lineHeight": 1.25,
			"baseline": 147
		},
		{
			"type": "ellipse",
			"version": 279,
			"versionNonce": 1701416917,
			"isDeleted": false,
			"id": "aT6ndmCroCIoJyJQd66kF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -347.51237662442657,
			"y": 427.23702845440926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101,
			"height": 31.1875,
			"seed": 1574993243,
			"groupIds": [
				"90QDHNTwXW3p3JYR1ju5z"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710593660323,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 318,
			"versionNonce": 850782011,
			"isDeleted": false,
			"id": "Scl2VVLw05DGzwkz0Dde8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -347.49675162442657,
			"y": 433.82296595440926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 102.0390625,
			"height": 105.6953125,
			"seed": 96633051,
			"groupIds": [
				"90QDHNTwXW3p3JYR1ju5z"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "NRBUnI81"
				},
				{
					"id": "8rehYCMqb3XjunxICNudL",
					"type": "arrow"
				},
				{
					"id": "jBR8TYWGg9-VaHw3WdEoJ",
					"type": "arrow"
				}
			],
			"updated": 1710593681475,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 7,
			"versionNonce": 1868305979,
			"isDeleted": false,
			"id": "NRBUnI81",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -309.36721213468047,
			"y": 474.17062220440926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.779983520507812,
			"height": 25,
			"seed": 487506933,
			"groupIds": [
				"90QDHNTwXW3p3JYR1ju5z"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710593667312,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "S3",
			"rawText": "S3",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Scl2VVLw05DGzwkz0Dde8",
			"originalText": "S3",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 653,
			"versionNonce": 23697595,
			"isDeleted": false,
			"id": "0657zq7ly7aAUJjXgsawn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -754.1705797494266,
			"y": 432.66476282940926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.17578125000004,
			"height": 81.08984375,
			"seed": 451770203,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "LKKOvRkz"
				},
				{
					"id": "jBR8TYWGg9-VaHw3WdEoJ",
					"type": "arrow"
				},
				{
					"id": "YW8mKGB2rJ1j6jkyE_Yvq",
					"type": "arrow"
				}
			],
			"updated": 1710593709989,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 616,
			"versionNonce": 305062293,
			"isDeleted": false,
			"id": "LKKOvRkz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -716.1266725838992,
			"y": 463.20968470440926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.08796691894531,
			"height": 20,
			"seed": 1251726331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710593644025,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "CDN",
			"rawText": "CDN",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "0657zq7ly7aAUJjXgsawn",
			"originalText": "CDN",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 51,
			"versionNonce": 48935180,
			"isDeleted": false,
			"id": "8rehYCMqb3XjunxICNudL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -296.5592516244266,
			"y": 697.7682784544093,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.2819248826290845,
			"height": 157.25,
			"seed": 1784563125,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912908,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9EHZepHr0ExQvUgRXw2k9",
				"gap": 1.456852737661734,
				"focus": -0.01592041424038913
			},
			"endBinding": {
				"elementId": "Scl2VVLw05DGzwkz0Dde8",
				"gap": 1,
				"focus": 0.11113970012947565
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
					-4.2819248826290845,
					-157.25
				]
			]
		},
		{
			"type": "arrow",
			"version": 111,
			"versionNonce": 1551092492,
			"isDeleted": false,
			"id": "jBR8TYWGg9-VaHw3WdEoJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -351.81706412442657,
			"y": 479.01046595440926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.3359374999999,
			"height": 1.9765625,
			"seed": 1406196629,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912910,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Scl2VVLw05DGzwkz0Dde8",
				"gap": 4.3203125,
				"focus": 0.13686379484290173
			},
			"endBinding": {
				"elementId": "0657zq7ly7aAUJjXgsawn",
				"gap": 4.841796875,
				"focus": 0.08350188679596668
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
					-288.3359374999999,
					-1.9765625
				]
			]
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 762148876,
			"isDeleted": false,
			"id": "YW8mKGB2rJ1j6jkyE_Yvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -693.7949578159394,
			"y": 514.7546065794094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.1549188084871957,
			"height": 180.2167968749999,
			"seed": 565315605,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710739912910,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0657zq7ly7aAUJjXgsawn",
				"gap": 1,
				"focus": -0.11411278445649226
			},
			"endBinding": {
				"elementId": "hrbf_DFgM736i0RESTe4w",
				"gap": 4.36757862971433,
				"focus": 0.11553467110701814
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
					-2.1549188084871957,
					180.2167968749999
				]
			]
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
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 938.5514536183225,
		"scrollY": 532.5268604344797,
		"zoom": {
			"value": 0.45
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