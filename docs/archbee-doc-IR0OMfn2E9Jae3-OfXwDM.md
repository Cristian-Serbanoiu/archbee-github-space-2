---
title: PEANUT MIREL
slug: IR0O-o
docTags: 
createdAt: Wed Mar 25 2026 14:43:19 GMT+0000 (Coordinated Universal Time)
updatedAt: Thu Mar 26 2026 07:33:10 GMT+0000 (Coordinated Universal Time)
---

:::ContentSnippet{docRefId="IOQVkUNUKZP4S5CSlNiFi"}

:::

:::ApiMethodV2
```json
{
  "name": "Get Cakes",
  "method": "GET",
  "url": "https://api.cakes.com",
  "description": "Get a cake by its ID",
  "tab": "examples",
  "examples": {
    "languages": [
      {
        "id": "quio4EItFech4Ljx2eWjF",
        "language": "javascript",
        "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar raw = JSON.stringify({\n   \"id\": \"String\"\n});\n\nvar requestOptions = {\n   method: 'GET',\n   headers: myHeaders,\n   body: raw,\n   redirect: 'follow'\n};\n\nfetch(\"https://api.cakes.com\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));",
        "customLabel": ""
      }
    ],
    "selectedLanguageId": "quio4EItFech4Ljx2eWjF"
  },
  "results": {
    "languages": [
      {
        "id": "v2S3vBvqhxD1Anv28NIcd",
        "language": "200",
        "code": "{\n  \"name\": \"Cake's name\",\n}",
        "customLabel": ""
      },
      {
        "id": "RdjpjJzgph2GFDzqsCWru",
        "language": "404",
        "code": "{\n  \"message\": \"Ain't no cake like that.\"\n}",
        "customLabel": ""
      }
    ],
    "selectedLanguageId": "v2S3vBvqhxD1Anv28NIcd"
  },
  "request": {
    "pathParameters": [],
    "queryParameters": [],
    "headerParameters": [],
    "formDataParameters": [],
    "bodyDataParameters": [
      {
        "name": "id",
        "kind": "required",
        "type": "string",
        "description": "ID of the cake to get"
      }
    ]
  },
  "currentNewParameter": {
    "label": "Body Parameter",
    "value": "bodyDataParameters"
  },
  "hasTryItOut": false
}
```
:::

:::ApiMethodV2
```json
{
  "name": "Get Cakes",
  "method": "GET",
  "url": "https://api.cakes.com",
  "description": "Get a cake by its ID",
  "tab": "examples",
  "examples": {
    "languages": [
      {
        "id": "xoIpdSswpDP8jSsX-Twsx",
        "language": "javascript",
        "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar raw = JSON.stringify({\n   \"id\": \"String\"\n});\n\nvar requestOptions = {\n   method: 'GET',\n   headers: myHeaders,\n   body: raw,\n   redirect: 'follow'\n};\n\nfetch(\"https://api.cakes.com\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));",
        "customLabel": ""
      }
    ],
    "selectedLanguageId": "xoIpdSswpDP8jSsX-Twsx"
  },
  "results": {
    "languages": [
      {
        "id": "_VrPVgEC1nFusoNgL7mBS",
        "language": "200",
        "code": "{\n  \"name\": \"Cake's name\",\n}",
        "customLabel": ""
      },
      {
        "id": "Smt-73FPH6EZj6lKpBplp",
        "language": "404",
        "code": "{\n  \"message\": \"Ain't no cake like that.\"\n}",
        "customLabel": ""
      }
    ],
    "selectedLanguageId": "_VrPVgEC1nFusoNgL7mBS"
  },
  "request": {
    "pathParameters": [],
    "queryParameters": [],
    "headerParameters": [],
    "formDataParameters": [],
    "bodyDataParameters": [
      {
        "name": "id",
        "kind": "required",
        "type": "string",
        "description": "ID of the cake to get"
      }
    ]
  },
  "currentNewParameter": {
    "label": "Body Parameter",
    "value": "bodyDataParameters"
  },
  "hasTryItOut": false
}
```
:::

:::ContentSnippet{docRefId="WqDaDfi7X92gWSkdUjeUG"}

:::

::::CodeDrawer{title="Code Section Title" codeEditorData="[object Object]" responsesEditorData="[object Object]" isResponseExpanded="true"}
:::CodeblockTabsExamples
```javascript
CODE CODE
```
:::

:::CodeblockTabsResponses
```javascript
CODE CODE
```
:::
::::

::::CodeDrawer{title="Code Section Title" codeEditorData="[object Object]" responsesEditorData="[object Object]" isResponseExpanded="true"}
:::CodeblockTabsExamples
```javascript
CODE CODE
```
:::

:::CodeblockTabsResponses
```javascript
CODE CODE
```
:::
::::

::::CodeDrawer{title="Code Section Title" codeEditorData="[object Object]" responsesEditorData="[object Object]" isResponseExpanded="true"}
:::CodeblockTabsExamples
```javascript
CODE CODE
```
:::

:::CodeblockTabsResponses
```javascript
CODE CODE
```
:::
::::

