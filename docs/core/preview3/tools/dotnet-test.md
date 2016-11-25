---
title: Comando dotnet-test | SDK de .NET Core
description: El comando &quot;dotnet test&quot; se usa para ejecutar pruebas unitarias en un proyecto determinado.
keywords: dotnet-test, CLI, comando de la CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 66c9f949980612f6e21b6d441c004cc09f4eb7d3

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Nombre

`dotnet-test`: controlador de prueba de .NET

## <a name="synopsis"></a>Sinopsis

`dotnet test [project] [--help] 
    [--settings] [--listTests] [--testCaseFilter] 
    [--testAdapterPath] [--logger] 
    [--configuration] [--output] [--framework] [--diag]
    [--noBuild]`  

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. Las pruebas unitarias son proyectos de biblioteca de clases que tienen dependencias en el marco de pruebas unitarias (por ejemplo, NUnit o xUnit) y en el ejecutor dotnet test de ese marco de pruebas unitarias. Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba también necesitan especificar el ejecutor de la prueba. Para ello se utiliza un elemento `<PackageReference>` ordinario, como se puede ver en el siguiente archivo de proyecto de ejemplo:

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
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Test.Sdk">
      <Version>15.0.0-preview-20161024-02</Version>
    </PackageReference>
    <PackageReference Include="xunit">
      <Version>2.2.0-beta3-build3402</Version>
    </PackageReference>
    <PackageReference Include="xunit.runner.visualstudio">
      <Version>2.2.0-beta4-build1188</Version>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="options"></a>Opciones

`[project]`
    
Especifica una ruta de acceso al proyecto de prueba. Si se omite, se toma como predeterminado el directorio actual.

`-h|--help`

Imprime una corta ayuda para el comando.

`-s | --settings <SETTINGS_FILE>`

Configuración que se usará al ejecutar las pruebas. 

`-lt | --listTests`

Enumera todas las pruebas detectadas en el proyecto actual. 

`-tcf | --testCaseFilter <EXPRESSION>`

Filtrar las pruebas del proyecto actual con la expresión dada. 

`-tap | --testAdapterPath <TEST_ADAPTER_PATH>`

Usa los adaptadores de prueba personalizados desde la ruta especificada en esta ejecución de pruebas. 

`--logger <LOGGER>`

Especifica un registrador para resultados de pruebas. 

`-c|--configuration <Debug|Release>`

Configuración con la que se va a realizar la compilación. El valor predeterminado es `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-f|--framework [FRAMEWORK]`

Busca archivos binarios de prueba para un marco específico.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Busca archivos binarios de prueba para el tiempo de ejecución especificado.

`--noBuild` 

No compila el proyecto de prueba antes de ejecutarlo. 

`-d | --diag <DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado. 

## <a name="examples"></a>Ejemplos

Ejecución de las pruebas en el proyecto en el directorio actual:

`dotnet test` 

Ejecución de las pruebas en el proyecto test1:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>Vea también

[Marcos](../../../standard/frameworks.md)

[Catálogo de identificadores de tiempo de ejecución (RID)](../../rid-catalog.md)



<!--HONumber=Nov16_HO3-->


