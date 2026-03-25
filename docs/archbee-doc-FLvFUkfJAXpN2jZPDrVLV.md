---
title: Unblock a specific endpoint
docTags: 
createdAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
---

{
  "id": "EeV4etv53utaTaTgLOnDv",
  "type": "api-oas-v2",
  "data": {
    "method": "GET",
    "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}",
    "servers": [
      {
        "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}",
        "description": "Production server"
      }
    ],
    "name": "Unblock a specific endpoint",
    "description": "Unblock a specific endpoint to allow IM to try and resend data to the endpoint",
    "contentType": "application/json",
    "request": {
      "pathParameters": [
        {
          "kind": "required",
          "name": "id",
          "type": "integer<int64>",
          "description": ""
        }
      ],
      "headerParameters": [],
      "queryParameters": [],
      "bodyDataParameters": [],
      "formDataParameters": [],
      "oAuthParameters": [
        {
          "id": "bearerAuth",
          "name": "bearerAuth",
          "kind": "optional",
          "type": "http",
          "scheme": "bearer"
        }
      ]
    },
    "responses": [
      {
        "statusCode": "204",
        "description": "No Content",
        "jsonExample": "",
        "isExpanded": true
      },
      {
        "statusCode": "401",
        "description": "Unauthorized",
        "jsonExample": "",
        "isExpanded": true,
        "schema": [
          {
            "kind": "optional",
            "type": "object",
            "description": "",
            "customType": "ErrorDetails",
            "schema": [
              {
                "name": "rootCause",
                "kind": "optional",
                "type": "string",
                "description": "",
                "example": ""
              },
              {
                "name": "errors",
                "kind": "optional",
                "type": "array",
                "description": "In case of an invalid request (422 status code), the request body contains an array of error objects",
                "modelRef": "#/components/schemas/ElementError",
                "customType": "ElementError[]",
                "schema": [
                  {
                    "name": "elementName",
                    "kind": "optional",
                    "type": "string",
                    "description": "The field in the object where the error occurred.\nFor general errors, the field might be omitted.",
                    "example": ""
                  },
                  {
                    "name": "errorCode",
                    "kind": "required",
                    "type": "string",
                    "description": "Underscored delimited string representing the error.",
                    "example": ""
                  },
                  {
                    "name": "parameters",
                    "kind": "optional",
                    "type": "map",
                    "description": "Additional information regarding the failure",
                    "example": "",
                    "customType": "map<string, object>",
                    "schema": []
                  }
                ]
              }
            ],
            "modelRef": "#/components/schemas/ErrorDetails",
            "isExpanded": true
          }
        ]
      },
      {
        "statusCode": "422",
        "description": "Request error",
        "jsonExample": "",
        "isExpanded": true,
        "schema": [
          {
            "kind": "optional",
            "type": "object",
            "description": "",
            "customType": "ValidationException",
            "schema": [
              {
                "name": "errorList",
                "kind": "optional",
                "type": "array",
                "description": "List of validation errors",
                "modelRef": "#/components/schemas/ElementError",
                "customType": "ElementError[]",
                "schema": [
                  {
                    "name": "elementName",
                    "kind": "optional",
                    "type": "string",
                    "description": "The field in the object where the error occurred.\nFor general errors, the field might be omitted.",
                    "example": ""
                  },
                  {
                    "name": "errorCode",
                    "kind": "required",
                    "type": "string",
                    "description": "Underscored delimited string representing the error.",
                    "example": ""
                  },
                  {
                    "name": "parameters",
                    "kind": "optional",
                    "type": "map",
                    "description": "Additional information regarding the failure",
                    "example": "",
                    "customType": "map<string, object>",
                    "schema": []
                  }
                ]
              }
            ],
            "modelRef": "#/components/schemas/ValidationException",
            "isExpanded": true
          }
        ]
      },
      {
        "statusCode": "500",
        "description": "Internal error",
        "jsonExample": "",
        "isExpanded": true
      }
    ],
    "hasXCodeSamples": false,
    "examples": {
      "languages": [
        {
          "id": "PFo3T67Yd_UMotMKxjPG4",
          "language": "curl",
          "label": "cURL",
          "code": "curl --location --globoff 'https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}' \\\n--header 'Accept: application/json' \\\n--header 'Content-Type: application/json'"
        },
        {
          "id": "bfVe4VvpSuQsdE4V0B02a",
          "language": "javascript",
          "label": "javascript",
          "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar requestOptions = {\n   method: 'GET',\n   headers: myHeaders,\n   redirect: 'follow'\n};\n\nfetch(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));"
        },
        {
          "id": "96ltKKnUN92QQVhhFrhq5",
          "language": "ruby",
          "label": "Ruby",
          "code": "require \"uri\"\nrequire \"json\"\nrequire \"net/http\"\n\nurl = URI(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}\")\n\nhttps = Net::HTTP.new(url.host, url.port)\nhttps.use_ssl = true\n\nrequest = Net::HTTP::Get.new(url)\nrequest[\"Accept\"] = \"application/json\"\nrequest[\"Content-Type\"] = \"application/json\"\n\nresponse = https.request(request)\nputs response.read_body\n"
        },
        {
          "id": "dAt8Ru1x8vce5QlQvy1CB",
          "language": "python",
          "label": "Python",
          "code": "import requests\nimport json\n\nurl = \"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/flows/management/reset-failures/connection-endpoint/{id}\"\n\npayload = {}\nheaders = {\n   'Accept': 'application/json',\n   'Content-Type': 'application/json'\n}\n\nresponse = requests.request(\"GET\", url, headers=headers, data=payload)\n\nprint(response.text)\n"
        }
      ],
      "selectedLanguageId": "PFo3T67Yd_UMotMKxjPG4"
    },
    "results": {
      "languages": [
        {
          "id": "9gkvkIbWCTYjOQkCjQ6At",
          "language": "204",
          "code": "// No Content \n"
        },
        {
          "id": "ntgREjWBpKN-QRgUcOvjH",
          "language": "401",
          "code": "// Unauthorized \n{\n  \"rootCause\": \"\",\n  \"errors\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "_-pe06kRdS0aIhq5l5T0c",
          "language": "422",
          "code": "// Request error \n{\n  \"errorList\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "av6FvppJ2dI7rt8y0VVlm",
          "language": "500",
          "code": "// Internal error \n"
        }
      ],
      "selectedLanguageId": "9gkvkIbWCTYjOQkCjQ6At"
    }
  },
  "children": [
    {
      "text": ""
    }
  ]
}