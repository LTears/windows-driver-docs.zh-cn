---
title: WDI_TLV_DELETE_PORT_PARAMETERS
description: WDI_TLV_DELETE_PORT_PARAMETERS 是包含参数的 OID_WDI_TASK_DELETE_PORT TLV。
ms.assetid: F3DDECDC-1A92-4022-9E2C-780ED480172C
ms.date: 07/18/2017
keywords:
- 从 Windows Vista 开始 WDI_TLV_DELETE_PORT_PARAMETERS 网络驱动程序
ms.localizationpriority: medium
ms.openlocfilehash: b9623fdc7dfaf098ccd6791f3aa6185973ab730d
ms.sourcegitcommit: a33b7978e22d5bb9f65ca7056f955319049a2e4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "56524846"
---
# <a name="wditlvdeleteportparameters"></a>WDI\_TLV\_删除\_端口\_参数


WDI\_TLV\_删除\_端口\_参数是包含参数的 TLV [OID\_WDI\_任务\_删除\_端口](https://msdn.microsoft.com/library/windows/hardware/dn925950).

## <a name="tlv-type"></a>TLV 类型


0x2A

## <a name="length"></a>长度


所有包含的元素的大小的总和 （以字节为单位）。

## <a name="values"></a>值


| 在任务栏的搜索框中键入   | 描述                          |
|--------|--------------------------------------|
| UINT16 | 指定要删除的端口号。 |

 

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
<td><p>Windows Server 2016</p></td>
</tr>
<tr class="odd">
<td><p>标头</p></td>
<td>Wditypes.hpp</td>
</tr>
</tbody>
</table>

 

 



