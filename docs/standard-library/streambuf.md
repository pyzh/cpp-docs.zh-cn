---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 138ec5bb28e108751a7d4b03651826db38c098fa
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026927"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

包含 iostreams 标准标头 \<streambuf > 来定义此模板类 [basic_streambuf](../standard-library/basic-streambuf-class.md)，这是 iostreams 类的基本操作。 此标头通常包含在另一 iostream 标头中；很少会直接包含它。

## <a name="syntax"></a>语法

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Typedef

|类型名称|描述|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|专用化`basic_streambuf`，它使用**char**作为模板参数。|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|专用化`basic_streambuf`，它使用**wchar_t**作为模板参数。|

### <a name="classes"></a>类

|类|描述|
|-|-|
|[basic_streambuf 类](http://msdn.microsoft.com/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|此模板类描述一个用于派生流缓冲区的抽象基类，该缓冲区控制元素与特定的流表示形式的来回传输。|

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 编程](../standard-library/iostream-programming.md)<br/>
[iostreams 约定](../standard-library/iostreams-conventions.md)<br/>
