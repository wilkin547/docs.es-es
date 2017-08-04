---
title: 'Comando dotnet-remove reference: CLI de .NET Core'
description: "El comando dotnet-remove reference constituye una opción práctica para quitar las referencias entre proyectos."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e22f64370be4b56597a303d79d3aabe1ff22a78a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-reference"></a>dotnet-remove reference

## <a name="name"></a>Name

`dotnet-remove reference`: quita las referencias de proyecto a proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descripción

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

