---
title: 'WDI_TLV_IPV4_LSO_V2 (0xD3) '
description: WDI_TLV_IPV4_LSO_V2 是包含大型发送卸载 V2 参数的 TLV 的 TLV。
ms.date: 07/18/2017
keywords:
- 从 Windows Vista 开始 WDI_TLV_IPV4_LSO_V2 (0xD3) 网络驱动程序
ms.localizationpriority: medium
ms.openlocfilehash: 60163386e30334de02a92f32999fb2cc17281758
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96809883"
---
# <a name="wdi_tlv_ipv4_lso_v2-0xd3"></a>WDI \_ TLV \_ IPV4 \_ LSO \_ V2 (0xD3) 


WDI \_ tlv \_ ipv4 \_ LSO \_ v2 是一个 tlv，其中包含适用于 IPV4 的大型发送卸载 V2 参数。

## <a name="tlv-type"></a>TLV 类型


0xD3

## <a name="length"></a>长度


Sum (所有包含的元素的大小) 。

## <a name="values"></a>值


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UINT32</td>
<td>封装类型。 有效值是：
<ul>
<li>WDI_ENCAPSULATION_IEEE_802_11</li>
</ul></td>
</tr>
<tr class="even">
<td>UINT32</td>
<td>最大卸载大小。 由每个数据包的 TCP 用户数据的最大字节数指定。</td>
</tr>
<tr class="odd">
<td>UINT32</td>
<td>最小段计数。 由分段后应出现的段数的最小数目指定。</td>
</tr>
</tbody>
</table>

 

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

 

 




