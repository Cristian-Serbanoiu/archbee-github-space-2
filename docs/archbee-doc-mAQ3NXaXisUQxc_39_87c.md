---
title: Run Inbound Integration flow
docTags: 
createdAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
---

{
  "id": "gX66DIXDoDuz9YoNX2xe0",
  "type": "api-oas-v2",
  "data": {
    "method": "POST",
    "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound",
    "servers": [
      {
        "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound",
        "description": "Production server"
      }
    ],
    "name": "Run Inbound Integration flow",
    "description": "<p>Creates and updates work orders, work units, assets and forms objects within the Locusview system</p>",
    "contentType": "application/json",
    "request": {
      "pathParameters": [],
      "headerParameters": [],
      "queryParameters": [],
      "bodyDataParameters": [
        {
          "kind": "required",
          "name": "body",
          "type": "object",
          "description": "Request to run an Inbound integration flow",
          "customType": "IntegrationInboundFlowRequest",
          "schema": [
            {
              "name": "endpointAlias",
              "kind": "optional",
              "type": "string",
              "description": "Alias for the endpoint. Optional Field. Results are returned if the endpoint was sent in the request and if SkipInboundResponseDispatch is set to false",
              "example": "inboundFolder"
            },
            {
              "name": "integrationName",
              "kind": "optional",
              "type": "string",
              "description": "Integration type name",
              "example": "myIntegration"
            },
            {
              "name": "integrationFlowName",
              "kind": "optional",
              "type": "string",
              "description": "Integration flow name",
              "example": "flow1"
            },
            {
              "name": "objects",
              "kind": "optional",
              "type": "array",
              "description": "List of all new/updated entities",
              "modelRef": "#/components/schemas/AbstractInboundObject",
              "customType": "AbstractInboundObject[]",
              "schema": [
                {
                  "name": "action",
                  "kind": "optional",
                  "type": "string<ADD | UPDATE>",
                  "description": "Desired action to take on the entity",
                  "example": "ADD, UPDATE"
                },
                {
                  "name": "referenceId",
                  "kind": "optional",
                  "type": "string",
                  "description": "Entity ID of the 3rd party system",
                  "example": ""
                },
                {
                  "name": "lvId",
                  "kind": "optional",
                  "type": "integer<int64>",
                  "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                  "example": 0
                },
                {
                  "name": "typeName",
                  "kind": "optional",
                  "type": "string",
                  "description": "Locusview Entity Type Name",
                  "example": "Pipe"
                },
                {
                  "name": "entityType",
                  "kind": "optional",
                  "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                  "description": "Locusview Entity Type",
                  "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                }
              ]
            },
            {
              "name": "endpointAlias",
              "kind": "optional",
              "type": "string",
              "description": "Alias for the endpoint. Optional Field. Results are returned if the endpoint was sent in the request and if SkipInboundResponseDispatch is set to false",
              "example": "inboundFolder"
            },
            {
              "name": "integrationName",
              "kind": "optional",
              "type": "string",
              "description": "Integration type name",
              "example": "myIntegration"
            },
            {
              "name": "integrationFlowName",
              "kind": "optional",
              "type": "string",
              "description": "Integration flow name",
              "example": "flow1"
            },
            {
              "name": "objects",
              "kind": "optional",
              "type": "object",
              "description": "List of all new/updated entities",
              "modelRef": "#/components/schemas/InboundObject",
              "customType": "InboundObject[]",
              "schema": [],
              "complexType": "allOf",
              "complexItems": [
                {
                  "name": "AbstractInboundObject",
                  "description": "",
                  "modelRef": "#/components/schemas/AbstractInboundObject",
                  "schema": [
                    {
                      "name": "action",
                      "kind": "optional",
                      "type": "string<ADD | UPDATE>",
                      "description": "Desired action to take on the entity",
                      "example": "ADD, UPDATE"
                    },
                    {
                      "name": "referenceId",
                      "kind": "optional",
                      "type": "string",
                      "description": "Entity ID of the 3rd party system",
                      "example": ""
                    },
                    {
                      "name": "lvId",
                      "kind": "optional",
                      "type": "integer<int64>",
                      "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                      "example": 0
                    },
                    {
                      "name": "typeName",
                      "kind": "optional",
                      "type": "string",
                      "description": "Locusview Entity Type Name",
                      "example": "Pipe"
                    },
                    {
                      "name": "entityType",
                      "kind": "optional",
                      "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                      "description": "Locusview Entity Type",
                      "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                    }
                  ]
                },
                {
                  "name": "object",
                  "description": "",
                  "schema": [
                    {
                      "name": "action",
                      "kind": "optional",
                      "type": "string<ADD | UPDATE>",
                      "description": "Desired action to take on the entity",
                      "example": "ADD, UPDATE"
                    },
                    {
                      "name": "referenceId",
                      "kind": "optional",
                      "type": "string",
                      "description": "Entity ID of the 3rd party system",
                      "example": ""
                    },
                    {
                      "name": "lvId",
                      "kind": "optional",
                      "type": "integer<int64>",
                      "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                      "example": 0
                    },
                    {
                      "name": "typeName",
                      "kind": "optional",
                      "type": "string",
                      "description": "Locusview Entity Type Name",
                      "example": "Pipe"
                    },
                    {
                      "name": "entityType",
                      "kind": "optional",
                      "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                      "description": "Locusview Entity Type",
                      "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                    },
                    {
                      "name": "parent",
                      "kind": "optional",
                      "type": "object",
                      "description": "Inbound Parent Object",
                      "modelRef": "#/components/schemas/ObjectParent",
                      "customType": "ObjectParent",
                      "schema": [
                        {
                          "name": "referenceId",
                          "kind": "optional",
                          "type": "string",
                          "description": "Reference Id",
                          "example": ""
                        },
                        {
                          "name": "entityType",
                          "kind": "optional",
                          "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                          "description": "Entity Type",
                          "example": ""
                        }
                      ]
                    },
                    {
                      "name": "fields",
                      "kind": "optional",
                      "type": "map",
                      "description": "",
                      "example": "",
                      "customType": "map<string, object>",
                      "schema": []
                    },
                    {
                      "name": "geometries",
                      "kind": "optional",
                      "type": "array",
                      "description": "",
                      "modelRef": "#/components/schemas/InboundGeometry",
                      "customType": "InboundGeometry[]",
                      "schema": [
                        {
                          "name": "latitude",
                          "kind": "optional",
                          "type": "number",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "longitude",
                          "kind": "optional",
                          "type": "number",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "altitude",
                          "kind": "optional",
                          "type": "number",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "datum",
                          "kind": "optional",
                          "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "recordType",
                          "kind": "optional",
                          "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                          "description": "",
                          "example": ""
                        }
                      ]
                    },
                    {
                      "name": "status",
                      "kind": "optional",
                      "type": "string<IN_PROGRESS | SUBMITTED | IN_REVIEW | APPROVED | REJECTED | EXPORTED | NEW | DRAFT>",
                      "description": "",
                      "example": ""
                    },
                    {
                      "name": "assignment",
                      "kind": "optional",
                      "type": "object",
                      "description": "",
                      "modelRef": "#/components/schemas/Assignment",
                      "customType": "Assignment",
                      "schema": [
                        {
                          "name": "userIds",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "integer",
                          "customType": "integer[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "usernames",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "string",
                          "customType": "string[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "groupnames",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "string",
                          "customType": "string[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "groupIds",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "integer",
                          "customType": "integer[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "users",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/FieldUser",
                          "customType": "FieldUser[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "username",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "firstName",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "lastName",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "guid",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "email",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "status",
                              "kind": "optional",
                              "type": "string<ACTIVE | INACTIVE | LOCKED>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "groupIds",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            }
                          ]
                        },
                        {
                          "name": "groups",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/GroupPreview",
                          "customType": "GroupPreview[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "name",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "description",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "usersCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "groupsCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "policiesCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            }
                          ]
                        }
                      ]
                    },
                    {
                      "name": "permission",
                      "kind": "optional",
                      "type": "object",
                      "description": "",
                      "modelRef": "#/components/schemas/Permission",
                      "customType": "Permission",
                      "schema": [
                        {
                          "name": "userIds",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "integer",
                          "customType": "integer[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "groupIds",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "integer",
                          "customType": "integer[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "usernames",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "string",
                          "customType": "string[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "groupnames",
                          "kind": "optional",
                          "type": "array",
                          "writeOnly": true,
                          "description": "",
                          "example": "",
                          "itemType": "string",
                          "customType": "string[]",
                          "itemExample": "",
                          "itemDefault": ""
                        },
                        {
                          "name": "users",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/FieldUser",
                          "customType": "FieldUser[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "username",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "firstName",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "lastName",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "guid",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "email",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "status",
                              "kind": "optional",
                              "type": "string<ACTIVE | INACTIVE | LOCKED>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "groupIds",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            }
                          ]
                        },
                        {
                          "name": "groups",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/GroupPreview",
                          "customType": "GroupPreview[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "name",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "description",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "usersCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "groupsCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "policiesCount",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            }
                          ]
                        },
                        {
                          "name": "allowAll",
                          "kind": "optional",
                          "type": "boolean",
                          "description": "",
                          "example": ""
                        }
                      ]
                    },
                    {
                      "name": "materials",
                      "kind": "optional",
                      "type": "array",
                      "description": "",
                      "modelRef": "#/components/schemas/Material",
                      "customType": "Material[]",
                      "schema": [
                        {
                          "name": "id",
                          "kind": "optional",
                          "type": "integer<int64>",
                          "description": "",
                          "example": 0
                        },
                        {
                          "name": "partNumber",
                          "kind": "optional",
                          "type": "string",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "projectId",
                          "kind": "optional",
                          "type": "integer<int64>",
                          "description": "",
                          "example": 0
                        },
                        {
                          "name": "status",
                          "kind": "optional",
                          "type": "string<APPROVED | REJECTED | PENDING>",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "numberOfAssets",
                          "kind": "optional",
                          "type": "integer<int32>",
                          "description": "",
                          "example": 0
                        },
                        {
                          "name": "catalogItem",
                          "kind": "optional",
                          "type": "object",
                          "description": "",
                          "modelRef": "#/components/schemas/Catalog",
                          "customType": "Catalog",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "createDate",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "lastUpdated",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "active",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "typeId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "customFields",
                              "kind": "optional",
                              "type": "map",
                              "description": "",
                              "example": "",
                              "customType": "map<string, object>",
                              "schema": []
                            },
                            {
                              "name": "astmBarcode",
                              "kind": "optional",
                              "type": "string",
                              "writeOnly": true,
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "catalogItems",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/Catalog",
                          "customType": "Catalog[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "createDate",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "lastUpdated",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "active",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "typeId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "customFields",
                              "kind": "optional",
                              "type": "map",
                              "description": "",
                              "example": "",
                              "customType": "map<string, object>",
                              "schema": []
                            },
                            {
                              "name": "astmBarcode",
                              "kind": "optional",
                              "type": "string",
                              "writeOnly": true,
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "quantity",
                          "kind": "optional",
                          "type": "number",
                          "description": "",
                          "example": ""
                        }
                      ]
                    },
                    {
                      "name": "design",
                      "kind": "optional",
                      "type": "object",
                      "description": "Inbound Design",
                      "modelRef": "#/components/schemas/InboundDesign",
                      "customType": "InboundDesign",
                      "schema": [
                        {
                          "name": "workLocations",
                          "kind": "optional",
                          "type": "array",
                          "description": "List of Work Locations",
                          "modelRef": "#/components/schemas/InboundWorkLocation",
                          "customType": "InboundWorkLocation[]",
                          "schema": [
                            {
                              "name": "name",
                              "kind": "optional",
                              "type": "string",
                              "description": "Work Location Name",
                              "example": "WL 1"
                            },
                            {
                              "name": "wuTypeName",
                              "kind": "optional",
                              "type": "string",
                              "description": "The relevant Work Unit Type name",
                              "example": "Paving"
                            },
                            {
                              "name": "geometries",
                              "kind": "optional",
                              "type": "array",
                              "description": "Simplified geometry list",
                              "modelRef": "#/components/schemas/InboundGeometry",
                              "customType": "InboundGeometry[]",
                              "schema": [
                                {
                                  "name": "latitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "longitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "altitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "datum",
                                  "kind": "optional",
                                  "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "recordType",
                                  "kind": "optional",
                                  "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                  "description": "",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "order",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "Order",
                              "example": 0
                            },
                            {
                              "name": "plannedCompatibleUnits",
                              "kind": "optional",
                              "type": "array",
                              "description": "List of Planned Compatible Units. Planned CUS  are imported compatible units within the work design. Planned CUS  are displayed in the mobile app based on association with a specific Work Design associated with a particular work order. ",
                              "modelRef": "#/components/schemas/PlannedCompatibleUnit",
                              "customType": "PlannedCompatibleUnit[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "projectId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "quantity",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "compatibleUnitId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "geometries",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "modelRef": "#/components/schemas/Geometry",
                                  "customType": "Geometry[]",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "createDate",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastUpdated",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "createUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "updateUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "projectId",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "uuid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "accuracyInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "satelliteCount",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "recordType",
                                      "kind": "optional",
                                      "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "fixQuality",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "datum",
                                      "kind": "optional",
                                      "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "correctionAge",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "dsId",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "depthInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lrfMetadata",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "modelRef": "#/components/schemas/LrfMetadata",
                                      "customType": "LrfMetadata[]",
                                      "schema": [
                                        {
                                          "name": "latitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "altitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "accuracyInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "horizontalDistanceInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "verticalDistanceInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "azimuthDegrees",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lrfEyeHeightInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "latitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "poleInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "datum",
                                          "kind": "optional",
                                          "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "poleInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitudeGeoid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "ellipsoidHeight",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "deleted",
                                      "kind": "optional",
                                      "type": "boolean",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "deviceInfo",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/DeviceInfo",
                                      "customType": "DeviceInfo",
                                      "schema": [
                                        {
                                          "name": "deviceType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "serialNumber",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firmwareVersion",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "connectionName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "solutionType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalLatitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalLongitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalAltitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groundPositionType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "imuState",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    }
                                  ]
                                },
                                {
                                  "name": "workLocationId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "integrationData",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/JsonNode",
                                  "customType": "JsonNode",
                                  "schema": []
                                },
                                {
                                  "name": "designAttributes",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "externalCuId",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "workFunction",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "symbology",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/Symbology",
                                  "customType": "Symbology",
                                  "schema": [
                                    {
                                      "name": "symbol",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lineType",
                                      "kind": "optional",
                                      "type": "string<SOLID | DOTTED | DASHED | LIGHT_SOLID | LIGHT_DOTTED | LIGHT_NARROW_DASHED | NARROW_SOLID | DOUBLE_DASHED | THIN_DOUBLE_DASHED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "coloring",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/Coloring",
                                      "customType": "Coloring",
                                      "schema": [
                                        {
                                          "name": "symbolColor",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "linePinColor",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    }
                                  ]
                                },
                                {
                                  "name": "createUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "updateUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "createDate",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastUpdated",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "parent",
                              "kind": "optional",
                              "type": "object",
                              "description": "Inbound Parent Object",
                              "modelRef": "#/components/schemas/ObjectParent",
                              "customType": "ObjectParent",
                              "schema": [
                                {
                                  "name": "referenceId",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "Reference Id",
                                  "example": ""
                                },
                                {
                                  "name": "entityType",
                                  "kind": "optional",
                                  "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                                  "description": "Entity Type",
                                  "example": ""
                                }
                              ]
                            }
                          ]
                        },
                        {
                          "name": "plannedCompatibleUnits",
                          "kind": "optional",
                          "type": "array",
                          "description": "List of planned compatible units (CUs)",
                          "modelRef": "#/components/schemas/PlannedCompatibleUnit",
                          "customType": "PlannedCompatibleUnit[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "projectId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "quantity",
                              "kind": "optional",
                              "type": "number",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "compatibleUnitId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "geometries",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/Geometry",
                              "customType": "Geometry[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "createDate",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastUpdated",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "createUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "updateUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "projectId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "uuid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "latitude84",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "longitude84",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "altitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "accuracyInches",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "latitudeSd",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "longitudeSd",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "altitudeSd",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "satelliteCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "recordType",
                                  "kind": "optional",
                                  "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "fixQuality",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "datum",
                                  "kind": "optional",
                                  "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "correctionAge",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "dsId",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "depthInches",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lrfMetadata",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "modelRef": "#/components/schemas/LrfMetadata",
                                  "customType": "LrfMetadata[]",
                                  "schema": [
                                    {
                                      "name": "latitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "accuracyInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "horizontalDistanceInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "verticalDistanceInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "azimuthDegrees",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lrfEyeHeightInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "poleInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "datum",
                                      "kind": "optional",
                                      "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                      "description": "",
                                      "example": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "poleInches",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "latitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "longitude",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "altitudeGeoid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "ellipsoidHeight",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "deleted",
                                  "kind": "optional",
                                  "type": "boolean",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "deviceInfo",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/DeviceInfo",
                                  "customType": "DeviceInfo",
                                  "schema": [
                                    {
                                      "name": "deviceType",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "serialNumber",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firmwareVersion",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "connectionName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "solutionType",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "originalLatitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "originalLongitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "originalAltitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groundPositionType",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "imuState",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    }
                                  ]
                                }
                              ]
                            },
                            {
                              "name": "workLocationId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "integrationData",
                              "kind": "optional",
                              "type": "object",
                              "description": "",
                              "modelRef": "#/components/schemas/JsonNode",
                              "customType": "JsonNode",
                              "schema": []
                            },
                            {
                              "name": "designAttributes",
                              "kind": "optional",
                              "type": "map",
                              "description": "",
                              "example": "",
                              "customType": "map<string, object>",
                              "schema": []
                            },
                            {
                              "name": "externalCuId",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "workFunction",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "symbology",
                              "kind": "optional",
                              "type": "object",
                              "description": "",
                              "modelRef": "#/components/schemas/Symbology",
                              "customType": "Symbology",
                              "schema": [
                                {
                                  "name": "symbol",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lineType",
                                  "kind": "optional",
                                  "type": "string<SOLID | DOTTED | DASHED | LIGHT_SOLID | LIGHT_DOTTED | LIGHT_NARROW_DASHED | NARROW_SOLID | DOUBLE_DASHED | THIN_DOUBLE_DASHED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "coloring",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/Coloring",
                                  "customType": "Coloring",
                                  "schema": [
                                    {
                                      "name": "symbolColor",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "linePinColor",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    }
                                  ]
                                }
                              ]
                            },
                            {
                              "name": "createUser",
                              "kind": "optional",
                              "type": "object",
                              "description": "",
                              "modelRef": "#/components/schemas/FieldUser",
                              "customType": "FieldUser",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "username",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "firstName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "guid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "email",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "status",
                                  "kind": "optional",
                                  "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "groupIds",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "example": "",
                                  "itemType": "integer",
                                  "customType": "integer[]",
                                  "itemExample": "",
                                  "itemDefault": ""
                                }
                              ]
                            },
                            {
                              "name": "updateUser",
                              "kind": "optional",
                              "type": "object",
                              "description": "",
                              "modelRef": "#/components/schemas/FieldUser",
                              "customType": "FieldUser",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "username",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "firstName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "guid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "email",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "status",
                                  "kind": "optional",
                                  "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "groupIds",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "example": "",
                                  "itemType": "integer",
                                  "customType": "integer[]",
                                  "itemExample": "",
                                  "itemDefault": ""
                                }
                              ]
                            },
                            {
                              "name": "createDate",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "lastUpdated",
                              "kind": "optional",
                              "type": "string<date-time>",
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "datum",
                          "kind": "optional",
                          "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                          "description": "Datum - WGS84 is the default",
                          "example": ""
                        }
                      ]
                    },
                    {
                      "name": "links",
                      "kind": "optional",
                      "type": "array",
                      "description": "",
                      "modelRef": "#/components/schemas/InboundLink",
                      "customType": "InboundLink[]",
                      "schema": [
                        {
                          "name": "action",
                          "kind": "optional",
                          "type": "string<ADD | UPDATE>",
                          "description": "Only ADD is supported to add a work unit for a work location",
                          "example": "ADD"
                        },
                        {
                          "name": "entityType",
                          "kind": "optional",
                          "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                          "description": "Only WORK_LOCATION is supported",
                          "example": "WORK_LOCATION"
                        },
                        {
                          "name": "referenceId",
                          "kind": "optional",
                          "type": "string",
                          "description": "The work location name",
                          "example": "WL 1"
                        },
                        {
                          "name": "uuid",
                          "kind": "optional",
                          "type": "string",
                          "description": "Generated by the IM for internal use, the client can ignore this",
                          "example": ""
                        }
                      ]
                    }
                  ]
                }
              ]
            }
          ],
          "modelRef": "#/components/schemas/IntegrationInboundFlowRequest",
          "complexItems": [
            {
              "name": "object",
              "schema": [
                {
                  "name": "endpointAlias",
                  "kind": "optional",
                  "type": "string",
                  "description": "Alias for the endpoint. Optional Field. Results are returned if the endpoint was sent in the request and if SkipInboundResponseDispatch is set to false",
                  "example": "inboundFolder"
                },
                {
                  "name": "integrationName",
                  "kind": "optional",
                  "type": "string",
                  "description": "Integration type name",
                  "example": "myIntegration"
                },
                {
                  "name": "integrationFlowName",
                  "kind": "optional",
                  "type": "string",
                  "description": "Integration flow name",
                  "example": "flow1"
                },
                {
                  "name": "objects",
                  "kind": "optional",
                  "type": "array",
                  "description": "List of all new/updated entities",
                  "modelRef": "#/components/schemas/AbstractInboundObject",
                  "customType": "AbstractInboundObject[]",
                  "schema": [
                    {
                      "name": "action",
                      "kind": "optional",
                      "type": "string<ADD | UPDATE>",
                      "description": "Desired action to take on the entity",
                      "example": "ADD, UPDATE"
                    },
                    {
                      "name": "referenceId",
                      "kind": "optional",
                      "type": "string",
                      "description": "Entity ID of the 3rd party system",
                      "example": ""
                    },
                    {
                      "name": "lvId",
                      "kind": "optional",
                      "type": "integer<int64>",
                      "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                      "example": 0
                    },
                    {
                      "name": "typeName",
                      "kind": "optional",
                      "type": "string",
                      "description": "Locusview Entity Type Name",
                      "example": "Pipe"
                    },
                    {
                      "name": "entityType",
                      "kind": "optional",
                      "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                      "description": "Locusview Entity Type",
                      "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                    }
                  ]
                }
              ],
              "modelRef": "#/components/schemas/AbstractIntegrationInboundFlowRequest",
              "customType": "AbstractIntegrationInboundFlowRequest"
            },
            {
              "name": "object",
              "schema": [
                {
                  "name": "endpointAlias",
                  "kind": "optional",
                  "type": "string",
                  "description": "Alias for the endpoint. Optional Field. Results are returned if the endpoint was sent in the request and if SkipInboundResponseDispatch is set to false",
                  "example": "inboundFolder"
                },
                {
                  "name": "integrationName",
                  "kind": "optional",
                  "type": "string",
                  "description": "Integration type name",
                  "example": "myIntegration"
                },
                {
                  "name": "integrationFlowName",
                  "kind": "optional",
                  "type": "string",
                  "description": "Integration flow name",
                  "example": "flow1"
                },
                {
                  "name": "objects",
                  "kind": "optional",
                  "type": "object",
                  "description": "List of all new/updated entities",
                  "modelRef": "#/components/schemas/InboundObject",
                  "customType": "InboundObject[]",
                  "schema": [],
                  "complexType": "allOf",
                  "complexItems": [
                    {
                      "name": "AbstractInboundObject",
                      "description": "",
                      "modelRef": "#/components/schemas/AbstractInboundObject",
                      "schema": [
                        {
                          "name": "action",
                          "kind": "optional",
                          "type": "string<ADD | UPDATE>",
                          "description": "Desired action to take on the entity",
                          "example": "ADD, UPDATE"
                        },
                        {
                          "name": "referenceId",
                          "kind": "optional",
                          "type": "string",
                          "description": "Entity ID of the 3rd party system",
                          "example": ""
                        },
                        {
                          "name": "lvId",
                          "kind": "optional",
                          "type": "integer<int64>",
                          "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                          "example": 0
                        },
                        {
                          "name": "typeName",
                          "kind": "optional",
                          "type": "string",
                          "description": "Locusview Entity Type Name",
                          "example": "Pipe"
                        },
                        {
                          "name": "entityType",
                          "kind": "optional",
                          "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                          "description": "Locusview Entity Type",
                          "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                        }
                      ]
                    },
                    {
                      "name": "object",
                      "description": "",
                      "schema": [
                        {
                          "name": "action",
                          "kind": "optional",
                          "type": "string<ADD | UPDATE>",
                          "description": "Desired action to take on the entity",
                          "example": "ADD, UPDATE"
                        },
                        {
                          "name": "referenceId",
                          "kind": "optional",
                          "type": "string",
                          "description": "Entity ID of the 3rd party system",
                          "example": ""
                        },
                        {
                          "name": "lvId",
                          "kind": "optional",
                          "type": "integer<int64>",
                          "description": "The Locusview entity Id (i.e., asset, form, work order, or work unit) that correlates with the referenceId",
                          "example": 0
                        },
                        {
                          "name": "typeName",
                          "kind": "optional",
                          "type": "string",
                          "description": "Locusview Entity Type Name",
                          "example": "Pipe"
                        },
                        {
                          "name": "entityType",
                          "kind": "optional",
                          "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                          "description": "Locusview Entity Type",
                          "example": "WORK_ORDER, ASSET, WORK_UNIT, FORM, DESIGN"
                        },
                        {
                          "name": "parent",
                          "kind": "optional",
                          "type": "object",
                          "description": "Inbound Parent Object",
                          "modelRef": "#/components/schemas/ObjectParent",
                          "customType": "ObjectParent",
                          "schema": [
                            {
                              "name": "referenceId",
                              "kind": "optional",
                              "type": "string",
                              "description": "Reference Id",
                              "example": ""
                            },
                            {
                              "name": "entityType",
                              "kind": "optional",
                              "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                              "description": "Entity Type",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "fields",
                          "kind": "optional",
                          "type": "map",
                          "description": "",
                          "example": "",
                          "customType": "map<string, object>",
                          "schema": []
                        },
                        {
                          "name": "geometries",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/InboundGeometry",
                          "customType": "InboundGeometry[]",
                          "schema": [
                            {
                              "name": "latitude",
                              "kind": "optional",
                              "type": "number",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "longitude",
                              "kind": "optional",
                              "type": "number",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "altitude",
                              "kind": "optional",
                              "type": "number",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "datum",
                              "kind": "optional",
                              "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "recordType",
                              "kind": "optional",
                              "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "status",
                          "kind": "optional",
                          "type": "string<IN_PROGRESS | SUBMITTED | IN_REVIEW | APPROVED | REJECTED | EXPORTED | NEW | DRAFT>",
                          "description": "",
                          "example": ""
                        },
                        {
                          "name": "assignment",
                          "kind": "optional",
                          "type": "object",
                          "description": "",
                          "modelRef": "#/components/schemas/Assignment",
                          "customType": "Assignment",
                          "schema": [
                            {
                              "name": "userIds",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "usernames",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "string",
                              "customType": "string[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "groupnames",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "string",
                              "customType": "string[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "groupIds",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "users",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/FieldUser",
                              "customType": "FieldUser[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "username",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "firstName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "guid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "email",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "status",
                                  "kind": "optional",
                                  "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "groupIds",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "example": "",
                                  "itemType": "integer",
                                  "customType": "integer[]",
                                  "itemExample": "",
                                  "itemDefault": ""
                                }
                              ]
                            },
                            {
                              "name": "groups",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/GroupPreview",
                              "customType": "GroupPreview[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "name",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "description",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "usersCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "groupsCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "policiesCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                }
                              ]
                            }
                          ]
                        },
                        {
                          "name": "permission",
                          "kind": "optional",
                          "type": "object",
                          "description": "",
                          "modelRef": "#/components/schemas/Permission",
                          "customType": "Permission",
                          "schema": [
                            {
                              "name": "userIds",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "groupIds",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "integer",
                              "customType": "integer[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "usernames",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "string",
                              "customType": "string[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "groupnames",
                              "kind": "optional",
                              "type": "array",
                              "writeOnly": true,
                              "description": "",
                              "example": "",
                              "itemType": "string",
                              "customType": "string[]",
                              "itemExample": "",
                              "itemDefault": ""
                            },
                            {
                              "name": "users",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/FieldUser",
                              "customType": "FieldUser[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "username",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "firstName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "guid",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "email",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "status",
                                  "kind": "optional",
                                  "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "groupIds",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "example": "",
                                  "itemType": "integer",
                                  "customType": "integer[]",
                                  "itemExample": "",
                                  "itemDefault": ""
                                }
                              ]
                            },
                            {
                              "name": "groups",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/GroupPreview",
                              "customType": "GroupPreview[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "name",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "description",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "usersCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "groupsCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "policiesCount",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "",
                                  "example": 0
                                }
                              ]
                            },
                            {
                              "name": "allowAll",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "materials",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/Material",
                          "customType": "Material[]",
                          "schema": [
                            {
                              "name": "id",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "partNumber",
                              "kind": "optional",
                              "type": "string",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "projectId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "status",
                              "kind": "optional",
                              "type": "string<APPROVED | REJECTED | PENDING>",
                              "description": "",
                              "example": ""
                            },
                            {
                              "name": "numberOfAssets",
                              "kind": "optional",
                              "type": "integer<int32>",
                              "description": "",
                              "example": 0
                            },
                            {
                              "name": "catalogItem",
                              "kind": "optional",
                              "type": "object",
                              "description": "",
                              "modelRef": "#/components/schemas/Catalog",
                              "customType": "Catalog",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "createDate",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastUpdated",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "active",
                                  "kind": "optional",
                                  "type": "boolean",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "typeId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "customFields",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "astmBarcode",
                                  "kind": "optional",
                                  "type": "string",
                                  "writeOnly": true,
                                  "description": "",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "catalogItems",
                              "kind": "optional",
                              "type": "array",
                              "description": "",
                              "modelRef": "#/components/schemas/Catalog",
                              "customType": "Catalog[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "createDate",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastUpdated",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "active",
                                  "kind": "optional",
                                  "type": "boolean",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "typeId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "customFields",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "astmBarcode",
                                  "kind": "optional",
                                  "type": "string",
                                  "writeOnly": true,
                                  "description": "",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "quantity",
                              "kind": "optional",
                              "type": "number",
                              "description": "",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "design",
                          "kind": "optional",
                          "type": "object",
                          "description": "Inbound Design",
                          "modelRef": "#/components/schemas/InboundDesign",
                          "customType": "InboundDesign",
                          "schema": [
                            {
                              "name": "workLocations",
                              "kind": "optional",
                              "type": "array",
                              "description": "List of Work Locations",
                              "modelRef": "#/components/schemas/InboundWorkLocation",
                              "customType": "InboundWorkLocation[]",
                              "schema": [
                                {
                                  "name": "name",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "Work Location Name",
                                  "example": "WL 1"
                                },
                                {
                                  "name": "wuTypeName",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "The relevant Work Unit Type name",
                                  "example": "Paving"
                                },
                                {
                                  "name": "geometries",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "Simplified geometry list",
                                  "modelRef": "#/components/schemas/InboundGeometry",
                                  "customType": "InboundGeometry[]",
                                  "schema": [
                                    {
                                      "name": "latitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "datum",
                                      "kind": "optional",
                                      "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "recordType",
                                      "kind": "optional",
                                      "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                      "description": "",
                                      "example": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "order",
                                  "kind": "optional",
                                  "type": "integer<int32>",
                                  "description": "Order",
                                  "example": 0
                                },
                                {
                                  "name": "plannedCompatibleUnits",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "List of Planned Compatible Units. Planned CUS  are imported compatible units within the work design. Planned CUS  are displayed in the mobile app based on association with a specific Work Design associated with a particular work order. ",
                                  "modelRef": "#/components/schemas/PlannedCompatibleUnit",
                                  "customType": "PlannedCompatibleUnit[]",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "projectId",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "quantity",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "compatibleUnitId",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "geometries",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "modelRef": "#/components/schemas/Geometry",
                                      "customType": "Geometry[]",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "createDate",
                                          "kind": "optional",
                                          "type": "string<date-time>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastUpdated",
                                          "kind": "optional",
                                          "type": "string<date-time>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "createUser",
                                          "kind": "optional",
                                          "type": "object",
                                          "description": "",
                                          "modelRef": "#/components/schemas/FieldUser",
                                          "customType": "FieldUser",
                                          "schema": [
                                            {
                                              "name": "id",
                                              "kind": "optional",
                                              "type": "integer<int64>",
                                              "description": "",
                                              "example": 0
                                            },
                                            {
                                              "name": "username",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "firstName",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "lastName",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "guid",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "email",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "status",
                                              "kind": "optional",
                                              "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "groupIds",
                                              "kind": "optional",
                                              "type": "array",
                                              "description": "",
                                              "example": "",
                                              "itemType": "integer",
                                              "customType": "integer[]",
                                              "itemExample": "",
                                              "itemDefault": ""
                                            }
                                          ]
                                        },
                                        {
                                          "name": "updateUser",
                                          "kind": "optional",
                                          "type": "object",
                                          "description": "",
                                          "modelRef": "#/components/schemas/FieldUser",
                                          "customType": "FieldUser",
                                          "schema": [
                                            {
                                              "name": "id",
                                              "kind": "optional",
                                              "type": "integer<int64>",
                                              "description": "",
                                              "example": 0
                                            },
                                            {
                                              "name": "username",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "firstName",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "lastName",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "guid",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "email",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "status",
                                              "kind": "optional",
                                              "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "groupIds",
                                              "kind": "optional",
                                              "type": "array",
                                              "description": "",
                                              "example": "",
                                              "itemType": "integer",
                                              "customType": "integer[]",
                                              "itemExample": "",
                                              "itemDefault": ""
                                            }
                                          ]
                                        },
                                        {
                                          "name": "projectId",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "uuid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "latitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "altitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "accuracyInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "latitudeSd",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitudeSd",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "altitudeSd",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "satelliteCount",
                                          "kind": "optional",
                                          "type": "integer<int32>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "recordType",
                                          "kind": "optional",
                                          "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "fixQuality",
                                          "kind": "optional",
                                          "type": "integer<int32>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "datum",
                                          "kind": "optional",
                                          "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "correctionAge",
                                          "kind": "optional",
                                          "type": "integer<int32>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "dsId",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "depthInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lrfMetadata",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "modelRef": "#/components/schemas/LrfMetadata",
                                          "customType": "LrfMetadata[]",
                                          "schema": [
                                            {
                                              "name": "latitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "longitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "altitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "accuracyInches",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "horizontalDistanceInches",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "verticalDistanceInches",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "azimuthDegrees",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "lrfEyeHeightInches",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "latitude84",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "longitude84",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "poleInches",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "datum",
                                              "kind": "optional",
                                              "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                              "description": "",
                                              "example": ""
                                            }
                                          ]
                                        },
                                        {
                                          "name": "poleInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "latitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "altitudeGeoid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "ellipsoidHeight",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "deleted",
                                          "kind": "optional",
                                          "type": "boolean",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "deviceInfo",
                                          "kind": "optional",
                                          "type": "object",
                                          "description": "",
                                          "modelRef": "#/components/schemas/DeviceInfo",
                                          "customType": "DeviceInfo",
                                          "schema": [
                                            {
                                              "name": "deviceType",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "serialNumber",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "firmwareVersion",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "connectionName",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "solutionType",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "originalLatitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "originalLongitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "originalAltitude",
                                              "kind": "optional",
                                              "type": "number",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "groundPositionType",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "imuState",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            }
                                          ]
                                        }
                                      ]
                                    },
                                    {
                                      "name": "workLocationId",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "integrationData",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/JsonNode",
                                      "customType": "JsonNode",
                                      "schema": []
                                    },
                                    {
                                      "name": "designAttributes",
                                      "kind": "optional",
                                      "type": "map",
                                      "description": "",
                                      "example": "",
                                      "customType": "map<string, object>",
                                      "schema": []
                                    },
                                    {
                                      "name": "externalCuId",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "workFunction",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "symbology",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/Symbology",
                                      "customType": "Symbology",
                                      "schema": [
                                        {
                                          "name": "symbol",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lineType",
                                          "kind": "optional",
                                          "type": "string<SOLID | DOTTED | DASHED | LIGHT_SOLID | LIGHT_DOTTED | LIGHT_NARROW_DASHED | NARROW_SOLID | DOUBLE_DASHED | THIN_DOUBLE_DASHED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "coloring",
                                          "kind": "optional",
                                          "type": "object",
                                          "description": "",
                                          "modelRef": "#/components/schemas/Coloring",
                                          "customType": "Coloring",
                                          "schema": [
                                            {
                                              "name": "symbolColor",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            },
                                            {
                                              "name": "linePinColor",
                                              "kind": "optional",
                                              "type": "string",
                                              "description": "",
                                              "example": ""
                                            }
                                          ]
                                        }
                                      ]
                                    },
                                    {
                                      "name": "createUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "updateUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "createDate",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastUpdated",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "parent",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "Inbound Parent Object",
                                  "modelRef": "#/components/schemas/ObjectParent",
                                  "customType": "ObjectParent",
                                  "schema": [
                                    {
                                      "name": "referenceId",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "Reference Id",
                                      "example": ""
                                    },
                                    {
                                      "name": "entityType",
                                      "kind": "optional",
                                      "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                                      "description": "Entity Type",
                                      "example": ""
                                    }
                                  ]
                                }
                              ]
                            },
                            {
                              "name": "plannedCompatibleUnits",
                              "kind": "optional",
                              "type": "array",
                              "description": "List of planned compatible units (CUs)",
                              "modelRef": "#/components/schemas/PlannedCompatibleUnit",
                              "customType": "PlannedCompatibleUnit[]",
                              "schema": [
                                {
                                  "name": "id",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "projectId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "quantity",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "compatibleUnitId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "geometries",
                                  "kind": "optional",
                                  "type": "array",
                                  "description": "",
                                  "modelRef": "#/components/schemas/Geometry",
                                  "customType": "Geometry[]",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "createDate",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastUpdated",
                                      "kind": "optional",
                                      "type": "string<date-time>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "createUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "updateUser",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/FieldUser",
                                      "customType": "FieldUser",
                                      "schema": [
                                        {
                                          "name": "id",
                                          "kind": "optional",
                                          "type": "integer<int64>",
                                          "description": "",
                                          "example": 0
                                        },
                                        {
                                          "name": "username",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firstName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lastName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "guid",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "email",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "status",
                                          "kind": "optional",
                                          "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groupIds",
                                          "kind": "optional",
                                          "type": "array",
                                          "description": "",
                                          "example": "",
                                          "itemType": "integer",
                                          "customType": "integer[]",
                                          "itemExample": "",
                                          "itemDefault": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "projectId",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "uuid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude84",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "accuracyInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitudeSd",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "satelliteCount",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "recordType",
                                      "kind": "optional",
                                      "type": "string<INTERNAL | EXTERNAL | MANUAL | CALCULATED | DEFAULT | IMPORTED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "fixQuality",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "datum",
                                      "kind": "optional",
                                      "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "correctionAge",
                                      "kind": "optional",
                                      "type": "integer<int32>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "dsId",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "depthInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lrfMetadata",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "modelRef": "#/components/schemas/LrfMetadata",
                                      "customType": "LrfMetadata[]",
                                      "schema": [
                                        {
                                          "name": "latitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "altitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "accuracyInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "horizontalDistanceInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "verticalDistanceInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "azimuthDegrees",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "lrfEyeHeightInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "latitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "longitude84",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "poleInches",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "datum",
                                          "kind": "optional",
                                          "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    },
                                    {
                                      "name": "poleInches",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "latitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "longitude",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "altitudeGeoid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "ellipsoidHeight",
                                      "kind": "optional",
                                      "type": "number",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "deleted",
                                      "kind": "optional",
                                      "type": "boolean",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "deviceInfo",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/DeviceInfo",
                                      "customType": "DeviceInfo",
                                      "schema": [
                                        {
                                          "name": "deviceType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "serialNumber",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "firmwareVersion",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "connectionName",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "solutionType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalLatitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalLongitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "originalAltitude",
                                          "kind": "optional",
                                          "type": "number",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "groundPositionType",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "imuState",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    }
                                  ]
                                },
                                {
                                  "name": "workLocationId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "",
                                  "example": 0
                                },
                                {
                                  "name": "integrationData",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/JsonNode",
                                  "customType": "JsonNode",
                                  "schema": []
                                },
                                {
                                  "name": "designAttributes",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "externalCuId",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "workFunction",
                                  "kind": "optional",
                                  "type": "string",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "symbology",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/Symbology",
                                  "customType": "Symbology",
                                  "schema": [
                                    {
                                      "name": "symbol",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lineType",
                                      "kind": "optional",
                                      "type": "string<SOLID | DOTTED | DASHED | LIGHT_SOLID | LIGHT_DOTTED | LIGHT_NARROW_DASHED | NARROW_SOLID | DOUBLE_DASHED | THIN_DOUBLE_DASHED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "coloring",
                                      "kind": "optional",
                                      "type": "object",
                                      "description": "",
                                      "modelRef": "#/components/schemas/Coloring",
                                      "customType": "Coloring",
                                      "schema": [
                                        {
                                          "name": "symbolColor",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        },
                                        {
                                          "name": "linePinColor",
                                          "kind": "optional",
                                          "type": "string",
                                          "description": "",
                                          "example": ""
                                        }
                                      ]
                                    }
                                  ]
                                },
                                {
                                  "name": "createUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "updateUser",
                                  "kind": "optional",
                                  "type": "object",
                                  "description": "",
                                  "modelRef": "#/components/schemas/FieldUser",
                                  "customType": "FieldUser",
                                  "schema": [
                                    {
                                      "name": "id",
                                      "kind": "optional",
                                      "type": "integer<int64>",
                                      "description": "",
                                      "example": 0
                                    },
                                    {
                                      "name": "username",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "firstName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "lastName",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "guid",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "email",
                                      "kind": "optional",
                                      "type": "string",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "status",
                                      "kind": "optional",
                                      "type": "string<ACTIVE | INACTIVE | LOCKED>",
                                      "description": "",
                                      "example": ""
                                    },
                                    {
                                      "name": "groupIds",
                                      "kind": "optional",
                                      "type": "array",
                                      "description": "",
                                      "example": "",
                                      "itemType": "integer",
                                      "customType": "integer[]",
                                      "itemExample": "",
                                      "itemDefault": ""
                                    }
                                  ]
                                },
                                {
                                  "name": "createDate",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                },
                                {
                                  "name": "lastUpdated",
                                  "kind": "optional",
                                  "type": "string<date-time>",
                                  "description": "",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "datum",
                              "kind": "optional",
                              "type": "string<WGS84 | NAD83 | ITRF08 | ITRF2014 | OSGB36 | GDA2020 | NZGD2000 | SIRGAS2000 | SVY21 | NAD27 | GGRS87>",
                              "description": "Datum - WGS84 is the default",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "links",
                          "kind": "optional",
                          "type": "array",
                          "description": "",
                          "modelRef": "#/components/schemas/InboundLink",
                          "customType": "InboundLink[]",
                          "schema": [
                            {
                              "name": "action",
                              "kind": "optional",
                              "type": "string<ADD | UPDATE>",
                              "description": "Only ADD is supported to add a work unit for a work location",
                              "example": "ADD"
                            },
                            {
                              "name": "entityType",
                              "kind": "optional",
                              "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                              "description": "Only WORK_LOCATION is supported",
                              "example": "WORK_LOCATION"
                            },
                            {
                              "name": "referenceId",
                              "kind": "optional",
                              "type": "string",
                              "description": "The work location name",
                              "example": "WL 1"
                            },
                            {
                              "name": "uuid",
                              "kind": "optional",
                              "type": "string",
                              "description": "Generated by the IM for internal use, the client can ignore this",
                              "example": ""
                            }
                          ]
                        }
                      ]
                    }
                  ]
                }
              ]
            }
          ],
          "complexType": "allOf",
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
            "description": "Inbound Integration response",
            "customType": "IntegrationInboundFlowResponse",
            "schema": [
              {
                "name": "inboundFlowId",
                "kind": "optional",
                "type": "integer<int64>",
                "description": "Flow execution id",
                "example": 0
              }
            ],
            "modelRef": "#/components/schemas/IntegrationInboundFlowResponse",
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
          "id": "yXHW267mM9ZtldCw7ZDy7",
          "language": "curl",
          "label": "cURL",
          "code": "curl --location 'https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound' \\\n--header 'Accept: application/json' \\\n--header 'Content-Type: application/json' \\\n--data '{\n  \"objects\": {}\n}'"
        },
        {
          "id": "YIlfHgbAP7Ig3OJsll7ZS",
          "language": "javascript",
          "label": "javascript",
          "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar raw = JSON.stringify({\n   \"objects\": {}\n});\n\nvar requestOptions = {\n   method: 'POST',\n   headers: myHeaders,\n   body: raw,\n   redirect: 'follow'\n};\n\nfetch(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));"
        },
        {
          "id": "BuaXbCdx85Kpn3ukvVNqV",
          "language": "ruby",
          "label": "Ruby",
          "code": "require \"uri\"\nrequire \"json\"\nrequire \"net/http\"\n\nurl = URI(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound\")\n\nhttps = Net::HTTP.new(url.host, url.port)\nhttps.use_ssl = true\n\nrequest = Net::HTTP::Post.new(url)\nrequest[\"Accept\"] = \"application/json\"\nrequest[\"Content-Type\"] = \"application/json\"\nrequest.body = JSON.dump({\n   \"objects\": {}\n})\n\nresponse = https.request(request)\nputs response.read_body\n"
        },
        {
          "id": "tNF-fgtd2yTxrBvtYT0MM",
          "language": "python",
          "label": "Python",
          "code": "import requests\nimport json\n\nurl = \"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound\"\n\npayload = json.dumps({\n   \"objects\": {}\n})\nheaders = {\n   'Accept': 'application/json',\n   'Content-Type': 'application/json'\n}\n\nresponse = requests.request(\"POST\", url, headers=headers, data=payload)\n\nprint(response.text)\n"
        }
      ],
      "selectedLanguageId": "yXHW267mM9ZtldCw7ZDy7"
    },
    "results": {
      "languages": [
        {
          "id": "2CsCCB0vIqofmXFPgNx0X",
          "language": "200",
          "code": "// Success \n{\n  \"inboundFlowId\": \"\"\n}"
        },
        {
          "id": "G3bse3B-yVArbShr58R9Q",
          "language": "401",
          "code": "// Unauthorized \n{\n  \"rootCause\": \"\",\n  \"errors\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "xo6XTAybqAI9rHwOgZZ30",
          "language": "422",
          "code": "// Request error \n{\n  \"errorList\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "CgIxOIX_9KseZKzmvLeJ5",
          "language": "500",
          "code": "// Internal error \n"
        }
      ],
      "selectedLanguageId": "2CsCCB0vIqofmXFPgNx0X"
    }
  },
  "children": [
    {
      "text": ""
    }
  ]
}