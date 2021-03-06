---
title: _bstr_t::operator + =，+ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aad73939b8fd011fd6e1c9bf16f8dfe6eb303ff3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405738"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft 专用**  
  
 将字符追加到 `_bstr_t` 对象的结尾或串联两个字符串。  
  
## <a name="syntax"></a>语法  
  
```  
_bstr_t& operator+=( const _bstr_t& s1 );  
_bstr_t operator+( const _bstr_t& s1 );  
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);  
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);  
```  
  
#### <a name="parameters"></a>参数  
 *s1*  
 一个 `_bstr_t` 对象。  
  
 *s2*  
 多字节字符串。  
  
 *s3*  
 一个 Unicode 字符串。  
  
## <a name="remarks"></a>备注  
 以下运算符将执行字符串串联：  
  
-   **operator + = (***s1***)** 中封装的字符追加`BSTR`的*s1*到此对象封装末尾`BSTR`.  
  
-   **operator + (***s1***)** 返回新`_bstr_t`此对象的连接在一起构成`BSTR`与*s1*。  
  
-   **operator + (***s2***&#124;***s1***)** 返回一个新`_bstr_t`通过串联构成多字节字符串*s2*，已转换为 Unicode，与`BSTR`封装在*s1*。          
  
-   **operator + (***s3* **，***s1***)** 返回一个新`_bstr_t`通过将 Unicode 字符串构成*s3*与`BSTR`封装在*s1*。        
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [_bstr_t 类](../cpp/bstr-t-class.md)