---
title: Comando dotnet nuget locals
description: El comando dotnet nuget locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 6436bbaee7ae50f4b225c32b2245c737b0d359c3
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539267"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nombre

`dotnet nuget locals`: borra o enumera recursos locales de NuGet.

## <a name="synopsis"></a>Sinopsis

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet nuget locals` borra o enumera los recursos locales de NuGet en la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la máquina.

## <a name="arguments"></a>Argumentos

* **`CACHE_LOCATION`**

  La ubicación de caché que se va a mostrar o borrar. Acepta uno de los valores siguientes:

  * `all`: indica que la operación especificada se debe aplicar a todos los tipos de caché: caché de solicitudes http, caché de paquetes globales y caché temporal.
  * `http-cache`: indica que la operación especificada se aplica solo a la caché de solicitudes http. Las otras ubicaciones de caché no se ven afectadas.
  * `global-packages`: indica que la operación especificada se aplica solo a la caché de paquetes globales. Las otras ubicaciones de caché no se ven afectadas.
  * `temp`: indica que la operación especificada se aplica solo a la caché temporal. Las otras ubicaciones de caché no se ven afectadas.

## <a name="options"></a>Opciones

* **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`-c|--clear`**

  La opción de borrado ejecuta una operación de borrado sobre el tipo de caché especificado. El contenido de los directorios de caché se elimina de forma recursiva. El usuario o grupo de ejecución deben tener permiso para los archivos en los directorios de la caché. En caso contrario, se muestra un error para indicar los archivos o las carpetas que no se han borrado.

* **`-l|--list`**

  La opción de lista se usa para mostrar la ubicación del tipo de caché especificado.

## <a name="examples"></a>Ejemplos

* Muestra las rutas de acceso de todos los directorios de caché locales (el directorio de caché http, el directorio de caché de paquetes globales y el directorio de caché temporal):

  ```console
  dotnet nuget locals –l all
  ```

* Muestra la ruta de acceso del directorio de la caché de solicitudes http:

  ```console
  dotnet nuget locals --list http-cache
  ```

* Borra todos los archivos de todos los directorios de caché locales (directorio de caché http, directorio de caché de paquetes globales y directorio de caché temporal):

  ```console
  dotnet nuget locals --clear all
  ```

* Borra todos los archivos del directorio local de la caché de paquetes globales:

  ```console
  dotnet nuget locals -c global-packages
  ```

* Borra todos los archivos del directorio local de la caché temporal:

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a>Solución de problemas

Para más información sobre problemas y errores comunes encontrados al usar el comando `dotnet nuget locals`, consulte [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).
