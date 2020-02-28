---
title: -warnaserror (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 7d43941629e933ac5a9e9c9d6a1388b6194f8d99
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503479"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="fece6-102">-warnaserror (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="fece6-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="fece6-103">La opción **-warnaserror+** trata todas las advertencias como errores</span><span class="sxs-lookup"><span data-stu-id="fece6-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fece6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fece6-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="fece6-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fece6-105">Remarks</span></span>  
 <span data-ttu-id="fece6-106">Cualquier mensaje que se notificaría de manera normal como una advertencia se notifica en su lugar como un error, y el proceso de compilación se detiene (no se compila ningún archivo de salida).</span><span class="sxs-lookup"><span data-stu-id="fece6-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="fece6-107">De manera predeterminada, **-warnaserror-** está en vigor, lo que provoca que las advertencias no impidan la generación de un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="fece6-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="fece6-108">**-warnaserror**, que es igual que **-warnaserror+** , hace que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="fece6-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="fece6-109">Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.</span><span class="sxs-lookup"><span data-stu-id="fece6-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="fece6-110">Se puede especificar el conjunto de todas las advertencias de nulabilidad con la abreviatura **nullable**.</span><span class="sxs-lookup"><span data-stu-id="fece6-110">The set of all nullability warnings can be specified with the **nullable** shorthand.</span></span>
  
 <span data-ttu-id="fece6-111">Use [-warn](./warn-compiler-option.md) para especificar el nivel de advertencias que quiere que muestre el compilador.</span><span class="sxs-lookup"><span data-stu-id="fece6-111">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="fece6-112">Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="fece6-112">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="fece6-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fece6-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="fece6-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fece6-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="fece6-115">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fece6-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="fece6-116">Modifique la propiedad **Tratar advertencias como errores**.</span><span class="sxs-lookup"><span data-stu-id="fece6-116">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="fece6-117">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="fece6-117">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fece6-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fece6-118">Example</span></span>  
 <span data-ttu-id="fece6-119">Compile `in.cs` y haga que el compilador no muestre ninguna advertencia:</span><span class="sxs-lookup"><span data-stu-id="fece6-119">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="fece6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fece6-120">See also</span></span>

- [<span data-ttu-id="fece6-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="fece6-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="fece6-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fece6-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
