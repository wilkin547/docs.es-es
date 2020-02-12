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
# <a name="manage-dependencies-with-net-core-sdk-10"></a>Administración de dependencias con el SDK 1.0 de .NET Core

Con el paso de los proyectos .NET Core de project.json a csproj y MSBuild, también se ha producido una inversión significativa que ha dado lugar a la unificación del archivo de proyecto y los recursos que permiten el seguimiento de dependencias. Para los proyectos .NET Core, esto es similar a lo que hizo project.json. No hay ningún archivo independiente JSON o XML que realice el seguimiento de las dependencias de NuGet. Con este cambio, también hemos introducido otro tipo de *referencia* en la sintaxis de csproj llamada `<PackageReference>`.

Este documento describe el nuevo tipo de referencia. También muestra cómo agregar a su proyecto una dependencia de paquete mediante este nuevo tipo de referencia.

## <a name="the-new-packagereference-element"></a>El nuevo elemento \<PackageReference>

El elemento `<PackageReference>` tiene la siguiente estructura básica:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Si ya conoce MSBuild, le resultarán familiares los otros tipos de referencia que ya existen. La clave es la instrucción `Include`, que especifica el id. de paquete que se quiere agregar al proyecto. El elemento secundario `<Version>` especifica la versión que se obtiene. Las versiones se especifican según las como por [reglas de versión de NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Si no está familiarizado con la sintaxis del archivo del proyecto, vea la documentación de [referencia de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) para obtener más información.

Use condiciones para agregar una dependencia que solo está disponible en un destino específico, tal como se muestra en el ejemplo siguiente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

La dependencia solo será válida si la compilación sucede para ese destino dado. El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto. Con aplicaciones .NET Core más comunes, no será necesario hacer esto.

## <a name="add-a-dependency-to-the-project"></a>Incorporación de una dependencia al proyecto

Agregar una dependencia a su proyecto es muy sencillo. Este es un ejemplo de cómo agregar la versión `9.0.1` de Json.NET a su proyecto. Por supuesto, es aplicable a cualquier otra dependencia de NuGet.

El archivo del proyecto tiene dos o más nodos `<ItemGroup>`. Uno de los nodos ya contiene elementos `<PackageReference>`. Se puede agregar la nueva dependencia a este nodo o crear uno nuevo; el resultado será el mismo.

En el ejemplo siguiente se usa la plantilla predeterminada que coloca `dotnet new console`. Se trata de una aplicación de consola simple. Cuando abra el proyecto, encontrará el elemento `<ItemGroup>` que ya contiene `<PackageReference>`. Agréguele lo siguiente:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

Después de esto, guarde el proyecto y ejecute el comando `dotnet restore` para instalar la dependencia.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

El proyecto completo tiene este aspecto:

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

## <a name="remove-a-dependency-from-the-project"></a>Eliminación de una dependencia del proyecto

La eliminación de una dependencia del archivo de proyecto supone simplemente quitar el elemento `<PackageReference>` del archivo de proyecto.
