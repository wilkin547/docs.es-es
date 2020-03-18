---
title: -define (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 4a3622b6acc8ebe9c590b01b67074ae59396fc34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173749"
---
# <a name="-define-c-compiler-options"></a><span data-ttu-id="0c0b6-102">-define (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0c0b6-102">-define (C# Compiler Options)</span></span>
<span data-ttu-id="0c0b6-103">La opción **-define** define `name` como un símbolo en todos los archivos de código fuente de su programa.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-103">The **-define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c0b6-104">Syntax</span></span>  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c0b6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c0b6-105">Arguments</span></span>  
 <span data-ttu-id="0c0b6-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="0c0b6-106">`name`, `name2`</span></span>  
 <span data-ttu-id="0c0b6-107">El nombre de uno o más símbolos que quiere definir.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c0b6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c0b6-108">Remarks</span></span>  
 <span data-ttu-id="0c0b6-109">La opción **-define** provoca el mismo efecto que usar una directiva del preprocesador [#define](../preprocessor-directives/preprocessor-define.md), salvo que la opción del compilador está en vigor para todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-109">The **-define** option has the same effect as using a [#define](../preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="0c0b6-110">Un símbolo permanece definido en un archivo de origen hasta que una directiva [#undef](../preprocessor-directives/preprocessor-undef.md) en el archivo de origen quita la definición.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-110">A symbol remains defined in a source file until an [#undef](../preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="0c0b6-111">Cuando usa la opción -define, una directiva `#undef` en un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-111">When you use the -define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="0c0b6-112">Los símbolos creados por esta opción se pueden usar con [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md) y [#endif](../preprocessor-directives/preprocessor-endif.md) para compilar los archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-112">You can use symbols created by this option with [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), and [#endif](../preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="0c0b6-113">**-d** es la forma abreviada de **-define**.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-113">**-d** is the short form of **-define**.</span></span>  
  
 <span data-ttu-id="0c0b6-114">Se pueden definir varios símbolos con **-define** mediante un punto y coma o una coma para separar los nombres de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-114">You can define multiple symbols with **-define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="0c0b6-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c0b6-115">For example:</span></span>  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="0c0b6-116">El propio compilador de C# no define ningún símbolo o macro que puede usar en su código fuente; todas las definiciones de símbolo deben definirse por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c0b6-117">El valor `#define` de C# no permite que se le proporcione un valor a un símbolo; como en lenguajes como C++.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="0c0b6-118">Por ejemplo, `#define` no puede usarse para crear una macro o para definir una constante.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="0c0b6-119">Si necesita definir una constante, use una variable `enum`.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="0c0b6-120">Si quiere crear una macro de estilo de C++, considere alternativas como genéricos.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="0c0b6-121">Como las macros son notoriamente propensas a errores, C# deshabilita su uso pero proporciona alternativas más seguras.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0c0b6-122">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c0b6-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="0c0b6-123">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-123">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="0c0b6-124">En la pestaña **Compilar**, escriba el símbolo que va a definirse en el cuadro **Símbolos de compilación condicional**.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="0c0b6-125">Por ejemplo, si está usando el ejemplo de código siguiente, simplemente escriba `xx` en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="0c0b6-126">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c0b6-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c0b6-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c0b6-127">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c0b6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c0b6-128">See also</span></span>

- [<span data-ttu-id="0c0b6-129">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="0c0b6-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="0c0b6-130">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="0c0b6-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
