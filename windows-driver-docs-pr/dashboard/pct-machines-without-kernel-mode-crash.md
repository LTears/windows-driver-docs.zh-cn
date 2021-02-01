---
title: 遇到内核模式崩溃的计算机所占的百分比
description: 该度量将 7 天滑动窗口中的遥测数据进行聚合并形成经历了内核模式崩溃的计算机所占的百分比
ms.topic: article
ms.date: 05/29/2020
ms.localizationpriority: medium
ms.openlocfilehash: 7f8dd9090ea096f41bb894f61629c44dc43088f7
ms.sourcegitcommit: 5e51e63585f35597cf06fc0ab5c0cc7cb39ca22a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "98861863"
---
# <a name="percent-of-machines-without-a-kernel-mode-crash"></a>没有内核模式崩溃的计算机所占的百分比

## <a name="description"></a>说明

内核模式崩溃 (KMC) 由停止操作系统的内核错误导致。 如果用户遇到 KMC，其计算机会突然崩溃，并显示蓝屏。 此类崩溃可能会导致用户工作流中断，并且导致数据丢失。

## <a name="measure-attributes"></a>度量属性

|属性|值|
|----|----|
|受众|Standard|
|时间段|7 天滑动窗口|
|度量标准|计算机的聚合|
|最小总体数量|100 台计算机|
|通过标准|<= 1% 的计算机遇到了内核模式崩溃|
|已启用队列|是|
|每队列最小总体数量|500 台计算机|
|度量 ID|26118008|

## <a name="calculation"></a>计算

1. 该度量将 7 天滑动窗口中的遥测数据进行聚合并形成经历了 KMC 的计算机所占的百分比。
2. 崩溃的计算机数 = 计数（安装驱动程序时遇到 KMC 的计算机）
3. 计算机总数 = 计数（已成功安装驱动程序的计算机数）

### <a name="final-calculation"></a>最终计算

未遇到 KMC 的计算机的百分比 = 崩溃的计算机数/计算机总数
