---
title: 编译器错误 C2869 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2869
dev_langs:
- C++
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9aa6092347b224abf02e0d6fac394146094e576
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246247"
---
# <a name="compiler-error-c2869"></a>编译器错误 C2869
name： 已定义为命名空间  
  
 你无法重用已使用与命名空间的名称。  
  
 下面的示例生成 C2869:  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```