---
title: 如何： 将现有 MFC 功能区转换为功能区资源 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2551709652df0e0c65b1b0b6b5085550044e9966
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928992"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>如何：将现有 MFC 功能区转换为功能区资源
功能区资源比手动编码的功能区更直观，且更易于修改和维护。 本主题描述如何将 MFC 项目中手动编码的功能区转换为功能区资源。  
  
 你必须具有的现有 MFC 项目具有使用 MFC 功能区类，例如，代码[CMFCRibbonBar 类](../mfc/reference/cmfcribbonbar-class.md)。  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>将 MFC 功能区转换为功能区资源  
  
1.  在 Visual Studio 中，在现有 MFC 项目中，打开源文件其中`CMFCRibbonBar`初始化对象。 通常，此文件是 mainfrm.cpp。 在功能区的初始化代码之后添加以下代码。  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     保存并关闭文件。  
  
2.  生成并运行 MFC 应用程序，然后在“记事本”中打开 RibbonOutput.txt，并复制其内容。  
  
3.  在 Visual Studio 中，在**项目**菜单上，单击**添加资源**。 在**添加资源**对话框中，选择**功能区**，然后单击**新建**。  
  
     Visual Studio 会创建一个功能区资源并在设计视图中打开它。 功能区资源 ID 是 IDR_RIBBON1，将显示在**资源视图**。 功能区在 ribbon1.mfcribbon-ms XML 文件中定义。  
  
4.  在 Visual Studio 中，打开 ribbon1.mfcribbon-ms，删除其内容，然后粘贴先前复制的 RibbonOutput.txt 的内容。 保存并关闭 ribbon1.mfcribbon-ms。  
  
5.  再次打开在其中初始化 CMFCRibbonBar 对象的源文件（通常是 mainfrm.cpp），然后注释掉现有的功能区代码。 在注释掉的代码之后添加以下代码。  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  生成项目并运行程序。  
  
## <a name="see-also"></a>请参阅  
 [功能区设计器 (MFC)](../mfc/ribbon-designer-mfc.md)

