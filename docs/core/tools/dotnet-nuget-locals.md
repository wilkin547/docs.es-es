---
title: 'Comando dotnet-nuget-locals: CLI de .NET Core'
description: "El comando dotnet-nuget-locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina."
keywords: dotnet-nuget-locals, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2c9ea7b3b7c61b347cb7c56254773290f04a0cd6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-locals"></a>dotnet-nuget locals

## <a name="name"></a>Name

`dotnet-nuget locals`: borra o enumera recursos locales de NuGet. 

## <a name="synopsis"></a>Sinopsis

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet nuget locals` borra o enumera los recursos locales de NuGet en la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la máquina.

## <a name="arguments"></a>Argumentos

`CACHE_LOCATION`

Uno de los siguientes valores:

`all`

Indica que la operación especificada se debe aplicar a todos los tipos de caché: caché de solicitudes http, caché de paquetes globales y caché temporal.

`http-cache`

Indica que la operación especificada se aplica solo a la caché de solicitudes http. Las otra ubicaciones de caché no se ven afectadas.

`global-packages`

Indica que la operación especificada se aplica solo a la caché de paquetes globales. Las otra ubicaciones de caché no se ven afectadas.

`temp`

Indica que la operación especificada se aplica solo a la caché temporal. Las otra ubicaciones de caché no se ven afectadas.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-c|--clear`

La opción de borrado realiza una operación de borrado sobre el tipo de caché especificado. El contenido de los directorios de caché se elimina de forma recursiva. El usuario o grupo de ejecución deben tener permiso para los archivos en los directorios de la caché. En caso contrario, se muestra un error para indicar que los archivos o carpetas no se han borrado.

`-l|--list`

La opción de lista se usa para mostrar la ubicación del tipo de caché especificado. 

`--force-english-output`

Fuerza la salida de la línea de comandos en inglés.

## <a name="examples"></a>Ejemplos

Muestra las rutas de acceso de todos los directorios de caché locales (el directorio de caché http, el directorio de caché de paquetes globales y el directorio de caché temporal):

`dotnet nuget locals –l all`

Muestra la ruta de acceso del directorio de la caché de solicitudes http:

`dotnet nuget locals --list http-cache`

Borra todos los archivos de todos los directorios de caché locales (directorio de caché http, directorio de caché de paquetes globales y directorio de caché temporal):

`dotnet nuget locals --clear all`

Borra todos los archivos del directorio local de la caché de paquetes globales:

`dotnet nuget locals -c global-packages`

Borra todos los archivos del directorio local de la caché temporal:

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Solución de problemas

Para más información sobre problemas y errores comunes encontrados al usar el comando `dotnet nuget locals`, consulte [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).

