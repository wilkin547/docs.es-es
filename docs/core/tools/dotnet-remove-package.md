---
title: Comando dotnet-remove package | Microsoft Docs
description: "El comando dotnet-remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 87c80ad193df9cc3e0feabc41bb58f1d8dda23cd
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-package"></a>dotnet-remove package

## <a name="name"></a>Name

`dotnet-remove package`: quita la referencia de paquete de un archivo de proyecto.

## <a name="synopsis"></a>Sinopsis

```
dotnet remove [project] package <package_name>
dotnet remove package [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.

## <a name="arguments"></a>Argumentos

`project`

Archivo del proyecto sobre el que actuar. Si no se especifica, el comando buscará uno en el directorio actual.

`package_name`

La referencia de paquete que hay que quitar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Quita el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:

`dotnet remove package Newtonsoft.Json`
