---
title: 编译器错误 C3490 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 593e5509ada926f27243a761da3470eb2d846a22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258745"
---
# <a name="compiler-error-c3490"></a>编译器错误 C3490
无法修改 var，因为正在通过 const 对象对其进行访问  
  
 在 `const` 方法中声明的 lambda 表达式不能修改不可变成员数据。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   从方法声明删除 `const` 修饰符。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3490，因为它修改 `_i` 方法中的成员变量 `const` ：  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>示例  
 下面的示例通过从方法声明删除 `const` 修饰符解决了错误 C3490：  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>请参阅  
 [Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)