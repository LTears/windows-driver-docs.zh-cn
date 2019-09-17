---
title: 驱动程序度量属性
description: 用于驱动程序外部测试的度量通常会共享属性，这些属性可进行度量：从遥测数据到聚合过程，再到 Microsoft 评估度量的方式。
ms.topic: article
ms.date: 05/20/2019
ms.author: paslote
author: parkeratmicrosoft
ms.localizationpriority: medium
ms.openlocfilehash: 461f3d4960df662ae70cb612a2ef42c2a414986f
ms.sourcegitcommit: 04da1962e34908adeca54fcf5bbfbaa456efca5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2019
ms.locfileid: "70223987"
---
# <a name="driver-measure-attributes"></a>驱动程序度量属性

Microsoft 的一组度量通常共享其构造和计算逻辑中的属性。 这些属性存在于整个度量工作流：从收集遥测数据到聚合过程，再到 Microsoft 评估度量的方式。
每个度量定义都有“度量属性”部分，其中列出其属性的值  。

## <a name="audience-types"></a>受众类型

Microsoft 将受众定义为一组计算机，它们可下载已进行外部测试、逐渐推出或发布的驱动程序。 这些驱动程序可通过 Windows 更新 (WU) 或第三方下载程序分发到计算机。 受众分 3 种类型：标准受众、扩展受众和生态系统受众    。

### <a name="standard-audience"></a>标准受众

标准受众的度量仅从符合以下特征的计算机收集遥测数据：直接从 WU 接收驱动程序，并且符合提交过程中设置的驱动程序目标约束（如 HWID、CHID、OS 下限和上限）。 

### <a name="expanded-audience"></a>扩展受众

扩展受众的度量从符合以下特征的计算机收集遥测数据：符合驱动程序的目标约束，并且从任意源接收驱动程序，包括第三方下载程序。

### <a name="ecosystem-audience"></a>生态系统受众

生态系统受众的度量将数据收集范围扩展到驱动程序目标约束以外，以减轻采样干扰并提高度量的统计意义。 这些度量从符合以下特征的计算机收集遥测数据：从任意源下载驱动程序，包括下载同一版本驱动程序的非目标计算机。 

当一个驱动程序与另一驱动程序具有相同的驱动程序 INF 版本、驱动程序 INF 日期和体系结构时，则视为它们相同。 

## <a name="time-period"></a>时间段

聚合遥测数据时，大多数度量从 7 天滑动窗口收集数据；驱动程序处于外部测试状态的时间不足 7 天时，滑动窗口的范围将缩小为外部测试的持续时间。 通过将数据范围限制为 7 天，Microsoft 可以说明工作日和周末之间的计算机使用情况差异。

此外，查看多个度量后，Microsoft 就能知道在同一时间段内所发生的故障。  

## <a name="measurement-criteria---machine-count-and-instance-count"></a>度量标准 - 计算机计数和实例计数

度量可确定出现错误的不同计算机所占的百分比，或者可聚合观察到的所有错误实例，其中一台计算机可具有多个在外部测试中进行计数的实例。

用于计算计算机百分比的度量通常可监视二进制结果。 例如，“成功完成驱动程序安装过程的计算机所占的百分比”度量可确定驱动程序是否完成安装且未出错，并计算成功安装驱动程序的计算机所占的百分比  。

与此相反，用于评估实例的度量可监视一个用例的多个返回结果。 例如，“相机预览故障率”度量监视与预览功能使用相关的多个相机事件  。 该度量确定在预览过程中计算机遇到错误的频率和阶段，并计算该功能的平均故障率。

## <a name="minimum-population-and-minimum-instances"></a>最小总体数量和最小实例数

每个度量都有一个名为“最小总体数量”或“最小实例数”的属性，用于定义度量的计算逻辑具有统计意义所需的最小计数   。 如果度量没有足够的数据，则驱动程序的外部测试状态显示“数据不足”  。

用于评估预期行为中异常的度量（例如，“以意外的断开连接结束的 Wi-fi 会话的百分比”）需要更大的最小总体数量才能提供质量评估  。

## <a name="passing-criteria"></a>通过标准

度量的通过标准是驱动程序要通过 Microsoft 批准所必须达到的最低质量标准  。 此值通过度量的“当前值”进行评估，在度量使用其计算逻辑处理遥测数据时计算得出。

如果所有应用的度量都超过了其通过标准，则 Microsoft 会将驱动程序视为高质量。

## <a name="measure-id"></a>度量 ID

度量的 ID 是唯一标识符，由 Microsoft 用于在与外部合作伙伴讨论驱动程序决策时简化评估评论中的通信。