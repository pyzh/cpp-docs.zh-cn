---
title: path 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::path
dev_langs:
- C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea20d43e2679addc10465cfc549a64fc210274f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861683"
---
# <a name="path-class"></a>path 类

**path** 类存储类型为 string\_type 的对象，此处处于阐释目的将其称为 myname，它适合用作路径名称。 string\_type 是 basic\_string\<value_type> 的同义词，其中 value\_type 是 Windows 下 char 的同义词或 Posix 下 wchar_t 的同义词。

有关详细信息和代码示例，请参阅[文件系统导航 (C++)](../standard-library/file-system-navigation.md)。

## <a name="syntax"></a>语法

```cpp
class path;
```

## <a name="pathappend"></a>path::append

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

成员函数将指定序列追加到 mypath（按需进行转换和插入 preferred_separator）。

## <a name="pathassign"></a>path::assign

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

成员函数将 mypath 替换为指定的序列（按需转换）。

## <a name="pathbegin"></a>path::begin

```cpp
iterator begin() const;
```

返回路径名称中指示第一个路径元素的 path::iterator（若存在）。

## <a name="pathcstr"></a>path::c_str

```cpp
const value_type& *c_str() const noexcept;
```

返回指向 mypath 中第一个字符的指针。

## <a name="pathclear"></a>path::clear

```cpp
void clear() noexcept;
```

成员函数执行 mypath.clear()

## <a name="pathcompare"></a>path::compare

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

第一个函数返回 mypath.compare(pval.native())。 第二个函数返回 mypath.compare(str)。 第三个函数返回 mypath.compare(ptr)。

## <a name="pathconcat"></a>path::concat

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

成员函数通过按需进行转换（但不插入分隔符），将指定序列追加到 mypath。

## <a name="pathconstiterator"></a>path::const_iterator

```cpp
typedef iterator const_iterator;
```

类型是迭代器的同义词。

## <a name="pathempty"></a>path::empty

```cpp
bool empty() const noexcept;
```

返回 mypath.empty()。

## <a name="pathend"></a>path::end

```cpp
iterator end() const;
```

返回类型迭代器的序列末迭代器。

## <a name="pathextension"></a>path::extension

```cpp
path extension() const;
```

返回 filename() X 的前缀，例如：

如果 X == path(".") &#124;&#124; X == path("..") 或如果 X 不包含任何点，则前缀为空。

否则，前缀以最右侧的点开头（并将其包含在内）。

## <a name="pathfilename"></a>path::filename

```cpp
path filename() const;
```

返回 myname 的根目录组件，尤其是 `empty()  path() : *--end()`。 组件可能为空。

## <a name="pathgenericstring"></a>path::generic_string

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

返回 `this->string<Elem, Traits, Alloc>(al)` ，其中（在 Windows 下）任何反斜杠均转换为正斜杠。

## <a name="pathgenericu16string"></a>path::generic_u16string

```cpp
u16string generic_u16string() const;
```

返回 u16string()，其中（在 Windows 下）任何反斜杠均转换为正斜杠。

## <a name="pathgenericu32string"></a>path::generic_u32string

```cpp
u32string generic_u32string() const;
```

返回 u32string()，其中（在 Windows 下）任何反斜杠均转换为正斜杠。

## <a name="pathgenericu8string"></a>path::generic_u8string

```cpp
string generic_u8string() const;
```

返回 u8string()，其中（在 Windows 下）任何反斜杠均转换为正斜杠。

## <a name="pathgenericwstring"></a>path::generic_wstring

```cpp
wstring generic_wstring() const;
```

返回 wstring()，其中（在 Windows 下）任何反斜杠均转换为正斜杠。

## <a name="pathhasextension"></a>path::has_extension

```cpp
bool has_extension() const;
```

返回 !extension().empty()。

## <a name="pathhasfilename"></a>path::has_filename

```cpp
bool has_filename() const;
```

返回 !filename().empty()。

## <a name="pathhasparentpath"></a>path::has_parent_path

```cpp
bool has_parent_path() const;
```

返回 !parent_path().empty()。

## <a name="pathhasrelativepath"></a>path::has_relative_path

```cpp
bool has_relative_path() const;
```

返回 !relative_path().empty()。

## <a name="pathhasrootdirectory"></a>path::has_root_directory

```cpp
bool has_root_directory() const;
```

返回 !root_directory().empty()。

## <a name="pathhasrootname"></a>path::has_root_name

```cpp
bool has_root_name() const;
```

返回 !root_name().empty()。

## <a name="pathhasrootpath"></a>path::has_root_path

```cpp
bool has_root_path() const;
```

返回 !root_path().empty()。

## <a name="pathhasstem"></a>path::has_stem

```cpp
bool has_stem() const;
```

返回 !stem().empty()。

## <a name="pathisabsolute"></a>path::is_absolute

```cpp
bool is_absolute() const;
```

对于 Windows，函数返回 has_root_name() && has_root_directory()。 对于 Posix，函数返回 has_root_directory()。

## <a name="pathisrelative"></a>path::is_relative

```cpp
bool is_relative() const;
```

返回 !is_absolute()。

## <a name="pathiterator"></a>path::iterator

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

此类描述了一个双向常量迭代器，该迭代器指定序列中 myname 的路径组件：

1. 根名称（如存在）

1. 根目录（如存在）

1. 父路径的剩余目录元素（如存在），并以 filename 结尾（如存在）

对于 pval，类型 path 的对象为：

1. path::iterator X = pval.begin() 指定路径名中的第一个路径元素（如存在）。

1. 当 X 点刚超出组件序列的末尾，则 X == pval.end() 为 true。

3. *X 返回一个匹配当前组件的字符串

1. ++X 指定序列中的下一个组件（如存在）。

1. --X 指定序列中的之前的组件（如存在）。

1. 更改 myname 会使所有指定 myname 中的元素的迭代器无效。

## <a name="pathmakepreferred"></a>path::make_preferred

```cpp
path& make_preferred();
```

成员函数按需将每个分隔符转换为 preferred_separator。

## <a name="pathnative"></a>path::native

```cpp
const string_type& native() const noexcept;
```

返回 myname。

## <a name="pathoperator"></a>path::operator=

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

第一个成员函数将 right.myname 复制到 myname。 第二个成员函数将 right.myname 移动到 myname。 第三个成员函数的行为与 *this = path(source) 相同。

## <a name="pathoperator"></a>path::operator+=

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

成员函数的行为与以下相应表达式相同：

1. concat(right);

1. concat(path(str));

1. concat(ptr);

1. concat(string_type(1, elem));

1. concat(source);

1. concat(path(basic_string\<Elem>(1, elem)));

## <a name="pathoperator"></a>path::operator/=

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

成员函数的行为与以下相应表达式相同：

1. append(right);

1. append(source);

## <a name="pathoperator-stringtype"></a>path::operator string_type

```cpp
operator string_type() const;
```

成员运算符返回 myname。

## <a name="pathparentpath"></a>path::parent_path

```cpp
path parent_path() const;
```

返回 myname 的父路径组件，尤其是删除 filename().native() 后 myname 的前缀和任何前面紧邻的目录分隔符。 （同样，如果 begin() != end()，则为通过连续应用 operator/= 在范围 [begin(), --end()) 内所有元素的组合。）组件可能为空。

## <a name="pathpath"></a>path::path

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

构造函数均以各种方式来构造 myname：

对于 path()，它为 myname()。

对于 path(const path& right)，则为 myname(right.myname)。

对于 path(path&& right)，则为 myname(right.myname)。

对于 template\<class Source> path(const Source& source)，则为 myname(source)。

对于 template\<class Source> path(const Source& source, const locale& loc)，则为 myname(source)，其中从 loc 获取任何所需的 codecvt facet。

对于 template\<class InIt> path(InIt first, InIt last)，则为 myname(first, last)。

对于 template\<class InIt> path(InIt first, InIt last, const locale& loc)，则为 myname(first, last)，其中从 loc 获取任何所需的 codecvt facet。

## <a name="pathpreferredseparator"></a>path::preferred_separator

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

常量对象提供首选字符来分隔路径组件，具体取决于主机操作系统。 请注意，在 Windows 下的大多数上下文中，同样允许在它的位置使用 L'/'。

## <a name="pathrelativepath"></a>path::relative_path

```cpp
path relative_path() const;
```

返回 myname 的相对路径组件，尤其是删除 root_path().native() 后 myname 的前缀和任何紧随其后的冗余目录分隔符。 组件可能为空。

## <a name="pathremovefilename"></a>path::remove_filename

```cpp
path& remove_filename();
```

## <a name="pathreplaceextension"></a>path::replace_extension

```cpp
path& replace_extension(const path& newext = path());
```

成员函数首先从 myname 中删除前缀 extension().native()。 然后，如果 !newext.empty() && newext[0] != dot（其中圆点为 *path(".").c_str()），则将圆点追加到 myname。 然后将 newext 追加到 myname。

## <a name="pathreplacefilename"></a>path::replace_filename

```cpp
path& replace_filename(const path& pval);
```

成员函数执行：

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathrootdirectory"></a>path::root_directory

```cpp
path root_directory() const;
```

返回 myname 的根目录组件。 组件可能为空。

## <a name="pathrootname"></a>path::root_name

```cpp
path root_name() const;
```

返回 myname 的根名称组件。 组件可能为空。

## <a name="pathrootpath"></a>path::root_path

```cpp
path root_path() const;
```

返回 myname 的根路径组件，尤其是 root_name() / root_directory。 组件可能为空。

## <a name="pathstem"></a>path::stem

```cpp
path stem() const;
```

返回 myname 的主干组件，尤其是删除了任何尾随 extension().native() 的 filename().native()。 组件可能为空。

## <a name="pathstring"></a>path::string

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

第一个（模板）成员函数按以下相同的方式转换 mypath 中存储的序列：

1. 对于 string\<char, Traits, Alloc>()，为 string()

1. 对于 string\<wchar_t, Traits, Alloc>()，为 wstring()

1. 对于 string\<char16_t, Traits, Alloc>()，为 u16string()

1. 对于 string\<char32_t, Traits, Alloc>()，为 u32string()

第二个成员函数将 mypath 中存储的序列转换为 char 序列的主机系统偏好的编码，并将其返回存储到类型 string 的对象中。

## <a name="pathstringtype"></a>path::string_type

```cpp
typedef basic_string<value_type> string_type;
```

类型为 basic_string<value_type> 的同义词。

## <a name="pathswap"></a>path::swap

```cpp
void swap(path& right) noexcept;
```

执行 swap(mypath, right.mypath)。

## <a name="pathu16string"></a>path::u16string

```cpp
u16string u16string() const;
```

成员函数将 mypath 中存储的序列转换为 UTF-16，并将其返回存储到类型 u16string 的对象中。

## <a name="pathu32string"></a>path::u32string

```cpp
u32string u32string() const;
```

成员函数将 mypath 中存储的序列转换为 UTF-32，并将其返回存储到类型 u32string 的对象中。

## <a name="pathu8string"></a>path::u8string

```cpp
string u8string() const;
```

成员函数将 mypath 中存储的序列转换为 UTF-8，并将其返回存储到类型u8string 的对象中。

## <a name="pathvaluetype"></a>path::value_type

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

类型描述了主机操作系统偏好的路径元素。

## <a name="pathwstring"></a>path::wstring

```cpp
wstring wstring() const;
```

将 mypath 中存储的序列转换为 wchar_t 序列的主机系统偏好的编码，并将其返回存储到类型 wstring 的对象中。

## <a name="requirements"></a>要求

**标头：** \<文件系统 >

**命名空间：** std::experimental::filesystem

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)<br/>
