---
title: 获取能量源阈值（功能索引 7）
description: 此函数将返回警告和错误阈值，如果命中或超过此阈值，则表示 (ES) 出现能量源问题。
ms.localizationpriority: medium
ms.date: 10/17/2018
ms.openlocfilehash: c2ecb117d43258530c8921b97076d958509ec6b7
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96835293"
---
# <a name="get-energy-source-thresholds-function-index-7"></a>获取能量源阈值（功能索引 7）


此函数将返回警告和错误阈值，如果命中或超过此阈值，则表示 (ES) 出现能量源问题。 如果 ES 受主机管理，并且平台不支持阈值，则此函数可能返回失败状态。

> [!NOTE]
> 标记为星形 () 的所有寄存器 \* 都是在可通过字节可寻址的、支持电源的接口规范中定义的寄存器。

 

## <a name="span-idinputspanspan-idinputspanspan-idinputspaninput"></a><span id="Input"></span><span id="input"></span><span id="INPUT"></span>送


### <a name="span-idargs3spanspan-idargs3spanspan-idargs3spanargs3"></a><span id="Args3"></span><span id="args3"></span><span id="ARGS3"></span>Args3

无。

## <a name="span-idoutputspanspan-idoutputspanspan-idoutputspanoutput"></a><span id="Output"></span><span id="output"></span><span id="OUTPUT"></span>输出


<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段</th>
<th align="left">字节长度</th>
<th align="left">字节偏移量</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>状态</strong></td>
<td align="left">4</td>
<td align="left">0</td>
<td align="left"><p>请参阅 <a href="-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md" data-raw-source="[_DSM Method Output](-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md)">_DSM 方法输出</a> 获取详细信息。</p></td>
</tr>
<tr class="even">
<td align="left"><strong>ES 生存期百分比警告阈值</strong></td>
<td align="left">1</td>
<td align="left">4</td>
<td align="left"><p>ES 生存期的警告阈值的百分比值。</p>
<p><em>Byte 0 – <em>ES_LIFETIME_WARNING_THRESHOLD (</em>) </p></td>
</tr>
<tr class="odd">
<td align="left"><strong>ES 生存期百分比错误阈值</strong></td>
<td align="left">1</td>
<td align="left">5</td>
<td align="left"><p>ES 生存期的错误阈值的百分比值。</p>
<p></em>Byte 0 – <em>ES_LIFETIME_ERROR_THRESHOLD (</em>) </p></td>
</tr>
<tr class="even">
<td align="left"><strong>ES 温度警告阈值</strong></td>
<td align="left">1</td>
<td align="left">6</td>
<td align="left"><p>ES 温度的警告阈值的百分比值。</p>
<p><em>Byte 0 – <em>ES_TEMP_WARNING_THRESHOLD (</em>) </p></td>
</tr>
<tr class="odd">
<td align="left"><strong>ES 温度错误阈值</strong></td>
<td align="left">1</td>
<td align="left">7</td>
<td align="left"><p>ES 温度的错误阈值的百分比值。</p>
<p></em>Byte 0 – <em>ES_TEMP_ERROR_THRESHOLD (</em>) </p></td>
</tr>
</tbody>
</table>

 

## <a name="span-idrelated_topicsspanrelated-topics"></a><span id="related_topics"></span>相关主题


[设置能量源生存期警告阈值（功能索引 8）](set-energy-source-lifetime-warning-threshold--function-index-8-.md)

[设置能量源温度警告阈值（功能索引 9）](set-energy-source-temperature-warning-threshold--function-index-9-.md)

[\_用于字节寻址的支持能源的函数类 (函数接口 1) 的 DSM 接口 ](-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md)

 

 






