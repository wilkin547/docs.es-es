---
title: 'Comando dotnet-add reference: CLI de .NET Core'
description: El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos.
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.openlocfilehash: ee9c058b83238655bd90a4bf5c809a9d0e4c13d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet add reference` Agrega referencias entre proyectos (P2P) .

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Description

El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto. Después de ejecutar el comando, los elementos [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) se agregan al archivo del proyecto.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

`PROJECT_REFERENCES`

Referencias entre proyectos (P2P) que se van a agregar. Especifique uno o más proyectos. [El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-f|--framework <FRAMEWORK>`

Agrega referencias de proyecto solo cuando apunta a un[marco](../../standard/frameworks.md) específico.

## <a name="examples"></a>Ejemplos

Agregar una referencia de proyecto:

`dotnet add app/app.csproj reference lib/lib.csproj`

Agregar varias referencias de proyecto al proyecto en el directorio actual:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`
