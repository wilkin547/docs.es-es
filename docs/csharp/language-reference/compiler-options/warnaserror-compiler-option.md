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
ms.openlocfilehash: 66c78ee56c9d5153b5b878b2e695ad4ee6bffe0b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606251"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="8efb9-102">-warnaserror (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="8efb9-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="8efb9-103">La opción **-warnaserror+** trata todas las advertencias como errores</span><span class="sxs-lookup"><span data-stu-id="8efb9-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8efb9-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="8efb9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8efb9-105">Remarks</span></span>  
 <span data-ttu-id="8efb9-106">Cualquier mensaje que se notificaría de manera normal como una advertencia se notifica en su lugar como un error, y el proceso de compilación se detiene (no se compila ningún archivo de salida).</span><span class="sxs-lookup"><span data-stu-id="8efb9-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="8efb9-107">De manera predeterminada, **-warnaserror-** está en vigor, lo que provoca que las advertencias no impidan la generación de un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="8efb9-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="8efb9-108">**-warnaserror**, que es igual que **-warnaserror+** , hace que las advertencias se traten como errores.</span><span class="sxs-lookup"><span data-stu-id="8efb9-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="8efb9-109">Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.</span><span class="sxs-lookup"><span data-stu-id="8efb9-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="8efb9-110">Use [-warn](./warn-compiler-option.md) para especificar el nivel de advertencias que quiere que muestre el compilador.</span><span class="sxs-lookup"><span data-stu-id="8efb9-110">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="8efb9-111">Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="8efb9-111">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8efb9-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8efb9-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="8efb9-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8efb9-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="8efb9-114">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="8efb9-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="8efb9-115">Modifique la propiedad **Tratar advertencias como errores**.</span><span class="sxs-lookup"><span data-stu-id="8efb9-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="8efb9-116">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="8efb9-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8efb9-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8efb9-117">Example</span></span>  
 <span data-ttu-id="8efb9-118">Compile `in.cs` y haga que el compilador no muestre ninguna advertencia:</span><span class="sxs-lookup"><span data-stu-id="8efb9-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8efb9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8efb9-119">See also</span></span>

- [<span data-ttu-id="8efb9-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="8efb9-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="8efb9-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="8efb9-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
