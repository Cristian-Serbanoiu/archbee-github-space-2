---
title: Get results for a specific flow execution id
docTags: 
createdAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
---

{
  "id": "v54IrdtJJjM_6vSuQuOhV",
  "type": "api-oas-v2",
  "data": {
    "method": "GET",
    "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking",
    "servers": [
      {
        "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking",
        "description": "Production server"
      }
    ],
    "name": "Get results for a specific flow execution id",
    "description": "This API is used to poll an inbound flow and check the results of a completed flow",
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
        "statusCode": "200",
        "description": "Success",
        "jsonExample": "",
        "isExpanded": true,
        "schema": [
          {
            "kind": "optional",
            "type": "object",
            "description": "Integration Inbound Tracking Response",
            "customType": "IntegrationInboundTrackingResponse",
            "schema": [
              {
                "name": "context",
                "kind": "optional",
                "type": "string",
                "description": "Describes body contents",
                "example": "INBOUND_RESULTS"
              },
              {
                "name": "inboundId",
                "kind": "optional",
                "type": "integer<int64>",
                "description": "Flow execution id",
                "example": 1
              },
              {
                "name": "status",
                "kind": "optional",
                "type": "string<IN_PROGRESS | SUCCEEDED | FAILED | ACCEPTED | BLOCKED | PARTIAL_FAIL>",
                "description": "Current Status of the Inbound Flow",
                "example": "IN_PROGRESS, SUCCEEDED, FAILED, ACCEPTED, BLOCKED, PARTIAL_FAIL"
              },
              {
                "name": "lvStatus",
                "kind": "optional",
                "type": "string<IN_PROGRESS | SUCCEEDED | FAILED | ACCEPTED | BLOCKED | PARTIAL_FAIL>",
                "description": "Internal Status of the Inbound Flow in Lousview",
                "example": "SUCCEEDED, FAILED, PARTIAL_FAIL"
              },
              {
                "name": "e2eFlowStatus",
                "kind": "optional",
                "type": "string<IN_PROGRESS | SUCCEEDED | FAILED | ACCEPTED | BLOCKED | PARTIAL_FAIL>",
                "description": "Dispatching Status of the Inbound Flow",
                "example": "IN_PROGRESS, SUCCEEDED, FAILED, ACCEPTED, BLOCKED"
              },
              {
                "name": "createdEntities",
                "kind": "optional",
                "type": "map",
                "description": "List of all created entities during the flow",
                "example": "",
                "customType": "map<string, integer>",
                "schema": []
              },
              {
                "name": "updatedEntities",
                "kind": "optional",
                "type": "map",
                "description": "List of all updated entities during the flow",
                "example": "",
                "customType": "map<string, integer>",
                "schema": []
              },
              {
                "name": "errors",
                "kind": "optional",
                "type": "map",
                "description": "List all errors during the flow",
                "example": "",
                "customType": "map<string, ObjectError[]>",
                "schema": []
              },
              {
                "name": "details",
                "kind": "optional",
                "type": "object",
                "description": "Integration Inbound Tracking Details",
                "modelRef": "#/components/schemas/IntegrationInboundTrackingDetails",
                "customType": "IntegrationInboundTrackingDetails",
                "schema": [
                  {
                    "name": "createdEntities",
                    "kind": "optional",
                    "type": "array",
                    "description": "List of all created entities during the flow",
                    "modelRef": "#/components/schemas/IntegrationInboundTrackingEntity",
                    "customType": "IntegrationInboundTrackingEntity[]",
                    "schema": [
                      {
                        "name": "action",
                        "kind": "optional",
                        "type": "string<ADD | UPDATE>",
                        "description": "Action",
                        "example": "ADD, UPDATE"
                      },
                      {
                        "name": "referenceId",
                        "kind": "optional",
                        "type": "string",
                        "description": "The client reference ID",
                        "example": ""
                      },
                      {
                        "name": "lvId",
                        "kind": "optional",
                        "type": "integer<int64>",
                        "description": "Locusview identifier",
                        "example": 0
                      },
                      {
                        "name": "entityType",
                        "kind": "optional",
                        "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                        "description": "Entity type",
                        "example": "WORK_ORDER, WORK_UNIT, ASSET, FORM"
                      },
                      {
                        "name": "errorList",
                        "kind": "optional",
                        "type": "array",
                        "description": "List of errors",
                        "modelRef": "#/components/schemas/ObjectError",
                        "customType": "ObjectError[]",
                        "schema": [
                          {
                            "name": "errorCode",
                            "kind": "optional",
                            "type": "string",
                            "description": "Error code",
                            "example": "INVALID_INPUT"
                          },
                          {
                            "name": "field",
                            "kind": "optional",
                            "type": "string",
                            "description": "Field name",
                            "example": "inputMethod"
                          },
                          {
                            "name": "description",
                            "kind": "optional",
                            "type": "string",
                            "description": "More details on why the field failed",
                            "example": ""
                          }
                        ]
                      }
                    ]
                  },
                  {
                    "name": "updatedEntities",
                    "kind": "optional",
                    "type": "array",
                    "description": "List of all updated entities during the flow",
                    "modelRef": "#/components/schemas/IntegrationInboundTrackingEntity",
                    "customType": "IntegrationInboundTrackingEntity[]",
                    "schema": [
                      {
                        "name": "action",
                        "kind": "optional",
                        "type": "string<ADD | UPDATE>",
                        "description": "Action",
                        "example": "ADD, UPDATE"
                      },
                      {
                        "name": "referenceId",
                        "kind": "optional",
                        "type": "string",
                        "description": "The client reference ID",
                        "example": ""
                      },
                      {
                        "name": "lvId",
                        "kind": "optional",
                        "type": "integer<int64>",
                        "description": "Locusview identifier",
                        "example": 0
                      },
                      {
                        "name": "entityType",
                        "kind": "optional",
                        "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                        "description": "Entity type",
                        "example": "WORK_ORDER, WORK_UNIT, ASSET, FORM"
                      },
                      {
                        "name": "errorList",
                        "kind": "optional",
                        "type": "array",
                        "description": "List of errors",
                        "modelRef": "#/components/schemas/ObjectError",
                        "customType": "ObjectError[]",
                        "schema": [
                          {
                            "name": "errorCode",
                            "kind": "optional",
                            "type": "string",
                            "description": "Error code",
                            "example": "INVALID_INPUT"
                          },
                          {
                            "name": "field",
                            "kind": "optional",
                            "type": "string",
                            "description": "Field name",
                            "example": "inputMethod"
                          },
                          {
                            "name": "description",
                            "kind": "optional",
                            "type": "string",
                            "description": "More details on why the field failed",
                            "example": ""
                          }
                        ]
                      }
                    ]
                  },
                  {
                    "name": "errors",
                    "kind": "optional",
                    "type": "array",
                    "description": "List of all entities that got errors during the flow",
                    "modelRef": "#/components/schemas/IntegrationInboundTrackingEntity",
                    "customType": "IntegrationInboundTrackingEntity[]",
                    "schema": [
                      {
                        "name": "action",
                        "kind": "optional",
                        "type": "string<ADD | UPDATE>",
                        "description": "Action",
                        "example": "ADD, UPDATE"
                      },
                      {
                        "name": "referenceId",
                        "kind": "optional",
                        "type": "string",
                        "description": "The client reference ID",
                        "example": ""
                      },
                      {
                        "name": "lvId",
                        "kind": "optional",
                        "type": "integer<int64>",
                        "description": "Locusview identifier",
                        "example": 0
                      },
                      {
                        "name": "entityType",
                        "kind": "optional",
                        "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                        "description": "Entity type",
                        "example": "WORK_ORDER, WORK_UNIT, ASSET, FORM"
                      },
                      {
                        "name": "errorList",
                        "kind": "optional",
                        "type": "array",
                        "description": "List of errors",
                        "modelRef": "#/components/schemas/ObjectError",
                        "customType": "ObjectError[]",
                        "schema": [
                          {
                            "name": "errorCode",
                            "kind": "optional",
                            "type": "string",
                            "description": "Error code",
                            "example": "INVALID_INPUT"
                          },
                          {
                            "name": "field",
                            "kind": "optional",
                            "type": "string",
                            "description": "Field name",
                            "example": "inputMethod"
                          },
                          {
                            "name": "description",
                            "kind": "optional",
                            "type": "string",
                            "description": "More details on why the field failed",
                            "example": ""
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            "modelRef": "#/components/schemas/IntegrationInboundTrackingResponse",
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
          "id": "a88y2JrMedY8QgOFeNLQk",
          "language": "curl",
          "label": "cURL",
          "code": "curl --location --globoff 'https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking' \\\n--header 'Accept: application/json' \\\n--header 'Content-Type: application/json'"
        },
        {
          "id": "i65-mFaT2Xxkh1ytQy4v8",
          "language": "javascript",
          "label": "javascript",
          "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar requestOptions = {\n   method: 'GET',\n   headers: myHeaders,\n   redirect: 'follow'\n};\n\nfetch(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));"
        },
        {
          "id": "y0pAK3g5UQbPV6ZAlg-I8",
          "language": "ruby",
          "label": "Ruby",
          "code": "require \"uri\"\nrequire \"json\"\nrequire \"net/http\"\n\nurl = URI(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking\")\n\nhttps = Net::HTTP.new(url.host, url.port)\nhttps.use_ssl = true\n\nrequest = Net::HTTP::Get.new(url)\nrequest[\"Accept\"] = \"application/json\"\nrequest[\"Content-Type\"] = \"application/json\"\n\nresponse = https.request(request)\nputs response.read_body\n"
        },
        {
          "id": "NgPJtICn9kBw_t7KASRfz",
          "language": "python",
          "label": "Python",
          "code": "import requests\nimport json\n\nurl = \"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/{id}/tracking\"\n\npayload = {}\nheaders = {\n   'Accept': 'application/json',\n   'Content-Type': 'application/json'\n}\n\nresponse = requests.request(\"GET\", url, headers=headers, data=payload)\n\nprint(response.text)\n"
        }
      ],
      "selectedLanguageId": "a88y2JrMedY8QgOFeNLQk"
    },
    "results": {
      "languages": [
        {
          "id": "Rsn8HjiHdSDoAgOwdSoFJ",
          "language": "200",
          "code": "// Success \n{\n  \"context\": \"INBOUND_RESULTS\",\n  \"inboundId\": 1,\n  \"status\": \"IN_PROGRESS, SUCCEEDED, FAILED, ACCEPTED, BLOCKED, PARTIAL_FAIL\",\n  \"lvStatus\": \"SUCCEEDED, FAILED, PARTIAL_FAIL\",\n  \"e2eFlowStatus\": \"IN_PROGRESS, SUCCEEDED, FAILED, ACCEPTED, BLOCKED\",\n  \"createdEntities\": \"\",\n  \"updatedEntities\": \"\",\n  \"errors\": \"\",\n  \"details\": {\n    \"createdEntities\": [\n      {\n        \"action\": \"ADD, UPDATE\",\n        \"referenceId\": \"\",\n        \"lvId\": \"\",\n        \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n        \"errorList\": [\n          {\n            \"errorCode\": \"INVALID_INPUT\",\n            \"field\": \"inputMethod\",\n            \"description\": \"\"\n          }\n        ]\n      }\n    ],\n    \"updatedEntities\": [\n      {\n        \"action\": \"ADD, UPDATE\",\n        \"referenceId\": \"\",\n        \"lvId\": \"\",\n        \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n        \"errorList\": [\n          {\n            \"errorCode\": \"INVALID_INPUT\",\n            \"field\": \"inputMethod\",\n            \"description\": \"\"\n          }\n        ]\n      }\n    ],\n    \"errors\": [\n      {\n        \"action\": \"ADD, UPDATE\",\n        \"referenceId\": \"\",\n        \"lvId\": \"\",\n        \"entityType\": \"WORK_ORDER, WORK_UNIT, ASSET, FORM\",\n        \"errorList\": [\n          {\n            \"errorCode\": \"INVALID_INPUT\",\n            \"field\": \"inputMethod\",\n            \"description\": \"\"\n          }\n        ]\n      }\n    ]\n  }\n}"
        },
        {
          "id": "Ht7v5W9gUwY3hJBnj_8ko",
          "language": "401",
          "code": "// Unauthorized \n{\n  \"rootCause\": \"\",\n  \"errors\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "hib3fUBr1uJB0xjcd2Q_a",
          "language": "422",
          "code": "// Request error \n{\n  \"errorList\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "CDtem0gkJE5KFdnr7AUQN",
          "language": "500",
          "code": "// Internal error \n"
        }
      ],
      "selectedLanguageId": "Rsn8HjiHdSDoAgOwdSoFJ"
    }
  },
  "children": [
    {
      "text": ""
    }
  ]
}