---
title: 双 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dual
dev_langs:
- C++
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60a4326975f60455e6d2ef90575f5c940287042a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644107"
---
# <a name="dual"></a>dual
双重接口.idl 文件中放置一个接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
[dual]  
```  
  
## <a name="remarks"></a>备注  
 当**双**c + + 属性优先于接口时，会导致将接口置于生成的.idl 文件中的库块。  
  
## <a name="example"></a>示例  
 下面的代码是使用特性块**双**接口定义的前面：  
  
```cpp  
// cpp_attr_ref_dual.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]  
  
__interface IStatic : IDispatch   
{  
   HRESULT Func1(int i);  
   [   propget,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([out, retval] long *nSize);  
   [   propput,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([in] long nSize);      
};  
  
[cpp_quote("#include file.h")];  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**interface**|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|`dispinterface`|  
  
 有关详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDL 特性](../windows/idl-attributes.md)   
 [按使用情况的特性](../windows/attributes-by-usage.md)   
 [自定义](../windows/custom-cpp.md)   
 [调度接口](../windows/dispinterface.md)   
 [对象](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   