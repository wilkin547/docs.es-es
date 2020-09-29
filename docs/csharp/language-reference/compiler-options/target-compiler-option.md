---
description: -target (Opciones del compilador de C#)
title: -target (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: bcae4b64bdd2a939e35666a9068611b273c261da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188426"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="ac659-103">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ac659-103">-target (C# Compiler Options)</span></span>

<span data-ttu-id="ac659-104">La opción del compilador **-target** se puede especificar en uno de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac659-104">The **-target** compiler option can be specified in one of the following forms:</span></span>  
  
 [<span data-ttu-id="ac659-105">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="ac659-105">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="ac659-106">Para crear un archivo .exe para aplicaciones de la Tienda Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="ac659-106">To create an .exe file for Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="ac659-107">/target:exe</span><span class="sxs-lookup"><span data-stu-id="ac659-107">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="ac659-108">Para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="ac659-108">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="ac659-109">/target:library</span><span class="sxs-lookup"><span data-stu-id="ac659-109">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="ac659-110">Para crear una biblioteca de código.</span><span class="sxs-lookup"><span data-stu-id="ac659-110">To create a code library.</span></span>  
  
 [<span data-ttu-id="ac659-111">/target:module</span><span class="sxs-lookup"><span data-stu-id="ac659-111">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="ac659-112">Para crear un módulo.</span><span class="sxs-lookup"><span data-stu-id="ac659-112">To create a module.</span></span>  
  
 [<span data-ttu-id="ac659-113">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="ac659-113">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="ac659-114">Para crear un programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac659-114">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="ac659-115">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="ac659-115">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="ac659-116">Para crear un archivo .winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="ac659-116">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="ac659-117">A menos que se especifique **-target:module**, **-target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="ac659-117">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="ac659-118">Para obtener más información, vea [Ensamblados en .NET](../../../standard/assembly/index.md) y [Atributos comunes](../attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="ac659-118">For more information, see [Assemblies in .NET](../../../standard/assembly/index.md) and [Common Attributes](../attributes/global.md).</span></span>  
  
 <span data-ttu-id="ac659-119">El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe.</span><span class="sxs-lookup"><span data-stu-id="ac659-119">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="ac659-120">Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="ac659-120">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="ac659-121">El compilador crea solo un manifiesto de ensamblado por compilación.</span><span class="sxs-lookup"><span data-stu-id="ac659-121">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="ac659-122">La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac659-122">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="ac659-123">Todos los archivos de salida, excepto los creados con **-target:module**, pueden contener un manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac659-123">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="ac659-124">Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ac659-124">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="ac659-125">Independientemente de cuál sea el primer archivo de salida ( **-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos ( **-target:module**).</span><span class="sxs-lookup"><span data-stu-id="ac659-125">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="ac659-126">Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ac659-126">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="ac659-127">Para obtener más información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac659-127">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac659-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac659-128">See also</span></span>

- [<span data-ttu-id="ac659-129">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ac659-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ac659-130">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="ac659-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="ac659-131">-subsystemversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ac659-131">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
