---
title: 'Comando dotnet-remove package: CLI de .NET Core'
description: "El comando dotnet-remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-package"></a>dotnet-remove package

## <a name="name"></a>Name

`dotnet-remove package`: quita la referencia de paquete de un archivo de proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo del proyecto. Si no se especifica, el comando buscará uno en el directorio actual.

`PACKAGE_NAME`

La referencia de paquete que hay que quitar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Quita el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:

`dotnet remove package Newtonsoft.Json`

