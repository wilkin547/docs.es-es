---
title: "Organización del proyecto para admitir .NET Framework y .NET Core"
description: "Ayuda para los propietarios del proyecto que quieren compilar su solución en .NET Framework y en .NET Core, en paralelo."
keywords: ".NET, .NET Core, .NET Framework, diseño del proyecto, varios marcos"
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 93bec65e3bbee93855d6f5bce5e2d6cea8bb9f3d
ms.contentlocale: es-es
ms.lasthandoff: 08/11/2017

---

# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="a81ad-104">Organización del proyecto para admitir .NET Framework y .NET Core</span><span class="sxs-lookup"><span data-stu-id="a81ad-104">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="a81ad-105">En este artículo se ofrece ayuda a los propietarios del proyecto que quieren compilar su solución en .NET Framework y en .NET Core, en paralelo.</span><span class="sxs-lookup"><span data-stu-id="a81ad-105">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="a81ad-106">Se proporcionan varias opciones para organizar los proyectos a fin de permitir que los desarrolladores alcancen este objetivo.</span><span class="sxs-lookup"><span data-stu-id="a81ad-106">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="a81ad-107">En la lista siguiente se proporcionan algunos escenarios típicos que debe considerar cuando decida cómo va a configurar el diseño del proyecto con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a81ad-107">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="a81ad-108">Es posible que la lista no abarque todos los aspectos que quiere, pero debe darles prioridad en función de las necesidades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a81ad-108">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="a81ad-109">[**Combinar los proyectos existentes y los proyectos de .NET Core en proyectos únicos**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="a81ad-109">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="a81ad-110">*Para qué se usa:*</span><span class="sxs-lookup"><span data-stu-id="a81ad-110">*What this is good for:*</span></span>
  * <span data-ttu-id="a81ad-111">Para simplificar el proceso de compilación mediante la compilación de un proyecto único en lugar de compilar varios proyectos, donde cada uno de ellos tiene como destino una plataforma o versión distinta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a81ad-111">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="a81ad-112">Simplifique la administración de archivos de origen en proyectos con compatibilidad con múltiples versiones, porque debe administrar un solo archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a81ad-112">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="a81ad-113">Cuando agrega o quita archivos de origen, las alternativas requieren que los sincronice manualmente con los otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="a81ad-113">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="a81ad-114">Para generar fácilmente un paquete NuGet para consumo.</span><span class="sxs-lookup"><span data-stu-id="a81ad-114">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="a81ad-115">Le permite escribir código para una versión específica de .NET Framework en las bibliotecas a través del uso de directivas de compilador.</span><span class="sxs-lookup"><span data-stu-id="a81ad-115">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="a81ad-116">*Escenarios no admitidos:*</span><span class="sxs-lookup"><span data-stu-id="a81ad-116">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="a81ad-117">Se necesita que los desarrolladores que usan Visual Studio 2017 abran los proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="a81ad-117">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="a81ad-118">Para admitir versiones anteriores de Visual Studio, una opción mejor es [mantener los archivos de proyecto en distintas carpetas](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="a81ad-118">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <span data-ttu-id="a81ad-119"><a name="support-vs"></a>[**Mantener separados los proyectos existentes y los proyectos de .NET Core nuevos**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="a81ad-119"><a name="support-vs"></a>[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="a81ad-120">*Para qué se usa:*</span><span class="sxs-lookup"><span data-stu-id="a81ad-120">*What this is good for:*</span></span>
  * <span data-ttu-id="a81ad-121">Para mantener la compatibilidad con el desarrollo en proyectos existentes sin tener que hacer una actualización para los desarrolladores o colaboradores que posiblemente no tengan Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a81ad-121">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="a81ad-122">Para disminuir la posibilidad de generar nuevos errores en proyectos existentes porque esos proyectos no requieren renovación de código.</span><span class="sxs-lookup"><span data-stu-id="a81ad-122">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="a81ad-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a81ad-123">Example</span></span>

<span data-ttu-id="a81ad-124">Considere el siguiente repositorio:</span><span class="sxs-lookup"><span data-stu-id="a81ad-124">Consider the repository below:</span></span>

<span data-ttu-id="a81ad-125">![Proyecto existente][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="a81ad-125">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="a81ad-126">[**Código fuente**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="a81ad-126">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="a81ad-127">A continuación se describen varias formas de agregar compatibilidad para .NET Core para este repositorio en función de las restricciones y la complejidad de los proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="a81ad-127">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="a81ad-128">Reemplazo de proyectos existentes por un proyecto .NET Core con compatibilidad con múltiples versiones</span><span class="sxs-lookup"><span data-stu-id="a81ad-128">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="a81ad-129">Reorganice el repositorio de manera que se quite cualquier archivo *\*.csproj* existente y se cree un archivo *\*.csproj* único que establezca varios marcos de trabajo como destino.</span><span class="sxs-lookup"><span data-stu-id="a81ad-129">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="a81ad-130">Esta es una opción excelente, porque un proyecto único se puede compilar para distintos marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a81ad-130">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="a81ad-131">También tiene la capacidad de controlar distintas dependencias y opciones de compilación por cada marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="a81ad-131">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="a81ad-132">![Creación de un csproj con varios marcos de destino][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="a81ad-132">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="a81ad-133">[**Código fuente**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="a81ad-133">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="a81ad-134">Los cambios que debe tener en cuenta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a81ad-134">Changes to note are:</span></span>
* <span data-ttu-id="a81ad-135">Reemplazo de *packages.config* y *\*.csproj* por un nuevo [.NET Core *\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="a81ad-135">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="a81ad-136">Los paquetes NuGet se especifican con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="a81ad-136">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="a81ad-137">Mantenimiento de los proyectos existentes y creación de un proyecto .NET Core</span><span class="sxs-lookup"><span data-stu-id="a81ad-137">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="a81ad-138">Si hay proyectos existentes que tienen como destino marcos de trabajo anteriores, puede que desee dejarlos intactos y usar un proyecto .NET Core para establecer como destino marcos de trabajo futuros.</span><span class="sxs-lookup"><span data-stu-id="a81ad-138">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="a81ad-139">![Proyecto .NET Core con un proyecto existente en una carpeta distinta][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="a81ad-139">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="a81ad-140">[**Código fuente**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="a81ad-140">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="a81ad-141">Los cambios que debe tener en cuenta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a81ad-141">Changes to note are:</span></span>
* <span data-ttu-id="a81ad-142">.NET Core y los proyectos existentes se mantienen en carpetas independientes.</span><span class="sxs-lookup"><span data-stu-id="a81ad-142">The .NET Core and existing projects are kept in separate folders.</span></span>
    * <span data-ttu-id="a81ad-143">Mantener los proyectos en carpetas independientes evita que sea necesario tener Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a81ad-143">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="a81ad-144">Puede crear una solución independiente que solo abra los proyectos anteriores.</span><span class="sxs-lookup"><span data-stu-id="a81ad-144">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a81ad-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a81ad-145">See Also</span></span>

<span data-ttu-id="a81ad-146">Vea la [documentación sobre el traslado de .NET Core][porting-doc] para obtener más orientación sobre cómo migrar a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a81ad-146">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
<span data-ttu-id="a81ad-147">[example-initial-project]: media/project-structure/project.png "Proyecto existente"</span><span class="sxs-lookup"><span data-stu-id="a81ad-147">[example-initial-project]: media/project-structure/project.png "Existing project"</span></span>
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

<span data-ttu-id="a81ad-148">[example-csproj]: media/project-structure/project.csproj.png "Creación de un csproj con varios marcos de destino"</span><span class="sxs-lookup"><span data-stu-id="a81ad-148">[example-csproj]: media/project-structure/project.csproj.png "Create an csproj that targets multiple frameworks"</span></span>
[example-csproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

<span data-ttu-id="a81ad-149">[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Proyecto .NET Core con PCL existente en una carpeta distinta"</span><span class="sxs-lookup"><span data-stu-id="a81ad-149">[example-csproj-different-folder]: media/project-structure/project.csproj.different.png ".NET Core project with existing PCL in different folder"</span></span>
[example-csproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project

