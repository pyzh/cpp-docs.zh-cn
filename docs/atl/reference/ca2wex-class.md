---
title: CA2WEX 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f19046cc825fabd2a3a41020a9f4c141dc98489e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882814"
---
# <a name="ca2wex-class"></a>CA2WEX 类
字符串转换宏 CA2TEX、 CA2CTEX、 CT2WEX，和 CT2CWEX 和 typedef CA2W 使用此类。  
  
> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类和其成员。  
  
## <a name="syntax"></a>语法  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>参数  
 *t_nBufferLength*  
 在转换过程中所使用的缓冲区的大小。 默认长度为 128 个字节。  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|构造函数。|  
|[CA2WEX:: ~ CA2WEX](#dtor)|析构函数。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|转换运算符。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|将源字符串存储的数据成员。|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|静态缓冲区，用于存储转换后的字符串。|  
  
## <a name="remarks"></a>备注  
 除非需要额外的功能，在代码中使用 CA2TEX、 CA2CTEX、 CT2WEX、 CT2CWEX 或 CA2W。  
  
 此类包含固定大小的静态缓冲区用于存储转换的结果。 如果结果太大而无法放入静态缓冲区，类分配内存使用**malloc**，当对象超出范围时释放内存。 这样可确保与不同的文本转换宏可在以前版本的 ATL，此类可以安全地在循环中使用和堆栈不会溢出。  
  
 如果类尝试分配内存堆和失败时，它将调用`AtlThrow`用 E_OUTOFMEMORY 自变量。  
  
 默认情况下，ATL 转换类和宏用于当前线程的 ANSI 代码页转换。 如果你想要重写特定转换该行为，作为类的构造函数的第二个参数指定代码页。  
  
 下列宏基于此类：  
  
- CA2TEX  
  
- CA2CTEX  
  
- CT2WEX  
  
- CT2CWEX  
  
 以下 typedef 基于此类：  
  
- CA2W  
  
 这些文本转换宏的讨论，请参阅[ATL 和 MFC 字符串转换宏](string-conversion-macros.md)。  
  
## <a name="example"></a>示例  
 请参阅[ATL 和 MFC 字符串转换宏](string-conversion-macros.md)有关使用这些字符串转换宏的示例。  
  
## <a name="requirements"></a>要求  
 **标头：** atlconv.h  
  
##  <a name="ca2wex"></a>  CA2WEX::CA2WEX  
 构造函数。  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>参数  
 *psz*  
 要转换的文本字符串。  
  
 *nCodePage*  
 用来执行转换的代码页。 请参阅 Windows SDK 函数的代码页参数讨论[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)的更多详细信息。  
  
### <a name="remarks"></a>备注  
 分配在转换过程中所使用的缓冲区。  
  
##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX  
 析构函数。  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>备注  
 释放分配的缓冲区。  
  
##  <a name="m_psz"></a>  CA2WEX::m_psz  
 将源字符串存储的数据成员。  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer  
 静态缓冲区，用于存储转换后的字符串。  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CA2WEX::operator LPWSTR  
 转换运算符。  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>返回值  
 返回文本字符串，键入 LPWSTR。  
  
## <a name="see-also"></a>请参阅  
 [CA2AEX 类](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX 类](../../atl/reference/ca2caex-class.md)   
 [CW2AEX 类](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX 类](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX 类](../../atl/reference/cw2wex-class.md)   
 [类概述](../../atl/atl-class-overview.md)
