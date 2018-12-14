---
title: 'Comando dotnet nuget delete: CLI de .NET Core'
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 451352ea652b77e44dcaf731d5b6cce230d1ef78
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126840"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a>Descripción

El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor. Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.

## <a name="arguments"></a>Argumentos

* **`PACKAGE_NAME`**

  Nombre o id. del paquete que se va a eliminar.

* **`PACKAGE_VERSION`**

  Versión del paquete que se va a eliminar.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

* **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--interactive`**

  Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación. Opción disponible a partir del SDK de .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  La clave de API para el servidor.

* **`--no-service-endpoint`**

  No agrega "api/v2/paquete" a la dirección URL de origen. Opción disponible a partir del SDK de .NET Core 2.1.

* **`--non-interactive`**

  No pide confirmaciones o entradas de usuario.

* **`-s|--source <SOURCE>`**

  Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`. Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

* **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`-k|--api-key <API_KEY>`**

  La clave de API para el servidor.

* **`--non-interactive`**

  No pide confirmaciones o entradas de usuario.

* **`-s|--source <SOURCE>`**

  Especifica la dirección URL del servidor. Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`. Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).

---

## <a name="examples"></a>Ejemplos

* Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```