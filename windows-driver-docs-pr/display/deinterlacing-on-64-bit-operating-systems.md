---
title: 在 64 位操作系统上去隔行
description: 在 64 位操作系统上去隔行
ms.assetid: ffac0c1a-2c92-4beb-9622-26d10e1a06aa
keywords:
- 取消隔行扫描 WDK DirectX VA，64年位
- 64 位 WDK DirectX VA
ms.date: 04/20/2017
ms.localizationpriority: medium
ms.openlocfilehash: 60ac6369578520237a9695065d6e84b5b250dd4e
ms.sourcegitcommit: a33b7978e22d5bb9f65ca7056f955319049a2e4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "56555537"
---
# <a name="deinterlacing-on-64-bit-operating-systems"></a>在 64 位操作系统上去隔行


为了确保由 32 位应用程序启动的取消隔行扫描操作已成功上运行 64 位操作系统，显示器驱动程序代码必须首先检测到应用程序是 32 位或 64 位。 若要执行检测，该驱动程序应检查**大小**的成员[ **DXVA\_DeinterlaceBlt** ](https://msdn.microsoft.com/library/windows/hardware/ff563912)应用程序传递的结构。 DXVA 的 32 位版本的大小\_DeinterlaceBlt 小于 32 位和 64 位之间的指针大小差异由于 64 位版本的大小。 如果该驱动程序确定起始应用程序是 32 位，该驱动程序应处理取消隔行扫描操作的形式转换。 有关形式转换的详细信息，请参阅[在 64 位驱动程序中支持 32 位 I/O](https://msdn.microsoft.com/library/windows/hardware/ff563897)。

下面的代码示例演示了该驱动程序应如何处理转换 （thunk）：

```cpp
switch (lpData->dwFunction) {
case DXVA_DeinterlaceBltFnCode:
    {   
        DXVA_DeinterlaceBlt* pBlt = (DXVA_DeinterlaceBlt*)lpData->lpInputData; 
         if (pBlt->Size == sizeof(DXVA_DeinterlaceBlt)) {
            // correctly formed 64-bit or 32-bit structure, so use it
        }
#ifdef _WIN64
        else if (pBlt->Size < sizeof(DXVA_DeinterlaceBlt)) {
            // 32-bit structure, so thunk it!
        }
#endif
        else {
            // unknown structure, so return error;
        }
    }
```

 

 




