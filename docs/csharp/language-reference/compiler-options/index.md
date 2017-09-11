---
title: Opciones del compilador de C#
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.options
dev_langs:
- CSharp
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 02cfb7708959057de593506db55e4f31f5ab4fd0
ms.openlocfilehash: 7c5f5274a5685e50fb7f1d06771b0340200d1c3f
ms.contentlocale: es-es
ms.lasthandoff: 08/28/2017

---
# <a name="c-compiler-options"></a><span data-ttu-id="536fe-102">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="536fe-102">C# Compiler Options</span></span>
<span data-ttu-id="536fe-103">El compilador genera archivos ejecutables (.exe), archivos de biblioteca de vínculos dinámicos (.dll) o módulos de códigos (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="536fe-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="536fe-104">Cada opción del compilador está disponible en dos formatos: **-option** y **/option**.</span><span class="sxs-lookup"><span data-stu-id="536fe-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="536fe-105">En la documentación solo se muestra el formato **/option**.</span><span class="sxs-lookup"><span data-stu-id="536fe-105">The documentation only shows the **/option** form.</span></span>  
  
 <span data-ttu-id="536fe-106">En Visual Web Developer 2008, establezca las opciones del compilador en el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="536fe-106">In Visual Web Developer 2008, you set compiler options in the web.config file.</span></span> <span data-ttu-id="536fe-107">Para más información, vea [\<compiler> Element](https://msdn.microsoft.com/library/y9x69bzw) (<compilador> Elemento).</span><span class="sxs-lookup"><span data-stu-id="536fe-107">For more information, see [\<compiler> Element](https://msdn.microsoft.com/library/y9x69bzw).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="536fe-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="536fe-108">In This Section</span></span>  
 [<span data-ttu-id="536fe-109">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="536fe-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 <span data-ttu-id="536fe-110">Información sobre la creación de una aplicación de Visual C# desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="536fe-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="536fe-111">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="536fe-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="536fe-112">Proporciona los pasos para ejecutar vsvars32.bat para habilitar las compilaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="536fe-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="536fe-113">Opciones del compilador de C#, por categoría</span><span class="sxs-lookup"><span data-stu-id="536fe-113">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 <span data-ttu-id="536fe-114">Una lista de categorías de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="536fe-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="536fe-115">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="536fe-115">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 <span data-ttu-id="536fe-116">Una lista alfabética de las opciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="536fe-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="536fe-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="536fe-117">Related Sections</span></span>  
 [<span data-ttu-id="536fe-118">Página Compilación, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="536fe-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="536fe-119">Configuración de propiedades que controlan cómo se compila, crea y depura el proyecto.</span><span class="sxs-lookup"><span data-stu-id="536fe-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="536fe-120">Incluye información sobre los pasos de compilación personalizada en proyectos de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="536fe-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="536fe-121">Compilaciones predeterminadas y personalizadas</span><span class="sxs-lookup"><span data-stu-id="536fe-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="536fe-122">Información sobre los tipos de compilación y las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="536fe-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="536fe-123">Preparar y administrar compilaciones</span><span class="sxs-lookup"><span data-stu-id="536fe-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="536fe-124">Procedimientos para compilar en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="536fe-124">Procedures for building within the Visual Studio development environment.</span></span>

