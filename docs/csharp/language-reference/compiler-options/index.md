---
title: Opciones del compilador de C#
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: a0affaf3691d2392c9f8d7502204d0122f2ea428
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="c-compiler-options"></a><span data-ttu-id="14fbf-102">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="14fbf-102">C# Compiler Options</span></span>
<span data-ttu-id="14fbf-103">El compilador genera archivos ejecutables (.exe), archivos de biblioteca de vínculos dinámicos (.dll) o módulos de códigos (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="14fbf-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="14fbf-104">Cada opción del compilador está disponible en dos formatos: **-option** y **/option**.</span><span class="sxs-lookup"><span data-stu-id="14fbf-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="14fbf-105">En la documentación solo se muestra el formato **-option**.</span><span class="sxs-lookup"><span data-stu-id="14fbf-105">The documentation only shows the **-option** form.</span></span>  
  
 <span data-ttu-id="14fbf-106">En Visual Studio, establezca las opciones del compilador en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="14fbf-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="14fbf-107">Para más información, vea [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md) (<compilador> Elemento).</span><span class="sxs-lookup"><span data-stu-id="14fbf-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14fbf-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="14fbf-108">In This Section</span></span>  
 [<span data-ttu-id="14fbf-109">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="14fbf-109">Command-line Building With csc.exe</span></span>](command-line-building-with-csc-exe.md)  
 <span data-ttu-id="14fbf-110">Información sobre la creación de una aplicación de Visual C# desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="14fbf-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="14fbf-111">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14fbf-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="14fbf-112">Proporciona los pasos para ejecutar vsvars32.bat para habilitar las compilaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="14fbf-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="14fbf-113">Opciones del compilador de C#, por categoría</span><span class="sxs-lookup"><span data-stu-id="14fbf-113">C# Compiler Options Listed by Category</span></span>](listed-by-category.md)  
 <span data-ttu-id="14fbf-114">Una lista de categorías de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="14fbf-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="14fbf-115">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="14fbf-115">C# Compiler Options Listed Alphabetically</span></span>](listed-alphabetically.md)  
 <span data-ttu-id="14fbf-116">Una lista alfabética de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="14fbf-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14fbf-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="14fbf-117">Related Sections</span></span>  
 [<span data-ttu-id="14fbf-118">Página Compilación, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="14fbf-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="14fbf-119">Configuración de propiedades que controlan cómo se compila, crea y depura el proyecto.</span><span class="sxs-lookup"><span data-stu-id="14fbf-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="14fbf-120">Incluye información sobre los pasos de compilación personalizada en proyectos de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="14fbf-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="14fbf-121">Compilaciones predeterminadas y personalizadas</span><span class="sxs-lookup"><span data-stu-id="14fbf-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="14fbf-122">Información sobre los tipos de compilación y las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="14fbf-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="14fbf-123">Preparar y administrar compilaciones</span><span class="sxs-lookup"><span data-stu-id="14fbf-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="14fbf-124">Procedimientos para compilar en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14fbf-124">Procedures for building within the Visual Studio development environment.</span></span>
