---
title: 编译器警告 （等级 4） C4680 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4680
dev_langs:
- C++
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64c43a1d099d47cbf9b3705bb57c783780aa00aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300129"
---
# <a name="compiler-warning-level-4-c4680"></a>编译器警告（等级 4）C4680
class： 组件类不指定的默认接口。  
  
 A[默认](../../windows/default-cpp.md)类标记为未指定接口[组件类](../../windows/coclass.md)属性。 为了使有用的对象，它必须实现接口。  
  
 下面的示例生成 C4680:  
  
```  
// C4680.cpp  
// compile with: /W4  
#include <windows.h>  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface1  
{  
   HRESULT f1();  
};  
  
[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface2  
{  
   HRESULT f1();  
};  
  
// to resolve C4680, specify a source interface also  
// for example, default(IMyIface1, IMyface2)  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]  
class CMyClass : public IMyIface1  
{   // C4680  
};  
  
int main()  
{  
}  
```