---
title: _TRUNCATE | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _TRUNCATE
- TRUNCATE
dev_langs:
- C++
helpviewer_keywords:
- TRUNCATE constant
- _TRUNCATE constant
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8bec6553502942fa3dc0376fff05a14f1971f53
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413877"
---
# <a name="truncate"></a>_TRUNCATE
指定字符串截断行为。  
  
## <a name="syntax"></a>语法  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>备注  
 `_TRUNCATE` 在作为这些函数的 `count` 参数传递时启用截断行为：  
  
 [strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [mbstowcs_s、_mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 [mbsrtowcs_s](../c-runtime-library/reference/mbsrtowcs-s.md)  
  
 [wcstombs_s、_wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [wcsrtombs_s](../c-runtime-library/reference/wcsrtombs-s.md)  
  
 [_snprintf_s、_snprintf_s_l、_snwprintf_s、_snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
 如果目标缓冲区因过小而无法保存整个字符串，则这些函数的常规行为是将其视为错误情况（请参阅[参数验证](../c-runtime-library/parameter-validation.md)）。 但是，如果通过传递 `_TRUNCATE` 启用字符串截断，则这些函数将仅复制适当数量的字符串，使目标缓冲区以 null 结尾并成功返回。  
  
 字符串截断将更改受影响函数的返回值。 如果未出现截断，则下列函数将返回 0；如果出现截断，则返回 `STRUNCATE`：  
  
 [strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [wcstombs_s、_wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [mbstowcs_s、_mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 如果未出现截断，则下列函数将返回复制的字符数量；如果出现截断，则将返回 -1（与原始 snprintf 函数的行为匹配）：  
  
 [_snprintf_s、_snprintf_s_l、_snwprintf_s、_snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
## <a name="example"></a>示例  
  
```  
// crt_truncate.c  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
   char src[] = "1234567890";  
   char dst[5];  
   errno_t err = strncpy_s(dst, _countof(dst), src, _TRUNCATE);  
   if ( err == STRUNCATE )  
      printf( "truncation occurred!\n" );  
   printf( "'%s'\n", dst );  
}  
```  
  
```Output  
truncation occurred!  
'1234'  
```  
  
## <a name="see-also"></a>请参阅  
 [全局常量](../c-runtime-library/global-constants.md)