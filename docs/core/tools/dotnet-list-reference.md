---
title: Comando dotnet-list reference | Microsoft Docs
description: "El comando dotnet-list reference constituye una opción práctica para enumerar referencias entre proyectos."
keywords: dotnet-list, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e95aa43bfed78d72ef1ea5f3883ae64e06ffaa99
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-list-reference"></a>dotnet-list reference

## <a name="name"></a>Name

`dotnet-list reference`: enumera referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

```
dotnet list [project] reference
dotnet list reference [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.

## <a name="arguments"></a>Argumentos

`project`

El archivo de proyecto para el que enumerar las referencias. Si no se especifica, el comando buscará uno en el directorio actual.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Enumerar las referencias del proyecto para el proyecto especificado:

`dotnet list app/app.csproj reference`

Enumerar las referencias del proyecto para el proyecto en el directorio actual:

`dotnet list reference`

