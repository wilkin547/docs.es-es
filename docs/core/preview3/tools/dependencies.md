---
title: "Administración de dependencias en .NET Core Tooling Preview 3"
description: Preview 3 implica cambios en la forma en que se administran las dependencias
keywords: CLI, extensibilidad, comandos personalizados, .NET Core
author: blackdwarf
manager: wpickett
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: e04d5f3b08c7f6885ed9914a91fc308234e6ce3b

---

<a name="managing-dependencies-in-net-core-preview-3-tooling"></a>Administración de dependencias en .NET Core Tooling Preview 3
----------------------------------------------------

# <a name="overview"></a>Información general
Con el paso de los proyectos .NET Core de project.json a csproj y MSBuild, también se ha producido una inversión significativa que ha dado lugar a la unificación del archivos de proyecto y los recursos que permiten el seguimiento de dependencias. Para los proyectos .NET Core, esto es similar a lo que hizo project.json. No hay ningún archivo independiente JSON o XML que realice el seguimiento de las dependencias de NuGet. Con este cambio, también hemos introducido otro tipo de *referencia* en la sintaxis de csproj llamada `<PackageReference>`. 

Este documento describe el nuevo tipo de referencia. También muestra cómo agregar a su proyecto una dependencia de paquete mediante este nuevo tipo de referencia. 

# <a name="the-new-packagereference-element"></a>El nuevo elemento <PackageReference>.
El elemento `<PackageReference>` tiene la siguiente estructura básica:

```xml
<PackageReference Include="<Package_ID>">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Si está familiarizado con MSBuild, le resultarán familiares los otros [tipos de referencia]() que ya existen. La clave es la instrucción `Include` que especifica el identificador de paquete que desea agregar al proyecto. El elemento secundario `<Version>` especifica la versión que se obtiene. Las versiones se especifican según las como por [reglas de versión de NuGet](https://docs.nuget.org/ndocs/create-packages/dependency-versions#version-ranges).  

> **Nota:** Si no está familiarizado con la sintaxis general de `csproj`, puede usar la [documentación de referencia de proyecto de MSBuild]() para más información.  

La adición de una dependencia que solo está disponible en un destino específico se realiza mediante condiciones:

```xml
<PackageReference Include="<Package_ID>" Condition="'$(TargetFramework)' == 'netcoreapp1.0'">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Lo anterior significa que la dependencia solo será válida si la compilación sucede para ese destino dado. El elemento `$(TargetFramework)` de la condición es una propiedad de MSBuild que se está configurando en el proyecto. Con aplicaciones .NET Core más comunes, no será necesario hacer esto. 

# <a name="adding-a-dependency-to-your-project"></a>Adición de una dependencia al proyecto
Agregar una dependencia a su proyecto es muy sencillo. Este es un ejemplo de cómo agregar la versión `JSON.net` `9.0.1` a su proyecto. Por supuesto, es aplicable a cualquier otra dependencia de NuGet. 

Al abrir el archivo de proyecto, verá dos o más nodos `<ItemGroup>`. Observe que uno de los nodos ya contiene elementos `<PackageReference>`. Puede agregar la nueva dependencia a este nodo, o crear uno nuevo; es su decisión, ya que el resultado será el mismo. 

En este ejemplo utilizaremos la plantilla predeterminada que se ha descartado mediante `dotnet new`. Se trata de una aplicación de consola simple. Cuando se abre el proyecto, primero encontramos el elemento `<ItemGroup>` que ya contiene `<PackageReference>`. A continuación, le agregamos lo siguiente:

```xml
<PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
</PackageReference>
```
Después de esto, guardamos el proyecto y ejecutamos el comando `dotnet restore` para instalar la dependencia. 

El proyecto completo tiene este aspecto:

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
        <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

# <a name="removing-a-dependency-from-the-project"></a>Eliminación de una dependencia del proyecto
La eliminación de una dependencia del archivo de proyecto supone simplemente quitar el elemento `<PackageReference>` del archivo de proyecto. 





<!--HONumber=Nov16_HO3-->


