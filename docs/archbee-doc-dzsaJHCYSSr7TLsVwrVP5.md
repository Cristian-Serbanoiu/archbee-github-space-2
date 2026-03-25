---
title: Run on demand Integration Flow
docTags: 
createdAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
---

{
  "id": "dWwNXQgXNZq-NBvOShx66",
  "type": "api-oas-v2",
  "data": {
    "method": "POST",
    "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}",
    "servers": [
      {
        "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}",
        "description": "Production server"
      }
    ],
    "name": "Run on demand Integration Flow",
    "description": "Triggers an on demand Integration Flow by flow Id",
    "contentType": "application/json",
    "request": {
      "pathParameters": [
        {
          "kind": "required",
          "name": "id",
          "type": "integer<int64>",
          "description": "Integration Flow Id"
        }
      ],
      "headerParameters": [],
      "queryParameters": [],
      "bodyDataParameters": [
        {
          "kind": "required",
          "name": "body",
          "type": "object",
          "description": "Request to run an integration flow",
          "customType": "IntegrationFlowRequest",
          "schema": [
            {
              "name": "integrationFlowId",
              "kind": "required",
              "type": "integer<int64>",
              "description": "The id of the Integration Flow to run",
              "example": 1
            },
            {
              "name": "entities",
              "kind": "required",
              "type": "array",
              "description": "Entities list to export. \n For Esri / HTTPS connection: single entity only.\nFor FTP / SharePoint connections: multiple work order entities are allowed",
              "modelRef": "#/components/schemas/IntegrationFlowEntity",
              "customType": "IntegrationFlowEntity[]",
              "schema": [
                {
                  "name": "entityType",
                  "kind": "required",
                  "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                  "description": "The entity type to export",
                  "example": "WORK_ORDER, WORK_UNIT, ASSET, FORM"
                },
                {
                  "name": "entityId",
                  "kind": "required",
                  "type": "integer<int64>",
                  "description": "The entity ID to export",
                  "example": 1
                },
                {
                  "name": "workOrderId",
                  "kind": "optional",
                  "type": "integer<int64>",
                  "description": "Work Order Id",
                  "example": 1
                }
              ]
            },
            {
              "name": "origin",
              "kind": "optional",
              "type": "string",
              "description": "The source of the request",
              "example": "Scheduler, RuleEngine"
            },
            {
              "name": "triggerId",
              "kind": "optional",
              "type": "integer<int64>",
              "description": "The ID of the entity that triggered this API, e.g., Rule, Schedule",
              "example": 2
            },
            {
              "name": "ignoreDelta",
              "kind": "optional",
              "type": "boolean",
              "description": "If true, ignores the delta flag from the flow configuration and exports the entire entity and its children",
              "example": true
            }
          ],
          "modelRef": "#/components/schemas/IntegrationFlowRequest",
          "isExpanded": true
        }
      ],
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
        "statusCode": "200",
        "description": "Success",
        "jsonExample": "",
        "isExpanded": true,
        "schema": [
          {
            "kind": "optional",
            "type": "object",
            "description": "Integration result for successful response",
            "customType": "IntegrationResult",
            "schema": [
              {
                "name": "flowExecutionId",
                "kind": "optional",
                "type": "integer<int64>",
                "description": "Flow execution Id",
                "example": 1
              },
              {
                "name": "flowId",
                "kind": "optional",
                "type": "integer<int64>",
                "description": "Integration Flow Id",
                "example": 1
              }
            ],
            "modelRef": "#/components/schemas/IntegrationResult",
            "isExpanded": true
          }
        ]
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
          "id": "6NmTJt0KfChVkkpfclvnp",
          "language": "curl",
          "label": "cURL",
          "code": "curl --location --globoff 'https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}' \\\n--header 'Accept: application/json' \\\n--header 'Content-Type: application/json' \\\n--data '{\n  \"integrationFlowId\": 1,\n  \"entities\": [\n    {\n      \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n      \"entityId\": 1\n    }\n  ]\n}'"
        },
        {
          "id": "BZv6mj3qcX__dABhmqMeB",
          "language": "javascript",
          "label": "javascript",
          "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar raw = JSON.stringify({\n   \"integrationFlowId\": 1,\n   \"entities\": [\n      {\n         \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n         \"entityId\": 1\n      }\n   ]\n});\n\nvar requestOptions = {\n   method: 'POST',\n   headers: myHeaders,\n   body: raw,\n   redirect: 'follow'\n};\n\nfetch(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));"
        },
        {
          "id": "DUTNuJ4uvSEQDOgTsFtW_",
          "language": "ruby",
          "label": "Ruby",
          "code": "require \"uri\"\nrequire \"json\"\nrequire \"net/http\"\n\nurl = URI(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}\")\n\nhttps = Net::HTTP.new(url.host, url.port)\nhttps.use_ssl = true\n\nrequest = Net::HTTP::Post.new(url)\nrequest[\"Accept\"] = \"application/json\"\nrequest[\"Content-Type\"] = \"application/json\"\nrequest.body = JSON.dump({\n   \"integrationFlowId\": 1,\n   \"entities\": [\n      {\n         \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n         \"entityId\": 1\n      }\n   ]\n})\n\nresponse = https.request(request)\nputs response.read_body\n"
        },
        {
          "id": "zuP16Nujd6pmNBXFANS-T",
          "language": "python",
          "label": "Python",
          "code": "import requests\nimport json\n\nurl = \"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integrations/flows/on-demand/{id}\"\n\npayload = json.dumps({\n   \"integrationFlowId\": 1,\n   \"entities\": [\n      {\n         \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n         \"entityId\": 1\n      }\n   ]\n})\nheaders = {\n   'Accept': 'application/json',\n   'Content-Type': 'application/json'\n}\n\nresponse = requests.request(\"POST\", url, headers=headers, data=payload)\n\nprint(response.text)\n"
        }
      ],
      "selectedLanguageId": "6NmTJt0KfChVkkpfclvnp"
    },
    "results": {
      "languages": [
        {
          "id": "GpYI4FiOeUjk7BOM_hhDx",
          "language": "200",
          "code": "// Success \n{\n  \"flowExecutionId\": 1,\n  \"flowId\": 1\n}"
        },
        {
          "id": "AtARQBUUXiRn04s4--L9F",
          "language": "401",
          "code": "// Unauthorized \n{\n  \"rootCause\": \"\",\n  \"errors\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "npBNEJq7vjgt8dWhKHiH6",
          "language": "422",
          "code": "// Request error \n{\n  \"errorList\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "nlAErMce7TNDB0HLHYJ4F",
          "language": "500",
          "code": "// Internal error \n"
        }
      ],
      "selectedLanguageId": "GpYI4FiOeUjk7BOM_hhDx"
    }
  },
  "children": [
    {
      "text": ""
    }
  ]
}