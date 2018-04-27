---
title: Líneas de comandos de compilación de ejemplo (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b61ef6facf33fa043cad28a78405a19308a9864f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="9f599-102">Líneas de comandos de compilación de ejemplo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f599-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="9f599-103">Como alternativa a la compilación de programas de Visual Basic desde dentro de Visual Studio, puede compilar desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).</span><span class="sxs-lookup"><span data-stu-id="9f599-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="9f599-104">El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones que controlan entrada y salida de archivos, ensamblados y depuración y opciones de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="9f599-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="9f599-105">Cada opción está disponible en dos formatos intercambiables: `-option` y `/option`.</span><span class="sxs-lookup"><span data-stu-id="9f599-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="9f599-106">Esta documentación se muestra solo la `-option` formulario.</span><span class="sxs-lookup"><span data-stu-id="9f599-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="9f599-107">En la tabla siguiente se enumera algunas líneas de comandos de ejemplo que puede modificar para su propio uso.</span><span class="sxs-lookup"><span data-stu-id="9f599-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="9f599-108">En</span><span class="sxs-lookup"><span data-stu-id="9f599-108">To</span></span>|<span data-ttu-id="9f599-109">Usar</span><span class="sxs-lookup"><span data-stu-id="9f599-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="9f599-110">Compilar File.vb y crear File.exe</span><span class="sxs-lookup"><span data-stu-id="9f599-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="9f599-111">Compilar File.vb y crear File.dll</span><span class="sxs-lookup"><span data-stu-id="9f599-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="9f599-112">Compilar File.vb y crea My.exe</span><span class="sxs-lookup"><span data-stu-id="9f599-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="9f599-113">Compilar File.vb y crear una biblioteca y un ensamblado de referencia denominado File.dll</span><span class="sxs-lookup"><span data-stu-id="9f599-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="9f599-114">Compilar todos los archivos de Visual Basic en el directorio actual, con optimizaciones en y `DEBUG` símbolo definido, generar File2.exe</span><span class="sxs-lookup"><span data-stu-id="9f599-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="9f599-115">Compilar todos los archivos de Visual Basic en el directorio actual, generando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias.</span><span class="sxs-lookup"><span data-stu-id="9f599-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="9f599-116">Compilar todos los archivos de Visual Basic en el directorio actual al archivo algo.dll.</span><span class="sxs-lookup"><span data-stu-id="9f599-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="9f599-117">Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando con sus opciones del compilador en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="9f599-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="9f599-118">Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **nivel de detalle de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="9f599-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="9f599-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f599-119">See Also</span></span>  
 [<span data-ttu-id="9f599-120">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f599-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9f599-121">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="9f599-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
