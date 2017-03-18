---
title: Comando dotnet-remove reference | Microsoft Docs
description: "El comando dotnet-remove reference constituye una opción práctica para quitar las referencias entre proyectos."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 1f1a364b703c6b83a9b21ee420d62411bf9cd3ec
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-reference"></a>dotnet-remove reference

## <a name="name"></a>Name

`dotnet-remove reference`: quita las referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

```
dotnet remove [project] reference [-f|--framework] <project_references>
dotnet remove reference [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.

## <a name="arguments"></a>Argumentos

`project`

Archivo del proyecto sobre el que actuar. Si no se especifica, el comando buscará uno en el directorio actual.

`project_references`

Referencias entre proyectos que quitar. Puede especificar uno o varios proyectos. El patrón Glob se admite en terminales basados en Unix/Linux.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-f|--framework <FRAMEWORK>`

Quita la referencia solo cuando el destino es un marco específico.

## <a name="examples"></a>Ejemplos

Quitar una referencia de proyecto del proyecto especificado:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Quitar varias referencias de proyecto del proyecto en el directorio actual:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Quitar varias referencias de proyecto usando el patrón de uso de comodines:

`dotnet remove app/app.csproj reference **/*.csproj`
