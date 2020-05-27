---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702842"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Administración de dependencias en aplicaciones .NET Core

En este artículo se explica cómo agregar y quitar dependencias mediante la modificación del archivo de proyecto o mediante la CLI.

## <a name="the-packagereference-element"></a>Elemento \<PackageReference>

El archivo del proyecto `<PackageReference>` tiene la estructura siguiente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

El atributo `Include` especifica el identificador del paquete que se va a agregar al proyecto. El atributo `Version` especifica la versión que se va a obtener. Las versiones se especifican en función de las [reglas de versión de NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Si no está familiarizado con la sintaxis del archivo del proyecto, vea la documentación de [Referencia de proyectos de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) para obtener más información.

Use condiciones para agregar una dependencia que solo está disponible en un destino específico, tal como se muestra en el ejemplo siguiente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

En el ejemplo anterior, la dependencia solo será válida si la compilación sucede para ese destino dado. El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto. En las aplicaciones .NET Core más comunes, no es necesario hacer esto.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Adición de una dependencia mediante la edición del archivo del proyecto

Para agregar una dependencia, agregue un elemento `<PackageReference>` dentro de un elemento `<ItemGroup>`. Puede agregar a un elemento `<ItemGroup>` existente o crear uno. En el ejemplo siguiente se usa el proyecto de aplicación de consola predeterminado creado por `dotnet new console`:

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

## <a name="add-a-dependency-by-using-the-cli"></a>Adición de una dependencia mediante la CLI

Para agregar una dependencia, ejecute el comando [dotnet add package](dotnet-add-package.md), como se muestra en el ejemplo siguiente:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Eliminación de una dependencia mediante la edición del archivo del proyecto

Para quitar una dependencia, quite su elemento `<PackageReference>` del archivo del proyecto.

## <a name="remove-a-dependency-by-using-the-cli"></a>Eliminación de una dependencia mediante la CLI

Para quitar una dependencia, ejecute el comando [dotnet remove package](dotnet-remove-package.md), como se muestra en el ejemplo siguiente:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>Vea también

* [Referencias de paquete en archivos de proyecto](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [Comando dotnet list package](dotnet-list-package.md)
