---
title: 'Roinitializewrapper:: Roinitializewrapper 构造函数 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 193f0d16b03991e24cb16a90b3310512f6e86054
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604386"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper 构造函数
初始化的新实例**RoInitializeWrapper**类。  
  
## <a name="syntax"></a>语法  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
### <a name="parameters"></a>参数  
 *flags*  
 RO_INIT_TYPE 枚举，指定 Windows 运行时提供的支持之一。  
  
## <a name="remarks"></a>备注  
 **RoInitializeWrapper**类调用`Windows::Foundation::Initialize(flags)`。  
  
## <a name="requirements"></a>要求  
 **标头：** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>请参阅  
 [HandleT 类](../windows/handlet-class.md)