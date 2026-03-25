---
title: Run Inbound Integration Live Data flow
docTags: 
createdAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Dec 30 2025 16:32:17 GMT+0000 (Coordinated Universal Time)
---

{
  "id": "SiABJ_8BdMuYVRgrOnmrJ",
  "type": "api-oas-v2",
  "data": {
    "method": "POST",
    "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data",
    "servers": [
      {
        "url": "https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data",
        "description": "Production server"
      }
    ],
    "name": "Run Inbound Integration Live Data flow",
    "description": "Creates and updates Compatible Unit objects within the Locusview system",
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
          "description": "Request to run a live data Inbound integration flow",
          "customType": "IntegrationInboundFlowLiveDataRequest",
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
              "modelRef": "#/components/schemas/InboundLiveDataObject",
              "customType": "InboundLiveDataObject[]",
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
                      "name": "compatibleUnit",
                      "kind": "optional",
                      "type": "object",
                      "description": "Inbound Compatible Unit",
                      "modelRef": "#/components/schemas/InboundCompatibleUnit",
                      "customType": "InboundCompatibleUnit",
                      "schema": [
                        {
                          "name": "externalCuId",
                          "kind": "optional",
                          "type": "string",
                          "description": "Compatible unit external ID",
                          "example": ""
                        },
                        {
                          "name": "description",
                          "kind": "optional",
                          "type": "string",
                          "description": "Description",
                          "example": ""
                        },
                        {
                          "name": "unitOfMeasure",
                          "kind": "optional",
                          "type": "string",
                          "description": "Unit of measure",
                          "example": ""
                        },
                        {
                          "name": "workFunctions",
                          "kind": "optional",
                          "type": "array",
                          "description": "A list of applicative work functions values this CU can be attached with",
                          "example": "Install, Remove",
                          "itemType": "string",
                          "customType": "string[]",
                          "itemExample": "Install, Remove",
                          "itemDefault": ""
                        },
                        {
                          "name": "active",
                          "kind": "optional",
                          "type": "boolean",
                          "description": "Whether the CU is active",
                          "example": false
                        },
                        {
                          "name": "composingEntity",
                          "kind": "optional",
                          "type": "object",
                          "description": "Inbound Composing Entity",
                          "modelRef": "#/components/schemas/InboundComposingEntity",
                          "customType": "InboundComposingEntity",
                          "schema": [
                            {
                              "name": "lvId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "The composing entity object Id",
                              "example": 0
                            },
                            {
                              "name": "entityType",
                              "kind": "required",
                              "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                              "description": "The entity type the entity originated from",
                              "example": "ASSET, FORM"
                            },
                            {
                              "name": "typeName",
                              "kind": "required",
                              "type": "string",
                              "description": "The entity type name from which the entity originated",
                              "example": "Pipe"
                            },
                            {
                              "name": "fields",
                              "kind": "optional",
                              "type": "map",
                              "description": "Custom fields for the entity. Either the custom field alias or the backend value can be sent",
                              "example": "",
                              "customType": "map<string, object>",
                              "schema": []
                            },
                            {
                              "name": "child",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "Indicates whether it's a component (child) or the main composingEntity",
                              "example": ""
                            },
                            {
                              "name": "quantity",
                              "kind": "optional",
                              "type": "number",
                              "description": "The number of instances as in the design",
                              "example": ""
                            }
                          ]
                        },
                        {
                          "name": "components",
                          "kind": "optional",
                          "type": "array",
                          "description": "Relevant to CU that represents an assembly asset. \nAn array of composing entity objects representing the children components of the Assembly CU",
                          "modelRef": "#/components/schemas/InboundComposingEntity",
                          "customType": "InboundComposingEntity[]",
                          "schema": [
                            {
                              "name": "lvId",
                              "kind": "optional",
                              "type": "integer<int64>",
                              "description": "The composing entity object Id",
                              "example": 0
                            },
                            {
                              "name": "entityType",
                              "kind": "required",
                              "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                              "description": "The entity type the entity originated from",
                              "example": "ASSET, FORM"
                            },
                            {
                              "name": "typeName",
                              "kind": "required",
                              "type": "string",
                              "description": "The entity type name from which the entity originated",
                              "example": "Pipe"
                            },
                            {
                              "name": "fields",
                              "kind": "optional",
                              "type": "map",
                              "description": "Custom fields for the entity. Either the custom field alias or the backend value can be sent",
                              "example": "",
                              "customType": "map<string, object>",
                              "schema": []
                            },
                            {
                              "name": "child",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "Indicates whether it's a component (child) or the main composingEntity",
                              "example": ""
                            },
                            {
                              "name": "quantity",
                              "kind": "optional",
                              "type": "number",
                              "description": "The number of instances as in the design",
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
          "modelRef": "#/components/schemas/IntegrationInboundFlowLiveDataRequest",
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
                  "modelRef": "#/components/schemas/InboundLiveDataObject",
                  "customType": "InboundLiveDataObject[]",
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
                          "name": "compatibleUnit",
                          "kind": "optional",
                          "type": "object",
                          "description": "Inbound Compatible Unit",
                          "modelRef": "#/components/schemas/InboundCompatibleUnit",
                          "customType": "InboundCompatibleUnit",
                          "schema": [
                            {
                              "name": "externalCuId",
                              "kind": "optional",
                              "type": "string",
                              "description": "Compatible unit external ID",
                              "example": ""
                            },
                            {
                              "name": "description",
                              "kind": "optional",
                              "type": "string",
                              "description": "Description",
                              "example": ""
                            },
                            {
                              "name": "unitOfMeasure",
                              "kind": "optional",
                              "type": "string",
                              "description": "Unit of measure",
                              "example": ""
                            },
                            {
                              "name": "workFunctions",
                              "kind": "optional",
                              "type": "array",
                              "description": "A list of applicative work functions values this CU can be attached with",
                              "example": "Install, Remove",
                              "itemType": "string",
                              "customType": "string[]",
                              "itemExample": "Install, Remove",
                              "itemDefault": ""
                            },
                            {
                              "name": "active",
                              "kind": "optional",
                              "type": "boolean",
                              "description": "Whether the CU is active",
                              "example": false
                            },
                            {
                              "name": "composingEntity",
                              "kind": "optional",
                              "type": "object",
                              "description": "Inbound Composing Entity",
                              "modelRef": "#/components/schemas/InboundComposingEntity",
                              "customType": "InboundComposingEntity",
                              "schema": [
                                {
                                  "name": "lvId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "The composing entity object Id",
                                  "example": 0
                                },
                                {
                                  "name": "entityType",
                                  "kind": "required",
                                  "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                                  "description": "The entity type the entity originated from",
                                  "example": "ASSET, FORM"
                                },
                                {
                                  "name": "typeName",
                                  "kind": "required",
                                  "type": "string",
                                  "description": "The entity type name from which the entity originated",
                                  "example": "Pipe"
                                },
                                {
                                  "name": "fields",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "Custom fields for the entity. Either the custom field alias or the backend value can be sent",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "child",
                                  "kind": "optional",
                                  "type": "boolean",
                                  "description": "Indicates whether it's a component (child) or the main composingEntity",
                                  "example": ""
                                },
                                {
                                  "name": "quantity",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "The number of instances as in the design",
                                  "example": ""
                                }
                              ]
                            },
                            {
                              "name": "components",
                              "kind": "optional",
                              "type": "array",
                              "description": "Relevant to CU that represents an assembly asset. \nAn array of composing entity objects representing the children components of the Assembly CU",
                              "modelRef": "#/components/schemas/InboundComposingEntity",
                              "customType": "InboundComposingEntity[]",
                              "schema": [
                                {
                                  "name": "lvId",
                                  "kind": "optional",
                                  "type": "integer<int64>",
                                  "description": "The composing entity object Id",
                                  "example": 0
                                },
                                {
                                  "name": "entityType",
                                  "kind": "required",
                                  "type": "string<ALERT | ALERT_TYPE | FIELD | PROJECT_TYPE | PROJECT | JOINT | JOINT_TYPE | FORM | FORM_TYPE | ASSET | ASSET_TYPE | MODULE | GEOMETRY | DIMENSION | ENTITIES_LINKS | CATALOG | RECONCILIATION | MATERIAL | ASSIGNMENT | PERMISSION | AUTO_ATTACHMENT | MEASUREMENT | CATALOG_INDEX_LOOKUP | HEAT_NUMBER_COMBINATION | ACCESS_MANAGEMENT | WORKFLOW_STEP_TYPE | NONE | WORKFLOW_STEP | PLANNED_CU | COMPATIBLE_UNIT | COMPATIBLE_UNIT_TYPE | WORK_LOCATION | DESIGN | REPORT | UNPLANNED_COMPATIBLE_UNIT | WORK_ORDER | WORK_UNIT | WORK_ORDER_TYPE | WORK_UNIT_TYPE | INTEGRATION_FLOW | EXTERNAL_LINKS | EXISTING_ASSET_TYPE | ASSEMBLY_ASSETS | COMPATIBLE_UNIT_COMPARISON>",
                                  "description": "The entity type the entity originated from",
                                  "example": "ASSET, FORM"
                                },
                                {
                                  "name": "typeName",
                                  "kind": "required",
                                  "type": "string",
                                  "description": "The entity type name from which the entity originated",
                                  "example": "Pipe"
                                },
                                {
                                  "name": "fields",
                                  "kind": "optional",
                                  "type": "map",
                                  "description": "Custom fields for the entity. Either the custom field alias or the backend value can be sent",
                                  "example": "",
                                  "customType": "map<string, object>",
                                  "schema": []
                                },
                                {
                                  "name": "child",
                                  "kind": "optional",
                                  "type": "boolean",
                                  "description": "Indicates whether it's a component (child) or the main composingEntity",
                                  "example": ""
                                },
                                {
                                  "name": "quantity",
                                  "kind": "optional",
                                  "type": "number",
                                  "description": "The number of instances as in the design",
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
          "id": "_u3rBKzJw-kUIf0oPS70f",
          "language": "curl",
          "label": "cURL",
          "code": "curl --location 'https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data' \\\n--header 'Accept: application/json' \\\n--header 'Content-Type: application/json' \\\n--data '{\n  \"objects\": {\n    \"compatibleUnit\": {\n      \"composingEntity\": {\n        \"entityType\": \"ASSET, FORM\",\n        \"typeName\": \"Pipe\"\n      },\n      \"components\": [\n        {\n          \"entityType\": \"ASSET, FORM\",\n          \"typeName\": \"Pipe\"\n        }\n      ]\n    }\n  }\n}'"
        },
        {
          "id": "JOhgiPOA0Gy_628tzWPSl",
          "language": "javascript",
          "label": "javascript",
          "code": "var myHeaders = new Headers();\nmyHeaders.append(\"Accept\", \"application/json\");\nmyHeaders.append(\"Content-Type\", \"application/json\");\n\nvar raw = JSON.stringify({\n   \"objects\": {\n      \"compatibleUnit\": {\n         \"composingEntity\": {\n            \"entityType\": \"ASSET, FORM\",\n            \"typeName\": \"Pipe\"\n         },\n         \"components\": [\n            {\n               \"entityType\": \"ASSET, FORM\",\n               \"typeName\": \"Pipe\"\n            }\n         ]\n      }\n   }\n});\n\nvar requestOptions = {\n   method: 'POST',\n   headers: myHeaders,\n   body: raw,\n   redirect: 'follow'\n};\n\nfetch(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data\", requestOptions)\n   .then(response => response.text())\n   .then(result => console.log(result))\n   .catch(error => console.log('error', error));"
        },
        {
          "id": "X2Mrm6bWEdxmbD8pZfGE1",
          "language": "ruby",
          "label": "Ruby",
          "code": "require \"uri\"\nrequire \"json\"\nrequire \"net/http\"\n\nurl = URI(\"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data\")\n\nhttps = Net::HTTP.new(url.host, url.port)\nhttps.use_ssl = true\n\nrequest = Net::HTTP::Post.new(url)\nrequest[\"Accept\"] = \"application/json\"\nrequest[\"Content-Type\"] = \"application/json\"\nrequest.body = JSON.dump({\n   \"objects\": {\n      \"compatibleUnit\": {\n         \"composingEntity\": {\n            \"entityType\": \"ASSET, FORM\",\n            \"typeName\": \"Pipe\"\n         },\n         \"components\": [\n            {\n               \"entityType\": \"ASSET, FORM\",\n               \"typeName\": \"Pipe\"\n            }\n         ]\n      }\n   }\n})\n\nresponse = https.request(request)\nputs response.read_body\n"
        },
        {
          "id": "oeK8QGWykX--gnrPLQIas",
          "language": "python",
          "label": "Python",
          "code": "import requests\nimport json\n\nurl = \"https://<organization name>.locusview.io/api/<version>/<endpoint>/api/v1/integration/inbound/live-data\"\n\npayload = json.dumps({\n   \"objects\": {\n      \"compatibleUnit\": {\n         \"composingEntity\": {\n            \"entityType\": \"ASSET, FORM\",\n            \"typeName\": \"Pipe\"\n         },\n         \"components\": [\n            {\n               \"entityType\": \"ASSET, FORM\",\n               \"typeName\": \"Pipe\"\n            }\n         ]\n      }\n   }\n})\nheaders = {\n   'Accept': 'application/json',\n   'Content-Type': 'application/json'\n}\n\nresponse = requests.request(\"POST\", url, headers=headers, data=payload)\n\nprint(response.text)\n"
        }
      ],
      "selectedLanguageId": "_u3rBKzJw-kUIf0oPS70f"
    },
    "results": {
      "languages": [
        {
          "id": "13tcFJ9nddH4Kl94iqu2o",
          "language": "200",
          "code": "// Success \n{\n  \"inboundFlowId\": \"\"\n}"
        },
        {
          "id": "MbXvmJ4bXgSaBa3nONqDd",
          "language": "401",
          "code": "// Unauthorized \n{\n  \"rootCause\": \"\",\n  \"errors\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "LGPLhDlRyUAFWtcWp_iMd",
          "language": "422",
          "code": "// Request error \n{\n  \"errorList\": [\n    {\n      \"elementName\": \"\",\n      \"errorCode\": \"\",\n      \"parameters\": \"\"\n    }\n  ]\n}"
        },
        {
          "id": "CsRayMy2DMouEVfc-L3KV",
          "language": "500",
          "code": "// Internal error \n"
        }
      ],
      "selectedLanguageId": "13tcFJ9nddH4Kl94iqu2o"
    }
  },
  "children": [
    {
      "text": ""
    }
  ]
}