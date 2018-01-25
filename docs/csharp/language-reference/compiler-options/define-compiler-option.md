---
title: -define (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 273437a4250a393274fa20ad4c02b61dce35ed34
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-define-c-compiler-options"></a><span data-ttu-id="dd0bd-102">-define (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="dd0bd-102">-define (C# Compiler Options)</span></span>
<span data-ttu-id="dd0bd-103">La opción **-define** define `name` como un símbolo en todos los archivos de código fuente de su programa.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-103">The **-define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd0bd-104">Syntax</span></span>  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd0bd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dd0bd-105">Arguments</span></span>  
 <span data-ttu-id="dd0bd-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="dd0bd-106">`name`, `name2`</span></span>  
 <span data-ttu-id="dd0bd-107">El nombre de uno o más símbolos que quiere definir.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd0bd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd0bd-108">Remarks</span></span>  
 <span data-ttu-id="dd0bd-109">La opción **-define** provoca el mismo efecto que usar una directiva del preprocesador [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), salvo que la opción del compilador está en vigor para todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-109">The **-define** option has the same effect as using a [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="dd0bd-110">Un símbolo permanece definido en un archivo de origen hasta que una directiva [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) en el archivo de origen quita la definición.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-110">A symbol remains defined in a source file until an [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="dd0bd-111">Cuando usa la opción -define, una directiva `#undef` en un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-111">When you use the -define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="dd0bd-112">Los símbolos creados por esta opción se pueden usar con [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) y [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) para compilar los archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-112">You can use symbols created by this option with [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), and [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="dd0bd-113">**-d** es la forma abreviada de **-define**.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-113">**-d** is the short form of **-define**.</span></span>  
  
 <span data-ttu-id="dd0bd-114">Se pueden definir varios símbolos con **-define** mediante un punto y coma o una coma para separar los nombres de símbolos.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-114">You can define multiple symbols with **-define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="dd0bd-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd0bd-115">For example:</span></span>  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="dd0bd-116">El propio compilador de C# no define ningún símbolo o macro que puede usar en su código fuente; todas las definiciones de símbolo deben definirse por el usuario.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd0bd-117">El valor `#define` de C# no permite que se le proporcione un valor a un símbolo; como en lenguajes como C++.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="dd0bd-118">Por ejemplo, `#define` no puede usarse para crear una macro o para definir una constante.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="dd0bd-119">Si necesita definir una constante, use una variable `enum`.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="dd0bd-120">Si quiere crear una macro de estilo de C++, considere alternativas como genéricos.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="dd0bd-121">Como las macros son notoriamente propensas a errores, C# deshabilita su uso pero proporciona alternativas más seguras.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dd0bd-122">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dd0bd-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="dd0bd-123">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-123">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="dd0bd-124">En la pestaña **Compilar**, escriba el símbolo que va a definirse en el cuadro **Símbolos de compilación condicional**.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="dd0bd-125">Por ejemplo, si está usando el ejemplo de código siguiente, simplemente escriba `xx` en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="dd0bd-126">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd0bd-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd0bd-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd0bd-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd0bd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd0bd-128">See Also</span></span>  
 [<span data-ttu-id="dd0bd-129">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="dd0bd-129">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="dd0bd-130">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="dd0bd-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
