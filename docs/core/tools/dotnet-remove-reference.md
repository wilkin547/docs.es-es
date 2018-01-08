---
title: 'Comando dotnet remove reference: CLI de .NET Core'
description: "El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet remove reference`: quita las referencias de proyecto a proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Description

El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Archivo de proyecto de destino. Si no se especifica, el comando busca uno en el directorio actual.

`PROJECT_REFERENCES`

Referencias de proyecto a proyecto (P2P) para quitar. Puede especificar uno o varios proyectos. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

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
