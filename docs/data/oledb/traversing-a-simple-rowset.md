---
title: 遍历简单行集合 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], rowsets
- rowsets [C++], accessing
- simple rowsets
- OLE DB consumers [C++], database attributes
- accessors [C++], rowsets
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6ba5262577fc9176669916a7fc30d299d06770a8
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336649"
---
# <a name="traversing-a-simple-rowset"></a>遍历简单行集合
下面的示例演示不涉及命令的快速而简便的数据库访问。 以下使用者代码，在 ATL 项目中，从名为的表中检索记录*艺术家*Microsoft Access 数据库使用 Microsoft OLE DB Provider for ODBC。 该代码会创建[CTable](../../data/oledb/ctable-class.md)取值函数的表对象基于用户记录类`CArtists`。 打开的连接、 打开该连接上的会话，并在会话中打开表。  
  
```cpp  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists>> artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL, DBPROP_AUTH_INTEGRATED);  

session.Open(connection);  

artists.Open(session, "Artists");  
  
// Get data from the rowset  
while (artists.MoveNext() == S_OK)  
{  
   cout << artists.m_szFirstName;  
   cout << artists.m_szLastName;  
}  
```  
  
 用户记录`CArtists`，如下所示：  
  
```cpp  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 OLE DB 使用者模板](../../data/oledb/working-with-ole-db-consumer-templates.md)