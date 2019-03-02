---
title: 获取所有产品
description: Microsoft 硬件 API 中的此方法会检索注册到 Windows 开发人员中心帐户的所有产品的数据。
author: balapv
ms.author: balapv
ms.topic: article
ms.date: 04/05/2018
ms.localizationpriority: medium
ms.openlocfilehash: 447e1ab8d129c5a4c03488cfedd412a4831d2601
ms.sourcegitcommit: a33b7978e22d5bb9f65ca7056f955319049a2e4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "56518299"
---
# <a name="get-all-products"></a>获取所有产品

使用 Microsoft 硬件 API 中的此方法检索注册到 Windows 开发人员中心帐户的所有产品的数据。

## <a name="prerequisites"></a>必备条件

如果尚未开始操作，请先完成 Microsoft 硬件 API 的所有[先决条件](dashboard-api.md)，然后再尝试使用其中任何方法。

## <a name="request"></a>请求

此方法具有以下语法。 请参阅以下部分，获取标头和请求正文的使用示例和描述。

|方法|请求 URI|
|--|--|
|GET| `https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/` |

### <a name="request-header"></a>请求头

|标头|在任务栏的搜索框中键入|描述|
|--|--|--|
|授权|字符串|必需。 Azure AD 访问令牌的格式为 **Bearer** \<token\>。|
|accept|字符串|可选。 指定内容的类型。 允许的值是“application/json”|

### <a name="request-parameters"></a>请求参数

请勿为此方法提供请求参数。

### <a name="request-body"></a>请求正文

请勿为此方法提供请求正文。

### <a name="request-examples"></a>请求示例

以下示例演示了如何检索注册到帐户的所有产品的相关信息。

```cpp
GET https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/ HTTP/1.1
Authorization: Bearer <your access token>
```

## <a name="response"></a>响应

以下示例演示了注册到开发者帐户的所有产品的成功请求所返回的 JSON 响应正文。 为简洁起见，此示例仅显示该请求返回的前两个产品的数据。 有关响应正文中这些值的详细信息，请参阅以下部分。

```json
{
  "value": [
    {
      "id": 9007199267351834,
      "sharedProductId": 1152921504606971100,
      "links": [
        {
          "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/9007199267351834",
          "rel": "self",
          "method": "GET"
        },
        {
          "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/9007199267351834/submissions",
          "rel": "get_submissions",
          "method": "GET"
        }
      ],
      "isCommitted": true,
      "isExtensionInf": false, "_comment": "This field is deprecated and moved to submission resource",
      "deviceMetadataIds": [],
      "deviceType": "notSet",
      "isTestSign": false,
      "isFlightSign": false,
      "marketingNames": [],
      "productName": "NewDriverHacked",
      "selectedProductTypes": {},
      "requestedSignatures": [
        "WINDOWS_v100_X64_TH1_FULL",
        "WINDOWS_v63_X64"
      ],
      "additionalAttributes": {},
      "testHarness": "hlk"
    },
    {
      "id": 9007199267351836,
      "sharedProductId": 1152921504606971100,
      "links": [
        {
          "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/9007199267351835",
          "rel": "self",
          "method": "GET"
        },
        {
          "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products/9007199267351835/submissions",
          "rel": "get_submissions",
          "method": "GET"
        }
      ],
      "isCommitted": true,
      "isExtensionInf": false, "_comment": "This field is deprecated and moved to submission resource",
      "announcementDate": "2016-10-22T00:00:00Z",
      "deviceMetadataCategory": "Input.Digitizer.Multitouch",
      "deviceMetadataIds": [],
      "deviceType": "internalExternal",
      "isTestSign": false,
      "isFlightSign": false,  
      "marketingNames": [
        "MEU"
      ],
      "productName": "Mew2?",
      "selectedProductTypes": {
        "windows_v100": "Touch",
        "windows81": "Unclassified"
      },
      "requestedSignatures": [
        "WINDOWS_v100_X64_TH1_FULL",
        "WINDOWS_v63_X64"
      ],
      "additionalAttributes": {},
      "testHarness": "hlk"
    }
  ],
  "links": [
    {
      "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products?pageSize=50",
      "rel": "self",
      "method": "GET"
    },
    {
      "href": "https://manage.devcenter.microsoft.com/v1.0/my/hardware/products?pageSize=50&continuationToken=PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTE2Ij8%2BPENvbnRpbnVhdGlvblRva2VuPjxWZXJzaW9uPjIuMDwvVmVyc2lvbj48VHlwZT5UYWJsZTwvVHlwZT48TmV4dFBhcnRpdGlvbktleT4xITQ4IWNIVmliR2x6YUdWeWN5MHdNREF3TURBd01EQXdNREF3TURBd01ESTVPVFl6T1RJdzwvTmV4dFBhcnRpdGlvbktleT48TmV4dFJvd0tleT4xITk2IWRYTmxjaTFrWld4bGRHVmtMVEF0SUNBZ0lDQWdTR0Z5WkhkaGNtVkVjbWwyWlhJdGNISnZaSFZqZEhNdE1EQXdNREF3TURBd09UQXdOekU1T1RJMk56TTNNakUyTkEtLTwvTmV4dFJvd0tleT48VGFyZ2V0TG9jYXRpb24%2BUHJpbWFyeTwvVGFyZ2V0TG9jYXRpb24%2BPC9Db250aW51YXRpb25Ub2tlbj4%3D",
      "rel": "next_link",
      "method": "GET"
    }
  ]
}
```

### <a name="response-body"></a>响应正文

| 值 | 在任务栏的搜索框中键入 | 描述 |
|:--|:--|:--|
| value | 数组 | 一个对象数组，其中包含注册到你帐户的每个产品的相关信息。 有关每个对象中的数据的详细信息，请参阅[产品资源](get-product-data.md#product-resource)。 |
| links | 数组 | 一个对象数组，其中包含有关包含实体的有用链接。 有关更多详细信息，请参阅[链接对象](get-product-data.md#link-object)  |


## <a name="error-codes"></a>错误代码

有关详细信息，请参阅[错误代码](get-product-data.md#error-codes)。 

## <a name="see-also"></a>另请参阅

- [硬件仪表板 API 示例 (GitHub)](https://aka.ms/hpc_async_api_samples)