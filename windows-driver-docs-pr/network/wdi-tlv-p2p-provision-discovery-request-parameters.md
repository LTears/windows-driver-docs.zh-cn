---
title: WDI_TLV_P2P_PROVISION_DISCOVERY_REQUEST_PARAMETERS
description: WDI_TLV_P2P_PROVISION_DISCOVERY_REQUEST_PARAMETERS 是包含 Wi-Fi 预配发现请求参数的 TLV。
ms.date: 07/18/2017
keywords:
- 从 Windows Vista 开始 WDI_TLV_P2P_PROVISION_DISCOVERY_REQUEST_PARAMETERS 网络驱动程序
ms.localizationpriority: medium
ms.openlocfilehash: 28691e900d58a264e381882ffff1c5794d7dc91c
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96818191"
---
# <a name="wdi_tlv_p2p_provision_discovery_request_parameters"></a>WDI \_ TLV \_ P2P \_ 预配 \_ 发现 \_ 请求 \_ 参数


WDI \_ tlv \_ P2P \_ 预配 \_ 发现 \_ 请求 \_ 参数是一个 TLV，其中包含 Wi-Fi 预配发现请求参数。

## <a name="tlv-type"></a>TLV 类型


0x85

## <a name="length"></a>长度


Sum (所有包含的元素的大小) 。

## <a name="values"></a>值


| 类型  | 描述                                                                                                                                                          |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| UINT8 | Wi-Fi 直接分组功能位掩码。 位掩码与 Wi-Fi 直接技术规范的表13组功能位图定义中定义的位掩码匹配。 |
| UINT8 | 上面的组功能位图中的位由操作系统设置。                                                                                  |

 

<a name="requirements"></a>要求
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>最低受支持的客户端</p></td>
<td><p>Windows 10</p></td>
</tr>
<tr class="even">
<td><p>最低受支持的服务器</p></td>
<td><p>Windows Server 2016</p></td>
</tr>
<tr class="odd">
<td><p>标头</p></td>
<td>Wditypes.hpp</td>
</tr>
</tbody>
</table>

 

 




