---
title: __vmx_vmptrld |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 599e15414a944602ee196f3910a1c5dd561c906d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324845"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Microsoft 专用**  
  
 从指定的地址加载到当前虚拟机控件结构 (VMCS) 的指针。  
  
## <a name="syntax"></a>语法  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] *`VmcsPhysicalAddress`  
 存储 VMCS 指针的位置的地址。  
  
## <a name="return-value"></a>返回值  
 0  
 操作成功。  
  
 1  
 操作失败，当前 VMCS 的 `VM-instruction error field` 中提供了扩展状态。  
  
 2  
 操作失败，无可用状态。  
  
## <a name="remarks"></a>备注  
 VMCS 指针是一个 64 位物理地址。  
  
 `__vmx_vmptrld`函数等同于`VMPTRLD`计算机指令。 此函数支持主机的虚拟机监视器与来宾操作系统及其应用程序进行交互。 有关详细信息，搜索文档中，"Intel 虚拟化技术规范为 ia-32 Intel 体系结构，"在文档编号 C97063-002， [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)站点。  
  
## <a name="requirements"></a>要求  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)