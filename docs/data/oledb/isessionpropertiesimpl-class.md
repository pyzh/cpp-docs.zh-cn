---
title: ISessionPropertiesImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5da668814888c11c5aaa0734be5ebc39b943778e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337250"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl 类
提供的实现[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)接口。  
  
## <a name="syntax"></a>语法

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>参数  
 *T*  
 您的类，派生自`ISessionPropertiesImpl`。  
  
 *PropClass*  
 用户可定义属性类，默认值为*T*。  

## <a name="requirements"></a>要求  
 **标头：** atldb.h  
  
## <a name="members"></a>成员  
  
### <a name="interface-methods"></a>接口方法  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|返回当前会话设置会话属性组中的属性列表。|  
|[SetProperties](#setproperties)|设置会话属性组中的属性。|  
  
## <a name="remarks"></a>备注  
 在会话上必需的接口。 此类通过调用定义的一个静态函数实现会话属性[属性集映射](../../data/oledb/begin-propset-map.md)。 应在会话类中指定的属性集映射。  
  
## <a name="getproperties"></a> Isessionpropertiesimpl:: Getproperties
返回中的属性列表`DBPROPSET_SESSION`对会话当前设置的属性组。  
  
### <a name="syntax"></a>语法  
  
```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[ISessionProperties::GetProperties](https://msdn.microsoft.com/library/ms723643.aspx)中*OLE DB 程序员参考*。 

## <a name="setproperties"></a> Isessionpropertiesimpl:: Setproperties
设置属性`DBPROPSET_SESSION`属性组。  
  
### <a name="syntax"></a>语法  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[ISessionProperties::SetProperties](https://msdn.microsoft.com/library/ms714405.aspx)中*OLE DB 程序员参考*。  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)