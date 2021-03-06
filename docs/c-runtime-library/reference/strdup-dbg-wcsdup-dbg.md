---
title: _strdup_dbg、_wcsdup_dbg | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strdup_dbg
- _wcsdup_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
dev_langs:
- C++
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b6e8f5f4634ec93cab619c1e073fa8071691fe6
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451375"
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg、_wcsdup_dbg

版本的[_strdup and _wcsdup](strdup-wcsdup-mbsdup.md)使用的调试版本**malloc**。

## <a name="syntax"></a>语法

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>参数

*strSource*<br/>
null 终止的源字符串。

*blockType*<br/>
内存块的请求类型： **_CLIENT_BLOCK**或 **_NORMAL_BLOCK**。

*filename*<br/>
指向请求分配操作的源文件名的指针或**NULL**。

*linenumber*<br/>
请求分配操作所在的源文件中的行数或**NULL**。

## <a name="return-value"></a>返回值

其中每个函数返回一个指向复制字符串的存储位置或**NULL**如果无法分配存储。

## <a name="remarks"></a>备注

**_Strdup_dbg**和 **_wcsdup_dbg**函数相等 **_strdup**和 **_wcsdup**只不过，当 **_调试**是定义，这些函数将使用的调试版本**malloc**， **_malloc_dbg**来为复制的字符串分配内存。 有关信息的调试功能的 **_malloc_dbg**，请参阅[_malloc_dbg](malloc-dbg.md)。

在大多数情况下，无需显式调用这些函数。 相反，你可以定义标志 **_CRTDBG_MAP_ALLOC**。 当 **_CRTDBG_MAP_ALLOC**定义，则调用 **_strdup**和 **_wcsdup**重新映射到 **_strdup_dbg**和 **_wcsdup_dbg**分别与*blockType*设置为 **_NORMAL_BLOCK**。 因此，不需要显式调用这些函数，除非你希望将堆块作为标记 **_CLIENT_BLOCK**。 有关块类型的详细信息，请参阅[调试堆中的块类型](/visualstudio/debugger/crt-debug-heap-details)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**_strdup_dbg**， **_wcsdup_dbg**|\<crtdbg.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有调试版本。

## <a name="see-also"></a>请参阅

[字符串操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup、_wcsdup、_mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[堆分配函数的调试版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
