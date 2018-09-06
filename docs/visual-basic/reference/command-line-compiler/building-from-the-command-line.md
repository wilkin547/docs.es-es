---
title: Compilar desde la línea de comandos (Visual Basic)
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
ms.openlocfilehash: 89bcd6e0e7c1cc867bf853dc9bbe96628942ace2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43867006"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="b956f-102">Compilar desde la línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b956f-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="b956f-103">Un proyecto de Visual Basic se compone de uno o varios archivos de código fuente independiente.</span><span class="sxs-lookup"><span data-stu-id="b956f-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="b956f-104">Durante el proceso conocido como compilación, estos archivos se reúnen en un paquete, un único archivo ejecutable que se puede ejecutar como una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b956f-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="b956f-105">Visual Basic proporciona un compilador de línea de comandos como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b956f-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="b956f-106">El compilador de línea de comandos está diseñado para situaciones en las que no es necesario el conjunto completo de características del IDE, por ejemplo, cuando se están utilizando o escribir en los equipos con sistema limitados memoria o espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b956f-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="b956f-107">Para compilar archivos de origen desde el IDE de Visual Studio, elija el **compilar** comando desde el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="b956f-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b956f-108">Al compilar los archivos de proyecto utilizando el IDE de Visual Studio, puede mostrar información acerca de los asociados **vbc** comando y sus modificadores en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="b956f-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="b956f-109">Para mostrar esta información, abra el [cuadro de diálogo Opciones, proyectos y soluciones, compilación y ejecución](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)y, a continuación, establezca el **detalles de la salida de compilación del proyecto de MSBuild** a **Normal** o un mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="b956f-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="b956f-110">Para obtener más información, consulte [Cómo: Ver, guardar y configurar archivos de registro de compilación](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="b956f-110">For more information, see [How to: View, Save, and Configure Build Log Files](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="b956f-111">Puede compilar archivos de proyecto (.vbproj) en un símbolo del sistema mediante el uso de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b956f-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="b956f-112">Para obtener más información, consulte [referencia de línea de comandos](/visualstudio/msbuild/msbuild-command-line-reference) y [Tutorial: utilizar MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="b956f-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b956f-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b956f-113">In This Section</span></span>  
 [<span data-ttu-id="b956f-114">Invocar al compilador de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b956f-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="b956f-115">Describe cómo invocar el compilador de línea de comandos en el símbolo del sistema de MS-DOS o de un subdirectorio específico.</span><span class="sxs-lookup"><span data-stu-id="b956f-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="b956f-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b956f-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="b956f-117">Proporciona una lista de líneas de comandos de ejemplo que se pueden modificar para su propio uso.</span><span class="sxs-lookup"><span data-stu-id="b956f-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b956f-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b956f-118">Related Sections</span></span>  
 [<span data-ttu-id="b956f-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b956f-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="b956f-120">Proporciona listas de opciones del compilador, organizadas alfabéticamente o por propósito.</span><span class="sxs-lookup"><span data-stu-id="b956f-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="b956f-121">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="b956f-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="b956f-122">Describe cómo compilar secciones concretas del código.</span><span class="sxs-lookup"><span data-stu-id="b956f-122">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="b956f-123">Compilar y limpiar proyectos y soluciones en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b956f-123">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="b956f-124">Describe cómo organizar, lo que se incluirán en diferentes compilaciones, elija las propiedades del proyecto y asegúrese de que los proyectos se compilan en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="b956f-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
