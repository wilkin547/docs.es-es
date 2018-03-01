---
title: -target (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44dd99ef834f98a1a918c659d3057f8f6f91805a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="6a23b-102">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6a23b-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="6a23b-103">La opción del compilador **-target** se puede especificar en uno de estos cuatro formatos:</span><span class="sxs-lookup"><span data-stu-id="6a23b-103">The **-target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="6a23b-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="6a23b-104">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="6a23b-105">Para crear un archivo .exe para aplicaciones de [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a23b-105">To create an .exe file for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="6a23b-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="6a23b-106">-target:exe</span></span>](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 <span data-ttu-id="6a23b-107">Para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="6a23b-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="6a23b-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="6a23b-108">-target:library</span></span>](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 <span data-ttu-id="6a23b-109">Para crear una biblioteca de código.</span><span class="sxs-lookup"><span data-stu-id="6a23b-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="6a23b-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="6a23b-110">-target:module</span></span>](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 <span data-ttu-id="6a23b-111">Para crear un módulo.</span><span class="sxs-lookup"><span data-stu-id="6a23b-111">To create a module.</span></span>  
  
 [<span data-ttu-id="6a23b-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="6a23b-112">-target:winexe</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 <span data-ttu-id="6a23b-113">Para crear un programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="6a23b-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="6a23b-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="6a23b-114">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 <span data-ttu-id="6a23b-115">Para crear un archivo .winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="6a23b-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="6a23b-116">A menos que se especifique **-target:module**, **-target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="6a23b-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="6a23b-117">Para más información, vea [Ensamblados en Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) y [Atributos comunes](../../programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6a23b-117">For more information, see [Assemblies in the Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) and [Common Attributes](../../programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
 <span data-ttu-id="6a23b-118">El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe.</span><span class="sxs-lookup"><span data-stu-id="6a23b-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="6a23b-119">Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="6a23b-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="6a23b-120">El compilador crea solo un manifiesto de ensamblado por compilación.</span><span class="sxs-lookup"><span data-stu-id="6a23b-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="6a23b-121">La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6a23b-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="6a23b-122">Todos los archivos de salida, excepto los creados con **-target:module**, pueden contener un manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6a23b-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="6a23b-123">Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6a23b-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="6a23b-124">Independientemente de cuál sea el primer archivo de salida (**-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos (**-target:module**).</span><span class="sxs-lookup"><span data-stu-id="6a23b-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="6a23b-125">Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6a23b-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="6a23b-126">Para obtener más información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a23b-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a23b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a23b-127">See Also</span></span>  
 [<span data-ttu-id="6a23b-128">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="6a23b-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="6a23b-129">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="6a23b-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="6a23b-130">-subsystemversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6a23b-130">-subsystemversion (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
