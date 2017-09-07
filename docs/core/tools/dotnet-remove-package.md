---
title: 'Comando dotnet remove package: CLI de .NET Core'
description: "El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 4167f5465571259975572669e27f20c586b910da
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nombre

`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete de NuGet de un proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo del proyecto. Si no se especifica, el comando buscará uno en el directorio actual.

`PACKAGE_NAME`

La referencia de paquete que hay que quitar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Quita el paquete de NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:

`dotnet remove package Newtonsoft.Json`

