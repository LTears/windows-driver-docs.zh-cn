---
title: FSCTL_DUPLICATE_EXTENTS_TO_FILE_EX 控制代码
description: 将 FSCTL \_ 复制 \_ \_ 到文件的范围 \_ \_ （如控制代码）指示文件系统代表应用程序复制一系列文件字节。 目标文件可能与源文件相同，或与源文件不同。
keywords:
- FSCTL_DUPLICATE_EXTENTS_TO_FILE_EX 控制代码可安装的文件系统驱动程序
topic_type:
- apiref
api_name:
- FSCTL_DUPLICATE_EXTENTS_TO_FILE_EX
api_location:
- WinIoctl.h
- Ntifs.h
api_type:
- HeaderDef
ms.date: 11/28/2017
ms.localizationpriority: medium
ms.openlocfilehash: 34a71e4e4db32fd43628d99526c0477de94ac57d
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96808411"
---
# <a name="fsctl_duplicate_extents_to_file_ex-control-code"></a>\_将重复 \_ 区 FSCTL \_ 到 \_ 文件 \_ EX 控制代码


将 [**FSCTL \_ 复制 \_ 到文件的范围（ \_ \_ \_ 如**](fsctl-duplicate-extents-to-file-ex.md) 控制代码）指示文件系统代表应用程序复制一系列文件字节。 目标文件可能与源文件相同，或与源文件不同。

若要执行此操作，请调用具有以下参数的 [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 函数。

```ManagedCPlusPlus
BOOL 
   WINAPI 
   DeviceIoControl( (HANDLE)       hDevice,         // handle to device
                    (DWORD)        FSCTL_DUPLICATE_EXTENTS_TO_FILE_EX, // dwIoControlCode
                    (LPDWORD)      lpInBuffer,      // input buffer
                    (DWORD)        nInBufferSize,   // size of input buffer
                    (LPDWORD)      lpOutBuffer,     // output buffer
                    (DWORD)        nOutBufferSize,  // size of output buffer
                    (LPDWORD)      lpBytesReturned, // number of bytes returned
                    (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure
```

<a name="parameters"></a>参数
----------

*hDevice* \[中\]  
设备的句柄。 若要获取设备句柄，请调用 [**CreateFile**](/windows/win32/api/fileapi/nf-fileapi-createfilea) 函数。

*dwIoControlCode* \[中\]  
操作的控制代码。 对于此操作，请使用 [**FSCTL 的 \_ 重复 \_ 区 \_ \_ 文件 \_**](fsctl-duplicate-extents-to-file-ex.md) 。

*lpInBuffer*   
指向 **重复 \_ 区数据的指针 \_ 数据 \_ EX** 结构，它指定源文件、源字节范围以及要将范围复制到的目标文件偏移量。

*nInBufferSize* \[中\]  
输入缓冲区的大小（以字节为单位）。

*lpOutBuffer* \[弄\]  
不与此操作一起使用。 设置为 NULL。

*nOutBufferSize* \[中\]  
不与此操作一起使用。 设置为零 (0) 。

*lpBytesReturned* \[弄\]  
指向一个变量的指针，该变量接收存储在输出缓冲区中的数据的大小（以字节为单位）。

如果输出缓冲区太小，则调用失败， [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 返回 **错误 \_ \_ 缓冲区**，并且 *lpBytesReturned* 为零。

如果 *lpOverlapped* 为 **null**，则 *lpBytesReturned* 不能为 **null**。 即使当操作不返回任何输出数据并且 *lpOutBuffer* 为 **NULL** 时， [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 使用 *lpBytesReturned*。 此类操作完成后， *lpBytesReturned* 的值没有意义。

如果 *lpOverlapped* 不为 **null**，则 *lpBytesReturned* 可以为 **null**。 如果此参数不为 **NULL** ，并且操作返回数据，则在重叠操作完成之前， *lpBytesReturned* 是无意义的。 若要检索返回的字节数，请调用 [**getoverlappedresult 期间**](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult)。 如果 *hDevice* 参数与 i/o 完成端口关联，则可以通过调用 [**GetQueuedCompletionStatus**](/windows/win32/api/ioapiset/nf-ioapiset-getqueuedcompletionstatus)检索返回的字节数。

*lpOverlapped* \[中\]  
指向 [**重叠**](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) 的结构的指针。

如果在未指定 **文件 \_ 标志 \_ 重叠** 的情况下打开 *hDevice* ，则将忽略 *lpOverlapped* 。

如果使用 **FILE \_ 标记 \_ 交叠** 标志打开 *hDevice* ，则操作将作为 (异步) 操作的重叠进行。 在这种情况下， *lpOverlapped* 必须指向包含事件对象句柄的有效 [**重叠**](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) 结构。 否则，函数将会失败。

对于重叠操作， [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 将立即返回，并且在操作完成后会发出事件对象。 否则，在操作完成或发生错误之前，函数不会返回。

<a name="return-value"></a>返回值
------------

如果操作成功完成，则 [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 将返回一个非零值。

如果操作失败或挂起，则 [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 将返回零。 若要获取扩展的错误信息，请调用 [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)。

<a name="remarks"></a>备注
-------

有关此操作上的重叠 i/o 的含义，请参阅 [**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol) 主题的 "备注" 部分。

<a name="requirements"></a>要求
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>标头</p></td>
<td align="left">WinIoctl;Ntifs</td>
</tr>
</tbody>
</table>

## <a name="see-also"></a>请参阅


[**DeviceIoControl**](/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol)

