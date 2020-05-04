---
title: Líneas de comandos de compilación de ejemplo
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350853"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="8f107-102">Líneas de comandos de compilación de ejemplo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f107-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="8f107-103">Como alternativa a la compilación de programas de Visual Basic desde Visual Studio, se pueden realizar compilaciones desde la línea de comandos para generar archivos ejecutables (.exe) o archivos de biblioteca de vínculos dinámicos (.dll).</span><span class="sxs-lookup"><span data-stu-id="8f107-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="8f107-104">El compilador de línea de comandos de Visual Basic admite un conjunto completo de opciones con las que se controlan los archivos de entrada y salida, los ensamblados y las opciones de depuración y preprocesador.</span><span class="sxs-lookup"><span data-stu-id="8f107-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="8f107-105">Cada opción está disponible en dos formas intercambiables: `-option` y `/option`.</span><span class="sxs-lookup"><span data-stu-id="8f107-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="8f107-106">En esta documentación solo se muestra la forma `-option`.</span><span class="sxs-lookup"><span data-stu-id="8f107-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="8f107-107">En la siguiente tabla se muestran algunas líneas de comandos de ejemplo que puede modificar para uso propio.</span><span class="sxs-lookup"><span data-stu-id="8f107-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="8f107-108">En</span><span class="sxs-lookup"><span data-stu-id="8f107-108">To</span></span>|<span data-ttu-id="8f107-109">Usar</span><span class="sxs-lookup"><span data-stu-id="8f107-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="8f107-110">Compilar File.vb y crear File.exe</span><span class="sxs-lookup"><span data-stu-id="8f107-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="8f107-111">Compilar File.vb y crear File.dll</span><span class="sxs-lookup"><span data-stu-id="8f107-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="8f107-112">Compilar File.vb y crear My.exe</span><span class="sxs-lookup"><span data-stu-id="8f107-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="8f107-113">Compilar File.vb y crear una biblioteca y un ensamblado de referencia llamado File.dll</span><span class="sxs-lookup"><span data-stu-id="8f107-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="8f107-114">Compilar todos los archivos de Visual Basic del directorio actual, con las optimizaciones activadas y el símbolo `DEBUG` definido, creando así File2.exe</span><span class="sxs-lookup"><span data-stu-id="8f107-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="8f107-115">Compilar todos los archivos de Visual Basic del directorio actual, creando una versión de depuración de File2.dll sin mostrar el logotipo ni advertencias</span><span class="sxs-lookup"><span data-stu-id="8f107-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="8f107-116">Compilar todos los archivos de Visual Basic del directorio actual en un archivo Something.dll</span><span class="sxs-lookup"><span data-stu-id="8f107-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="8f107-117">Cuando se compila un proyecto con el IDE de Visual Studio, se puede mostrar información sobre el comando asociado **vbc** con sus opciones de compilador en la ventana salida.</span><span class="sxs-lookup"><span data-stu-id="8f107-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="8f107-118">Para ver esta información, abra el cuadro de diálogo [Opciones - Proyectos y soluciones - Compilar y ejecutar](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) y establezca **Detalles de la salida de la compilación del proyecto de MSBuild** en **Normal** o en un nivel de detalle más alto.</span><span class="sxs-lookup"><span data-stu-id="8f107-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f107-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f107-119">See also</span></span>

- [<span data-ttu-id="8f107-120">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f107-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8f107-121">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="8f107-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
