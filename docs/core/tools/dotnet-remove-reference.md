---
title: Comando dotnet remove reference
description: El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: a45153376d7d6eb764c1d2c6b473d04a273a2de1
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158338"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet remove reference`: quita las referencias entre proyectos (P2P).

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Archivo de proyecto de destino. Si no se especifica, el comando busca uno en el directorio actual.

`PROJECT_REFERENCES`

Referencias de proyecto a proyecto (P2P) que se van a quitar. Puede especificar uno o varios proyectos. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`-f|--framework <FRAMEWORK>`**

  Solo quita la referencia cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico con el formato TFM.

## <a name="examples"></a>Ejemplos

- Quitar una referencia de proyecto del proyecto especificado:

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- Quitar varias referencias de proyecto del proyecto en el directorio actual:

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Quitar varias referencias de proyecto con un patrón global en Unix/Linux:

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
