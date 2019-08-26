---
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
ms.openlocfilehash: 0630639433aed4c8dfddbf0144e9802ed3f4ee73
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606452"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="e87ff-102">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e87ff-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="e87ff-103">La opción del compilador **-target** se puede especificar en uno de estos cuatro formatos:</span><span class="sxs-lookup"><span data-stu-id="e87ff-103">The **-target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="e87ff-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="e87ff-104">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="e87ff-105">Para crear un archivo .exe para aplicaciones de [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e87ff-105">To create an .exe file for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="e87ff-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="e87ff-106">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="e87ff-107">Para crear un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="e87ff-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="e87ff-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="e87ff-108">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="e87ff-109">Para crear una biblioteca de código.</span><span class="sxs-lookup"><span data-stu-id="e87ff-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="e87ff-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="e87ff-110">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="e87ff-111">Para crear un módulo.</span><span class="sxs-lookup"><span data-stu-id="e87ff-111">To create a module.</span></span>  
  
 [<span data-ttu-id="e87ff-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="e87ff-112">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="e87ff-113">Para crear un programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="e87ff-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="e87ff-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="e87ff-114">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="e87ff-115">Para crear un archivo .winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="e87ff-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="e87ff-116">A menos que se especifique **-target:module**, **-target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e87ff-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="e87ff-117">Para más información, vea [Ensamblados en Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) y [Atributos comunes](../../programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-117">For more information, see [Assemblies in the Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) and [Common Attributes](../../programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
 <span data-ttu-id="e87ff-118">El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe.</span><span class="sxs-lookup"><span data-stu-id="e87ff-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="e87ff-119">Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="e87ff-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="e87ff-120">El compilador crea solo un manifiesto de ensamblado por compilación.</span><span class="sxs-lookup"><span data-stu-id="e87ff-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="e87ff-121">La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e87ff-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="e87ff-122">Todos los archivos de salida, excepto los creados con **-target:module**, pueden contener un manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e87ff-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="e87ff-123">Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e87ff-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="e87ff-124">Independientemente de cuál sea el primer archivo de salida ( **-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos ( **-target:module**).</span><span class="sxs-lookup"><span data-stu-id="e87ff-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="e87ff-125">Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e87ff-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="e87ff-126">Para obtener más información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="e87ff-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87ff-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e87ff-127">See also</span></span>

- [<span data-ttu-id="e87ff-128">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e87ff-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e87ff-129">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e87ff-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e87ff-130">-subsystemversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e87ff-130">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
