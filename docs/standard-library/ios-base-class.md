---
title: ios_base 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- xiosbase/std::ios_base::fmtflags
- xiosbase/std::ios_base::iostate
- xiosbase/std::ios_base::openmode
- xiosbase/std::ios_base::seekdir
- xiosbase/std::ios_base::event
- xiosbase/std::ios_base::adjustfield
- xiosbase/std::ios_base::app
- xiosbase/std::ios_base::ate
- xiosbase/std::ios_base::badbit
- xiosbase/std::ios_base::basefield
- xiosbase/std::ios_base::beg
- xiosbase/std::ios_base::binary
- xiosbase/std::ios_base::boolalpha
- xiosbase/std::ios_base::cur
- xiosbase/std::ios_base::dec
- xiosbase/std::ios_base::end
- xiosbase/std::ios_base::eofbit
- xiosbase/std::ios_base::failbit
- xiosbase/std::ios_base::fixed
- xiosbase/std::ios_base::floatfield
- xiosbase/std::ios_base::goodbit
- xiosbase/std::ios_base::hex
- xiosbase/std::ios_base::in
- xiosbase/std::ios_base::internal
- xiosbase/std::ios_base::left
- xiosbase/std::ios_base::oct
- xiosbase/std::ios_base::out
- xiosbase/std::ios_base::right
- xiosbase/std::ios_base::scientific
- xiosbase/std::ios_base::showbase
- xiosbase/std::ios_base::showpoint
- xiosbase/std::ios_base::showpos
- xiosbase/std::ios_base::skipws
- xiosbase/std::ios_base::trunc
- xiosbase/std::ios_base::unitbuf
- xiosbase/std::ios_base::uppercase
- xiosbase/std::ios_base::failure
- xiosbase/std::ios_base::flags
- xiosbase/std::ios_base::getloc
- xiosbase/std::ios_base::imbue
- xiosbase/std::ios_base::Init
- xiosbase/std::ios_base::iword
- xiosbase/std::ios_base::precision
- xiosbase/std::ios_base::pword
- ios/std::ios_base::register_callback
- xiosbase/std::ios_base::setf
- xiosbase/std::ios_base::sync_with_stdio
- xiosbase/std::ios_base::unsetf
- xiosbase/std::ios_base::width
- xiosbase/std::ios_base::xalloc
dev_langs:
- C++
helpviewer_keywords:
- std::ios_base [C++]
- std::ios_base [C++], event_callback
- std::ios_base [C++], fmtflags
- std::ios_base [C++], iostate
- std::ios_base [C++], openmode
- std::ios_base [C++], seekdir
- std::ios_base [C++], event
- std::ios_base [C++], adjustfield
- std::ios_base [C++], app
- std::ios_base [C++], ate
- std::ios_base [C++], badbit
- std::ios_base [C++], basefield
- std::ios_base [C++], beg
- std::ios_base [C++], binary
- std::ios_base [C++], boolalpha
- std::ios_base [C++], cur
- std::ios_base [C++], dec
- std::ios_base [C++], end
- std::ios_base [C++], eofbit
- std::ios_base [C++], failbit
- std::ios_base [C++], fixed
- std::ios_base [C++], floatfield
- std::ios_base [C++], goodbit
- std::ios_base [C++], hex
- std::ios_base [C++], in
- std::ios_base [C++], internal
- std::ios_base [C++], left
- std::ios_base [C++], oct
- std::ios_base [C++], out
- std::ios_base [C++], right
- std::ios_base [C++], scientific
- std::ios_base [C++], showbase
- std::ios_base [C++], showpoint
- std::ios_base [C++], showpos
- std::ios_base [C++], skipws
- std::ios_base [C++], trunc
- std::ios_base [C++], unitbuf
- std::ios_base [C++], uppercase
- std::ios_base [C++], failure
- std::ios_base [C++], flags
- std::ios_base [C++], getloc
- std::ios_base [C++], imbue
- std::ios_base [C++], Init
- std::ios_base [C++], iword
- std::ios_base [C++], precision
- std::ios_base [C++], pword
- std::ios_base [C++], register_callback
- std::ios_base [C++], setf
- std::ios_base [C++], sync_with_stdio
- std::ios_base [C++], unsetf
- std::ios_base [C++], width
- std::ios_base [C++], xalloc
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aec1d5291526360157b4e1a0b5b4eff9ae9fd454
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956447"
---
# <a name="iosbase-class"></a>ios_base 类

此类描述了不依赖模板参数的输入和输出流通用的存储和成员函数。 （模板类 [basic_ios](../standard-library/basic-ios-class.md) 描述了什么是通用对象以及什么依赖于模板参数。）

Ios_base 类的对象存储格式设置信息，其中包括：

- [fmtflags](#fmtflags) 类型的对象中的格式标志。

- [iostate](#iostate) 类型的对象中的异常掩码。

- 类型的对象中的字段宽度**int**。

- 类型的对象中的显示精度**int**。

- 类型的对象中的区域设置对象`locale`。

- 两个可扩展数组，包含类型的元素**长**并**void**指针。

Ios_base 类的对象还将流状态信息存储在 [iostate](#iostate) 类型的对象和回调堆栈中。

### <a name="constructors"></a>构造函数

|构造函数|描述|
|-|-|
|[ios_base](#ios_base)|构造 `ios_base` 对象。|

### <a name="typedefs"></a>Typedef

|类型名称|描述|
|-|-|
|[event_callback](#event_callback)|描述传递到 [register_call](#register_callback) 的函数。|
|[fmtflags](#fmtflags)|用于指定输出外观的常数。|
|[iostate](#iostate)|定义描述流状态的常数。|
|[openmode](#openmode)|介绍如何与流进行交互。|
|[seekdir](#seekdir)|指定偏移操作的起始点。|

### <a name="enums"></a>枚举

|||
|-|-|
|[event](#event)|指定事件类型。|

### <a name="constants"></a>常量

|||
|-|-|
|[adjustfield](#fmtflags)|定义为 `internal` &#124; `left` &#124; `right` 的位掩码。|
|[app](#openmode)|指定先查找到流末尾，再进行每个插入。|
|[ate](#openmode)|指定当首次创建其控制的对象时查找到流末尾。|
|[badbit](#iostate)|记录流缓冲区的完整性损失。|
|[basefield](#fmtflags)|定义为 `dec` &#124; `hex` &#124; `oct` 的位掩码。|
|[beg](#seekdir)|指定相对于序列的开头进行查找。|
|[binary](#openmode)|指定文件应读取为二进制流，而不是文本流。|
|[boolalpha](#fmtflags)|指定插入或提取类型的对象的**bool**作为名称 (如**true**并**false**) 而不是数值。|
|[cur](#seekdir)|指定相对于序列中的当前位置进行查找。|
|[dec](#fmtflags)|指定以十进制格式插入或提取整数值。|
|[end](#seekdir)|指定相对于序列的末尾进行查找。|
|[eofbit](#iostate)|从流中提取时，记录文件尾。|
|[failbit](#iostate)|记录一个从流中提取有效字段失败的操作。|
|[fixed](#fmtflags)|指定以定点格式（无指数域）插入浮点值。|
|[floatfield](#fmtflags)|定义为 `fixed` &#124; `scientific` 的位掩码|
|[goodbit](#iostate)|清除所有状态位。|
|[hex](#fmtflags)|指定以十六进制格式插入或提取整数值。|
|[in](#openmode)|指定从流中提取。|
|[internal](#fmtflags)|通过在生成的数字字段内的某一点插入填充字符，填充字段宽度。|
|[left](#fmtflags)|指定左对齐。|
|[oct](#fmtflags)|指定以八进制格式插入或提取整数值。|
|[out](#openmode)|指定插入到流。|
|[right](#fmtflags)|指定右对齐。|
|[scientific](#fmtflags)|指定以科学记数格式（具有一个指数域）插入浮点值。|
|[showbase](#fmtflags)|指定插入一个显示已生成整数字段的基的前缀。|
|[showpoint](#fmtflags)|指定在生成的浮点字段中无条件插入一个小数点。|
|[showpos](#fmtflags)|指定在生成的非负数字段中插入一个加号。|
|[skipws](#fmtflags)|指定在进行某些提取之前，先跳过前导空格。|
|[trunc](#openmode)|指定在创建其控制的对象后，删除现有文件的内容。|
|[unitbuf](#fmtflags)|将导致输出在每次插入后进行刷新。|
|[uppercase](#fmtflags)|指定在某些插入操作中插入小写字母的大写等效项。|

### <a name="member-functions"></a>成员函数

|成员函数|描述|
|-|-|
|[failure](#failure)|成员类用作 [basic_ios](../standard-library/basic-ios-class.md) 模板类中的 [clear](../standard-library/basic-ios-class.md#clear) 成员函数引发的所有异常的基类。|
|[flags](#flags)|设置或返回当前的标志设置。|
|[getloc](#getloc)|返回存储的区域设置对象。|
|[imbue](#imbue)|更改区域设置。|
|[Init](#init)|在构造时创建标准 iostream 对象。|
|[iword](#iword)|分配将存储为 `iword` 的值。|
|[precision](#precision)|指定浮点数中显示的位数。|
|[pword](#pword)|分配将存储为 `pword` 的值。|
|[register_callback](#register_callback)|指定一个回调函数。|
|[setf](#setf)|设置指定标志。|
|[sync_with_stdio](#sync_with_stdio)|确保 iostream 和 C 运行时库操作按照它们在源代码中出现的顺序发生。|
|[unsetf](#unsetf)|将导致指定的标志处于关闭状态。|
|[width](#width)|设置输出流的长度。|
|[xalloc](#xalloc)|指定变量应为流的一部分。|

### <a name="operators"></a>运算符

|运算符|描述|
|-|-|
|[operator=](#op_eq)|`ios_base` 对象的赋值运算符。|

## <a name="requirements"></a>要求

**标头：**\<ios>

**命名空间：** std

## <a name="event"></a>ios_base::event

指定事件类型。

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>备注

此类型是枚举的类型，该类型描述的对象可将作为参数使用的回调事件存储到使用 [register_callback](#register_callback) 注册的函数中。 非重复的事件值为：

- `copyfmt_event`标识调用末尾附近发生的回调[copyfmt](../standard-library/basic-ios-class.md#copyfmt)之前[异常掩码](../standard-library/ios-base-class.md)复制。

- `erase_event`标识发生在调用开始时的回调[copyfmt](../standard-library/basic-ios-class.md#copyfmt)，或调用的析构函数的开头**\*这**。

- `imbue_event`标识发生在结束对的调用的回调[imbue](#imbue)，该函数返回之前。

### <a name="example"></a>示例

有关示例，请参阅 [register_callback](#register_callback)。

## <a name="event_callback"></a>ios_base::event_callback

描述传递到 [register_call](#register_callback) 的函数。

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>参数

*（_e)* [事件](#event)。

*（_b)* 调用了事件的流。

*_I*用户定义的数字。

### <a name="remarks"></a>备注

此类型描述可使用 [register_callback](#register_callback) 注册的函数的指针。 此类函数不得引发任何异常。

### <a name="example"></a>示例

有关使用 `event_callback` 的示例，请参阅 [register_call](#register_callback)。

## <a name="failure"></a>ios_base::failure

根据 `iostreams` 库中的函数，类 `failure` 将引发的所有对象类型的基类定义为异常，以在流缓冲操作期间报告错误。

```cpp
namespace std {
    class failure : public system_error {
    public:
        explicit failure(
            const string& _Message,
            const error_code& _Code = io_errc::stream);

        explicit failure(
            const char* str,
            const error_code& _Code = io_errc::stream);
    };
}
```

### <a name="remarks"></a>备注

`what()` 返回的值是 `_Message` 的一个副本，可能基于 `_Code` 通过测试进行了扩充。 如果未指定 `_Code`，则默认值为 `make_error_code(io_errc::stream)`。

### <a name="example"></a>示例

```cpp
// ios_base_failure.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.exceptions(ios::failbit);
    try
    {
        file.open( "rm.txt", ios_base::in );
        // Opens nonexistent file for reading
    }
    catch( ios_base::failure f )
    {
        cout << "Caught an exception: " << f.what() << endl;
    }
}
```

```Output
Caught an exception: ios_base::failbit set
```

## <a name="flags"></a>ios_base::flags

设置或返回当前的标志设置。

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>参数

*fmtfl*新`fmtflags`设置。

### <a name="return-value"></a>返回值

先前或当前的 `fmtflags` 设置。

### <a name="remarks"></a>备注

有关标志列表，请参阅 [ios_base::fmtflags](#fmtflags)。

第一个成员函数返回存储的格式标志。 第二个成员函数存储*fmtfl*在格式标志并返回其先前的存储值。

### <a name="example"></a>示例

```cpp
// ios_base_flags.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    cout << cout.flags( ) << endl;
    cout.flags( ios::dec | ios::boolalpha );
    cout << cout.flags( );
}
```

```Output
513
16896
```

## <a name="fmtflags"></a>ios_base::fmtflags

用于指定输出外观的常数。

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type fmtflags;
   static const fmtflags boolalpha;
   static const fmtflags dec;
   static const fmtflags fixed;
   static const fmtflags hex;
   static const fmtflags internal;
   static const fmtflags left;
   static const fmtflags oct;
   static const fmtflags right;
   static const fmtflags scientific;
   static const fmtflags showbase;
   static const fmtflags showpoint;
   static const fmtflags showpos;
   static const fmtflags skipws;
   static const fmtflags unitbuf;
   static const fmtflags uppercase;
   static const fmtflags adjustfield;
   static const fmtflags basefield;
   static const fmtflags floatfield;
   // ...
};
```

### <a name="remarks"></a>备注

支持 [ios](../standard-library/ios.md) 中的操控器。

该类型是一个位掩码类型，它描述可存储格式标志的对象。 非重复的标志值（元素）为：

- `dec`，用于以十进制格式插入或提取整数值。

- `hex`，用于以十六进制格式插入或提取整数值。

- `oct`，用于以八进制格式插入或提取整数值。

- `showbase`，用于插入一个显示已生成整型域的基的前缀。

- `internal`，用于通过在生成的数字字段内的某一点插入填充字符，来根据需要填充字段宽度。 （有关设置字段宽度的信息，请参阅 [setw](../standard-library/iomanip-functions.md#setw)）。

- `left`，用于通过在已生成字段的末尾插入填充字符（左对齐），来根据需要填充字段宽度。

- `right`，用于通过在已生成字段的开头插入填充字符（右对齐），来根据需要填充字段宽度。

- `boolalpha`用于插入或提取类型的对象**bool**作为名称 (如**true**并**false**) 而不是数值。

- `fixed`，用于以固定点格式（不带指数字段）插入浮点值。

- `scientific`，用于以科学记数格式（不带指数域）插入浮点值。

- `showpoint`，用于在生成的浮点字段中无条件地插入十进制点。

- `showpos`，用于在生成的非负数字段中插入一个加号。

- `skipws`，用于在某些提取前跳过前导空格。

- `unitbuf`，用于在每次插入后刷新输出。

- `uppercase`，用于在某些插入中插入小写字母的大写等效项。

另外，还有些有用的值如下所示：

- `adjustfield`（定义为 `internal` &#124; `left` &#124; `right` 的位掩码）

- `basefield`（定义为 `dec` &#124; `hex` &#124; `oct`）

- `floatfield`（定义为 `fixed` &#124; `scientific`）

有关修改这些格式标志的函数的示例，请参阅 [\<iomanip>](../standard-library/iomanip.md)。

## <a name="getloc"></a>ios_base::getloc

返回存储的区域设置对象。

```cpp
locale getloc() const;
```

### <a name="return-value"></a>返回值

存储的区域设置对象。

### <a name="example"></a>示例

```cpp
// ios_base_getlock.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << cout.getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="imbue"></a>ios_base::imbue

更改区域设置。

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>参数

*_Loc*新的区域设置。

### <a name="return-value"></a>返回值

先前的区域设置。

### <a name="remarks"></a>备注

此成员函数存储 *_Loc*中的区域设置对象，然后报告回调事件和`imbue_event`。 它返回先前的存储值。

### <a name="example"></a>示例

有关示例，请参阅 [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue)。

## <a name="init"></a>ios_base::Init

在构造时创建标准 iostream 对象。

```cpp
class Init { };
```

### <a name="remarks"></a>备注

此嵌套类描述一个对象，该对象的构造可确保即使在执行任意静态对象的构造函数前也可正确构造标准 iostreams 对象。

## <a name="ios_base"></a>ios_base::ios_base

构造 ios_base 对象。

```cpp
ios_base();
```

### <a name="remarks"></a>备注

此（受保护）构造函数不会执行任何操作。 稍后对 **basic_ios::**[init](../standard-library/basic-ios-class.md#init) 的调用必须先初始化此对象，然后才可被安全销毁。 因此，类 ios_base 的唯一安全用途是作为模板类 [basic_ios](../standard-library/basic-ios-class.md) 的基类。

## <a name="iostate"></a>ios_base::iostate

描述流状态的常量的类型。

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>备注

该类型是一个位掩码类型，它描述可存储流状态信息的对象。 非重复的标志值（元素）为：

- `badbit`（用于记录流缓冲区的完整性损失）。

- `eofbit`（用于在从流提取时记录文件尾）。

- `failbit`（用于记录一个从流中提取有效字段失败的操作）。

此外，有用的值是`goodbit`，则无前面提到的 bits 设置 (`goodbit`保证为零)。

## <a name="iword"></a>ios_base::iword

分配将存储为 `iword` 的值。

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>参数

*idx*的值存储为索引`iword`。

### <a name="remarks"></a>备注

成员函数将返回元素的引用*idx*类型的元素的可扩展数组**长**。 所有元素均有效存在，且起初会存储值 0。 下次调用此对象的 `iword` 后、对象由对 **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) 的调用更改后或者对象被销毁后，该返回引用将无效。

如果*idx*为负或唯一的存储的元素不可用，如果该函数将调用[setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** 并返回可能不是唯一的引用。

若要获取唯一索引以用于类型 `ios_base` 的所有对象，请调用 [xalloc](#xalloc)。

### <a name="example"></a>示例

有关如何使用 `iword` 的示例，请参阅 [xalloc](#xalloc)。

## <a name="openmode"></a>ios_base::openmode

介绍如何与流进行交互。

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>备注

此类型为 `bitmask type`，它描述的对象可存储多个 iostreams 对象的开放模式。 非重复的标志值（元素）为：

- `app`若要查找每次插入前流的末尾。

- `ate`首次创建其控制的对象时查找流末尾。

- `binary`用于读取文件作为二进制流，而不是文本流。

- `in`以允许从流中的提取。

- `out`以允许插入到流。

- `trunc`若要创建其控制的对象时删除现有文件的内容。

### <a name="example"></a>示例

```cpp
// ios_base_openmode.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
}
```

## <a name="op_eq"></a>ios_base::operator=

ios_base 对象的赋值运算符。

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>参数

*右*类型的对象`ios_base`。

### <a name="return-value"></a>返回值

向其赋值的对象。

### <a name="remarks"></a>备注

此运算符复制存储的格式信息，从而创建任何可扩展数组的新副本。 它随后返回 **\*this**。 请注意，不会复制回调堆栈。

此运算符仅由派生自 `ios_base` 的类使用。

## <a name="precision"></a>ios_base::precision

指定浮点数中显示的位数。

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>参数

*_Prec*有效位数来显示或固定表示法中小数点后的位数。

### <a name="return-value"></a>返回值

第一个成员函数返回存储的[显示精度](../standard-library/ios-base-class.md)。 第二个成员函数存储 *_Prec*在显示精度并返回其先前的存储值。

### <a name="remarks"></a>备注

浮点数以具有[固定](../standard-library/ios-functions.md#fixed)的固定表示法显示。

### <a name="example"></a>示例

```cpp
// ios_base_precision.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    float i = 31.31234F;

    cout.precision( 3 );
    cout << i << endl;          // display three significant digits
    cout << fixed << i << endl; // display three digits after decimal
                                // point
}
```

```Output
31.3
31.312
```

## <a name="pword"></a>ios_base::pword

分配将存储为 `pword` 的值。

```cpp
void *& pword(int _Idx);
```

### <a name="parameters"></a>参数

*上 _Idx*的值存储为索引`pword`。

### <a name="remarks"></a>备注

成员函数返回的引用元素 _ *Idx*类型的元素的可扩展数组**void**指针。 所有元素均有效存在，且起初会存储空指针。 下次调用此对象的 `pword` 后、对象由对 **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) 的调用更改后或者对象被销毁后，该返回引用将无效。

如果 _ *Idx* 为负或唯一存储对该元素不可用，则此函数会调用 [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** 并返回一个可能并不唯一的引用。

若要获取唯一索引以用于类型 `ios_base` 的所有对象，请调用 [xalloc](#xalloc)。

### <a name="example"></a>示例

有关使用 `pword` 的示例，请参考 [xalloc](#xalloc)。

## <a name="register_callback"></a>ios_base::register_callback

指定一个回调函数。

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>参数

*pfn*指向回调函数的指针。

*idx*用户定义的数字。

### <a name="remarks"></a>备注

成员函数将对推送`{pfn, idx}`到存储的回调堆栈[回调堆栈](../standard-library/ios-base-class.md)。 当回调事件**ev**进行报告后，调用函数时，按相反的顺序的注册表中，由表达式`(*pfn)(ev, *this, idx)`。

### <a name="example"></a>示例

```cpp
// ios_base_register_callback.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void callback1( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback1" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

void callback2( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback2" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

int main( )
{
    // Make sure the imbue will not throw an exception
    // assert( setlocale( LC_ALL, "german" )!=NULL );

    cout.register_callback( callback1, 0 );
    cin.register_callback( callback2, 0 );

    try
    {
        // If no exception because the locale's not found,
        // generate an imbue_event on callback1
        cout.imbue(locale("german"));
    }
    catch(...)
    {
        cout << "exception" << endl;
    }

    // This will
    // (1) erase_event on callback1
    // (2) copyfmt_event on callback2
    cout.copyfmt(cin);

    // We get two erase events from callback2 at the end because
    // both cin and cout have callback2 registered when cin and cout
    // are destroyed at the end of program.
}
```

```Output
in callback1
an imbue event
in callback1
an erase event
in callback2
an copyfmt event
in callback2
an erase event
in callback2
an erase event
```

## <a name="seekdir"></a>ios_base::seekdir

指定偏移操作的起始点。

```cpp
namespace std {
    class ios_base {
    public:
        typedef implementation-defined-enumerated-type seekdir;
        static const seekdir beg;
        static const seekdir cur;
        static const seekdir end;
        // ...
    };
}
```

### <a name="remarks"></a>备注

类型为描述一个对象，可以将存储作为若干 iostream 类的成员函数的参数所使用的搜索模式的枚举的类型。 非重复的标志值为：

- `beg`若要查找 （更改当前读取或写入位置） 相对于序列 （数组、 流或文件） 的开头。

- `cur`相对于序列中的当前位置进行查找。

- `end`相对于序列的末尾进行查找。

### <a name="example"></a>示例

```cpp
// ios_base_seekdir.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
    file.seekp( 0, ios_base::beg );
    file << "a";
    file.seekp( 0, ios_base::end );
    file << "a";
}
```

## <a name="setf"></a>ios_base::setf

设置指定标志。

```cpp
fmtflags setf(
    fmtflags _Mask
);
fmtflags setf(
    fmtflags _Mask,
    fmtflags _Unset
);
```

### <a name="parameters"></a>参数

*掩码 （_m)* 要启用的标志。

*_Unset*要关闭的标志。

### <a name="return-value"></a>返回值

    The previous format flags

### <a name="remarks"></a>备注

    The first member function effectively calls [flags](#flags)(_ *Mask* &#124; \_ *Flags*) (set selected bits) and then returns the previous format flags. The second member function effectively calls **flags**(\_ *Mask* **& fmtfl, flags& ~**`_Mask`) (replace selected bits under a mask) and then returns the previous format flags.

### <a name="example"></a>示例

```cpp
// ios_base_setf.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    int i = 10;
    cout << i << endl;

    cout.unsetf( ios_base::dec );
    cout.setf( ios_base::hex );
    cout << i << endl;

    cout.setf( ios_base::dec );
    cout << i << endl;
    cout.setf( ios_base::hex, ios_base::dec );
    cout << i << endl;
}
```

## <a name="sync_with_stdio"></a>ios_base::sync_with_stdio

确保 iostream 和 C 运行时库操作按照它们在源代码中出现的顺序发生。

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>参数

*_Sync*所有流都是否与同步`stdio`。

### <a name="return-value"></a>返回值

    Previous setting for this function.

### <a name="remarks"></a>备注

    The static member function stores a `stdio` sync flag, which is initially **true**. When **true**, this flag ensures that operations on the same file are properly synchronized between the [iostreams](../standard-library/iostreams-conventions.md) functions and those defined in the C++ Standard Library. Otherwise, synchronization may or may not be guaranteed, but performance may be improved. The function stores *_Sync* in the `stdio` sync flag and returns its previous stored value. You can call it reliably only before performing any operations on the standard streams.

## <a name="unsetf"></a>ios_base::unsetf

将导致指定的标志处于关闭状态。

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>参数

*掩码 （_m)* 要关闭的标志。

### <a name="remarks"></a>备注

    The member function effectively calls [flags](#flags)(`~`*_Mask* **& flags**) (clear selected bits).

### <a name="example"></a>示例

    See [ios_base::setf](#setf) for a sample of using `unsetf`.

## <a name="width"></a>ios_base::width

设置输出流的长度。

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>参数

*_Wide*的输出流的所需的大小。

### <a name="return-value"></a>返回值

    The current width setting.

### <a name="remarks"></a>备注

    The first member function returns the stored field width. The second member function stores *_Wide* in the field width and returns its previous stored value.

### <a name="example"></a>示例

```cpp
// ios_base_width.cpp
// compile with: /EHsc
#include <iostream>

int main( ) {
    using namespace std;

    cout.width( 20 );
    cout << cout.width( ) << endl;
    cout << cout.width( ) << endl;
}
```

```Output
20
0
```

## <a name="xalloc"></a>ios_base::xalloc

    Specifies that a variable is part of the stream.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>返回值

    The static member function returns a stored static value, which it increments on each call.

### <a name="remarks"></a>备注

    You can use the return value as a unique index argument when calling the member functions [iword](#iword) or [pword](#pword).

### <a name="example"></a>示例

```cpp
// ios_base_xalloc.cpp
// compile with: /EHsc
// Lets you store user-defined information.
// iword, jword, xalloc
#include <iostream>

int main( )
{
    using namespace std;

    static const int i = ios_base::xalloc();
    static const int j = ios_base::xalloc();
    cout.iword( i ) = 11;
    cin.iword( i ) = 13;
    cin.pword( j ) = "testing";
    cout << cout.iword( i ) << endl;
    cout << cin.iword( i ) << endl;
    cout << ( char * )cin.pword( j ) << endl;
}
```

```Output
11
13
testing
```

## <a name="see-also"></a>请参阅

[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 编程](../standard-library/iostream-programming.md)<br/>
[iostreams 约定](../standard-library/iostreams-conventions.md)<br/>
