---
title: 'Comando dotnet nuget delete: CLI de .NET Core'
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1e81501d526ae92336b808f98c7c192b55e89f98
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.

## <a name="synopsis"></a>Sinopsis

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Description

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