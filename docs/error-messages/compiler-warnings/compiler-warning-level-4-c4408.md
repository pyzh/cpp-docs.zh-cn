---
title: 编译器警告 （等级 4） C4408 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4408
dev_langs:
- C++
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 640a3de24921186bd441b8f8b9bc5f3dcd7e5810
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297575"
---
# <a name="compiler-warning-level-4-c4408"></a>编译器警告（等级 4）C4408
anonymousstruct 或联合不声明任何数据成员  
  
 匿名结构或联合必须具有至少一个数据成员。  
  
 以下示例生成 C4408：  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```