---
title: CMFCVisualManagerVS2005 类 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7282730779360ecc0bb93f0ae827b46ddff19d0
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038056"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005 类
`CMFCVisualManagerVS2005` 向应用程序提供 Microsoft Visual Studio 2005 外观。  
  
## <a name="syntax"></a>语法  
  
```  
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](#getdockingtabsborderssize)|绘制，可停靠选项卡式窗格中时，框架将调用此方法。 (重写[CMFCVisualManager::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize)。)|  
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](#getmditabsborderssize)|框架调用此方法之前，它可绘制窗口确定 MDITabs 窗口的边框大小。 (重写[CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)。)|  
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|(重写[CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor)。)|  
|[CMFCVisualManagerVS2005::GetTabFrameColors](#gettabframecolors)|(重写[CMFCVisualManagerOffice2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors)。)|  
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|返回自动隐藏按钮是否在当前视觉管理器中重叠。 (重写[CMFCVisualManager::HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons)。)|  
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|(重写[CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder)。)|  
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](#ondrawcaptionbutton)|（重写 `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`。）|  
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](#ondrawpanecaption)|(重写[CMFCVisualManagerOffice2003::OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption)。)|  
|[CMFCVisualManagerVS2005::OnDrawSeparator](#ondrawseparator)|(重写[CMFCVisualManagerOffice2003::OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator)。)|  
|[CMFCVisualManagerVS2005::OnDrawTab](#ondrawtab)|(重写[CMFCVisualManagerOffice2003::OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab)。)|  
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](#ondrawtoolboxframe)|(重写[CMFCVisualManager::OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe)。)|  
|[CMFCVisualManagerVS2005::OnEraseTabsArea](#onerasetabsarea)|(重写[CMFCVisualManagerOffice2003::OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea)。)|  
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|(重写[CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground)。)|  
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](#onfillhighlightedarea)|(重写[CMFCVisualManagerOffice2003::OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea)。)|  
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](#onfillminiframecaption)|（重写 `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`。）|  
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](#onupdatesystemcolors)|(重写[CMFCVisualManagerOffice2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors)。)|  
  
## <a name="remarks"></a>备注  
 CMFCVisualManagerVS2005 类用于更改你的应用程序类似于的可视外观[!INCLUDE[vsprvsext](../../mfc/reference/includes/vsprvsext_md.md)]。  
  
 所有此类的成员都派生自的此类上级的虚函数[CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 visual manager VS 2005。 此代码片段属于[桌面警报演示示例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
 [CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)  
  
## <a name="requirements"></a>要求  
 **标头：** afxvisualmanagervs2005.h  
  
##  <a name="getdockingtabsborderssize"></a>  CMFCVisualManagerVS2005::GetDockingTabsBordersSize  

  
```  
virtual int GetDockingTabsBordersSize();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="getmditabsborderssize"></a>  CMFCVisualManagerVS2005::GetMDITabsBordersSize  

  
```  
virtual int GetMDITabsBordersSize();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="getpropertygridgroupcolor"></a>  CMFCVisualManagerVS2005::GetPropertyGridGroupColor  

  
```  
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>参数  
 [in]*pPropList*  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="gettabframecolors"></a>  CMFCVisualManagerVS2005::GetTabFrameColors  

  
```  
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF& clrDark,  
    COLORREF& clrBlack,  
    COLORREF& clrHighlight,  
    COLORREF& clrFace,  
    COLORREF& clrDarkShadow,  
    COLORREF& clrLight,  
    CBrush*& pbrFace,  
    CBrush*& pbrBlack);
```  
  
### <a name="parameters"></a>参数  
 [in]*pTabWnd*  
 [in]*clrDark*  
 [in]*clrBlack*  
 [in]*clrHighlight*  
 [in]*clrFace*  
 [in]*clrDarkShadow*  
 [in]*clrLight*  
 [in]*pbrFace*  
 [in]*pbrBlack*  
  
### <a name="remarks"></a>备注  
  
##  <a name="hasoverlappedautohidebuttons"></a>  CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons  

  
```  
virtual BOOL HasOverlappedAutoHideButtons() const;  
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawautohidebuttonborder"></a>  CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder  

  
```  
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rectBounds*  
 [in]*rectBorderSize*  
 [in]*pButton*  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawcaptionbutton"></a>  CMFCVisualManagerVS2005::OnDrawCaptionButton  

  
```  
virtual void OnDrawCaptionButton(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*pButton*  
 [in]*bActive*  
 [in]*bHorz*  
 [in]*bMaximized*  
 [in]*bDisabled*  
 [in]*nImageID*  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawpanecaption"></a>  CMFCVisualManagerVS2005::OnDrawPaneCaption  

  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*pBar*  
 [in]*bActive*  
 [in]*rectCaption*  
 [in]*rectButtons*  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawseparator"></a>  CMFCVisualManagerVS2005::OnDrawSeparator  

  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*pBar*  
 [in]*rect*  
 [in]*bIsHoriz*  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawtab"></a>  CMFCVisualManagerVS2005::OnDrawTab  

  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rectTab*  
 [in]*iTab*  
 [in]*bIsActive*  
 [in]*pTabWnd*  
  
### <a name="remarks"></a>备注  
  
##  <a name="ondrawtoolboxframe"></a>  CMFCVisualManagerVS2005::OnDrawToolBoxFrame  

  
```  
virtual void OnDrawToolBoxFrame(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rect*  
  
### <a name="remarks"></a>备注  
  
##  <a name="onerasetabsarea"></a>  CMFCVisualManagerVS2005::OnEraseTabsArea  

  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rect*  
 [in]*pTabWnd*  
  
### <a name="remarks"></a>备注  
  
##  <a name="onfillautohidebuttonbackground"></a>  CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground  

  
```  
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,  
    CRect rect,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rect*  
 [in]*pButton*  
  
### <a name="remarks"></a>备注  
  
##  <a name="onfillhighlightedarea"></a>  CMFCVisualManagerVS2005::OnFillHighlightedArea  

  
```  
virtual void OnFillHighlightedArea(
    CDC* pDC,  
    CRect rect,  
    CBrush* pBrush,  
    CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rect*  
 [in]*pBrush*  
 [in]*pButton*  
  
### <a name="remarks"></a>备注  
  
##  <a name="onfillminiframecaption"></a>  CMFCVisualManagerVS2005::OnFillMiniFrameCaption  

  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDC*  
 [in]*rectCaption*  
 [in]*pFrameWnd*  
 [in]*bActive*  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="onupdatesystemcolors"></a>  CMFCVisualManagerVS2005::OnUpdateSystemColors  

  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [类](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP 类](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows 类](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManagerOffice2003 类](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)