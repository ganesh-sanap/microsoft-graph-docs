---
title: "List taughtClasses"
description: "Get the educationClass resources from the taughtClasses navigation property."
author: "mlafleur"
localization_priority: Normal
ms.prod: "education"
doc_type: apiPageType
---

# List Classes Taught by an Edu User

Namespace: microsoft.graph

Get the educationClass resources from the taughtClasses navigation property.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | EduRoster.ReadBasic                         |
| Delegated (personal Microsoft account) | Not supported                               |
| Application                            | EduRoster.Read.All, EduRoster.ReadWrite.All |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

```http
GET /education/me/taughtClasses
GET /education/users/{educationUserId}/taughtClasses
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [educationClass](../resources/educationclass.md) objects in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "list_educationclass"
}
-->

```http
GET https://graph.microsoft.com/v1.0/education/classes/{educationClassId}/members/{educationUserId}/taughtClasses
```

### Response

**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.education.rostering.api.educationClass)"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.education.rostering.api.educationClass",
      "displayName": "String",
      "mailNickname": "String",
      "description": "String",
      "createdBy": {
        "@odata.type": "microsoft.graph.identitySet"
      },
      "classCode": "String",
      "externalName": "String",
      "externalId": "String",
      "externalSource": "String",
      "externalSourceDetail": "String",
      "grade": "String",
      "term": {
        "@odata.type": "microsoft.graph.educationTerm"
      },
      "course": {
        "@odata.type": "microsoft.graph.educationCourse"
      }
    }
  ]
}
```
