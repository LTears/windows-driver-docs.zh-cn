---
title: WIA \_ IPS \_ PRINTER \_ ENDORSER \_ YOFFSET
description: WIA \_ IPS \_ PRINTER \_ ENDORSER \_ YOFFSET 属性用于配置垂直坐标，范围为 imprinting/认可区域左上角 (0.001 \ 0034; ) ，相对于要扫描和 imprinted/认可的物理文档的左上角，以秒为单位。 WIA 微型驱动程序创建并维护此属性。
keywords:
- WIA_IPS_PRINTER_ENDORSER_YOFFSET 图像设备
topic_type:
- apiref
api_name:
- WIA_IPS_PRINTER_ENDORSER_YOFFSET
api_location:
- Wiadef.h
api_type:
- HeaderDef
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 16a2a6c8c4e982c8a499bc1610860f71cfc9e898
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96783207"
---
# <a name="wia_ips_printer_endorser_yoffset"></a>WIA \_ IPS \_ PRINTER \_ ENDORSER \_ YOFFSET


**WIA \_ IPS \_ PRINTER \_ ENDORSER \_ YOFFSET** 属性用于配置相对于要扫描和 imprinted/认可的物理文档的左上角的 imprinting/认可区域左上角 (0.001 ") 中的纵向坐标（以英寸为单位）。 WIA 微型驱动程序创建并维护此属性。




属性类型： VT \_ UI4

有效值： WIA 内容 \_ \_ 范围

访问权限：读/写

<a name="remarks"></a>备注
-------

当 Wia IPS PRINTER ENDORSER 属性更改为新的特定输入源时，WIA 微型驱动程序可以更新有效的值范围和当前值)  (，当 [**WIA \_ IPS \_ PRINTER \_**](wia-ips-printer-endorser.md) 属性更改为新的特定输入源 (也就是说，从平板到进纸机) 。

对于所有 Imprinter/Endorser 数据源项，此属性是可选的。

<a name="requirements"></a>要求
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>标头</p></td>
<td>Wiadef (包含 Wiadef) </td>
</tr>
</tbody>
</table>

 

 





