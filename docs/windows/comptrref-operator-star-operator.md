---
title: 'Comptrref:: Operator * 运算符 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 229a5a61bfe28280f7bffcd92f9d9cebffa2415b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647155"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator* 运算符
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
InterfaceType* operator *();  
```  
  
## <a name="return-value"></a>返回值  
 指向由当前的接口指针**ComPtrRef**对象。  
  
## <a name="remarks"></a>备注  
 检索指向当前所表示接口的指针**ComPtrRef**对象。  
  
## <a name="requirements"></a>要求  
 **标头：** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [ComPtrRef 类](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)