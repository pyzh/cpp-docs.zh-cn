---
title: 工具栏控件样式 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35b5b87944f2b0f9ce78adbe42b59d92b98a6e5a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885830"
---
# <a name="toolbar-control-styles"></a>工具栏控件样式
[CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md)具有一组用于确定外观的样式标志和按钮的行为。 可以通过调用设置这些标志的组合[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)。 本主题列出了样式标志值及其含义。  
  
## <a name="property-values"></a>属性值  
 下列值确定控件表示的按钮的类型：  
  
 TBBS_BUTTON  
 标准按键（默认）。  
  
 TBBS_CHECKBOX  
 复选框  
  
 TBBS_CHECKGROUP  
 复选框组的开始。  
  
 TBBS_GROUP  
 按钮组的开始。  
  
 TBBS_SEPARATOR  
 分隔符。  
  
 下列值表示控件的当前状态：  
  
 TBBS_CHECKED  
 复选框处于选中状态。  
  
 TBBS_DISABLED  
 控件已禁用。  
  
 TBBS_INDETERMINATE  
 复选框处于不确定状态。  
  
 TBBS_PRESSED  
 按钮处于按下状态。  
  
 下列值将更改按钮在工具栏中的布局：  
  
 TBBS_BREAK  
 将项放置在新行或新列上，无需分隔列。  
  
## <a name="remarks"></a>备注  
 当前样式存储在[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)。 未在中设置新值`m_nStyle`直接，因为一些派生的类时执行附加处理调用`SetStyles`。  
  
 视觉管理器将确定按钮在每种状态下的外观。 请参阅[可视化管理器](../../mfc/visualization-manager.md)有关详细信息。  
  
## <a name="requirements"></a>要求  
 **标头：** afxtoolbarbutton.h  
  
## <a name="see-also"></a>请参阅  
 [宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [可视化管理器](../../mfc/visualization-manager.md)


