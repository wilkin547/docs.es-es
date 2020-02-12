---
title: Administración de dependencias en las herramientas de .NET Core
description: Explica cómo administrar las dependencias con las herramientas de .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965625"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="071a8-103">Administración de dependencias con el SDK 1.0 de .NET Core</span><span class="sxs-lookup"><span data-stu-id="071a8-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="071a8-104">Con el paso de los proyectos .NET Core de project.json a csproj y MSBuild, también se ha producido una inversión significativa que ha dado lugar a la unificación del archivo de proyecto y los recursos que permiten el seguimiento de dependencias.</span><span class="sxs-lookup"><span data-stu-id="071a8-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="071a8-105">Para los proyectos .NET Core, esto es similar a lo que hizo project.json.</span><span class="sxs-lookup"><span data-stu-id="071a8-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="071a8-106">No hay ningún archivo independiente JSON o XML que realice el seguimiento de las dependencias de NuGet.</span><span class="sxs-lookup"><span data-stu-id="071a8-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="071a8-107">Con este cambio, también hemos introducido otro tipo de *referencia* en la sintaxis de csproj llamada `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="071a8-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="071a8-108">Este documento describe el nuevo tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="071a8-108">This document describes the new reference type.</span></span> <span data-ttu-id="071a8-109">También muestra cómo agregar a su proyecto una dependencia de paquete mediante este nuevo tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="071a8-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="071a8-110">El nuevo elemento \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="071a8-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="071a8-111">El elemento `<PackageReference>` tiene la siguiente estructura básica:</span><span class="sxs-lookup"><span data-stu-id="071a8-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="071a8-112">Si ya conoce MSBuild, le resultarán familiares los otros tipos de referencia que ya existen.</span><span class="sxs-lookup"><span data-stu-id="071a8-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="071a8-113">La clave es la instrucción `Include`, que especifica el id. de paquete que se quiere agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="071a8-113">The key is the `Include` statement, which specifies the package ID that you wish to add to the project.</span></span> <span data-ttu-id="071a8-114">El elemento secundario `<Version>` especifica la versión que se obtiene.</span><span class="sxs-lookup"><span data-stu-id="071a8-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="071a8-115">Las versiones se especifican según las como por [reglas de versión de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="071a8-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="071a8-116">Si no está familiarizado con la sintaxis del archivo del proyecto, vea la documentación de [referencia de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="071a8-116">If you're not familiar with the project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="071a8-117">Use condiciones para agregar una dependencia que solo está disponible en un destino específico, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="071a8-117">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="071a8-118">La dependencia solo será válida si la compilación sucede para ese destino dado.</span><span class="sxs-lookup"><span data-stu-id="071a8-118">The dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="071a8-119">El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="071a8-119">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="071a8-120">Con aplicaciones .NET Core más comunes, no será necesario hacer esto.</span><span class="sxs-lookup"><span data-stu-id="071a8-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="071a8-121">Incorporación de una dependencia al proyecto</span><span class="sxs-lookup"><span data-stu-id="071a8-121">Add a dependency to the project</span></span>

<span data-ttu-id="071a8-122">Agregar una dependencia a su proyecto es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="071a8-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="071a8-123">Este es un ejemplo de cómo agregar la versión `9.0.1` de Json.NET a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="071a8-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="071a8-124">Por supuesto, es aplicable a cualquier otra dependencia de NuGet.</span><span class="sxs-lookup"><span data-stu-id="071a8-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="071a8-125">El archivo del proyecto tiene dos o más nodos `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="071a8-125">Your project file has two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="071a8-126">Uno de los nodos ya contiene elementos `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="071a8-126">One of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="071a8-127">Se puede agregar la nueva dependencia a este nodo o crear uno nuevo; el resultado será el mismo.</span><span class="sxs-lookup"><span data-stu-id="071a8-127">You can add your new dependency to this node or create a new one; the result will be the same.</span></span>

<span data-ttu-id="071a8-128">En el ejemplo siguiente se usa la plantilla predeterminada que coloca `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="071a8-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="071a8-129">Se trata de una aplicación de consola simple.</span><span class="sxs-lookup"><span data-stu-id="071a8-129">This is a simple console application.</span></span> <span data-ttu-id="071a8-130">Cuando abra el proyecto, encontrará el elemento `<ItemGroup>` que ya contiene `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="071a8-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="071a8-131">Agréguele lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="071a8-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="071a8-132">Después de esto, guarde el proyecto y ejecute el comando `dotnet restore` para instalar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="071a8-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="071a8-133">El proyecto completo tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="071a8-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="071a8-134">Eliminación de una dependencia del proyecto</span><span class="sxs-lookup"><span data-stu-id="071a8-134">Remove a dependency from the project</span></span>

<span data-ttu-id="071a8-135">La eliminación de una dependencia del archivo de proyecto supone simplemente quitar el elemento `<PackageReference>` del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="071a8-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
