---
title: OID_CO_DELETE_ADDRESS
description: 本主题介绍) OID_CO_DELETE_ADDRESS 对象标识符 (OID。
keywords:
- OID_CO_DELETE_ADDRESS
ms.date: 11/03/2017
ms.localizationpriority: medium
ms.openlocfilehash: 2ac87da350aeec5354ef8aa2fca9abbb787950d8
ms.sourcegitcommit: 418e6617e2a695c9cb4b37b5b60e264760858acd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96839997"
---
# <a name="oid_co_delete_address"></a>OID_CO_DELETE_ADDRESS

OID_CO_DELETE_ADDRESS OID 由客户端发送到呼叫管理器，以删除主机的别名地址。 别名地址的格式为 CO_ADDRESS 结构，定义如下：

```c++
typedef struct _CO_ADDRESS {
    ULONG   AddressSize;
    UCHAR   Address[1];
} CO_ADDRESS, *PCO_ADDRESS; 
```

此结构的成员包含以下信息：

**AddressSize**  
指定地址处的结构的大小（以字节为单位）。

**Address**  
指定包含别名地址的可变长度数组。 地址格式特定于呼叫管理器使用的信号协议。

## <a name="requirements"></a>要求

**版本**： Windows Vista 和更高版本的 **标头**： Ntddndis (包括 Ndis .h) 

