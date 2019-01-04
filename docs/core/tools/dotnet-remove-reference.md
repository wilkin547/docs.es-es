---
title: Comando dotnet remove reference
description: El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos.
ms.date: 05/29/2018
ms.openlocfilehash: bfac4721743babcf48fd8e86a50c8df136e1bfce
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170618"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet remove reference`: quita las referencias de proyecto a proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Archivo de proyecto de destino. Si no se especifica, el comando busca uno en el directorio actual.

`PROJECT_REFERENCES`

Referencias de proyecto a proyecto (P2P) que se van a quitar. Puede especificar uno o varios proyectos. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-f|--framework <FRAMEWORK>`

Quita la referencia solo cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico.

## <a name="examples"></a>Ejemplos

Quitar una referencia de proyecto del proyecto especificado:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Quitar varias referencias de proyecto del proyecto en el directorio actual:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Quitar varias referencias de proyecto con un patrón global en Unix/Linux:

`dotnet remove app/app.csproj reference **/*.csproj`
