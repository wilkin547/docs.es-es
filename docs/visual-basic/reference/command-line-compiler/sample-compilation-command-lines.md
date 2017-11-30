---
title: "Líneas de comandos de compilación de ejemplo (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="4b62d-102">Líneas de comandos de compilación de ejemplo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b62d-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="4b62d-103">Como alternativa a la compilación [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programas desde [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).</span><span class="sxs-lookup"><span data-stu-id="4b62d-103">As an alternative to compiling [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="4b62d-104">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador de línea de comandos admite un conjunto completo de opciones que controlan los archivos de entrada y salida, los ensamblados y depuración y opciones de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="4b62d-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="4b62d-105">Cada opción está disponible en dos formatos intercambiables: `-``option` y `/``option`.</span><span class="sxs-lookup"><span data-stu-id="4b62d-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="4b62d-106">Esta documentación se muestra solo la `/``option` formulario.</span><span class="sxs-lookup"><span data-stu-id="4b62d-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="4b62d-107">En la tabla siguiente se enumera algunas líneas de comandos de ejemplo que puede modificar para su propio uso.</span><span class="sxs-lookup"><span data-stu-id="4b62d-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="4b62d-108">Para</span><span class="sxs-lookup"><span data-stu-id="4b62d-108">To</span></span>|<span data-ttu-id="4b62d-109">Uso</span><span class="sxs-lookup"><span data-stu-id="4b62d-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="4b62d-110">Compilar File.vb y crear File.exe</span><span class="sxs-lookup"><span data-stu-id="4b62d-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="4b62d-111">Compilar File.vb y crear File.dll</span><span class="sxs-lookup"><span data-stu-id="4b62d-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="4b62d-112">Compilar File.vb y crea My.exe</span><span class="sxs-lookup"><span data-stu-id="4b62d-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="4b62d-113">Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe</span><span class="sxs-lookup"><span data-stu-id="4b62d-113">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="4b62d-114">Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.</span><span class="sxs-lookup"><span data-stu-id="4b62d-114">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="4b62d-115">Todos los compilar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual al archivo algo.dll.</span><span class="sxs-lookup"><span data-stu-id="4b62d-115">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="4b62d-116">Cuando se compila desde la línea de comandos, explícitamente debe hacer referencia a Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] biblioteca en tiempo de ejecución a través de la `/reference` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="4b62d-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4b62d-117">Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando con sus opciones del compilador en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="4b62d-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="4b62d-118">Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="4b62d-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="4b62d-119">Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="4b62d-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b62d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b62d-120">See Also</span></span>  
 [<span data-ttu-id="4b62d-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b62d-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4b62d-122">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="4b62d-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
