---
swagger: "2.0"
x-collection-name: Azure Cognitive Services
x-complete: 0
info:
  title: Azure Cognitive Services Cognitive Services Accounts Create
  description: Create Cognitive Services Account. Accounts is a resource group wide
    resource type. It holds the keys for developer to access intelligent APIs. It's
    also the resource type for billing.
  version: 1.0.0
host: management.azure.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.CognitiveServices/accounts/{accountName}:
    put:
      summary: Cognitive Services Accounts Create
      description: Create Cognitive Services Account. Accounts is a resource group
        wide resource type. It holds the keys for developer to access intelligent
        APIs. It's also the resource type for billing.
      operationId: CognitiveServicesAccounts_Create
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-cognitiveservicesaccountsaccountname-put
      parameters:
      - in: path
        name: accountName
        description: The name of Cognitive Services account
      - in: query
        name: No Name
      - in: body
        name: parameters
        description: The parameters to provide for the created account
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: resourceGroupName
        description: The name of the resource group within the users subscription
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Cognitive Service
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---