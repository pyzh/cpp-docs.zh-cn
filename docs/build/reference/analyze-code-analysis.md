---
title: -分析 （代码分析） |Microsoft 文档
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4893f30bae3b29538c8bead637cb4d083087a57b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376580"
---
# <a name="analyze-code-analysis"></a>/analyze（代码分析）

启用代码分析和控制选项。

## <a name="syntax"></a>语法

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>自变量

 /analyze  
 在默认模式下打开分析。 分析输出转到**输出**与其他错误信息类似的窗口。 使用 **/ 分析-** 来显式关闭分析。

 /analyze:WX-  
 指定 **/ 分析： WX-** 意味着代码分析警告不被视为错误使用编译时 **/WX**。 有关详细信息，请参阅 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX（警告级别）](../../build/reference/compiler-option-warning-level.md)。

 /analyze:log `filename`  
 将详细的分析器结果作为 XML 写入由 `filename` 指定的文件。

 /analyze:quiet  
 关闭到的分析器输出**输出**窗口。

 /analyze:stacksize `number`  
 `number`与此选项一起使用的参数指定的大小，以字节为单位的警告的堆栈帧[C6262](/visualstudio/code-quality/c6262)生成。 如果未指定此参数，则默认情况下堆栈帧的大小为 16KB。

 /analyze:max_paths `number`  
 用于此选项的 `number` 参数指定要分析的代码路径的最大数目。 如果未指定此参数，则默认情况下此数目为 256。 值越大，执行的检查越彻底，但分析时间可能会更长。

 /analyze:only  
 通常，编译器在运行分析器后会生成代码并执行更多语法检查。 **/ 分析： 仅**选项将关闭此代码生成传递; 这会使分析速度更快，但不是会发出编译错误和警告已由编译器的代码生成传递发现。 如果程序存在代码生成错误，则分析结果可能不可靠；因此，建议你只有在代码已传递代码生成语法检查且没有错误时才使用此选项。

 / 分析： ruleset `<file_path>.ruleset`  
可以指定哪个规则设置若要分析，包括你可以创建自己的自定义规则集。 当此开关设置时，规则引擎会更加高效，因为它不包括非成员之前运行设置指定的规则。 如果未设置该开关，则引擎将检查所有规则。

附带有 Visual Studio 的 ruleset 位于 **%VSINSTALLDIR%\Team Tools\Static 分析 Tools\Rule 集。**

以下示例自定义规则集告知以检查 C6001 和 C26494 的规则引擎。 可以将此文件的放置任意位置，只要它具有`.ruleset`扩展和你提供自变量中的完整路径。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ 分析： 插件  
在运行时代码分析的一部分，请使指定 PREfast 插件。 LocalEspC.dll 是插件实现与并发相关的代码分析签入的范围的 C261XX 警告。 例如， [C26100](/visualstudio/code-quality/c26100)， [C26101](/visualstudio/code-quality/c26101)，...， [C26167](/visualstudio/code-quality/c26167)。

若要运行 LocalEspC.dll，使用此编译器选项： **/ 分析： 插件 LocalEspC.dll**

若要运行 CppCoreCheck.dll，首先从开发人员命令提示中运行以下命令：

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

然后，使用此编译器选项： **/ 分析： 插件 EspXEngine.dll**。

## <a name="remarks"></a>备注

有关详细信息，请参阅[的代码分析 C/c + + 概述](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)和[的代码分析 C/c + + 警告](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 展开**配置属性**节点。

1. 展开**代码分析**节点。

1. 选择 **“常规”** 属性页。

1. 修改一个或多个**代码分析**属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>。

## <a name="see-also"></a>请参阅

- [编译器选项](../../build/reference/compiler-options.md)
- [设置编译器选项](../../build/reference/setting-compiler-options.md)