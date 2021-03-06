---
title: scoped_allocator_adaptor 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- scoped_allocator/std::scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor::rebind Struct
- scoped_allocator/std::scoped_allocator_adaptor::allocate
- scoped_allocator/std::scoped_allocator_adaptor::construct
- scoped_allocator/std::scoped_allocator_adaptor::deallocate
- scoped_allocator/std::scoped_allocator_adaptor::destroy
- scoped_allocator/std::scoped_allocator_adaptor::inner_allocator
- scoped_allocator/std::scoped_allocator_adaptor::max_size
- scoped_allocator/std::scoped_allocator_adaptor::outer_allocator
- scoped_allocator/std::scoped_allocator_adaptor::select_on_container_copy_construction
dev_langs:
- C++
helpviewer_keywords:
- std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor::allocate
- std::scoped_allocator_adaptor::construct
- std::scoped_allocator_adaptor::deallocate
- std::scoped_allocator_adaptor::destroy
- std::scoped_allocator_adaptor::inner_allocator
- std::scoped_allocator_adaptor::max_size
- std::scoped_allocator_adaptor::outer_allocator
- std::scoped_allocator_adaptor::select_on_container_copy_construction
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7025e0d52aa882c26e2785279626959ca6b29ac1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962925"
---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor 类

表示分配器嵌套。

## <a name="syntax"></a>语法

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>备注

模板类可封装一个或多个分配器的嵌套。 每个这样的类都具有一个类型为 `outer_allocator_type` 的最外层分配器，该类型也即 `Outer`，是 `scoped_allocator_adaptor` 对象的公共基类。 `Outer` 可用于分配容器要使用的内存。 通过调用 `outer_allocator` 可获取对此分配器基对象的引用。

嵌套的其余部分具有 `inner_allocator_type` 类型。 内部分配器用于为容器中的元素分配内存。 通过调用 `inner_allocator` 可获取对此类型的存储对象的引用。 如果 `Inner...` 不为空，则 `inner_allocator_type` 将具有类型 `scoped_allocator_adaptor<Inner...>`，`inner_allocator` 指示成员对象。 否则，`inner_allocator_type` 将具有类型 `scoped_allocator_adaptor<Outer>`，`inner_allocator` 指示整个对象。

嵌套的表现行为好像可以具有任意深度，可根据需要复制其最里层的封装分配器。

可借助界面中不可见的几个概念来帮助理解此模板类的行为。 最外层分配器，可协调对构造和销毁方法的所有调用。 它实际上是由递归函数 `OUTERMOST(X)` 定义的，其中 `OUTERMOST(X)` 是以下项之一。

- 如果 `X.outer_allocator()` 的格式正确，则 `OUTERMOST(X)` 为 `OUTERMOST(X.outer_allocator())`。

- 否则 `OUTERMOST(X)` 为 `X`。

需要定义三种类型以便进行展示：

|类型|描述|
|----------|-----------------|
|`Outermost`|`OUTERMOST(*this)` 的类型。|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>构造函数

|name|描述|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|构造 `scoped_allocator_adaptor` 对象。|

### <a name="typedefs"></a>Typedef

|名称|描述|
|----------|-----------------|
|`const_pointer`|此类型是 `const_pointer`（与分配器 `Outer` 关联）的同义词。|
|`const_void_pointer`|此类型是 `const_void_pointer`（与分配器 `Outer` 关联）的同义词。|
|`difference_type`|此类型是 `difference_type`（与分配器 `Outer` 关联）的同义词。|
|`inner_allocator_type`|此类型是嵌套适配器 `scoped_allocator_adaptor<Inner...>` 类型的同义词。|
|`outer_allocator_type`|此类型是基本分配器 `Outer` 类型的同义词。|
|`pointer`|此类型是 `pointer`（与分配器 `Outer` 关联）的同义词。|
|`propagate_on_container_copy_assignment`|仅当 `Outer_traits::propagate_on_container_copy_assignment` 或 `inner_allocator_type::propagate_on_container_copy_assignment` 为 true 时，该类型才为 true。|
|`propagate_on_container_move_assignment`|仅当 `Outer_traits::propagate_on_container_move_assignment` 或 `inner_allocator_type::propagate_on_container_move_assignment` 为 true 时，该类型才为 true。|
|`propagate_on_container_swap`|仅当 `Outer_traits::propagate_on_container_swap` 或 `inner_allocator_type::propagate_on_container_swap` 为 true 时，该类型才为 true。|
|`size_type`|此类型是 `size_type`（与分配器 `Outer` 关联）的同义词。|
|`value_type`|此类型是 `value_type`（与分配器 `Outer` 关联）的同义词。|
|`void_pointer`|此类型是 `void_pointer`（与分配器 `Outer` 关联）的同义词。|

### <a name="structs"></a>结构

|name|描述|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind 结构](#rebind_struct)|将 `Outer::rebind\<Other>::other` 类型定义为 `scoped_allocator_adaptor\<Other, Inner...>` 的同义词。|

### <a name="methods"></a>方法

|名称|描述|
|----------|-----------------|
|[allocate](#allocate)|通过使用 `Outer` 分配器分配内存。|
|[construct](#construct)|构造对象。|
|[deallocate](#deallocate)|通过使用外部分配器释放对象。|
|[destroy](#destroy)|销毁指定的对象。|
|[inner_allocator](#inner_allocator)|检索对类型为 `inner_allocator_type` 的存储对象的引用。|
|[max_size](#max_size)|确定可通过外部分配器分配的对象的最大数目。|
|[outer_allocator](#outer_allocator)|检索对类型为 `outer_allocator_type` 的存储对象的引用。|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|创建一个新的 `scoped_allocator_adaptor` 对象，其中每个存储分配器对象都可通过调用每个相应分配器的 `select_on_container_copy_construction` 进行初始化。|

## <a name="requirements"></a>要求

**标头：** \<scoped_allocator 1>

**命名空间：** std

## <a name="allocate"></a>  scoped_allocator_adaptor::allocate

通过使用 `Outer` 分配器分配内存。

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>参数

*计数*为分配足够的存储空间的元素数。

*提示*通过定位在请求之前分配的对象的地址可能帮助分配器对象的指针。

### <a name="return-value"></a>返回值

第一个成员函数返回 `Outer_traits::allocate(outer_allocator(), count)`。 第二个成员函数返回 `Outer_traits::allocate(outer_allocator(), count, hint)`。

## <a name="construct"></a>  scoped_allocator_adaptor::construct

构造对象。

```cpp
template <class Ty, class... Atypes>
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,
    tuple<Atypes1&&...>
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr,
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```

### <a name="parameters"></a>参数

*ptr*指向要构造对象的内存位置的指针。

*args*的参数列表。

*第一个*一对中第一种类型的对象。

*第二个*一对中的第二个类型的对象。

*右*移动或复制的现有对象。

### <a name="remarks"></a>备注

第一种方法处构造对象*ptr*通过调用`Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`，其中`xargs...`是以下值之一。

- 如果 `uses_allocator<Ty, inner_allocator_type>` 为 false，则 `xargs...` 为 `args...`。

- 如果 `uses_allocator<Ty, inner_allocator_type>` 为 true 且 `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` 为 true，则 `xargs...` 为 `allocator_arg, inner_allocator(), args...`。

- 如果 `uses_allocator<Ty, inner_allocator_type>` 为 true 且 `is_constructible<Ty, args..., inner_allocator()>` 为 true，则 `xargs...` 为 `args..., inner_allocator()`。

第二种方法对处构造对象*ptr*通过调用`Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`，其中`xargs...`是`first...`修改在上述列表中，和`Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`，其中`xargs...`是`second...`修改在上述列表中。

第三种方法的行为与 `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)` 相同。

第四种方法的行为与 `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))` 相同。

第五种方法的行为与 `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))` 相同。

第六种方法的行为与 `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))` 相同。

## <a name="deallocate"></a>  scoped_allocator_adaptor::deallocate

通过使用外部分配器释放对象。

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>参数

*ptr*指向要释放的对象的起始位置的指针。

*计数*要解除分配的对象数。

## <a name="destroy"></a>  scoped_allocator_adaptor::destroy

销毁指定的对象。

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>参数

*ptr*指向要销毁的对象的指针。

### <a name="return-value"></a>返回值

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="inner_allocator"></a>  scoped_allocator_adaptor::inner_allocator

检索对类型为 `inner_allocator_type` 的存储对象的引用。

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>返回值

对类型为 `inner_allocator_type` 的存储对象的引用。

## <a name="max_size"></a>  scoped_allocator_adaptor::max_size

确定可通过外部分配器分配的对象的最大数目。

```cpp
size_type max_size();
```

### <a name="return-value"></a>返回值

`Outer_traits::max_size(outer_allocator())`

## <a name="outer_allocator"></a>  scoped_allocator_adaptor::outer_allocator

检索对类型为 `outer_allocator_type` 的存储对象的引用。

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>返回值

对类型为 `outer_allocator_type` 的存储对象的引用。

## <a name="rebind_struct"></a>  scoped_allocator_adaptor::rebind 结构

将 `Outer::rebind\<Other>::other` 类型定义为 `scoped_allocator_adaptor\<Other, Inner...>` 的同义词。

重新绑定结构 {typedef Other_traits::rebind\<其他 > Other_alloc; typedef scoped_allocator_adaptor\<Other_alloc，内部...> 其他;};

## <a name="scoped_allocator_adaptor"></a>  scoped_allocator_adaptor::scoped_allocator_adaptor 构造函数

构造 `scoped_allocator_adaptor` 对象。

```cpp
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(Outer2&& al,
    const Inner&... rest) noexcept;
```

### <a name="parameters"></a>参数

*右*的现有`scoped_allocator_adaptor`。

*al*要用作外部分配器的现有分配器。

*rest*要用作内部分配器的分配器的列表。

### <a name="remarks"></a>备注

第一个构造函数默认构造其存储分配器对象。 接下来三个构造函数的每个构造中的相应对象从其存储的分配器对象*右*。 最后一个构造函数从参数列表中相应参数构造其存储分配器对象。

## <a name="select_on_container_copy_construction"></a>  scoped_allocator_adaptor::select_on_container_copy_construction

创建一个新的 `scoped_allocator_adaptor` 对象，其中每个存储分配器对象都可通过调用每个相应分配器的 `select_on_container_copy_construction` 进行初始化。

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>返回值

实际上，此方法将返回 `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`。 结果是一种新`scoped_allocator_adaptor`对象，其中每个存储分配器对象通过调用来初始化`al.select_on_container_copy_construction()`来相应分配器*al*。

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)<br/>
