---
title: Microsoft OS 2.0 描述符规范
description: Microsoft OS 2.0 描述符规范
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1ade884b5cb1eeaf95590c1454f74824e3a39d93
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96816457"
---
# <a name="microsoft-os-20-descriptors-specification"></a>Microsoft OS 2.0 描述符规范

本文档定义并说明 Microsoft OS 描述符版本2.0 的实现。 Microsoft 操作系统2.0 描述符的目标是解决操作系统描述符版本1.0 的限制和可靠性问题，并为 USB 设备启用特定于 Windows 的新功能。

此信息适用于以下操作系统：

  - Windows 10
  - Windows 8.1 预览版

**继续之前，请阅读许可协议。**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="text-align: center;"><strong><br />
Microsoft OS 描述符规范</strong><br />
</td>
</tr>
<tr class="even">
<td style="text-align: center;"><div style="font-size: 100%; border: thin inset; height: 400px; overflow: scroll; text-align: left; padding: 10px; background-color: white;">
<h3 id="microsoft-os-descriptor-specification-license-agreement">Microsoft 操作系统描述符规范许可协议</h3>
<p>这是一种法律协议， ( "协议" ) ， (个人或单个实体)  ( "你的" ) ，Microsoft Corporation ( "Microsoft" 规范 ) 。  下载、复制或以其他方式使用规范即表示您同意遵守本协议的条款。   </p>
<p><strong>第1部分定义。</strong></p>
<p> () "您的实现" 意味着您的： () 实现规范中所述的操作系统描述符集的固件和/或硬件，以与支持 Microsoft 操作系统描述符的操作系统或 Microsoft 授权的其他系统一起使用来检索和使用此信息;和 (ii) 软件驱动程序，该规范中所述的操作系统描述符集仅与 Windows 8.1 结合。</p>
<p> (b) "你的被授权者" 是指授权你使用你的实现的第三方。</p>
<p> (c) "规范" 表示 Microsoft 的操作系统描述符规范和任何随附的资料。</p>
<p>第<strong>2 节授予许可证</strong>。</p>
<p> ()    <strong>版权许可证</strong>。  Microsoft 特此授予你，该规范中的 Microsoft 的版权规定是一种非专用的、免版税、nontransferable、非 sublicensable 的个人全球许可证，可在内部为你和你的组织在开发实现中使用的技术副本提供副本。</p>
<p> (b)   <strong>专利许可证</strong>。  Microsoft 特此授予您在 Microsoft 的专利范围内的非专用、免版税、nontransferable、全球许可，这些专利仅在规范内提供，由 Microsoft 拥有或许可，可直接或间接地销售和分发到您的实现。  你可以根据相同的条款和条件将此专利许可证发放给你的许可证。</p>
<p> (c)    <strong>权限预留</strong>。  Microsoft 保留了该规范中的所有其他权利、其实现以及其中的任何知识产权。  对于任何其他 Microsoft 专利、商标、版权或其他知识产权，本文档不向您或任何其他实体授予任何许可。 </p>
<p><strong>第3部分：其他限制和义务</strong>。</p>
<p> (a) 你对规范的许可权限在你不创建、按照此类创建、修改或分发方式修改或分发你的许可实现，可以 () 创建或声称为 Microsoft 创建的义务，或与) 或 (b) grant 或声称向任何第三方 (授予的任何权利或 immunities，或向任何第三方授予对该规范中的任何权利或。</p>
<p> (b) 不损害任何其他权利，如果你未能遵守本协议的条款和条件，则 Microsoft 可能会终止本协议。 在这种情况中，必须销毁规范的所有副本，并且不得进一步分发公司实现。</p>
<p><strong>第4节免责声明。</strong></p>
<p>该规范 "按原样" 提供，不提供任何形式的保证。 在适用法律允许的最大范围内，Microsoft 会进一步拒绝所有担保，包括但不限于针对特定用途的适销性和适用性的任何默示保证，以及对标题和非侵害性的保证。 与规范的使用或性能引起的全部风险仍随你一起提供。</p>
<p><strong>第5部分：排除偶然、间接和某些其他损害。</strong></p>
<p><strong>对于适用法律允许的最大范围，在任何情况下，Microsoft 或其供应商对任何必然的都不承担责任，附带的、直接、间接、特殊、惩罚性或其他损害 (包括但不限于业务利润损失、业务中断、业务信息丢失或其他 pecuniary 损失) 因使用或不能使用该规范而产生的损失，即使 Microsoft 已被告知此类损失的可能性。由于某些州/管辖权不允许对间接或偶然损害的责任进行排除或限制，因此上述限制可能不适用于您。</strong></p>
<p><strong>第6节限制责任和补偿。</strong></p>
<p><strong>无论出于何种原因（包括但不限于以上所述的所有损害和所有直接或常规损失) ，你可能会出于任何 (原因而产生的任何损害，Microsoft 及其所有供应商在对本协议的任何规定和你的所有供应商提供的所有责任都将限制为你为该规范或美国 $ 5.00 实际支付的金额的更大值。上述限制、排除项和免责声明应该适用于适用法律允许的最大范围，即使任何补救措施未能满足其基本目的。</strong></p>
<p>第<strong>7 部分适用的法律</strong>。</p>
<p>如果在美国中获得此规范，则本协议受华盛顿州法律的管辖。 根据本协议中可能出现的任何争议，你同意位于华盛顿州金县的州和联邦法院。</p>
<p><strong>第8节赋值。</strong></p>
<p>如果没有参与方事先书面批准，任何一方都不能分配此协议。</p>
</div>
<p><br />
<a href="https://download.microsoft.com/download/3/5/6/3563ED4A-F318-4B66-A181-AB1D8F6FD42D/MS_OS_2_0_desc.docx">我接受，下载</a></p></td>
</tr>
</tbody>
</table>
