---
title: TAEF 错误代码
description: TAEF 错误代码
ms.assetid: E42AF880-12DA-42b7-AB6D-90011BD7E548
ms.date: 04/20/2017
ms.localizationpriority: medium
ms.openlocfilehash: 16a2a34a048178dea5ef2bddd692b1094acca3a9
ms.sourcegitcommit: a33b7978e22d5bb9f65ca7056f955319049a2e4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "56547195"
---
# <a name="taef-error-codes"></a>TAEF 错误代码


TAEF 可能会遇到错误的原因，例如在有多种无法连接到计算机中，以便跨计算机执行或接收的广为人知的测试元数据的值无效。 发生错误时，TAEF 显示一条错误消息，通常与错误关联的 HRESULT 值。 HRESULT 值的大多数都[熟知的系统错误代码](https://msdn.microsoft.com/library/ms681381.aspx)，但 TAEF 有时会显示自定义错误代码。

## <a name="span-idcustomtaefhresultvaluesspanspan-idcustomtaefhresultvaluesspanspan-idcustomtaefhresultvaluesspancustom-taef-hresult-values"></a><span id="Custom_TAEF_HRESULT_Values"></span><span id="custom_taef_hresult_values"></span><span id="CUSTOM_TAEF_HRESULT_VALUES"></span>自定义 TAEF HRESULT 值


因为当他们添加，则将下表中所述 TAEF 的自定义的 HRESULT 值。 目前，没有只有一个 TAEF 特定的 HRESULT 值。

| HRESULT                             | 值      | 描述                                                                                                                                                                                                                                    |
|-------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TAEF\_E\_无效\_测试\_环境 | 0x81A40001 | TAEF 测试请求通过其元数据的无效的测试环境。 元数据的影响的测试环境的示例包括[RunAs](runas.md)， [ThreadingModel](threading-models.md)，并[ActivationContext](activation-context.md)。 |

 

 

 




