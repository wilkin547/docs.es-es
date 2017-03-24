---
title: Comando dotnet-nuget-delete | Microsoft Docs
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
keywords: dotnet-nuget-delete, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 2ce157e3f32f3e899245e38bb4520b17be3e0b32
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

## <a name="name"></a>Nombre

`dotnet-nuget-delete`: elimina o quita de la lista un paquete del servidor. 

## <a name="synopsis"></a>Sinopsis

```
dotnet nuget delete [<package_name> <package_version>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor. Para NuGet.org, la acción es quitar de la lista el paquete.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `http://www.nuget.org`, `http://www.nuget.org/api/v3` y `http://www.nuget.org/api/v2/package`. Para fuentes privadas, sustituya el nombre de host (por ejemplo, `%hostname%/api/v3`).

`--non-interactive`

No pide confirmaciones o intervención del usuario.

`-k|--api-key <API_KEY>`

La clave de API para el servidor.

`--force-english-output`

Fuerza a que la salida de la línea de comandos esté en inglés.

## <a name="examples"></a>Ejemplos

Elimina la versión 1.0 del paquete MyPackage:

`dotnet nuget delete MyPackage 1.0` 

Elimina la versión 1.0 del paquete MyPackage, sin pedir al usuario credenciales u otra información:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

