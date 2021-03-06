---
title: 将接口添加到你的提供商 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d6bc5d1b6c47d2ffa26bffa98d47b930d6ed193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093541"
---
# <a name="adding-an-interface-to-your-provider"></a>将接口添加到提供程序
确定你想要将接口添加到 （通常数据源、 行集、 命令或会话对象由 OLE DB 提供程序向导创建） 的对象。 很有可能需要添加到接口的对象是指你的提供商目前不支持。 在这种情况下，运行 ATL OLE DB 提供程序向导来创建对象。 右键单击类视图中的项目，单击**添加类**从**添加**菜单，，然后单击**ATL OLE DB 访问接口**。 你可能想要将接口代码放在一个单独的目录，然后将文件复制到你的提供程序项目。  
  
 如果你创建新的类，以支持该接口，请从类中继承的对象。 例如，可能会将类添加**IRowsetIndexImpl**与行集的对象：  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
 添加到接口**COM_MAP**使用 COM_INTERFACE_ENTRY 宏的对象中。 如果没有任何映射，创建一个。 例如：  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 行集对象链的映射的其父对象，以便对象可以委托给的父类。 在此示例中，将添加到映射的 COM_INTERFACE_ENTRY_CHAIN 宏：  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 OLE DB 提供程序模板](../../data/oledb/working-with-ole-db-provider-templates.md)