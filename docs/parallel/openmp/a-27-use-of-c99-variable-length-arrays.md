---
title: A.27 利用 C99 可变长度数组 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96391aa7403a54160cb6ab83b9b28c1527a3e353
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690086"
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27   使用 C99 变长数组
下面的示例演示如何使用 C99 变量长度数组 (VLAs) 中`firstprivate`指令 ([部分 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md)页 26 上)。  
  
> [!NOTE]
>  在 Visual c + + 中当前不支持可变长度数组。  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```