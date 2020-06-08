---
title: Compilar desde la línea de comandos
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: ec6ae3328c2042af950d1ee78a33d3de97219f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414303"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="807e1-102">Compilar desde la línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="807e1-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="807e1-103">Un proyecto de Visual Basic se compone de uno o varios archivos de código fuente independientes.</span><span class="sxs-lookup"><span data-stu-id="807e1-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="807e1-104">Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.</span><span class="sxs-lookup"><span data-stu-id="807e1-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="807e1-105">Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="807e1-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="807e1-106">El compilador de línea de comandos está diseñado para situaciones en las que no se necesita el conjunto completo de características en el IDE; por ejemplo, cuando se usan equipos con memoria de sistema o espacio de almacenamiento limitados, o se escribe para estos equipos.</span><span class="sxs-lookup"><span data-stu-id="807e1-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="807e1-107">Para compilar los archivos de código fuente desde el IDE de Visual Studio, elija el comando **Compilar** en el menú **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="807e1-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="807e1-108">Al compilar archivos de proyecto mediante el IDE de Visual Studio, puede mostrar información acerca del comando **vbc** asociado y sus modificadores en la ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="807e1-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="807e1-109">Para mostrar esta información, abra el [cuadro de diálogo Opciones, Proyectos y soluciones, Compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) y, posteriormente, establezca el **nivel de detalle del resultado de la compilación del proyecto de MSBuild** en **Normal** o en un nivel más alto de detalle.</span><span class="sxs-lookup"><span data-stu-id="807e1-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="807e1-110">Para obtener más información, vea [Cómo: Ver, guardar y configurar archivos de registro de compilación](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="807e1-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="807e1-111">Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante MSBuild.</span><span class="sxs-lookup"><span data-stu-id="807e1-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="807e1-112">Para más información, consulte [Referencia de la línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: Usar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="807e1-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="807e1-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="807e1-113">In This Section</span></span>

<span data-ttu-id="807e1-114">[Cómo: Invocación del compilador de la línea de comandos](how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="807e1-114">[How to: Invoke the Command-Line Compiler](how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="807e1-115">Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema MS-DOS o en un subdirectorio específico.</span><span class="sxs-lookup"><span data-stu-id="807e1-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="807e1-116">[Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="807e1-116">[Sample Compilation Command Lines](sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="807e1-117">Proporciona una lista de líneas de comandos de ejemplo que puede modificar para su propio uso.</span><span class="sxs-lookup"><span data-stu-id="807e1-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="807e1-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="807e1-118">Related Sections</span></span>

<span data-ttu-id="807e1-119">[Compilador de línea de comandos de Visual Basic](index.md) </span><span class="sxs-lookup"><span data-stu-id="807e1-119">[Visual Basic Command-Line Compiler](index.md) </span></span>\
<span data-ttu-id="807e1-120">Proporciona listas de opciones del compilador organizadas en orden alfabético o por finalidad.</span><span class="sxs-lookup"><span data-stu-id="807e1-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="807e1-121">[Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="807e1-121">[Conditional Compilation](../../programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="807e1-122">Describe cómo compilar secciones de código determinadas.</span><span class="sxs-lookup"><span data-stu-id="807e1-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="807e1-123">[Compilar y limpiar proyectos y soluciones en Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="807e1-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="807e1-124">Describe cómo organizar lo que se incluirá en compilaciones diferentes, elegir las propiedades del proyecto y asegurarse de que los proyectos se compilan en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="807e1-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
