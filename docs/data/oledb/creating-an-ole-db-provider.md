---
title: 创建 OLE DB 提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5de304b7a21c47af18b8b753d6de704ef2473c5f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338787"
---
# <a name="creating-an-ole-db-provider"></a>创建 OLE DB 提供程序
创建 OLE DB 提供程序的建议的方法是使用这些向导创建的 ATL COM 项目和提供程序，然后修改使用 OLE DB 模板的文件。 自定义您的提供程序，你可以注释掉不需要的属性并添加可选接口。  
  
 基本步骤如下：  
  
1.  使用 ATL 项目向导创建基本项目文件和 ATL OLE DB 提供程序向导来创建提供程序 (选择**ATL OLE DB 访问接口**中的 Visual c + + 文件夹从**添加类**)。  
  
2.  修改中的代码`Execute`CMyProviderRS.h 中的方法。 有关示例，请参阅[字符串读入 OLE DB 提供程序](../../data/oledb/reading-strings-into-the-ole-db-provider.md)。  
  
3.  编辑 MyProviderDS.h、 MyProviderSess.h 和 MyProviderRS.h 中的属性映射。 向导将创建包含一个提供程序可能会实现的所有属性的属性映射。 完成属性映射，并删除或注释掉您的提供程序不需要支持的属性。  
  
4.  更新 PROVIDER_COLUMN_MAP，可以找到 MyProviderRS.h 中。 有关示例，请参阅[存储字符串中的 OLE DB 提供程序](../../data/oledb/storing-strings-in-the-ole-db-provider.md)。  
  
5.  当准备好测试你的提供商，可以通过尝试查找提供程序枚举中的提供程序对它进行测试。 枚举中找到提供程序的测试代码的示例，请参阅[CATDB](http://msdn.microsoft.com/003d516b-2bf6-444e-8be5-4ebaa0b66046)并[DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832)示例或中的示例[实现简单使用的者](../../data/oledb/implementing-a-simple-consumer.md)。  
  
6.  添加所需的任何其他接口。 有关示例，请参阅[增强简单的只读提供程序](../../data/oledb/enhancing-the-simple-read-only-provider.md)。  
  
    > [!NOTE]
    >  默认情况下，向导生成是符合 OLE DB 级别 0 的代码。 为确保你的应用程序保持符合级别 0，不要删除任何向导生成的接口从代码。  
  
## <a name="see-also"></a>请参阅  
 [CATDB](http://msdn.microsoft.com/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832)