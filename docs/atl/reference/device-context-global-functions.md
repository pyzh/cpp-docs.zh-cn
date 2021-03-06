---
title: 设备上下文全局函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d45468674d274c5f20b5533d782390cf2a6cec6
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881391"
---
# <a name="device-context-global-functions"></a>设备上下文全局函数
此函数创建给定设备的设备上下文。  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|创建设备上下文。|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
 创建设备上下文中指定的设备[DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)结构。  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>参数  
 *hdc*  
 [in]设备上下文或为 NULL 的现有句柄。  
  
 *ptd*  
 [in]一个指向`DVTARGETDEVICE`结构，其中包含有关目标设备的信息。  
  
### <a name="return-value"></a>返回值  
 返回的句柄中指定的设备的设备上下文`DVTARGETDEVICE`。 如果未不指定任何设备，则返回的句柄的默认显示设备。  
  
### <a name="remarks"></a>备注  
 如果结构为 NULL 并且*hdc*为 NULL，则创建的默认显示设备的设备上下文。  
  
 如果*hdc*不为 NULL 并*ptd*为 NULL，该函数将返回现有*hdc*。  

## <a name="requirements"></a>要求  
 **标头：** atlwin.h  
   
## <a name="see-also"></a>请参阅  
 [函数](../../atl/reference/atl-functions.md)
