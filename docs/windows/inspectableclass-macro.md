---
title: InspectableClass 宏 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a02e20f2b87afc312c24683417f808d636c2757f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608951"
---
# <a name="inspectableclass-macro"></a>InspectableClass 宏
设置运行时类名称和信任级别。  
  
## <a name="syntax"></a>语法  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
### <a name="parameters"></a>参数  
 *runtimeClassName*  
 运行时类的完整文本名称。  
  
 *trustLevel*  
 之一[TrustLevel](http://msdn.microsoft.com/library/br224625.aspx)枚举值。  
  
## <a name="remarks"></a>备注  
 **InspectableClass**宏可以仅可用于 Windows 运行时类型。  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [RuntimeClass 类](../windows/runtimeclass-class.md)