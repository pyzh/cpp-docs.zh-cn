---
title: valarray&lt;bool&gt; 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray<bool>
- valarray/std::valarray<bool>
dev_langs:
- C++
helpviewer_keywords:
- valarray<bool> class
ms.assetid: fc0e7121-4758-4ea5-86c3-f04448f04acf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6b9cd3778ceb90e5e73a927f098c62d2c1e9bad
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964292"
---
# <a name="valarrayltboolgt-class"></a>valarray&lt;bool&gt; 类

此模板类的专用的版本**valarray\<类型 >** 于类型的元素**bool**。

## <a name="syntax"></a>语法

```cpp
class valarray<bool>
```

## <a name="example"></a>示例

```cpp
// valarray_bool.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaBool ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
   for ( i = 0 ; i < 10 ; i++ )
      cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
   for ( i = 0 ; i < 10 ; i++ )
      cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBool = ( vaL < vaR );
   cout << "The result of the less-than comparison "
   << "test is the\n valarray<bool>: ( ";
   for ( i = 0 ; i < 10 ; i++ )
      cout << vaBool [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The result of the less-than comparison test is the
 valarray<bool>: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="requirements"></a>要求

**标头：**\<valarray>

**命名空间：** std

## <a name="see-also"></a>请参阅

[valarray 类](../standard-library/valarray-class.md)<br/>
[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
