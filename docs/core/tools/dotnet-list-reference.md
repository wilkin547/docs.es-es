---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117675"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet list reference`: enumera las referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.

## <a name="arguments"></a>Argumentos

* **`PROJECT | SOLUTION`**

  Especifica el archivo de solución o proyecto que se usará para enumerar las referencias. Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

* Enumerar las referencias del proyecto para el proyecto especificado:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Enumerar las referencias del proyecto para el proyecto en el directorio actual:

  ```dotnetcli
  dotnet list reference
  ```
