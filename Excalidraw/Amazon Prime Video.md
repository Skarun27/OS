---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Functional requirements:
1. Upload Video
2. Search a video
3. View videos (across multiple devices)

Non-functional requirements:
1. Uploads should be fast
2. No/minimal buffer
3. Low latency
4. High availability - eventual consistency
5. Reliability ^rIpGjYkV

Design Amazon Prime Video ^EsIxkmBm

Assumptions:
100 million monthly active users ^cXnCqVph

Viewers ^vX2hMiNl

Content creators ^0UqqDOF1

Video Upload service ^L6KBjarz

Processing Queue ^v1QZiyDq

Video Splitter ^wB4zsZQs


Object Store
(S3) ^J1uirfFo

Metadata DB ^BJfA45h7

Video Encoder ^5LtClsha

Load Balancer ^BdbqKjTw

Search Service ^0jaLRhHg

Elastic Search
Video API ^Arb1ZCmc

View Video Service ^UtNopFhU

Cache ^a7i5wgdt

CDN ^gtZXzfN9

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
			"version": 396,
			"versionNonce": 147506651,
			"isDeleted": false,
			"id": "rIpGjYkV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -746.7482638888889,
			"y": -527.2330729166667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 407.2796630859375,
			"height": 275,
			"seed": 1908118755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710451566000,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Functional requirements:\n1. Upload Video\n2. Search a video\n3. View videos (across multiple devices)\n\nNon-functional requirements:\n1. Uploads should be fast\n2. No/minimal buffer\n3. Low latency\n4. High availability - eventual consistency\n5. Reliability",
			"rawText": "Functional requirements:\n1. Upload Video\n2. Search a video\n3. View videos (across multiple devices)\n\nNon-functional requirements:\n1. Uploads should be fast\n2. No/minimal buffer\n3. Low latency\n4. High availability - eventual consistency\n5. Reliability",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Functional requirements:\n1. Upload Video\n2. Search a video\n3. View videos (across multiple devices)\n\nNon-functional requirements:\n1. Uploads should be fast\n2. No/minimal buffer\n3. Low latency\n4. High availability - eventual consistency\n5. Reliability",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 852657083,
			"isDeleted": false,
			"id": "EsIxkmBm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -202.4275173611111,
			"y": -487.72569444444446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 468.07183837890625,
			"height": 45,
			"seed": 1591459939,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710451569850,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Design Amazon Prime Video",
			"rawText": "Design Amazon Prime Video",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Design Amazon Prime Video",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 221,
			"versionNonce": 1982088483,
			"isDeleted": false,
			"id": "cXnCqVph",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 468.96875,
			"y": -482.52734375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 307.27972412109375,
			"height": 50,
			"seed": 798149411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438235840,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assumptions:\n100 million monthly active users",
			"rawText": "Assumptions:\n100 million monthly active users",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assumptions:\n100 million monthly active users",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 229,
			"versionNonce": 1106016461,
			"isDeleted": false,
			"id": "W3CEuU1V75oFEJwstxoXT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -618.1861979166667,
			"y": -153.56789434523807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1321263939,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0UqqDOF1"
				},
				{
					"id": "6CBdhqjAA55Xgdi4lKaW2",
					"type": "arrow"
				},
				{
					"id": "wnTKum4NSNCGbLH92OO6K",
					"type": "arrow"
				}
			],
			"updated": 1710438699683,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 1798759373,
			"isDeleted": false,
			"id": "0UqqDOF1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -578.251703898112,
			"y": -140.54836309523807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 84.75991821289062,
			"height": 50,
			"seed": 1748189229,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438684876,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Content\ncreators",
			"rawText": "Content creators",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "W3CEuU1V75oFEJwstxoXT",
			"originalText": "Content creators",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 279,
			"versionNonce": 932462253,
			"isDeleted": false,
			"id": "tnLHXlJ2_2yAx71IDUBpL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -626.4255022321429,
			"y": 280.6450892857142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 56.19140625,
			"seed": 1383981133,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "vX2hMiNl"
				},
				{
					"id": "nBy-wiCrQh373m3nTtWyM",
					"type": "arrow"
				},
				{
					"id": "7rDLqBvbIL_RS1KGltCnl",
					"type": "arrow"
				},
				{
					"id": "2irPvn3bPKetAe_w1e2jJ",
					"type": "arrow"
				}
			],
			"updated": 1710438855337,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1186717891,
			"isDeleted": false,
			"id": "vX2hMiNl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -578.2310137067523,
			"y": 296.2407924107142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 68.23992919921875,
			"height": 25,
			"seed": 791199245,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438828125,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Viewers",
			"rawText": "Viewers",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tnLHXlJ2_2yAx71IDUBpL",
			"originalText": "Viewers",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 285,
			"versionNonce": 1730509197,
			"isDeleted": false,
			"id": "9scyhSvOaZw1TmiWcZJ2q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -222.49655877976193,
			"y": -151.80598958333326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 884000429,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "L6KBjarz"
				},
				{
					"id": "6CBdhqjAA55Xgdi4lKaW2",
					"type": "arrow"
				},
				{
					"id": "PMzdp_3PMvLd5cotCFqcX",
					"type": "arrow"
				},
				{
					"id": "BRdUR8sqcd-PNydxMxzca",
					"type": "arrow"
				}
			],
			"updated": 1710438686809,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 230,
			"versionNonce": 884522989,
			"isDeleted": false,
			"id": "L6KBjarz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -201.84205591110958,
			"y": -138.78645833333326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.31990051269531,
			"height": 50,
			"seed": 161310989,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438686809,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Video Upload\nservice",
			"rawText": "Video Upload service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "9scyhSvOaZw1TmiWcZJ2q",
			"originalText": "Video Upload service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 259,
			"versionNonce": 1294210389,
			"isDeleted": false,
			"id": "6CBdhqjAA55Xgdi4lKaW2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -446.39713541666674,
			"y": -110.37012787174703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 222.67206101190482,
			"height": 3.6248901105925313,
			"seed": 1591145069,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560080,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "W3CEuU1V75oFEJwstxoXT",
				"gap": 7.16015625,
				"focus": 0.16856900058908156
			},
			"endBinding": {
				"elementId": "9scyhSvOaZw1TmiWcZJ2q",
				"gap": 1.228515625,
				"focus": 0.039852099340646104
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
					222.67206101190482,
					-3.6248901105925313
				]
			]
		},
		{
			"type": "rectangle",
			"version": 334,
			"versionNonce": 1781810381,
			"isDeleted": false,
			"id": "OSjO8amG9JJtn0I1NtioL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 131.748046875,
			"y": -154.88616071428555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1222153123,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "v1QZiyDq"
				},
				{
					"id": "TE-GKfXxWyL4cxrE0lgpM",
					"type": "arrow"
				},
				{
					"id": "5HEY_TWbVR0mpIJEPOD-k",
					"type": "arrow"
				}
			],
			"updated": 1710438688509,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 1514939181,
			"isDeleted": false,
			"id": "v1QZiyDq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 164.3925552368164,
			"y": -141.86662946428555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.33988952636719,
			"height": 50,
			"seed": 1416374083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438688509,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Processing\nQueue",
			"rawText": "Processing Queue",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "OSjO8amG9JJtn0I1NtioL",
			"originalText": "Processing Queue",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 393,
			"versionNonce": 759590509,
			"isDeleted": false,
			"id": "br4xrzcTIMX6poigg2eWQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 6.5495721726191505,
			"y": 37.34951636904748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1194226755,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "wB4zsZQs"
				},
				{
					"id": "PMzdp_3PMvLd5cotCFqcX",
					"type": "arrow"
				},
				{
					"id": "TE-GKfXxWyL4cxrE0lgpM",
					"type": "arrow"
				}
			],
			"updated": 1710438690499,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 2024282317,
			"isDeleted": false,
			"id": "wB4zsZQs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 22.904094877697275,
			"y": 62.86904761904748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 131.91986083984375,
			"height": 25,
			"seed": 444396515,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438690499,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Video Splitter",
			"rawText": "Video Splitter",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "br4xrzcTIMX6poigg2eWQ",
			"originalText": "Video Splitter",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 457,
			"versionNonce": 1543869571,
			"isDeleted": false,
			"id": "dh66_M5fIi39e8NlWZUFM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 575.2067522321429,
			"y": -212.09616815476193,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.223400297619,
			"height": 150.70238095238096,
			"seed": 1087373741,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "J1uirfFo"
				},
				{
					"id": "bTZWuo6_z60omCZYQsmDg",
					"type": "arrow"
				},
				{
					"id": "H_0IA4Pm269cKyeFXKue0",
					"type": "arrow"
				},
				{
					"id": "TkFFy9ut7tqCr1i-5tGAA",
					"type": "arrow"
				}
			],
			"updated": 1710438891931,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 459,
			"versionNonce": 583013251,
			"isDeleted": false,
			"id": "J1uirfFo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 588.5185103643508,
			"y": -174.24497767857144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.59988403320312,
			"height": 75,
			"seed": 1679639565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438574645,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "\nObject Store\n(S3)",
			"rawText": "\nObject Store\n(S3)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "dh66_M5fIi39e8NlWZUFM",
			"originalText": "\nObject Store\n(S3)",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "ellipse",
			"version": 221,
			"versionNonce": 481757507,
			"isDeleted": false,
			"id": "FOk00QQoSrnBNEcsziuJB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 573.3037574404764,
			"y": -213.27827380952385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.73828125,
			"height": 37.36328125,
			"seed": 1448819213,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710438427308,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 471,
			"versionNonce": 290604099,
			"isDeleted": false,
			"id": "I5PThndqke4_Ynm4Js9D5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 579.0536920456657,
			"y": 36.753441220238074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.223400297619,
			"height": 150.70238095238096,
			"seed": 1500118157,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BJfA45h7"
				},
				{
					"id": "BRdUR8sqcd-PNydxMxzca",
					"type": "arrow"
				},
				{
					"id": "ZX7vdcmORSEppiF1dNQv5",
					"type": "arrow"
				},
				{
					"id": "H_0IA4Pm269cKyeFXKue0",
					"type": "arrow"
				}
			],
			"updated": 1710438877350,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 466,
			"versionNonce": 799970925,
			"isDeleted": false,
			"id": "BJfA45h7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 585.9654333932057,
			"y": 99.60463169642856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140.39991760253906,
			"height": 25,
			"seed": 292872941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438466075,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Metadata DB",
			"rawText": "Metadata DB",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "I5PThndqke4_Ynm4Js9D5",
			"originalText": "Metadata DB",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "ellipse",
			"version": 274,
			"versionNonce": 296170243,
			"isDeleted": false,
			"id": "T6xz4LKl9knwAz5eNHhcS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 577.943107968285,
			"y": 34.358537946428555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.73828125,
			"height": 37.36328125,
			"seed": 672398669,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710438472425,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 412,
			"versionNonce": 381378765,
			"isDeleted": false,
			"id": "7HUZBqgKjyHhjo36hsk-z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 296.4485488164994,
			"y": 38.196428571428555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1076193005,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "5LtClsha"
				},
				{
					"id": "5HEY_TWbVR0mpIJEPOD-k",
					"type": "arrow"
				},
				{
					"id": "bTZWuo6_z60omCZYQsmDg",
					"type": "arrow"
				}
			],
			"updated": 1710438692041,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 529514285,
			"isDeleted": false,
			"id": "5LtClsha",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 312.2730574834916,
			"y": 63.715959821428555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 132.97988891601562,
			"height": 25,
			"seed": 907280717,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438692041,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Video Encoder",
			"rawText": "Video Encoder",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "7HUZBqgKjyHhjo36hsk-z",
			"originalText": "Video Encoder",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 196,
			"versionNonce": 1272634805,
			"isDeleted": false,
			"id": "PMzdp_3PMvLd5cotCFqcX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -55.86869448707216,
			"y": -75.79433837852389,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.96610080830743,
			"height": 109.53261962852378,
			"seed": 472119341,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560080,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9scyhSvOaZw1TmiWcZJ2q",
				"gap": 1.9989580426897646,
				"focus": -0.5045158019813538
			},
			"endBinding": {
				"elementId": "br4xrzcTIMX6poigg2eWQ",
				"gap": 3.611235119047592,
				"focus": -0.2854070034014118
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
					81.96610080830743,
					109.53261962852378
				]
			]
		},
		{
			"type": "arrow",
			"version": 233,
			"versionNonce": 1405924469,
			"isDeleted": false,
			"id": "TE-GKfXxWyL4cxrE0lgpM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.81312149460294,
			"y": 29.486049107142644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.11147524979705,
			"height": 104.1666666666665,
			"seed": 378810371,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560080,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "br4xrzcTIMX6poigg2eWQ",
				"gap": 7.863467261904816,
				"focus": 0.2443195605115818
			},
			"endBinding": {
				"elementId": "OSjO8amG9JJtn0I1NtioL",
				"gap": 4.166480654761699,
				"focus": -0.10749077774041292
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
					60.11147524979705,
					-104.1666666666665
				]
			]
		},
		{
			"type": "arrow",
			"version": 194,
			"versionNonce": 1915301749,
			"isDeleted": false,
			"id": "5HEY_TWbVR0mpIJEPOD-k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 287.21676308109215,
			"y": -76.23195684523807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.66334833436184,
			"height": 113.42838541666663,
			"seed": 1861245293,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "OSjO8amG9JJtn0I1NtioL",
				"gap": 2.6151413690474783,
				"focus": -0.2546329977593716
			},
			"endBinding": {
				"elementId": "7HUZBqgKjyHhjo36hsk-z",
				"gap": 1,
				"focus": 0.5469533452895561
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
					117.66334833436184,
					113.42838541666663
				]
			]
		},
		{
			"type": "arrow",
			"version": 148,
			"versionNonce": 1484887605,
			"isDeleted": false,
			"id": "bTZWuo6_z60omCZYQsmDg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 461.3116863698293,
			"y": 36.75194061063954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.96694057166985,
			"height": 163.29382673075838,
			"seed": 1228346563,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7HUZBqgKjyHhjo36hsk-z",
				"gap": 1.46335565476204,
				"focus": 0.532207970149254
			},
			"endBinding": {
				"elementId": "dh66_M5fIi39e8NlWZUFM",
				"gap": 7.92812529064372,
				"focus": 0.6223228470247073
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
					105.96694057166985,
					-163.29382673075838
				]
			]
		},
		{
			"type": "arrow",
			"version": 231,
			"versionNonce": 1287148021,
			"isDeleted": false,
			"id": "BRdUR8sqcd-PNydxMxzca",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -110.44633851044372,
			"y": -73.02139136904759,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 682.148328547181,
			"height": 248.85044642857133,
			"seed": 423582605,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9scyhSvOaZw1TmiWcZJ2q",
				"gap": 2.7455357142856656,
				"focus": -0.1413870019635317
			},
			"endBinding": {
				"elementId": "I5PThndqke4_Ynm4Js9D5",
				"gap": 7.3517020089284415,
				"focus": -0.7807205946931051
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
					97.60591783289541,
					248.85044642857133
				],
				[
					682.148328547181,
					244.92559523809518
				]
			]
		},
		{
			"type": "rectangle",
			"version": 418,
			"versionNonce": 125069965,
			"isDeleted": false,
			"id": "fVFaEZEOo5pl3xs10pt-w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -377.1452011835006,
			"y": 82.72395833333337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 2056206979,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BdbqKjTw"
				},
				{
					"id": "wV5xXmsQ1o0mDnKZb3Qjj",
					"type": "arrow"
				},
				{
					"id": "wnTKum4NSNCGbLH92OO6K",
					"type": "arrow"
				},
				{
					"id": "nBy-wiCrQh373m3nTtWyM",
					"type": "arrow"
				},
				{
					"id": "4GrNJyMO4m8f-pGsG05CN",
					"type": "arrow"
				}
			],
			"updated": 1710438816414,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 381,
			"versionNonce": 482227459,
			"isDeleted": false,
			"id": "BdbqKjTw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -366.4207062494186,
			"y": 108.24348958333337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 143.17991638183594,
			"height": 25,
			"seed": 711651875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438597583,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Load Balancer",
			"rawText": "Load Balancer",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "fVFaEZEOo5pl3xs10pt-w",
			"originalText": "Load Balancer",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 492,
			"versionNonce": 1343382819,
			"isDeleted": false,
			"id": "hH3znKW_BiTFVHCFNGlDf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -188.77094523111975,
			"y": 259.5171130952382,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1655077645,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0jaLRhHg"
				},
				{
					"id": "wV5xXmsQ1o0mDnKZb3Qjj",
					"type": "arrow"
				},
				{
					"id": "h49YvISDSAfbpj7PImXbR",
					"type": "arrow"
				}
			],
			"updated": 1710438750159,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 471,
			"versionNonce": 1198508227,
			"isDeleted": false,
			"id": "0jaLRhHg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -177.69642893473304,
			"y": 285.0366443452382,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 142.47987365722656,
			"height": 25,
			"seed": 1805488493,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438750159,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Search Service",
			"rawText": "Search Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hH3znKW_BiTFVHCFNGlDf",
			"originalText": "Search Service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 462,
			"versionNonce": 1925276483,
			"isDeleted": false,
			"id": "am-lPQEDDxEenVJLqCGAt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 164.5251857212612,
			"y": 260.2127976190475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1624451491,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Arb1ZCmc"
				},
				{
					"id": "h49YvISDSAfbpj7PImXbR",
					"type": "arrow"
				},
				{
					"id": "ZX7vdcmORSEppiF1dNQv5",
					"type": "arrow"
				}
			],
			"updated": 1710438728875,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 454,
			"versionNonce": 1406796515,
			"isDeleted": false,
			"id": "Arb1ZCmc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 175.02969469342918,
			"y": 273.2323288690475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 143.61988830566406,
			"height": 50,
			"seed": 2091121987,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438728875,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Elastic Search\nVideo API",
			"rawText": "Elastic Search\nVideo API",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "am-lPQEDDxEenVJLqCGAt",
			"originalText": "Elastic Search\nVideo API",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 132,
			"versionNonce": 617878805,
			"isDeleted": false,
			"id": "wV5xXmsQ1o0mDnKZb3Qjj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -297.021968296596,
			"y": 162.54408482142856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 102.79017857142867,
			"height": 127.04611199047093,
			"seed": 1073078061,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fVFaEZEOo5pl3xs10pt-w",
				"gap": 3.781063988095184,
				"focus": 0.09217014594384662
			},
			"endBinding": {
				"elementId": "hH3znKW_BiTFVHCFNGlDf",
				"gap": 5.460844494047592,
				"focus": -0.4585514579556158
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
					11.365327380952408,
					80.66592261904759
				],
				[
					102.79017857142867,
					127.04611199047093
				]
			]
		},
		{
			"type": "arrow",
			"version": 200,
			"versionNonce": 2067423893,
			"isDeleted": false,
			"id": "h49YvISDSAfbpj7PImXbR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.924498058500717,
			"y": 296.8022808179772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.74925595238108,
			"height": 1.5277544280099846,
			"seed": 1912446275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hH3znKW_BiTFVHCFNGlDf",
				"gap": 8.217540922619037,
				"focus": -0.039055048686669216
			},
			"endBinding": {
				"elementId": "am-lPQEDDxEenVJLqCGAt",
				"gap": 2.7004278273808495,
				"focus": -0.021390982155430335
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
					177.74925595238108,
					1.5277544280099846
				]
			]
		},
		{
			"type": "arrow",
			"version": 367,
			"versionNonce": 2136688629,
			"isDeleted": false,
			"id": "ZX7vdcmORSEppiF1dNQv5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 330.8240138462613,
			"y": 294.362424439504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 287.70089285714243,
			"height": 104.70152414188493,
			"seed": 753349645,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "am-lPQEDDxEenVJLqCGAt",
				"gap": 1.6699218750001137,
				"focus": -0.06376255471547927
			},
			"endBinding": {
				"elementId": "I5PThndqke4_Ynm4Js9D5",
				"gap": 2.205078125000057,
				"focus": -0.01370976378707081
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
					236.69270833333303,
					-3.8347086656945066
				],
				[
					287.70089285714243,
					-104.70152414188493
				]
			]
		},
		{
			"type": "arrow",
			"version": 128,
			"versionNonce": 931089653,
			"isDeleted": false,
			"id": "wnTKum4NSNCGbLH92OO6K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -530.8724147251672,
			"y": -74.16722470238096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.35342261904754,
			"height": 189.03645833333326,
			"seed": 1637326915,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "W3CEuU1V75oFEJwstxoXT",
				"gap": 3.3616071428571104,
				"focus": 0.012015116310479227
			},
			"endBinding": {
				"elementId": "fVFaEZEOo5pl3xs10pt-w",
				"gap": 3.3737909226191505,
				"focus": -0.2902027688533261
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
					22.54464285714272,
					154.06994047619037
				],
				[
					150.35342261904754,
					189.03645833333326
				]
			]
		},
		{
			"type": "arrow",
			"version": 310,
			"versionNonce": 206825045,
			"isDeleted": false,
			"id": "nBy-wiCrQh373m3nTtWyM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -537.0273043898884,
			"y": 276.20851934523796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 156.9993837123401,
			"height": 141.9754464285713,
			"seed": 43675267,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tnLHXlJ2_2yAx71IDUBpL",
				"gap": 4.436569940476261,
				"focus": -0.05483757851762229
			},
			"endBinding": {
				"elementId": "fVFaEZEOo5pl3xs10pt-w",
				"gap": 2.8827194940477057,
				"focus": 0.018711249646004964
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
					46.08420514091148,
					-123.14732142857133
				],
				[
					156.9993837123401,
					-141.9754464285713
				]
			]
		},
		{
			"type": "rectangle",
			"version": 530,
			"versionNonce": 1826286413,
			"isDeleted": false,
			"id": "zJ2KXVlIqqJbxu081xB0k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.24713570731024,
			"y": 412.9400809151788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 755639501,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "UtNopFhU"
				},
				{
					"id": "Dj4a_rhZlUFwZAZOWSeSV",
					"type": "arrow"
				},
				{
					"id": "4GrNJyMO4m8f-pGsG05CN",
					"type": "arrow"
				}
			],
			"updated": 1710438816414,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 526,
			"versionNonce": 405577539,
			"isDeleted": false,
			"id": "UtNopFhU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.91264016287664,
			"y": 425.9596121651788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 95.95991516113281,
			"height": 50,
			"seed": 124125997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438767207,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "View Video\nService",
			"rawText": "View Video Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zJ2KXVlIqqJbxu081xB0k",
			"originalText": "View Video Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 553,
			"versionNonce": 24954595,
			"isDeleted": false,
			"id": "cTk98LjQmIExvomizS_i9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.01253691173724,
			"y": 402.79127139136926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 164.62890625,
			"height": 76.0390625,
			"seed": 1577928077,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "a7i5wgdt"
				},
				{
					"id": "H_0IA4Pm269cKyeFXKue0",
					"type": "arrow"
				}
			],
			"updated": 1710438794650,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 556,
			"versionNonce": 440664099,
			"isDeleted": false,
			"id": "a7i5wgdt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 218.7870120093935,
			"y": 428.31080264136926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.0799560546875,
			"height": 25,
			"seed": 348589037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438787444,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cache",
			"rawText": "Cache",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "cTk98LjQmIExvomizS_i9",
			"originalText": "Cache",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 524,
			"versionNonce": 1397616661,
			"isDeleted": false,
			"id": "H_0IA4Pm269cKyeFXKue0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 333.5025852748327,
			"y": 441.44696335565493,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 337.42187499999983,
			"height": 250.84821428571425,
			"seed": 1114590701,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cTk98LjQmIExvomizS_i9",
				"gap": 3.8611421130954113,
				"focus": 0.10060690090363615
			},
			"endBinding": {
				"elementId": "I5PThndqke4_Ynm4Js9D5",
				"gap": 3.1429268973216153,
				"focus": -0.2399556159069117
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
					322.69345238095224,
					-13.210565476190482
				],
				[
					337.42187499999983,
					-250.84821428571425
				]
			]
		},
		{
			"type": "arrow",
			"version": 75,
			"versionNonce": 217612629,
			"isDeleted": false,
			"id": "Dj4a_rhZlUFwZAZOWSeSV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -15.340420677548309,
			"y": 452.21333240327397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 180.56919642857133,
			"height": 3.0394345238095184,
			"seed": 1515252899,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zJ2KXVlIqqJbxu081xB0k",
				"gap": 4.277808779761926,
				"focus": 0.06880547959200074
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
					180.56919642857133,
					-3.0394345238095184
				]
			]
		},
		{
			"type": "arrow",
			"version": 203,
			"versionNonce": 1499958965,
			"isDeleted": false,
			"id": "4GrNJyMO4m8f-pGsG05CN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.60009329659596,
			"y": 160.0555943080359,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.2410714285714,
			"height": 296.62574404761904,
			"seed": 1068725475,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560081,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fVFaEZEOo5pl3xs10pt-w",
				"gap": 1.2925734747025217,
				"focus": 0.5558270486775101
			},
			"endBinding": {
				"elementId": "zJ2KXVlIqqJbxu081xB0k",
				"gap": 1.1118861607143344,
				"focus": -0.441170258628564
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
					14.26711309523813,
					263.7909226190476
				],
				[
					154.2410714285714,
					296.62574404761904
				]
			]
		},
		{
			"type": "rectangle",
			"version": 471,
			"versionNonce": 1433061699,
			"isDeleted": false,
			"id": "ZcGgPhCn5Ky7K2ZO-eY1w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -569.3661833263577,
			"y": 429.4812825520836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.0589657738095,
			"height": 60,
			"seed": 1163291661,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "gtZXzfN9"
				},
				{
					"id": "7rDLqBvbIL_RS1KGltCnl",
					"type": "arrow"
				},
				{
					"id": "2irPvn3bPKetAe_w1e2jJ",
					"type": "arrow"
				},
				{
					"id": "TkFFy9ut7tqCr1i-5tGAA",
					"type": "arrow"
				}
			],
			"updated": 1710438891931,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 344,
			"versionNonce": 311956493,
			"isDeleted": false,
			"id": "gtZXzfN9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -553.5166854858397,
			"y": 446.9812825520836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 41.35997009277344,
			"height": 25,
			"seed": 891773549,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710438841358,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CDN",
			"rawText": "CDN",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZcGgPhCn5Ky7K2ZO-eY1w",
			"originalText": "CDN",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 73,
			"versionNonce": 1822863061,
			"isDeleted": false,
			"id": "7rDLqBvbIL_RS1KGltCnl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -543.0636349632625,
			"y": 339.0762416294647,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.07067298125855359,
			"height": 89.40504092261892,
			"seed": 888790755,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560082,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tnLHXlJ2_2yAx71IDUBpL",
				"gap": 2.2397460937504547,
				"focus": -0.01301235329763324
			},
			"endBinding": {
				"elementId": "ZcGgPhCn5Ky7K2ZO-eY1w",
				"gap": 1,
				"focus": -0.2823860338493842
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
					-0.07067298125855359,
					89.40504092261892
				]
			]
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 1282325909,
			"isDeleted": false,
			"id": "2irPvn3bPKetAe_w1e2jJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -516.6983075823102,
			"y": 424.00183686755986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.01116071428577925,
			"height": 85.27529761904759,
			"seed": 1117090883,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560082,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZcGgPhCn5Ky7K2ZO-eY1w",
				"gap": 5.479445684523739,
				"focus": 0.44161630925970197
			},
			"endBinding": {
				"elementId": "tnLHXlJ2_2yAx71IDUBpL",
				"gap": 1.8900437127980467,
				"focus": -0.33319302380427823
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
					0.01116071428577925,
					-85.27529761904759
				]
			]
		},
		{
			"type": "arrow",
			"version": 362,
			"versionNonce": 2135704309,
			"isDeleted": false,
			"id": "TkFFy9ut7tqCr1i-5tGAA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -492.2637837727864,
			"y": 465.73174758184564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1225.3319075163022,
			"height": 600.9952003724745,
			"seed": 320097165,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710451560082,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZcGgPhCn5Ky7K2ZO-eY1w",
				"gap": 4.043433779761756,
				"focus": 0.10603522628849094
			},
			"endBinding": {
				"elementId": "dh66_M5fIi39e8NlWZUFM",
				"gap": 7.179775717360371,
				"focus": -1.0505684852003139
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
					1159.2957428104833,
					80.05952380952374
				],
				[
					1225.3319075163022,
					-520.9356765629508
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
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 810.5971171061198,
		"scrollY": 756.9761477144734,
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