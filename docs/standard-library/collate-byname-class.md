---
title: collate_byname 类 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f104736d1c8f9d0ed60f2afd374345ab227300b4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964907"
---
# <a name="collatebyname-class"></a>collate_byname 类

一种派生模板类，用于描述一个对象来充当给定区域设置的排序规则 facet，从而检索与字符串排序约定有关的文化区域特定信息。

## <a name="syntax"></a>语法

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>参数

*_Locname*命名的区域设置。

*_Refs*初始引用计数。

## <a name="remarks"></a>备注

一种模板类，用于描述一个可充当类型 [collate](../standard-library/collate-class.md#collate)\<CharType> 的[区域设置 facet](../standard-library/locale-class.md#facet_class) 的对象。 其行为由[名为](../standard-library/locale-class.md#name)区域设置 *_Locname*。 每个构造函数通过 [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`) 初始化其基对象。

## <a name="requirements"></a>要求

**标头：** \<locale>

**命名空间：** std

## <a name="see-also"></a>请参阅

[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
