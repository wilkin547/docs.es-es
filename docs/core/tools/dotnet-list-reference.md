---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 946d3d523443fbe673b95dba95dbca327fde1699
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet list reference`: enumera referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Description

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo de proyecto que se usará para enumerar las referencias. Si no se especifica, el comando buscará uno en el directorio actual.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Enumerar las referencias del proyecto para el proyecto especificado:

`dotnet list app/app.csproj reference`

Enumerar las referencias del proyecto para el proyecto en el directorio actual:

`dotnet list reference`
