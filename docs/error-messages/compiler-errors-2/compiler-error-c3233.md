---
title: 编译器错误 C3233 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3233
dev_langs:
- C++
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 619b6d7f0c81dd982a2b87e4c1e02da4356f2af7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254650"
---
# <a name="compiler-error-c3233"></a>编译器错误 C3233
“type”：泛型类型形参已被约束  
  
 在多个 `where` 子句中约束一个泛型参数是无效的。  
  
 下面的示例生成 C3233：  
  
```  
// C3233.cpp  
// compile with: /clr /LD  
  
interface struct C {};  
interface struct D {};  
  
generic <class T>  
where T : C  
where T : D  
ref class E {};   // C3233  
```