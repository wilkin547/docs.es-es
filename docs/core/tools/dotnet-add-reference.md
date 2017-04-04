---
title: Comando dotnet-add reference - .NET Core CLI | Documentos de Microsoft
description: "El comando dotnet-add reference constituye una opción práctica para agregar referencias entre proyectos."
keywords: dotnet-add, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 1b342f0aea19c01d7bdae94552019f4c171fd1a2
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>Name

`dotnet-add reference` Agrega referencias entre proyectos (P2P) .

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto. Después de ejecutar el comando, los elementos [`<ProjectReference>`](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items) se agregan al archivo del proyecto.

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

