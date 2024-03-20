---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Functional requirements:
1. Group Chats
2. Send and receive messages in real time
3. Keep old messages in db ^8TRKRoEo

Capacity Estimate:
 ^uPggtUsv

1.  500M DAU
2. 40 messages / day / user
3. 100 bytes / msg
4. 20 billion msg / day
5. 2tb storage / day
6. 3.6 Pb storage / 5yrs ^ddJpyo1i

API Design ^Y4AhWMBB

1. POST /send(user_id, chat_id, 
   msgText, timestamp)
2. GET /fetch(chatId, paginationToken) ^rMhFsm2R

Database Schema ^Ho8ospgq

  Users table
userId: int
email: string
pw_hash: string ^f7UgXwqU

  Chats table
chatId: int
chatName: string ^kTM5V893

UserChat table
userId: int
chatId: string ^ZaoGxh6d

Client ^Le8PoIMc

LB ^xZtddshu

User Service ^WEubg1Wi

chat server ^4sKWKHXN

chat server ^AKNFbS4c

chat server ^skjByeDN

User, Chat, UserChat
     (MySQL) ^TGT9kV3r

User + UserChat Cache ^a5rMYlZG

Message Table ^4DOsROXw

           Note:
Since there are no write heavy
operation, we can store it these 
data in SQL Tables, to keep it
simple with Single Leader replication
since no potential write conflicts. ^SFl7CKtC

                Note:
Since the "Message Table" is gonna be 
write heavy, we can use Cassandra/HBase
as the NoSQL db of choice, as each /send API
will store message in the table and will be 
write-heavy. 

Higher write-thoughput is supported by Cassandra
/HBase since all the writes are going to 
in-memory buffer first. Column Oriented storage 
isn't imp since each message will have mulutiple 
columns to consure data from each row and hence
HBase wont be any helpful being a column Oriented
store 
 ^vbuuKp4r


Cassandra ^sb8f6GVO

                Note:
"Message Table" must be partitioned on
ChatId and also should have fields like 
timestamp and message content. ^3377SQYU

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
			"version": 1989,
			"versionNonce": 1939144181,
			"isDeleted": false,
			"id": "8TRKRoEo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1123.4770091603812,
			"y": -841.4729587818592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 320.5733642578125,
			"height": 77.17577009629137,
			"seed": 801164667,
			"groupIds": [
				"O4EY7opLNWBhinpdOw5gI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598868038,
			"link": null,
			"locked": false,
			"fontSize": 15.435154019258276,
			"fontFamily": 1,
			"text": "Functional requirements:\n1. Group Chats\n2. Send and receive messages in real time\n3. Keep old messages in db",
			"rawText": "Functional requirements:\n1. Group Chats\n2. Send and receive messages in real time\n3. Keep old messages in db",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Functional requirements:\n1. Group Chats\n2. Send and receive messages in real time\n3. Keep old messages in db",
			"lineHeight": 1.25,
			"baseline": 71
		},
		{
			"type": "rectangle",
			"version": 1131,
			"versionNonce": 2089514837,
			"isDeleted": false,
			"id": "cyBSVFHlROJWEiNYOlqPw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1139.9658612151097,
			"y": -850.0817984840003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 344.8857279024011,
			"height": 92.96679687500007,
			"seed": 418158811,
			"groupIds": [
				"O4EY7opLNWBhinpdOw5gI"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598868038,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1545,
			"versionNonce": 944672507,
			"isDeleted": false,
			"id": "wzJYT-qgRvh7-PRBv_9tF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -629.151628597667,
			"y": -1102.5898094747463,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 344.1450593140968,
			"height": 219.55663718387083,
			"seed": 1474676699,
			"groupIds": [
				"TLOI122ieCqcfJ-hVDwyl"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598849488,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1525,
			"versionNonce": 926480283,
			"isDeleted": false,
			"id": "uPggtUsv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.2738877632161625,
			"x": -512.6734747396335,
			"y": -1086.114249269849,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.61984252929688,
			"height": 50,
			"seed": 1429607547,
			"groupIds": [
				"TLOI122ieCqcfJ-hVDwyl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598849488,
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
			"version": 2022,
			"versionNonce": 168643643,
			"isDeleted": false,
			"id": "ddJpyo1i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -604.6474345097893,
			"y": -1051.2284621841036,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 292.61981201171875,
			"height": 150,
			"seed": 672386331,
			"groupIds": [
				"TLOI122ieCqcfJ-hVDwyl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598849488,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1.  500M DAU\n2. 40 messages / day / user\n3. 100 bytes / msg\n4. 20 billion msg / day\n5. 2tb storage / day\n6. 3.6 Pb storage / 5yrs",
			"rawText": "1.  500M DAU\n2. 40 messages / day / user\n3. 100 bytes / msg\n4. 20 billion msg / day\n5. 2tb storage / day\n6. 3.6 Pb storage / 5yrs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1.  500M DAU\n2. 40 messages / day / user\n3. 100 bytes / msg\n4. 20 billion msg / day\n5. 2tb storage / day\n6. 3.6 Pb storage / 5yrs",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "rectangle",
			"version": 1632,
			"versionNonce": 179953205,
			"isDeleted": false,
			"id": "9gMsGXUxQbmZx-9h7rq2Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -749.9213687607764,
			"y": -853.8248474021453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 321.58088764620356,
			"height": 99.32768831500795,
			"seed": 1661604699,
			"groupIds": [
				"7LGf97QpLi67oVeXpLRzt"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598876257,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1748,
			"versionNonce": 1420447637,
			"isDeleted": false,
			"id": "Y4AhWMBB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -630.6000463336675,
			"y": -847.693450403937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 72.07261657714844,
			"height": 16.630927115182708,
			"seed": 482668539,
			"groupIds": [
				"7LGf97QpLi67oVeXpLRzt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598876257,
			"link": null,
			"locked": false,
			"fontSize": 13.304741692146166,
			"fontFamily": 1,
			"text": "API Design",
			"rawText": "API Design",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Design",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 1958,
			"versionNonce": 1581618421,
			"isDeleted": false,
			"id": "rMhFsm2R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -733.8860267846712,
			"y": -822.9546574933131,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.14453125,
			"height": 48.8780786428315,
			"seed": 1614493851,
			"groupIds": [
				"7LGf97QpLi67oVeXpLRzt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598876257,
			"link": null,
			"locked": false,
			"fontSize": 13.577244067453194,
			"fontFamily": 3,
			"text": "1. POST /send(user_id, chat_id, \n   msgText, timestamp)\n2. GET /fetch(chatId, paginationToken)",
			"rawText": "1. POST /send(user_id, chat_id, \n   msgText, timestamp)\n2. GET /fetch(chatId, paginationToken)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. POST /send(user_id, chat_id, \n   msgText, timestamp)\n2. GET /fetch(chatId, paginationToken)",
			"lineHeight": 1.2,
			"baseline": 46
		},
		{
			"type": "rectangle",
			"version": 1580,
			"versionNonce": 1434530747,
			"isDeleted": false,
			"id": "BeQt4DN8GD4wPzM8lM_Fd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1301.502454772372,
			"y": -1093.2916058335272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 617.9847647466187,
			"height": 200.04763582517535,
			"seed": 1593971227,
			"groupIds": [
				"fLkX9Lmis_w1ZJBsakQyP",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1334,
			"versionNonce": 137954395,
			"isDeleted": false,
			"id": "Ho8ospgq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1070.5853407379398,
			"y": -1079.7115844491168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.4551239013672,
			"height": 24.957805754507003,
			"seed": 1053759163,
			"groupIds": [
				"fLkX9Lmis_w1ZJBsakQyP",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598843320,
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
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 742,
			"versionNonce": 15581435,
			"isDeleted": false,
			"id": "77uMJDbF5SFiGWiMcOKL4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1277.0143379553847,
			"y": -1041.7125807254015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 169.54296875,
			"height": 126.30078125,
			"seed": 1705965717,
			"groupIds": [
				"01zlgx3pH44F_ns8NL_8Q",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 839,
			"versionNonce": 1226959259,
			"isDeleted": false,
			"id": "f7UgXwqU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1269.3034004553847,
			"y": -1031.4821119754015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.85986328125,
			"height": 100,
			"seed": 449650165,
			"groupIds": [
				"01zlgx3pH44F_ns8NL_8Q",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598843320,
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
			"version": 852,
			"versionNonce": 369622587,
			"isDeleted": false,
			"id": "9_5xCAzj_yzwut7Hp2S2a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1070.5095825206022,
			"y": -1032.8470915949665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 176.39758831521726,
			"height": 110.47537364130437,
			"seed": 1676641941,
			"groupIds": [
				"_ZE35in2Wf-mef9u5QpW_",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 954,
			"versionNonce": 1384283867,
			"isDeleted": false,
			"id": "kTM5V893",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1062.7986450206022,
			"y": -1015.8197478449666,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.71986389160156,
			"height": 75,
			"seed": 1573645301,
			"groupIds": [
				"_ZE35in2Wf-mef9u5QpW_",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "  Chats table\nchatId: int\nchatName: string",
			"rawText": "  Chats table\nchatId: int\nchatName: string",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "  Chats table\nchatId: int\nchatName: string",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 854,
			"versionNonce": 1763961723,
			"isDeleted": false,
			"id": "fadlupGfKvbUDP75fQdr2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -868.6477923196636,
			"y": -1028.278477464532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 169.54296875,
			"height": 105.46178668478275,
			"seed": 2140963867,
			"groupIds": [
				"1rnHV81BkGDPps-rSz39I",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 984,
			"versionNonce": 1311687707,
			"isDeleted": false,
			"id": "ZaoGxh6d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -863.470822210968,
			"y": -1015.3645848014886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 153.0798797607422,
			"height": 75,
			"seed": 122374331,
			"groupIds": [
				"1rnHV81BkGDPps-rSz39I",
				"KyRHbR2-mdeVBbxuWxvS2"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710598843320,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "UserChat table\nuserId: int\nchatId: string",
			"rawText": "UserChat table\nuserId: int\nchatId: string",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "UserChat table\nuserId: int\nchatId: string",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"id": "bE43XgHsMcvgUOnPDQtAA",
			"type": "rectangle",
			"x": -1216.758418277971,
			"y": -528.4067655309418,
			"width": 76.68359375,
			"height": 68.26171875,
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
			"seed": 280912629,
			"version": 121,
			"versionNonce": 1343174811,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "Le8PoIMc"
				},
				{
					"id": "oFWeUYEBd-MZI_SnwW-P1",
					"type": "arrow"
				}
			],
			"updated": 1710599203161,
			"link": null,
			"locked": false
		},
		{
			"id": "Le8PoIMc",
			"type": "text",
			"x": -1205.4665939371507,
			"y": -506.7759061559418,
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
			"seed": 1402449749,
			"version": 54,
			"versionNonce": 1981455067,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599199743,
			"link": null,
			"locked": false,
			"text": "Client",
			"rawText": "Client",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "bE43XgHsMcvgUOnPDQtAA",
			"originalText": "Client",
			"lineHeight": 1.25
		},
		{
			"id": "jBu5dtv8G2NOffL2F0Eqx",
			"type": "diamond",
			"x": -1008.106074527971,
			"y": -542.1450467809418,
			"width": 80.0078125,
			"height": 92.078125,
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
			"seed": 471496981,
			"version": 140,
			"versionNonce": 182221013,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "xZtddshu"
				},
				{
					"id": "NSWC6yLQe_VqVCS0MusCD",
					"type": "arrow"
				}
			],
			"updated": 1710599166827,
			"link": null,
			"locked": false
		},
		{
			"id": "xZtddshu",
			"type": "text",
			"x": -981.364115909807,
			"y": -508.6255155309418,
			"width": 26.519989013671875,
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
			"seed": 675364405,
			"version": 54,
			"versionNonce": 1810340251,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599150742,
			"link": null,
			"locked": false,
			"text": "LB",
			"rawText": "LB",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "jBu5dtv8G2NOffL2F0Eqx",
			"originalText": "LB",
			"lineHeight": 1.25
		},
		{
			"id": "hohDlxUBKIRA6Wh5PPOq8",
			"type": "rectangle",
			"x": -768.418574527971,
			"y": -689.7544217809418,
			"width": 95.05859375,
			"height": 83.35546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"7NINXXZmK0xignNWgWSTx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1490102613,
			"version": 281,
			"versionNonce": 1064128885,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599098510,
			"link": null,
			"locked": false
		},
		{
			"id": "DjoHKTS_0Q6NRKmEf7vPH",
			"type": "rectangle",
			"x": -775.465449527971,
			"y": -692.8989530309418,
			"width": 97.3515625,
			"height": 81.00390625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"7NINXXZmK0xignNWgWSTx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 2063335989,
			"version": 152,
			"versionNonce": 1628265173,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599098510,
			"link": null,
			"locked": false
		},
		{
			"id": "JJ8Cm8GyGk7Dr507DOVFu",
			"type": "rectangle",
			"x": -782.840449527971,
			"y": -693.3442655309418,
			"width": 99.0546875,
			"height": 76.75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"7NINXXZmK0xignNWgWSTx"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 435583035,
			"version": 166,
			"versionNonce": 2016652411,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "WEubg1Wi"
				},
				{
					"id": "BSo45EQZhmmj0BBD95fDO",
					"type": "arrow"
				},
				{
					"id": "vz2J-xxiwo8Q9wsMflcPL",
					"type": "arrow"
				}
			],
			"updated": 1710599271512,
			"link": null,
			"locked": false
		},
		{
			"id": "WEubg1Wi",
			"type": "text",
			"x": -767.0730697672288,
			"y": -679.9692655309418,
			"width": 67.51992797851562,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"7NINXXZmK0xignNWgWSTx"
			],
			"frameId": null,
			"roundness": null,
			"seed": 930214709,
			"version": 14,
			"versionNonce": 1696631643,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599112329,
			"link": null,
			"locked": false,
			"text": "User\nService",
			"rawText": "User Service",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "JJ8Cm8GyGk7Dr507DOVFu",
			"originalText": "User Service",
			"lineHeight": 1.25
		},
		{
			"id": "PEUceZpcx3pWgv7U0jF6Y",
			"type": "rectangle",
			"x": -773.481074527971,
			"y": -552.8091092809418,
			"width": 94.53515625,
			"height": 70.1328125,
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
			"seed": 1471249045,
			"version": 32,
			"versionNonce": 166405819,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "4sKWKHXN"
				},
				{
					"id": "BwaaLNNCPxVaBOJv9DE0h",
					"type": "arrow"
				},
				{
					"id": "Gqvk9uplWS7ubOLCQwKck",
					"type": "arrow"
				},
				{
					"id": "asdP8kWA3K49CZTqHEYxz",
					"type": "arrow"
				},
				{
					"id": "SgQ_LD2E_MNM3HhyoVsvt",
					"type": "arrow"
				}
			],
			"updated": 1710599581301,
			"link": null,
			"locked": false
		},
		{
			"id": "4sKWKHXN",
			"type": "text",
			"x": -756.4134628336351,
			"y": -542.7427030309418,
			"width": 60.399932861328125,
			"height": 50,
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
			"seed": 218927445,
			"version": 13,
			"versionNonce": 1606230683,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599210378,
			"link": null,
			"locked": false,
			"text": "chat\nserver",
			"rawText": "chat server",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "PEUceZpcx3pWgv7U0jF6Y",
			"originalText": "chat server",
			"lineHeight": 1.25
		},
		{
			"id": "x5kwWMS7bpdr8fsV0OYPW",
			"type": "rectangle",
			"x": -769.879512027971,
			"y": -435.6216092809418,
			"width": 94.171875,
			"height": 70.546875,
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
			"seed": 1633114037,
			"version": 92,
			"versionNonce": 139557621,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Y5rQN2VCu5SZ9YMLzuQ85",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "AKNFbS4c"
				},
				{
					"id": "Gqvk9uplWS7ubOLCQwKck",
					"type": "arrow"
				},
				{
					"id": "k3ckeK9TStnY-WLs53fgY",
					"type": "arrow"
				},
				{
					"id": "Lrzpfaq4NWzT6MP6cswcf",
					"type": "arrow"
				}
			],
			"updated": 1710599585634,
			"link": null,
			"locked": false
		},
		{
			"id": "AKNFbS4c",
			"type": "text",
			"x": -752.9935409586351,
			"y": -425.3481717809418,
			"width": 60.399932861328125,
			"height": 50,
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
			"seed": 1719518331,
			"version": 3,
			"versionNonce": 602928341,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599214667,
			"link": null,
			"locked": false,
			"text": "chat\nserver",
			"rawText": "chat server",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "x5kwWMS7bpdr8fsV0OYPW",
			"originalText": "chat server",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 154,
			"versionNonce": 1924097819,
			"isDeleted": false,
			"id": "22QlrxIXehC5DxTyIREG2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -768.047480777971,
			"y": -321.5864530309418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.171875,
			"height": 70.546875,
			"seed": 1906633659,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "cAqpKSwoLHGB2sq2IE8He",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "skjByeDN"
				},
				{
					"id": "k3ckeK9TStnY-WLs53fgY",
					"type": "arrow"
				},
				{
					"id": "asdP8kWA3K49CZTqHEYxz",
					"type": "arrow"
				},
				{
					"id": "SoSzY61f1TZASu8gwUUD7",
					"type": "arrow"
				}
			],
			"updated": 1710599589684,
			"link": null,
			"locked": false
		},
		{
			"id": "skjByeDN",
			"type": "text",
			"x": -751.1615097086351,
			"y": -311.3130155309418,
			"width": 60.399932861328125,
			"height": 50,
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
			"seed": 2094640347,
			"version": 3,
			"versionNonce": 542156405,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599215993,
			"link": null,
			"locked": false,
			"text": "chat\nserver",
			"rawText": "chat server",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "22QlrxIXehC5DxTyIREG2",
			"originalText": "chat server",
			"lineHeight": 1.25
		},
		{
			"id": "NSWC6yLQe_VqVCS0MusCD",
			"type": "arrow",
			"x": -928.3732608519784,
			"y": -494.2648707057594,
			"width": 155.0796863240074,
			"height": 19.68876982518242,
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
			"seed": 2047110395,
			"version": 51,
			"versionNonce": 1180787867,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					155.0796863240074,
					-19.68876982518242
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "jBu5dtv8G2NOffL2F0Eqx",
				"gap": 1,
				"focus": 0.14954817910127569
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "BSo45EQZhmmj0BBD95fDO",
			"type": "arrow",
			"x": -886.586543277971,
			"y": -499.6802030309418,
			"width": 100.78125,
			"height": 155.08203125,
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
			"seed": 1994430005,
			"version": 96,
			"versionNonce": 1403001147,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					17.6796875,
					-128.58203125
				],
				[
					100.78125,
					-155.08203125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "JJ8Cm8GyGk7Dr507DOVFu",
				"gap": 2.96484375,
				"focus": 0.3051958774891079
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Y5rQN2VCu5SZ9YMLzuQ85",
			"type": "arrow",
			"x": -886.246699527971,
			"y": -498.7661405309418,
			"width": 113.734375,
			"height": 95.30078125,
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
			"seed": 500523291,
			"version": 126,
			"versionNonce": 76470683,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					40.6875,
					86.140625
				],
				[
					113.734375,
					95.30078125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "x5kwWMS7bpdr8fsV0OYPW",
				"gap": 2.6328125,
				"focus": -0.0757101376402689
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "cAqpKSwoLHGB2sq2IE8He",
			"type": "arrow",
			"x": -884.371699527971,
			"y": -498.2036405309418,
			"width": 113.78125,
			"height": 219.796875,
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
			"seed": 1323683893,
			"version": 120,
			"versionNonce": 317487291,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					8.63671875,
					180.94140625
				],
				[
					113.78125,
					219.796875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "22QlrxIXehC5DxTyIREG2",
				"gap": 2.54296875,
				"focus": -0.4982803114228752
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "oFWeUYEBd-MZI_SnwW-P1",
			"type": "arrow",
			"x": -1136.262324527971,
			"y": -494.9262967809418,
			"width": 132.37890625,
			"height": 2.71484375,
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
			"seed": 1240596917,
			"version": 56,
			"versionNonce": 2000722939,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					132.37890625,
					-2.71484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "bE43XgHsMcvgUOnPDQtAA",
				"gap": 3.8125,
				"focus": 0.00613208644950031
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "sl0N7RESncEq9opy03gIC",
			"type": "ellipse",
			"x": -509.26232452797103,
			"y": -694.9067655309418,
			"width": 63.30078125,
			"height": 21.02734375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"4BbhZDfrSAAOYnsbVlCi_"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1289870997,
			"version": 108,
			"versionNonce": 1617262331,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599253411,
			"link": null,
			"locked": false
		},
		{
			"id": "jNvxcbSMjWF0yOHAVuPzx",
			"type": "rectangle",
			"x": -513.258418277971,
			"y": -692.5747342809418,
			"width": 69.6171875,
			"height": 69.5703125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"4BbhZDfrSAAOYnsbVlCi_"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1205525205,
			"version": 104,
			"versionNonce": 990872021,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "J9z5YZsbY4CAnIdTzkRYu",
					"type": "arrow"
				},
				{
					"id": "crRnqeq3fhbid8uW1wOko",
					"type": "arrow"
				},
				{
					"id": "vz2J-xxiwo8Q9wsMflcPL",
					"type": "arrow"
				},
				{
					"id": "aVCuG-tTul2f4Us7l6nlw",
					"type": "arrow"
				}
			],
			"updated": 1710599375847,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 140,
			"versionNonce": 2089312795,
			"isDeleted": false,
			"id": "gCBXFcm-GfvbqXCwdgpFh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.76232452797103,
			"y": -752.7719999059418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.30078125,
			"height": 21.02734375,
			"seed": 425499221,
			"groupIds": [
				"ev-dPqIpxH1MQiE_BoMti"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710599257961,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 133,
			"versionNonce": 62372027,
			"isDeleted": false,
			"id": "8mH9y63xs1GkhDQb7jLCg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -375.75841827797103,
			"y": -750.4399686559418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.6171875,
			"height": 69.5703125,
			"seed": 1407223733,
			"groupIds": [
				"ev-dPqIpxH1MQiE_BoMti"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "J9z5YZsbY4CAnIdTzkRYu",
					"type": "arrow"
				}
			],
			"updated": 1710599265049,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 123,
			"versionNonce": 1530372725,
			"isDeleted": false,
			"id": "uPq-GusUk-vKNnSrpP6LV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -367.64123077797103,
			"y": -641.6274686559418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.30078125,
			"height": 21.02734375,
			"seed": 230049749,
			"groupIds": [
				"aqsyN8sPZHm9QOS68pswP"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710599260946,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 116,
			"versionNonce": 1213163125,
			"isDeleted": false,
			"id": "zaaJLz8BhY_kHvt78MCbz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.63732452797103,
			"y": -639.2954374059418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.6171875,
			"height": 69.5703125,
			"seed": 1000899893,
			"groupIds": [
				"aqsyN8sPZHm9QOS68pswP"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "crRnqeq3fhbid8uW1wOko",
					"type": "arrow"
				}
			],
			"updated": 1710599268129,
			"link": null,
			"locked": false
		},
		{
			"id": "J9z5YZsbY4CAnIdTzkRYu",
			"type": "arrow",
			"x": -441.17248077797103,
			"y": -660.2270780309418,
			"width": 62.59765625,
			"height": 56.375,
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
			"seed": 1792694933,
			"version": 44,
			"versionNonce": 752284699,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599265049,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					62.59765625,
					-56.375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "jNvxcbSMjWF0yOHAVuPzx",
				"focus": 0.47077798748386035,
				"gap": 2.46875
			},
			"endBinding": {
				"elementId": "8mH9y63xs1GkhDQb7jLCg",
				"focus": 0.5266930818902807,
				"gap": 2.81640625
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "crRnqeq3fhbid8uW1wOko",
			"type": "arrow",
			"x": -441.66857452797103,
			"y": -658.1333280309418,
			"width": 66.74609375,
			"height": 56.35546875,
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
			"seed": 391571803,
			"version": 47,
			"versionNonce": 1139822869,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599268129,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					66.74609375,
					56.35546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "jNvxcbSMjWF0yOHAVuPzx",
				"focus": -0.4892736833821264,
				"gap": 1.97265625
			},
			"endBinding": {
				"elementId": "zaaJLz8BhY_kHvt78MCbz",
				"focus": -0.5437630022495257,
				"gap": 3.28515625
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vz2J-xxiwo8Q9wsMflcPL",
			"type": "arrow",
			"x": -671.008418277971,
			"y": -650.4302030309418,
			"width": 156.7499999999999,
			"height": 4.926618185440702,
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
			"seed": 249876437,
			"version": 60,
			"versionNonce": 1303463547,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					156.7499999999999,
					-4.926618185440702
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "JJ8Cm8GyGk7Dr507DOVFu",
				"gap": 12.77734375,
				"focus": 0.16271022764799556
			},
			"endBinding": {
				"elementId": "jNvxcbSMjWF0yOHAVuPzx",
				"gap": 1,
				"focus": -0.0364361853427278
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "TGT9kV3r",
			"type": "text",
			"x": -644.164668277971,
			"y": -740.4614530309418,
			"width": 214.43984985351562,
			"height": 50,
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
			"seed": 2119702267,
			"version": 120,
			"versionNonce": 1425430971,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599309396,
			"link": null,
			"locked": false,
			"text": "User, Chat, UserChat\n     (MySQL)",
			"rawText": "User, Chat, UserChat\n     (MySQL)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "User, Chat, UserChat\n     (MySQL)",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 111,
			"versionNonce": 1593757845,
			"isDeleted": false,
			"id": "r9Ned-QdXINmmHfFu5Xd4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -525.897090152971,
			"y": -558.6059842809418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.53515625,
			"height": 85,
			"seed": 381297723,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "a5rMYlZG"
				},
				{
					"id": "aVCuG-tTul2f4Us7l6nlw",
					"type": "arrow"
				}
			],
			"updated": 1710599375847,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1068888379,
			"isDeleted": false,
			"id": "a5rMYlZG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -515.4614822428148,
			"y": -546.1059842809418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.6639404296875,
			"height": 60,
			"seed": 100656347,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710599367469,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "User +\nUserChat\nCache",
			"rawText": "User + UserChat Cache",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "r9Ned-QdXINmmHfFu5Xd4",
			"originalText": "User + UserChat Cache",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"id": "aVCuG-tTul2f4Us7l6nlw",
			"type": "arrow",
			"x": -477.80919952797103,
			"y": -621.4575467809418,
			"width": 2.84375,
			"height": 61.5234375,
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
			"seed": 1931319067,
			"version": 48,
			"versionNonce": 188916699,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.84375,
					61.5234375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "jNvxcbSMjWF0yOHAVuPzx",
				"gap": 1.546875,
				"focus": 0.028523441459162364
			},
			"endBinding": {
				"elementId": "r9Ned-QdXINmmHfFu5Xd4",
				"gap": 1.328125,
				"focus": 0.1155730668043838
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "BwaaLNNCPxVaBOJv9DE0h",
			"type": "arrow",
			"x": -516.707637027971,
			"y": -555.0044217809418,
			"width": 158.953125,
			"height": 43.4296875,
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
			"seed": 1532514267,
			"version": 164,
			"versionNonce": 240697115,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-86.5625,
					-27.28125
				],
				[
					-158.953125,
					16.1484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "PEUceZpcx3pWgv7U0jF6Y",
				"gap": 3.28515625,
				"focus": 0.14529360450950213
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Gqvk9uplWS7ubOLCQwKck",
			"type": "arrow",
			"x": -675.527949527971,
			"y": -513.9497342809418,
			"width": 35.66015625,
			"height": 115.16796875,
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
			"seed": 666196149,
			"version": 112,
			"versionNonce": 911666747,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					35.66015625,
					54.78125
				],
				[
					1.0625,
					115.16796875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "PEUceZpcx3pWgv7U0jF6Y",
				"gap": 3.41796875,
				"focus": -0.687880876831963
			},
			"endBinding": {
				"elementId": "x5kwWMS7bpdr8fsV0OYPW",
				"gap": 1.2421875,
				"focus": 0.7314858467151295
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"id": "k3ckeK9TStnY-WLs53fgY",
			"type": "arrow",
			"x": -673.211543277971,
			"y": -381.3794217809418,
			"width": 47.62890625,
			"height": 98.70312499999994,
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
			"seed": 1159368411,
			"version": 104,
			"versionNonce": 1643358555,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					47.62890625,
					51.7109375
				],
				[
					2.1171875,
					98.70312499999994
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "x5kwWMS7bpdr8fsV0OYPW",
				"gap": 2.49609375,
				"focus": -0.40352748304559927
			},
			"endBinding": {
				"elementId": "22QlrxIXehC5DxTyIREG2",
				"gap": 2.78125,
				"focus": 0.657114845585742
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"id": "asdP8kWA3K49CZTqHEYxz",
			"type": "arrow",
			"x": -676.711543277971,
			"y": -526.9262967809418,
			"width": 103,
			"height": 258.74609375,
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
			"seed": 600609237,
			"version": 162,
			"versionNonce": 1980483067,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					103,
					148.5234375
				],
				[
					5.1953125,
					258.74609375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "PEUceZpcx3pWgv7U0jF6Y",
				"gap": 2.234375,
				"focus": -0.7804709883726397
			},
			"endBinding": {
				"elementId": "22QlrxIXehC5DxTyIREG2",
				"gap": 2.359375,
				"focus": 0.8360645414443563
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"type": "ellipse",
			"version": 125,
			"versionNonce": 1592666933,
			"isDeleted": false,
			"id": "3mTtSwsZ_dKbpyL2wAXHL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -458.06701202797103,
			"y": -432.6274686559418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.30078125,
			"height": 21.02734375,
			"seed": 2102494715,
			"groupIds": [
				"G8gRY7SyRcBrkXkQH1Js9"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710599493857,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 122,
			"versionNonce": 32414811,
			"isDeleted": false,
			"id": "boCpx_K85Sv8eJW67maJD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -462.06310577797103,
			"y": -430.2954374059418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.6171875,
			"height": 69.5703125,
			"seed": 1858408091,
			"groupIds": [
				"G8gRY7SyRcBrkXkQH1Js9"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "Xwp_yJLs_eLpX75jEa6rM",
					"type": "arrow"
				},
				{
					"id": "Mwmoj7q8Yi-p3ZuuxeObn",
					"type": "arrow"
				},
				{
					"id": "Lrzpfaq4NWzT6MP6cswcf",
					"type": "arrow"
				},
				{
					"id": "SoSzY61f1TZASu8gwUUD7",
					"type": "arrow"
				}
			],
			"updated": 1710599589685,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 165,
			"versionNonce": 618196795,
			"isDeleted": false,
			"id": "1j04qEslRlFxh6SNMtI9s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -347.37169952797103,
			"y": -489.4126249059418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.30078125,
			"height": 21.02734375,
			"seed": 385691771,
			"groupIds": [
				"lN3Nf85ypH-MmnDYb-2Pf"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710599821068,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 229,
			"versionNonce": 1387546357,
			"isDeleted": false,
			"id": "u7AB4CGROoi5RU_fygnu9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -351.36779327797103,
			"y": -488.2446561559418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.6171875,
			"height": 70,
			"seed": 1519872283,
			"groupIds": [
				"lN3Nf85ypH-MmnDYb-2Pf"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "Xwp_yJLs_eLpX75jEa6rM",
					"type": "arrow"
				},
				{
					"id": "keX3-gWYeb5ZqWdZyyUrr",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "sb8f6GVO"
				}
			],
			"updated": 1710599830093,
			"link": null,
			"locked": false
		},
		{
			"id": "sb8f6GVO",
			"type": "text",
			"x": -344.80717773842025,
			"y": -483.2446561559418,
			"width": 56.49595642089844,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"lN3Nf85ypH-MmnDYb-2Pf"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1345735381,
			"version": 111,
			"versionNonce": 718905429,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599830094,
			"link": null,
			"locked": false,
			"text": "\nCassan\ndra",
			"rawText": "\nCassandra",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 54,
			"containerId": "u7AB4CGROoi5RU_fygnu9",
			"originalText": "\nCassandra",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 125,
			"versionNonce": 2136466997,
			"isDeleted": false,
			"id": "JjSCS19RvuNDO5DuxDrgG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -348.06701202797103,
			"y": -362.6274686559418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.30078125,
			"height": 21.02734375,
			"seed": 2050988795,
			"groupIds": [
				"NankLU50IyqDSAzZEjwoq"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710599495454,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 121,
			"versionNonce": 1864678837,
			"isDeleted": false,
			"id": "Z8h2Kir-0ZJMY7EbCwkVe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -352.06310577797103,
			"y": -360.2954374059418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.6171875,
			"height": 69.5703125,
			"seed": 791184283,
			"groupIds": [
				"NankLU50IyqDSAzZEjwoq"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "Mwmoj7q8Yi-p3ZuuxeObn",
					"type": "arrow"
				},
				{
					"id": "keX3-gWYeb5ZqWdZyyUrr",
					"type": "arrow"
				},
				{
					"id": "SoSzY61f1TZASu8gwUUD7",
					"type": "arrow"
				}
			],
			"updated": 1710600859802,
			"link": null,
			"locked": false
		},
		{
			"id": "4DOsROXw",
			"type": "text",
			"x": -370.76623077797103,
			"y": -398.4341092809418,
			"width": 118.44793701171875,
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
			"seed": 856365525,
			"version": 66,
			"versionNonce": 349298517,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599524768,
			"link": null,
			"locked": false,
			"text": "Message Table",
			"rawText": "Message Table",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Message Table",
			"lineHeight": 1.25
		},
		{
			"id": "Xwp_yJLs_eLpX75jEa6rM",
			"type": "arrow",
			"x": -391.89513702797103,
			"y": -417.3716092809418,
			"width": 39.52734375,
			"height": 33.09642977771165,
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
			"seed": 518508053,
			"version": 179,
			"versionNonce": 1083666555,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					13.9453125,
					-24.9453125
				],
				[
					39.52734375,
					-33.09642977771165
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "boCpx_K85Sv8eJW67maJD",
				"focus": 0.42647194315319964,
				"gap": 1
			},
			"endBinding": {
				"elementId": "u7AB4CGROoi5RU_fygnu9",
				"gap": 1,
				"focus": 0.1873026354160191
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"id": "Mwmoj7q8Yi-p3ZuuxeObn",
			"type": "arrow",
			"x": -413.11388702797103,
			"y": -358.2544217809418,
			"width": 57.87109375,
			"height": 43.5625,
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
			"seed": 649581467,
			"version": 104,
			"versionNonce": 1328675163,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710599623074,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					13.296875,
					33.07421875
				],
				[
					57.87109375,
					43.5625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "boCpx_K85Sv8eJW67maJD",
				"focus": 0.01716220402180718,
				"gap": 2.470703125
			},
			"endBinding": {
				"elementId": "Z8h2Kir-0ZJMY7EbCwkVe",
				"focus": -0.45972546098290284,
				"gap": 3.1796875
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"id": "keX3-gWYeb5ZqWdZyyUrr",
			"type": "arrow",
			"x": -279.61388702797103,
			"y": -449.8355106593193,
			"width": 39.359375,
			"height": 120.4209326283775,
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
			"seed": 1605841909,
			"version": 199,
			"versionNonce": 1458153755,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.359375,
					57.9717138783775
				],
				[
					0.7578125,
					120.4209326283775
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "u7AB4CGROoi5RU_fygnu9",
				"gap": 2.13671875,
				"focus": -0.5912548966709245
			},
			"endBinding": {
				"elementId": "Z8h2Kir-0ZJMY7EbCwkVe",
				"focus": 0.6390504014531985,
				"gap": 3.58984375
			},
			"startArrowhead": "arrow",
			"endArrowhead": "arrow"
		},
		{
			"id": "SgQ_LD2E_MNM3HhyoVsvt",
			"type": "arrow",
			"x": -677.945918277971,
			"y": -530.6801486046038,
			"width": 216.57421875,
			"height": 132.378851823662,
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
			"seed": 1797657717,
			"version": 51,
			"versionNonce": 1664659707,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					216.57421875,
					132.378851823662
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "PEUceZpcx3pWgv7U0jF6Y",
				"gap": 1,
				"focus": -0.663566127164718
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Lrzpfaq4NWzT6MP6cswcf",
			"type": "arrow",
			"x": -674.281855777971,
			"y": -388.8911405309418,
			"width": 210.16796875,
			"height": 2.125,
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
			"seed": 552376155,
			"version": 53,
			"versionNonce": 866366491,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600141021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					210.16796875,
					-2.125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "x5kwWMS7bpdr8fsV0OYPW",
				"gap": 1.42578125,
				"focus": 0.33420115285249485
			},
			"endBinding": {
				"elementId": "boCpx_K85Sv8eJW67maJD",
				"gap": 2.05078125,
				"focus": -0.11729643057086442
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SoSzY61f1TZASu8gwUUD7",
			"type": "arrow",
			"x": -681.5375511501084,
			"y": -250.0395780309418,
			"width": 336.3739188129506,
			"height": 40.852676065670494,
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
			"seed": 1634534165,
			"version": 199,
			"versionNonce": 916340181,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600860288,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					99.92366412213732,
					2.578125
				],
				[
					336.3739188129506,
					-38.274551065670494
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "22QlrxIXehC5DxTyIREG2",
				"focus": 0.9662347109633166,
				"gap": 1
			},
			"endBinding": {
				"elementId": "Z8h2Kir-0ZJMY7EbCwkVe",
				"focus": -0.7934996019720129,
				"gap": 2.4109958093295063
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "M3f3HR6k3fjhg6GtxmA1J",
			"type": "rectangle",
			"x": -272.3909842180235,
			"y": -743.5512967809418,
			"width": 297.33260471938183,
			"height": 147.3359375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"x32gOGlOPrTBd_OiUMpbc"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 2117298805,
			"version": 149,
			"versionNonce": 1819906203,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1710600075260,
			"link": null,
			"locked": false
		},
		{
			"id": "SFl7CKtC",
			"type": "text",
			"x": -264.5980154680235,
			"y": -726.2739530309418,
			"width": 279.5998229980469,
			"height": 120,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"x32gOGlOPrTBd_OiUMpbc"
			],
			"frameId": null,
			"roundness": null,
			"seed": 9852309,
			"version": 299,
			"versionNonce": 422546011,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710600113641,
			"link": null,
			"locked": false,
			"text": "           Note:\nSince there are no write heavy\noperation, we can store it these \ndata in SQL Tables, to keep it\nsimple with Single Leader replication\nsince no potential write conflicts.",
			"rawText": "           Note:\nSince there are no write heavy\noperation, we can store it these \ndata in SQL Tables, to keep it\nsimple with Single Leader replication\nsince no potential write conflicts.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "           Note:\nSince there are no write heavy\noperation, we can store it these \ndata in SQL Tables, to keep it\nsimple with Single Leader replication\nsince no potential write conflicts.",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 572,
			"versionNonce": 779722293,
			"isDeleted": false,
			"id": "4WTpH0yg0Yf2h94pOQH0d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -493.3219013433954,
			"y": -253.8402691202699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 408.8085764983032,
			"height": 313.3695554827352,
			"seed": 119014523,
			"groupIds": [
				"67XPnpEMPFNHx7L872At3"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710600702667,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1183,
			"versionNonce": 1858295157,
			"isDeleted": false,
			"id": "vbuuKp4r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -486.58752634339567,
			"y": -238.9965191202699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 399.4878234863281,
			"height": 300,
			"seed": 674741531,
			"groupIds": [
				"67XPnpEMPFNHx7L872At3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710600697114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "                Note:\nSince the \"Message Table\" is gonna be \nwrite heavy, we can use Cassandra/HBase\nas the NoSQL db of choice, as each /send API\nwill store message in the table and will be \nwrite-heavy. \n\nHigher write-thoughput is supported by Cassandra\n/HBase since all the writes are going to \nin-memory buffer first. Column Oriented storage \nisn't imp since each message will have mulutiple \ncolumns to consure data from each row and hence\nHBase wont be any helpful being a column Oriented\nstore \n",
			"rawText": "                Note:\nSince the \"Message Table\" is gonna be \nwrite heavy, we can use Cassandra/HBase\nas the NoSQL db of choice, as each /send API\nwill store message in the table and will be \nwrite-heavy. \n\nHigher write-thoughput is supported by Cassandra\n/HBase since all the writes are going to \nin-memory buffer first. Column Oriented storage \nisn't imp since each message will have mulutiple \ncolumns to consure data from each row and hence\nHBase wont be any helpful being a column Oriented\nstore \n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "                Note:\nSince the \"Message Table\" is gonna be \nwrite heavy, we can use Cassandra/HBase\nas the NoSQL db of choice, as each /send API\nwill store message in the table and will be \nwrite-heavy. \n\nHigher write-thoughput is supported by Cassandra\n/HBase since all the writes are going to \nin-memory buffer first. Column Oriented storage \nisn't imp since each message will have mulutiple \ncolumns to consure data from each row and hence\nHBase wont be any helpful being a column Oriented\nstore \n",
			"lineHeight": 1.25,
			"baseline": 294
		},
		{
			"type": "rectangle",
			"version": 477,
			"versionNonce": 1220345589,
			"isDeleted": false,
			"id": "dfydrqhFLitBk0-xf8XaT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -208.68834276032663,
			"y": -480.0096974445038,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 337.05895148331706,
			"height": 147.3359375,
			"seed": 1892906933,
			"groupIds": [
				"WncHyRWUBJ_7SleTyRReH"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1710600578801,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 858,
			"versionNonce": 308427445,
			"isDeleted": false,
			"id": "3377SQYU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 40,
			"angle": 0,
			"x": -201.57757223866207,
			"y": -464.78955192283934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 321.2637939453125,
			"height": 80,
			"seed": 1196734741,
			"groupIds": [
				"WncHyRWUBJ_7SleTyRReH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710600197055,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "                Note:\n\"Message Table\" must be partitioned on\nChatId and also should have fields like \ntimestamp and message content.",
			"rawText": "                Note:\n\"Message Table\" must be partitioned on\nChatId and also should have fields like \ntimestamp and message content.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "                Note:\n\"Message Table\" must be partitioned on\nChatId and also should have fields like \ntimestamp and message content.",
			"lineHeight": 1.25,
			"baseline": 74
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
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": "arrow",
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1521.815156377198,
		"scrollY": 1207.163308755129,
		"zoom": {
			"value": 0.6330607998371122
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