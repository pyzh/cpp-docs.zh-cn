---
title: ML 错误 A1007 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b883fad01943cd8cff71b3da9dee66407ccc93
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055724"
---
# <a name="ml-fatal-error-a1007"></a>ML 错误 A1007
**嵌套级别太深**  
  
 汇编程序达到其嵌套限制。 限制为除指明外否则 20 级别。  
  
 下列其中一项已嵌套太深：  
  
-   如高级指令[。如果](../../assembler/masm/dot-if.md)， [。重复](../../assembler/masm/dot-repeat.md)，或[。虽然](../../assembler/masm/dot-while.md)。  
  
-   结构定义。  
  
-   一个条件程序集指令。  
  
-   过程定义。  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md)指令 （限制为 10）。  
  
-   段定义。  
  
-   包含文件。  
  
-   宏。  
  
## <a name="see-also"></a>请参阅  
 [ML 错误消息](../../assembler/masm/ml-error-messages.md)