---
title: 从 UMDF 调用 WinUSB
description: 从 UMDF 调用 WinUSB
keywords:
- WinUSB WDK UMDF
- WinUSB WDK UMDF，转义 WinUSB
- 用户模式驱动程序 WDK UMDF，转义给 WinUSB
ms.date: 04/20/2017
ms.localizationpriority: medium
ms.openlocfilehash: a5342a44b300c1dfd0cbf1e293b09b6b003b0955
ms.sourcegitcommit: 10fecd036370f5eccb538004c5bec1fdd18c3275
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "98124125"
---
# <a name="calling-winusb-from-umdf"></a>从 UMDF 调用 WinUSB


[!include[UMDF 1 Deprecation](../includes/umdf-1-deprecation.md)]

当驱动程序无法使用 USB 特定的 UMDF 接口执行特定操作时，UMDF 驱动程序可以直接调用 [WinUSB 函数](/previous-versions/windows/hardware/drivers/ff540046(v=vs.85)#winusb) 。 若要调用 WinUSB 函数，驱动程序必须首先通过调用 [**IWDFUsbTargetDevice：： GetWinUsbHandle**](/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle) 或 [**IWDFUsbInterface：： GetWinUsbHandle**](/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getwinusbhandle)获取 WinUSB 接口句柄。 WinUSB 接口句柄用于定义所选配置中的第一个接口。

有关详细信息，请参阅 [如何使用 WinUSB 功能访问 USB 设备](../usbcon/using-winusb-api-to-communicate-with-a-usb-device.md)。

