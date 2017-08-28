---
title: 'Comando dotnet-add reference: CLI de .NET Core'
description: "El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 18e3ce22c1b9a4506b2690262d8d0c4e13a58ed1
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet add reference` Agrega referencias entre proyectos (P2P) .

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descripción

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

Especifica el archivo del proyecto. Si no se especifica, el comando buscará uno en el directorio actual.

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

Agregar varias referencias de proyecto:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`
