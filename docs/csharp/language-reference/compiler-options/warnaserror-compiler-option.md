---
description: -warnaserror (Opciones del compilador de C#)
title: -warnaserror (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 9c3b307668968865b401aedc04c79f95d4f32513
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171343"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="df687-103">-warnaserror (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="df687-103">-warnaserror (C# Compiler Options)</span></span>

<span data-ttu-id="df687-104">La opción **-warnaserror+** trata todas las advertencias como errores</span><span class="sxs-lookup"><span data-stu-id="df687-104">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df687-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df687-105">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="df687-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df687-106">Remarks</span></span>  

 <span data-ttu-id="df687-107">Cualquier mensaje que se notificaría de manera normal como una advertencia se notifica en su lugar como un error, y el proceso de compilación se detiene (no se compila ningún archivo de salida).</span><span class="sxs-lookup"><span data-stu-id="df687-107">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="df687-108">De manera predeterminada, **-warnaserror-** está en vigor, lo que provoca que las advertencias no impidan la generación de un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="df687-108">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="df687-109">**-warnaserror**, que es igual que **-warnaserror+**, hace que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="df687-109">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="df687-110">Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.</span><span class="sxs-lookup"><span data-stu-id="df687-110">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="df687-111">Se puede especificar el conjunto de todas las advertencias de nulabilidad con la abreviatura **nullable**.</span><span class="sxs-lookup"><span data-stu-id="df687-111">The set of all nullability warnings can be specified with the **nullable** shorthand.</span></span>
  
 <span data-ttu-id="df687-112">Use [-warn](./warn-compiler-option.md) para especificar el nivel de advertencias que quiere que muestre el compilador.</span><span class="sxs-lookup"><span data-stu-id="df687-112">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="df687-113">Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="df687-113">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="df687-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df687-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="df687-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="df687-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="df687-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="df687-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="df687-117">Modifique la propiedad **Tratar advertencias como errores**.</span><span class="sxs-lookup"><span data-stu-id="df687-117">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="df687-118">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="df687-118">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df687-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df687-119">Example</span></span>  

 <span data-ttu-id="df687-120">Compile `in.cs` y haga que el compilador no muestre ninguna advertencia:</span><span class="sxs-lookup"><span data-stu-id="df687-120">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="df687-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="df687-121">See also</span></span>

- [<span data-ttu-id="df687-122">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="df687-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="df687-123">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="df687-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
