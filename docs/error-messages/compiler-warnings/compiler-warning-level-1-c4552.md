---
title: 编译器警告 （等级 1） C4552 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4552
dev_langs:
- C++
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3b58d33286163050db533fed00d27abe8903e9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281123"
---
# <a name="compiler-warning-level-1-c4552"></a>编译器警告（等级 1）C4552
operator： 运算符起任何作用;预期带副作用的运算符  
  
 如果表达式语句作为表达式顶部有一个没有任何副作用的运算符，它可能是一个错误。  
  
 若要覆盖此警告，请将表达式放在括号中。  
  
 下面的示例生成 C4552:  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```