---
title: Organización de proyectos para .NET Framework y .NET Core
description: Ayuda para los propietarios del proyecto que quieren compilar su solución en .NET Framework y en .NET Core, en paralelo.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 701aa64be8d6c712ef635411ad6c226a3c3ab8ed
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522972"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="ecbaf-103">Organización del proyecto para admitir .NET Framework y .NET Core</span><span class="sxs-lookup"><span data-stu-id="ecbaf-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="ecbaf-104">Aprenda a crear una solución que se compila para .NET Framework y .NET Core en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="ecbaf-105">Consulte varias opciones para organizar los proyectos para alcanzar este objetivo.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="ecbaf-106">Los siguientes son algunos escenarios típicos que debe considerar cuando decida cómo va a configurar el diseño del proyecto con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="ecbaf-107">Es posible que la lista no abarque todos los aspectos que quiere, pero debe darles prioridad en función de las necesidades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="ecbaf-108">**Combinar los proyectos existentes y los proyectos de .NET Core en proyectos únicos**</span><span class="sxs-lookup"><span data-stu-id="ecbaf-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="ecbaf-109">*Para qué se usa:*</span><span class="sxs-lookup"><span data-stu-id="ecbaf-109">*What this is good for:*</span></span>
  - <span data-ttu-id="ecbaf-110">Para simplificar el proceso de compilación mediante la compilación de un proyecto único en lugar de compilar varios proyectos, donde cada uno de ellos tiene como destino una plataforma o versión distinta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="ecbaf-111">Simplifique la administración de archivos de origen en proyectos con compatibilidad con múltiples versiones, porque debe administrar un solo archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="ecbaf-112">Cuando agrega o quita archivos de origen, las alternativas requieren que los sincronice manualmente con los otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="ecbaf-113">Para generar fácilmente un paquete NuGet para consumo.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-113">Easily generating a NuGet package for consumption.</span></span>
  - <span data-ttu-id="ecbaf-114">Le permite escribir código para una versión específica de .NET Framework en las bibliotecas a través del uso de directivas de compilador.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="ecbaf-115">*Escenarios no admitidos:*</span><span class="sxs-lookup"><span data-stu-id="ecbaf-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="ecbaf-116">Se necesita que los desarrolladores que usan Visual Studio 2017 abran los proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="ecbaf-117">Para admitir versiones anteriores de Visual Studio, una opción mejor es [mantener los archivos de proyecto en distintas carpetas](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="ecbaf-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="ecbaf-118">[**Mantener separados los proyectos existentes y los proyectos de .NET Core nuevos**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="ecbaf-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="ecbaf-119">*Para qué se usa:*</span><span class="sxs-lookup"><span data-stu-id="ecbaf-119">*What this is good for:*</span></span>
  - <span data-ttu-id="ecbaf-120">Para mantener la compatibilidad con el desarrollo en proyectos existentes sin tener que hacer una actualización para los desarrolladores o colaboradores que posiblemente no tengan Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  - <span data-ttu-id="ecbaf-121">Para disminuir la posibilidad de generar nuevos errores en proyectos existentes porque esos proyectos no requieren renovación de código.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="ecbaf-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecbaf-122">Example</span></span>

<span data-ttu-id="ecbaf-123">Considere el siguiente repositorio:</span><span class="sxs-lookup"><span data-stu-id="ecbaf-123">Consider the repository below:</span></span>

![Proyecto existente](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="ecbaf-125">**Código fuente**</span><span class="sxs-lookup"><span data-stu-id="ecbaf-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="ecbaf-126">A continuación se describen varias formas de agregar compatibilidad para .NET Core para este repositorio en función de las restricciones y la complejidad de los proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="ecbaf-127">Reemplazo de proyectos existentes por un proyecto .NET Core con compatibilidad con múltiples versiones</span><span class="sxs-lookup"><span data-stu-id="ecbaf-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="ecbaf-128">Reorganice el repositorio de manera que se quite cualquier archivo *\*.csproj* existente y se cree un archivo *\*.csproj* único que establezca varios marcos de trabajo como destino.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="ecbaf-129">Esta es una opción excelente, porque un proyecto único se puede compilar para distintos marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="ecbaf-130">También tiene la capacidad de controlar distintas dependencias y opciones de compilación por cada marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![Creación de un csproj con varios marcos de destino](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="ecbaf-132">**Código fuente**</span><span class="sxs-lookup"><span data-stu-id="ecbaf-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="ecbaf-133">Los cambios que debe tener en cuenta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecbaf-133">Changes to note are:</span></span>

- <span data-ttu-id="ecbaf-134">Se reemplazan *packages.config* y *\*.csproj* con un nuevo archivo [ *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj) de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="ecbaf-135">Los paquetes NuGet se especifican con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="ecbaf-136">Mantenimiento de los proyectos existentes y creación de un proyecto .NET Core</span><span class="sxs-lookup"><span data-stu-id="ecbaf-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="ecbaf-137">Si hay proyectos existentes que tienen como destino marcos de trabajo anteriores, puede que desee dejarlos intactos y usar un proyecto .NET Core para establecer como destino marcos de trabajo futuros.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![Proyecto .NET Core con un proyecto existente en otra carpeta](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="ecbaf-139">**Código fuente**</span><span class="sxs-lookup"><span data-stu-id="ecbaf-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="ecbaf-140">Los cambios que debe tener en cuenta son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecbaf-140">Changes to note are:</span></span>

- <span data-ttu-id="ecbaf-141">.NET Core y los proyectos existentes se mantienen en carpetas independientes.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  - <span data-ttu-id="ecbaf-142">Mantener los proyectos en carpetas independientes evita que sea necesario tener Visual Studio 2017 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="ecbaf-143">Puede crear una solución independiente que solo abra los proyectos anteriores.</span><span class="sxs-lookup"><span data-stu-id="ecbaf-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecbaf-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecbaf-144">See also</span></span>

- [<span data-ttu-id="ecbaf-145">Documentación sobre la portabilidad a .NET Core</span><span class="sxs-lookup"><span data-stu-id="ecbaf-145">.NET Core porting documentation</span></span>](index.md)
