---
title: 'NETSDK1080: PackageReference a Microsoft.AspNetCore.App no es necesario'
description: Obtenga información sobre el error NETSDK1080 del SDK de .NET, que advierte sobre una entrada innecesaria en el archivo del proyecto.
ms.topic: error-reference
ms.date: 02/25/2021
f1_keywords:
- NETSDK1080
ms.openlocfilehash: ebf9484e4a358597a1177f95e92f68330180cd35
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206794"
---
# <a name="netsdk1080-packagereference-to-microsoftaspnetcoreapp-is-not-necessary"></a><span data-ttu-id="48ac2-103">NETSDK1080: PackageReference a Microsoft.AspNetCore.App no es necesario</span><span class="sxs-lookup"><span data-stu-id="48ac2-103">NETSDK1080: PackageReference to Microsoft.AspNetCore.App is not necessary</span></span>

<span data-ttu-id="48ac2-104">NETSDK1080 advierte de que el elemento `PackageReference` de `Microsoft.AspNetCore.App` en el archivo del proyecto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="48ac2-104">NETSDK1080 warns you that the `PackageReference` element for `Microsoft.AspNetCore.App` in your project file is not necessary.</span></span> <span data-ttu-id="48ac2-105">El mensaje de error es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48ac2-105">The full error message is similar to the following example:</span></span>

> <span data-ttu-id="48ac2-106">Advertencia NETSDK1080: PackageReference a Microsoft.AspNetCore.App no es necesario cuando el destino es .NET Core 3.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="48ac2-106">warning NETSDK1080: A PackageReference to Microsoft.AspNetCore.App is not necessary when targeting .NET Core 3.0 or higher.</span></span> <span data-ttu-id="48ac2-107">Si se usa Microsoft.NET.Sdk.Web, se hará referencia al marco de trabajo compartido de forma automática.</span><span class="sxs-lookup"><span data-stu-id="48ac2-107">If Microsoft.NET.Sdk.Web is used, the shared framework will be referenced automatically.</span></span> <span data-ttu-id="48ac2-108">De lo contrario, PackageReference debe reemplazarse por FrameworkReference.</span><span class="sxs-lookup"><span data-stu-id="48ac2-108">Otherwise, the PackageReference should be replaced with a FrameworkReference.</span></span>

<span data-ttu-id="48ac2-109">Este error suele producirse después de actualizar un proyecto a .NET Core 3.0 o una versión posterior desde una versión anterior que requería entradas `PackageReference` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="48ac2-109">This error typically occurs after you've upgraded a project to .NET Core 3.0 or later, from an earlier version that required `PackageReference` entries in the project file.</span></span>

## <a name="aspnet-core-project-files"></a><span data-ttu-id="48ac2-110">Archivos de proyecto de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="48ac2-110">ASP.NET Core project files</span></span>

<span data-ttu-id="48ac2-111">Por ejemplo, el archivo del proyecto original podría ser similar al de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="48ac2-111">For example, your original project file might look like this example:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp2.2</TargetFramework>
    <AspNetCoreHostingModel>InProcess</AspNetCoreHostingModel>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.App"/>
    <PackageReference Include="Microsoft.AspNetCore.Razor.Design" Version="2.2.0" PrivateAssets="All" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="48ac2-112">Después de actualizar a .NET Core 3.1, el archivo del proyecto para el mismo proyecto debe ser similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48ac2-112">After updating to .NET Core 3.1 the project file for the same project should look like the following example:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="48ac2-113">Realice estos cambios, en particular, elimine el elemento `PackageReference` para eliminar la advertencia.</span><span class="sxs-lookup"><span data-stu-id="48ac2-113">Make these changes, in particular delete the `PackageReference` element, to eliminate the warning.</span></span> <span data-ttu-id="48ac2-114">Para obtener más información, consulte [Quitar referencias de paquete obsoletas](/aspnet/core/migration/22-to-30#remove-obsolete-package-references).</span><span class="sxs-lookup"><span data-stu-id="48ac2-114">For more information, see [Remove obsolete package references](/aspnet/core/migration/22-to-30#remove-obsolete-package-references).</span></span>

## <a name="class-library-project"></a><span data-ttu-id="48ac2-115">Proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="48ac2-115">Class library project</span></span>

<span data-ttu-id="48ac2-116">En un proyecto de biblioteca de clases que usa API de ASP.NET Core, reemplace el elemento `PackageReference` con `FrameworkReference`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48ac2-116">In a class library project that uses ASP.NET Core APIs, replace the `PackageReference` with a `FrameworkReference`, as shown in the following example:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <FrameworkReference Include="Microsoft.AspNetCore.App" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="48ac2-117">Para obtener más información, consulte [Uso de API de ASP.NET Core en una biblioteca de clases](/aspnet/core/fundamentals/target-aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="48ac2-117">For more information, see [Use ASP.NET Core APIs in a class library](/aspnet/core/fundamentals/target-aspnetcore).</span></span>
