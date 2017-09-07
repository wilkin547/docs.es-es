---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: "El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b3e903c15a7486faa279d47ad5e2e00c090b19af
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nombre

`dotnet list reference`: enumera referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Descripción

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

