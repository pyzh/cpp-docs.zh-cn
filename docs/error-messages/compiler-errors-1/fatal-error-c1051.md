---
title: 错误 C1051 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1051
dev_langs:
- C++
helpviewer_keywords:
- C1051
ms.assetid: 87dcbd3b-0952-499a-bd42-64f9e8de2605
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d83d399d8ceba495856045f0502cc0f08c21eb7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198243"
---
# <a name="fatal-error-c1051"></a>错误 C1051
程序数据库文件，pdbfile 具有过时的格式，将其删除并重新编译  
  
 编译器无法更新程序数据库文件的较旧的版本号。 删除文件并重新编译您的程序与 **/Zi**或 **/ZI**。 有关详细信息，请参阅[/Z7、 /Zi、 /ZI （调试信息格式）](../../build/reference/z7-zi-zi-debug-information-format.md)