---
title: OID_WDI_SET_RECEIVE_COALESCING
description: 主机使用 OID_WDI_SET_RECEIVE_COALESCING 来为数据包合并添加数据包筛选器。
ms.date: 07/18/2017
keywords:
- 从 Windows Vista 开始 OID_WDI_SET_RECEIVE_COALESCING 网络驱动程序
ms.localizationpriority: medium
ms.custom: 19H1
ms.openlocfilehash: 17ca2eebb6fedc6b8d1d79105679985b98bd269d
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96829329"
---
# <a name="oid_wdi_set_receive_coalescing"></a>OID \_ WDI \_ 设置 \_ 接收 \_ 合并


OID \_ WDI \_ SET \_ 接收 \_ 合并由主机用于为数据包合并添加数据包筛选器。

| 范围 | 设置序列化任务 | 正常执行时间 (秒)  |
|-------|--------------------------|---------------------------------|
| 端口  | 是                      | 1                               |

 

当主机接收到来自 OS 的请求以设置数据包合并筛选器时，它将使用此命令为数据包合并添加数据包筛选器。 若要为数据包合并清除数据包筛选器，请参阅 [OID \_ WDI \_ SET \_ clear \_ RECEIVE \_ 合并](oid-wdi-set-clear-receive-coalescing.md)。

## <a name="set-property-parameters"></a>设置属性参数


| TLV                                                                               | 允许多个 TLV 实例 | 可选 | 说明                                 |
|-----------------------------------------------------------------------------------|--------------------------------|----------|---------------------------------------------|
| [**WDI \_ TLV \_ 设置 \_ 接收 \_ 合并**](./wdi-tlv-set-receive-coalescing.md) |                                |          | 要设置的数据包合并参数。 |

 

## <a name="set-property-results"></a>设置属性结果


无其他参数。 标头中的数据足够了。

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
<td>Dot11wdi</td>
</tr>
</tbody>
</table>

## <a name="see-also"></a>请参阅


[OID \_ WDI \_ 设置 \_ 清除 \_ 接收 \_ 合并](oid-wdi-set-clear-receive-coalescing.md)

 

