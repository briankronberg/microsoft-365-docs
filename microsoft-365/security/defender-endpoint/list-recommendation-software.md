---
title: List software by recommendation
description: Retrieves a security recommendation related to a specific software.
keywords: apis, graph api, supported apis, get, security recommendation, security recommendation for software, threat and vulnerability management, threat and vulnerability management api 
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance 
ms.topic: article
MS.technology: mde
ms.custom: api
---

# List software by recommendation

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Want to experience Defender for Endpoint? [Sign up for a free trial.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Retrieves a security recommendation related to a specific software.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.

Permission type|Permission|Permission display name
:---|:---|:---
Application|Software.Read.All|'Read Threat and Vulnerability Management Software information'
Delegated (work or school account)|SecurityRecommendation.Read|'Read Threat and Vulnerability Management security recommendation information'

## HTTP request

```http
GET /api/recommendations/{id}/software
```

## Request headers

Name|Type|Description
:---|:---|:---
Authorization|String|Bearer {token}. **Required**.

## Request body

Empty

## Response

If successful, this method returns 200 OK with the software associated with the security recommendations in the body.

## Example

### Request example

Here is an example of the request.

```http
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

### Response example

Here is an example of the response.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## Related topics

- [Risk-based Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Threat & Vulnerability security recommendation](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
