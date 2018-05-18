---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 24cb1124fc3f8707afe727e6a73d35d5dde39937
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
