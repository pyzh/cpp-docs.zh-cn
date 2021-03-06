---
title: 'Makeallocator:: Allocate 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 06f8db4c713feb69e0037d10879383411ea07007
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606258"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate 方法
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，指向已分配的内存中;否则为**nullptr**。  
  
## <a name="remarks"></a>备注  
 分配内存，并将其与当前相关联**MakeAllocator**对象。  
  
 已分配内存的大小是由当前指定的类型的大小**MakeAllocator**模板参数。  
  
 开发人员需要仅重写**Allocate()** 方法来实现不同的内存分配模型。  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [MakeAllocator 类](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)