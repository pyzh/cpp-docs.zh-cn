---
title: 事务 （MFC 数据访问） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9dd531aee6ac8014f2ce47ddee7fc5f82e35a63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107813"
---
# <a name="transactions--mfc-data-access"></a>事务（MFC 数据访问）
已开发出事务的概念以便根据一系列成功操作处理数据库结果状态的情况。 由于连续性操作可能修改先前操作的结果，因此可能会出现这种情况。 在这种情况下，如果任何一个操作失败，结果状态就有可能不确定。  
  
 要解决此问题，事务可以按以下这种方式对一系列操作进行分组，即以可以确定最后结果的完整性的这种方式分组。 所有操作必须成功，然后提交（写入到数据库），否则整个事务失败。 取消事务被称为回滚。 回滚允许恢复所做的更改，将数据库返回到事务前状态。  
  
 例如，在自动化银行事务中，如果将资金从帐户 A 转移到帐户 B，则从 A 取款和存入 B 的操作都必须成功以便正确处理款项，否则整个事务必须失败。  
  
 事务必须具有 ACID 属性，代表以下涵义：  
  
-   **原子性**事务工作的原子单位执行一次; 所有工作都完成或没有。  
  
-   **一致性**事务保持数据一致性，将数据的一个一致性状态转换成的数据的另一个一致状态。 必须在语义上保留事务绑定的数据。  
  
-   **隔离**事务是一个隔离单元，每个单独发生，独立于并发事务。 一个事务绝不可能看到另一个事务的中间阶段。  
  
-   **持续性**事务是一个恢复单元。 如果一个事务成功，它就会持续更新，即使该系统崩溃或已关闭。 如果事务失败，系统仍然处于之前提交事务的状态。  
  
 你可以在 OLE DB 中支持事务 (请参阅[支持 OLE DB 中的事务](../data/oledb/supporting-transactions-in-ole-db.md)) 或 ODBC (请参阅[事务 (ODBC)](../data/odbc/transaction-odbc.md))。  
  
 分布式事务是指更新分布式数据的事务，即多个连网计算机系统上的数据。 如果你想要支持分布式系统上的事务，则应使用 ADO.NET 而不是 OLE DB 事务支持。  
  
## <a name="see-also"></a>请参阅  
 [数据访问编程 (MFC/ATL)](../data/data-access-programming-mfc-atl.md)