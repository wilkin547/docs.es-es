---
title: Comando dotnet-add reference
description: El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos.
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631941"
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nombre

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

* **`PROJECT`**

  Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

* **`PROJECT_REFERENCES`**

  Referencias entre proyectos (P2P) que se van a agregar. Especifique uno o más proyectos. [El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`-f|--framework <FRAMEWORK>`**

  Agrega referencias de proyecto solo cuando apunta a un[marco](../../standard/frameworks.md) específico.

## <a name="examples"></a>Ejemplos

* Agregar una referencia de proyecto:

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* Agregar varias referencias de proyecto al proyecto en el directorio actual:

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
