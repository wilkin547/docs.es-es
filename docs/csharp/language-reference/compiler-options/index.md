---
description: Opciones del compilador de C#
title: Opciones del compilador de C#
ms.date: 08/28/2020
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: 502bd83ae52be9ae2f914847bb6bf7c7f2a0c411
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271820"
---
# <a name="c-compiler-options"></a><span data-ttu-id="a2d7b-103">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a2d7b-103">C# Compiler Options</span></span>

<span data-ttu-id="a2d7b-104">El compilador genera archivos ejecutables (.exe), archivos de biblioteca de vínculos dinámicos (.dll) o módulos de códigos (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="a2d7b-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="a2d7b-105">Cada opción del compilador está disponible en dos formatos: **-option** y **/option**.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="a2d7b-106">En la documentación solo se muestra el formato **-option**.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="a2d7b-107">En Visual Studio, establecerá las opciones del compilador en el archivo *web.config*.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="a2d7b-108">Para obtener más información, consulte [Elemento \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="a2d7b-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a2d7b-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a2d7b-109">In this section</span></span>

- <span data-ttu-id="a2d7b-110">[Compilación de línea de comandos con csc.exe](command-line-building-with-csc-exe.md): información sobre la compilación de una aplicación de C# desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="a2d7b-111">[Establecimiento de variables de entorno para la línea de comandos de Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md): se proporcionan los pasos para ejecutar *VsDevCmd.bat* con el fin de habilitar compilaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *VsDevCmd.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="a2d7b-112">[Opciones del compilador de C# enumeradas por categoría](listed-by-category.md): una lista de categorías de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="a2d7b-113">[Opciones del compilador de C# enumeradas alfabéticamente](listed-alphabetically.md): una lista alfabética de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a2d7b-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a2d7b-114">Related sections</span></span>

- <span data-ttu-id="a2d7b-115">[Página Compilar del Diseñador de proyectos](/visualstudio/ide/reference/build-page-project-designer-csharp): configuración de las propiedades que regulan la compilación y depuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="a2d7b-116">Incluye información sobre los pasos de compilación personalizada en proyectos de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="a2d7b-117">[Compilaciones predeterminadas y personalizadas](/visualstudio/ide/compiling-and-building-in-visual-studio): información sobre los tipos de compilación y las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="a2d7b-118">[Preparación y administración de compilaciones](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio): procedimientos para compilar en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2d7b-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
