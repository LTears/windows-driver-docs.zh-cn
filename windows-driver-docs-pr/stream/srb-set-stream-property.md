---
title: SRB \_ 设置 \_ 流 \_ 属性
description: SRB \_ 设置 \_ 流 \_ 属性
keywords:
- SRB_SET_STREAM_PROPERTY 流媒体设备
topic_type:
- apiref
api_name:
- SRB_SET_STREAM_PROPERTY
api_type:
- NA
ms.date: 11/28/2017
ms.localizationpriority: medium
ms.openlocfilehash: 575ae0e3cb6bbf646aa461ef07ec395ca86bf281
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96824895"
---
# <a name="srb_set_stream_property"></a>SRB \_ 设置 \_ 流 \_ 属性


## <span id="ddk_srb_set_stream_property_ks"></span><span id="DDK_SRB_SET_STREAM_PROPERTY_KS"></span>


类驱动程序将发送此请求，以便在微型驱动程序中查询针对此流的微型驱动程序定义的属性完成属性集请求所需的数据。

### <a name="span-idreturn_valuespanspan-idreturn_valuespanreturn-value"></a><span id="return_value"></span><span id="RETURN_VALUE"></span>返回值

微型驱动程序应将以下内容之一设置为 SRB 中的状态：

<span id="STATUS_SUCCESS"></span><span id="status_success"></span>状态 \_ 成功  
指示命令成功完成。

<span id="STATUS_NOT_IMPLEMENTED"></span><span id="status_not_implemented"></span>状态 \_ 未 \_ 实现  
指示微型驱动程序不支持该函数。

<span id="STATUS_IO_DEVICE_ERROR"></span><span id="status_io_device_error"></span>状态 \_ IO \_ 设备 \_ 错误  
指示出现硬件故障。

### <a name="comments"></a>注释

类驱动程序将操作的参数传递到 *pSrb* - &gt; **CommandData** 中。**PropertyInfo** buffer，形式为 [**流 \_ 属性 \_ 描述符**](/windows-hardware/drivers/ddi/strmini/ns-strmini-_stream_property_descriptor)的结构。 *PSrb* 指针指向 [**HW \_ 流 \_ 请求 \_ 块**](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block)结构。

流属性描述符的 **属性** 成员 \_ 描述了 \_ 有问题的属性，而 **PropertyInfo** 成员指定了要从中复制属性数据的缓冲区。 如果缓冲区太小，则微型驱动程序应将 *pSrb* 指向的 **状态** 成员设置为状态 \_ 缓冲区 \_ 溢出。

## <a name="see-also"></a>请参阅


[**SRB \_ 获取 \_ 流 \_ 属性**](srb-get-stream-property.md)

[**流 \_ 属性 \_ 描述符**](/windows-hardware/drivers/ddi/strmini/ns-strmini-_stream_property_descriptor)

 

