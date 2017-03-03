---
title: Comando dotnet-nuget-locals | Microsoft Docs
description: "El comando dotnet-nuget-locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina."
keywords: dotnet-nuget-locals, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 11/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 5f8c3be091b515553eb0db0ccfaee6bb8c620cff
ms.lasthandoff: 01/21/2017

---

#<a name="dotnet-nuget-locals"></a>dotnet-nuget-locals

[!INCLUDE[preview-warning](../../../includes/warning.md)] 

## <a name="name"></a>Nombre 
`dotnet-nuget-locals`: borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina. 

## <a name="synopsis"></a>Sinopsis

`dotnet nuget locals <cache_location> [--clear|--list] [--help] [--force-english-output]`

donde `<cache_location>` es uno de los valores siguientes: `all`, `http-cache`, `packages-cache`, `global-packages` o `temp`.

## <a name="description"></a>Descripción

El comando `dotnet nuget locals` borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.

## <a name="arguments"></a>Argumentos

`all`

Indica que la operación especificada se debe aplicar a todos los tipos de caché, es decir, caché de solicitudes http, caché de paquetes global y caché temporal.

`http-cache`

Indica que la operación especificada se debe aplicar solo a la caché de solicitudes http. Las otra ubicaciones de caché no se ven afectadas.

`global-packages`

Indica que la operación especificada se debe aplicar solo a la caché de paquetes global. Las otra ubicaciones de caché no se ven afectadas.

`temp`

Indica que la operación especificada se debe aplicar solo a la caché temporal. Las otra ubicaciones de caché no se ven afectadas.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-c|--clear`

La opción Borrar se usa para realizar una operación de borrado sobre el tipo de caché especificado. El contenido de los directorios de caché se elimina de forma recursiva. El usuario o grupo de ejecución deben tener permiso para los archivos de los directorios de caché para que la operación se realice correctamente. En caso contrario, se muestra un error para indicar que los archivos o carpetas no se han borrado.

`-l|--list`

La opción de lista se usa para mostrar la ubicación del tipo de caché especificado. 

`--force-english-output`

Fuerza a que la salida de la línea de comandos esté en inglés.

## <a name="examples"></a>Ejemplos

Muestra las rutas de acceso de todos los directorios de caché locales, es decir, el directorio de la caché de solicitudes http, el directorio de la caché de paquetes global y el directorio de la caché temporal.

`dotnet nuget locals –l all`

Muestra la ruta de acceso del directorio de la caché de solicitudes http:

`dotnet nuget locals --list http-cache`

Borra todos los archivos de todos los directorios de caché locales, es decir, el directorio de la caché de solicitudes http, el directorio de la caché de paquetes global y el directorio de la caché temporal.

`dotnet nuget locals --clear all`

Borra todos los archivos del directorio local de la caché de paquetes global:

`dotnet nuget locals -c global-packages`

Borra todos los archivos del directorio local de la caché temporal:

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Solución de problemas

Para más información sobre los problemas y errores encontrados más comúnmente al utilizar el comando `dotnet-nuget-locals`, consulte [Managing the NuGet cache](https://docs.microsoft.com/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).

