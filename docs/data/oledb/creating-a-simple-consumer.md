---
title: 创建简单使用者 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9f7c5a51765e2ce29df503aeefa9f850b71b1d4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339849"
---
# <a name="creating-a-simple-consumer"></a>创建简单使用者
使用 ATL 项目向导和 ATL OLE DB 使用者向导生成的 OLE DB 模板使用者。  
  
### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>若要为 OLE DB 使用者创建一个控制台应用程序  
  
1.  在 **“文件”** 菜单上，单击 **“新建”**，然后单击 **“项目”**。  
  
     此时将出现 “新建项目” 对话框。  
  
2.  在项目类型窗格中，单击**Visual c + + 项目**文件夹，，然后单击**Win32 项目**模板窗格中的图标。 在中**名称**框中，例如，输入你的项目名称**MyCons**。  
  
3.  单击 **“确定”**。  
  
     Win32 项目向导出现。  
  
4.  上**应用程序设置**页上，选择**控制台应用程序**，然后选择**添加对 ATL 的支持**。  
  
5.  单击**完成**若要关闭向导并生成该项目。  
  
 接下来，使用 ATL OLE DB 使用者向导添加 OLE DB 使用者对象。  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>若要创建使用者使用 ATL OLE DB 使用者向导  
  
1.  在类视图中，右键单击`MyCons`项目。  
  
2.  在快捷菜单上，单击**外**，然后单击**添加类**。  
  
     **添加类**对话框随即出现。  
  
3.  在类别窗格中，单击**Visual c + +**，单击**ATL OLE DB 使用者**图标在模板窗格中，然后单击**打开**。  
  
     将出现 ATL OLE DB 使用者向导。  
  
4.  单击**数据源**按钮。  
  
     **数据链接属性**对话框随即出现。  
  
5.  在中**数据链接属性**对话框框中，执行以下操作：  
  
    -   上**提供程序**选项卡上，指定 OLE DB 访问接口。  
  
    -   上**连接**选项卡上，在服务器上指定服务器名称、 登录 ID 和你的数据源和数据库的密码。  
  
    > [!NOTE]
    >  安全问题**允许保存密码**的功能**数据链接属性**对话框。 在中**输入信息以登录到服务器上**，有两个单选按钮：**使用 Windows NT 集成安全性**并**使用特定用户名和密码**。  
  
    > [!NOTE]
    >  如果选择**使用特定用户名和密码**，可以选择保存密码 (使用**允许保存密码**复选框); 但是，此选项是不安全。 我们建议您选择**使用 Windows NT 集成安全性**; 此选项使用 Windows NT 身份验证。  
  
    > [!NOTE]
    >  如果无法使用 Windows NT 集成安全性，应使用的中间层应用程序提示用户输入密码或者与安全机制来帮助保护其将密码存储在一个位置 (而不是在源代码中)。  
  
     选择您的提供程序和其他设置后，单击**测试连接**验证在前面的对话框页上所做的选择。 如果**结果**框报表`Test connection succeeded`，单击**确定**若要创建数据链接。  
  
     **选择数据库对象**对话框随即出现。  
  
6.  使用树控件选择表、 视图或存储的过程。 在此过程中，从 Northwind 数据库中选择产品表。  
  
7.  单击 **“确定”**。 此操作将返回到 ATL OLE DB 使用者向导。  
  
8.  在向导完成的名称`Class`并 **.h 文件**基于名称的表、 视图或存储所选的过程。 如果需要，可以编辑这些名称。  
  
9. 清除**特性化**复选框，以便该向导将创建使用者代码使用[OLE DB 模板类](../../data/oledb/ole-db-consumer-templates-reference.md)而不是默认[OLE DB 使用者特性](../../windows/ole-db-consumer-attributes.md)。  
  
10. 下**类型**，选择**命令**。  
  
     该向导将创建[CCommand](../../data/oledb/ccommand-class.md)-如果选择基于使用者**命令**或[CTable](../../data/oledb/ctable-class.md)-如果选择基于使用者**表**。 表或命令类命名所选对象，但您可以编辑该名称。  
  
11. 下**支持**，将保留**更改**，**插入**，以及**删除**框被清除。  
  
     选择**更改**，**插入**，并**删除**复选框，以根据需要支持更改、 插入和删除的行集中的记录。 详细了解数据写入数据存储，请参阅[更新行集](../../data/oledb/updating-rowsets.md)。  
  
12. 单击**完成**若要创建使用者。  
  
 该向导生成命令类和用户记录类，如中所示[使用者向导生成的类](../../data/oledb/consumer-wizard-generated-classes.md)。 命令类将具有你在中输入的名称`Class`向导中框 (在这种情况下， `CProducts`)，用户记录类将具有窗体的名称"*ClassName*访问器"(在这种情况下， `CProductsAccessor`)。  
  
> [!NOTE]
>  该向导将放入 Products.h 的以下行：  
  
```cpp  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  此行会阻止使用者应用程序进行编译，并提醒您检查您的连接字符串的硬编码的密码。 在检查你的连接字符串之后, 可以删除这行代码。  
  
## <a name="see-also"></a>请参阅  
 [使用向导创建 OLE DB 使用者](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)