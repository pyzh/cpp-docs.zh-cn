---
title: is_assignable 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5666aca2d6a855b64af26d38a1ae834fecec5d6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958460"
---
# <a name="isassignable-class"></a>is_assignable 类

测试 `From` 类型的值是否可以分配给 `To` 类型。

## <a name="syntax"></a>语法

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>参数

为接受赋值的对象的类型。

从提供的值的对象的类型。

## <a name="remarks"></a>备注

未计算的表达式 `declval<To>() = declval<From>()` 必须具有正确格式。 这两`From`并`To`必须是完整类型**void**，或具有未知边界的数组。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间：** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)<br/>
