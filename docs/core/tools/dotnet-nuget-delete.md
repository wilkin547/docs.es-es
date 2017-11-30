---
title: 'Comando dotnet nuget delete: CLI de .NET Core'
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 65fe52f07ed823b4f7518c5b1f2da1f7a61b0371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.

## <a name="synopsis"></a>Sinopsis

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor. Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.

## <a name="arguments"></a>Argumentos

`PACKAGE_NAME`

Paquete para eliminar.

`PACKAGE_VERSION`

Versión del paquete que se va a eliminar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `http://www.nuget.org`, `http://www.nuget.org/api/v3` y `http://www.nuget.org/api/v2/package`. Para fuentes privadas, sustituya el nombre de host (por ejemplo, `%hostname%/api/v3`).

`--non-interactive`

No pide confirmaciones o entradas de usuario.

`-k|--api-key <API_KEY>`

La clave de API para el servidor.

`--force-english-output`

Fuerza la salida de la línea de comandos en inglés.

## <a name="examples"></a>Ejemplos

Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`