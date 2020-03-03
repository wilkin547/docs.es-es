---
title: Administración de dependencias en .NET Core
description: Se explica cómo administrar las dependencias del proyecto para una aplicación .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157250"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="e8c0b-103">Administración de dependencias en aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="e8c0b-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="e8c0b-104">En este artículo se explica cómo agregar y quitar dependencias mediante la modificación del archivo de proyecto o mediante la CLI.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="e8c0b-105">Elemento \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="e8c0b-105">The \<PackageReference> element</span></span>

<span data-ttu-id="e8c0b-106">El archivo del proyecto `<PackageReference>` tiene la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8c0b-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="e8c0b-107">El atributo `Include` especifica el identificador del paquete que se va a agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="e8c0b-108">El atributo `Version` especifica la versión que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="e8c0b-109">Las versiones se especifican en función de las [reglas de versión de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="e8c0b-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="e8c0b-110">Si no está familiarizado con la sintaxis del archivo del proyecto, vea la documentación de [Referencia de proyectos de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="e8c0b-111">Use condiciones para agregar una dependencia que solo está disponible en un destino específico, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8c0b-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="e8c0b-112">En el ejemplo anterior, la dependencia solo será válida si la compilación sucede para ese destino dado.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="e8c0b-113">El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="e8c0b-114">En las aplicaciones .NET Core más comunes, no es necesario hacer esto.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="e8c0b-115">Adición de una dependencia mediante la edición del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="e8c0b-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="e8c0b-116">Para agregar una dependencia, agregue un elemento `<PackageReference>` dentro de un elemento `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="e8c0b-117">Puede agregar a un elemento `<ItemGroup>` existente o crear uno.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="e8c0b-118">En el ejemplo siguiente se usa el proyecto de aplicación de consola predeterminado creado por `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="e8c0b-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="e8c0b-119">Adición de una dependencia mediante la CLI</span><span class="sxs-lookup"><span data-stu-id="e8c0b-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="e8c0b-120">Para agregar una dependencia, ejecute el comando [dotnet add package](dotnet-add-package.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8c0b-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="e8c0b-121">Eliminación de una dependencia mediante la edición del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="e8c0b-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="e8c0b-122">Para quitar una dependencia, quite su elemento `<PackageReference>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8c0b-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="e8c0b-123">Eliminación de una dependencia mediante la CLI</span><span class="sxs-lookup"><span data-stu-id="e8c0b-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="e8c0b-124">Para quitar una dependencia, ejecute el comando [dotnet remove package](dotnet-remove-package.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8c0b-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="e8c0b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8c0b-125">See also</span></span>

* [<span data-ttu-id="e8c0b-126">Paquetes NuGet en archivos de proyecto</span><span class="sxs-lookup"><span data-stu-id="e8c0b-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="e8c0b-127">[Comando dotnet list package](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="e8c0b-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
