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
# <a name="netsdk1080-packagereference-to-microsoftaspnetcoreapp-is-not-necessary"></a>NETSDK1080: PackageReference a Microsoft.AspNetCore.App no es necesario

NETSDK1080 advierte de que el elemento `PackageReference` de `Microsoft.AspNetCore.App` en el archivo del proyecto no es necesario. El mensaje de error es similar al ejemplo siguiente:

> Advertencia NETSDK1080: PackageReference a Microsoft.AspNetCore.App no es necesario cuando el destino es .NET Core 3.0 o una versión posterior. Si se usa Microsoft.NET.Sdk.Web, se hará referencia al marco de trabajo compartido de forma automática. De lo contrario, PackageReference debe reemplazarse por FrameworkReference.

Este error suele producirse después de actualizar un proyecto a .NET Core 3.0 o una versión posterior desde una versión anterior que requería entradas `PackageReference` en el archivo del proyecto.

## <a name="aspnet-core-project-files"></a>Archivos de proyecto de ASP.NET Core

Por ejemplo, el archivo del proyecto original podría ser similar al de este ejemplo:

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

Después de actualizar a .NET Core 3.1, el archivo del proyecto para el mismo proyecto debe ser similar al del ejemplo siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

</Project>
```

Realice estos cambios, en particular, elimine el elemento `PackageReference` para eliminar la advertencia. Para obtener más información, consulte [Quitar referencias de paquete obsoletas](/aspnet/core/migration/22-to-30#remove-obsolete-package-references).

## <a name="class-library-project"></a>Proyecto de biblioteca de clases

En un proyecto de biblioteca de clases que usa API de ASP.NET Core, reemplace el elemento `PackageReference` con `FrameworkReference`, como se muestra en el ejemplo siguiente:

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

Para obtener más información, consulte [Uso de API de ASP.NET Core en una biblioteca de clases](/aspnet/core/fundamentals/target-aspnetcore).
