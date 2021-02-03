---
title: Administración de dependencias en .NET
description: Se explica cómo administrar las dependencias del proyecto para una aplicación .NET.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.topic: how-to
ms.date: 01/28/2021
ms.openlocfilehash: 9f5f814d0b4dc7aa3ff1a938c172475169a55bf2
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216133"
---
# <a name="manage-dependencies-in-net-applications"></a>Administración de dependencias en aplicaciones .NET

En este artículo se explica cómo agregar y quitar dependencias mediante la modificación del archivo de proyecto o mediante la CLI.

## <a name="the-packagereference-element"></a>El elemento \<PackageReference>

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

En el ejemplo anterior, la dependencia solo será válida si la compilación sucede para ese destino dado. El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto. En las aplicaciones .NET más comunes, no es necesario hacer esto.

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
