---
title: Comando dotnet store
description: El comando “dotnet store” almacena los ensamblados especificados en el almacenamiento de paquetes en tiempo de ejecución.
author: bleroy
ms.date: 05/29/2018
ms.openlocfilehash: 3a81e06f36ffbed68b7cc35de47aa5dca32bab6e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714199"
---
# <a name="dotnet-store"></a>dotnet store

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>NOMBRE

`dotnet store`: almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).

## <a name="synopsis"></a>Sinopsis

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a>Descripción

`dotnet store` almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md). De forma predeterminada, los ensamblados están optimizados para el tiempo de ejecución y el marco de trabajo de destino. Para obtener más información, consulte el tema [runtime package store](../deploying/runtime-store.md) (almacenamiento de paquetes en tiempo de ejecución).

## <a name="required-options"></a>Opciones necesarias

`-f|--framework <FRAMEWORK>`

Especifica la [plataforma de destino](../../standard/frameworks.md).

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

El *archivo de manifiesto de almacenamiento de paquetes* es un archivo XML que contiene la lista de paquetes que se va a almacenar. El formato del archivo de manifiesto es compatible con el formato de proyecto de estilo de SDK. Por tanto, se puede usar un archivo de proyecto que haga referencia a los paquetes deseados con la opción `-m|--manifest` para almacenar los ensamblados en el almacenamiento de paquetes en tiempo de ejecución. Para especificar varios archivos de manifiesto, repita la opción y la ruta de acceso para cada archivo. Por ejemplo: `--manifest packages1.csproj --manifest packages2.csproj`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

El [identificador en tiempo de ejecución](../rid-catalog.md) de destino.

## <a name="optional-options"></a>Opciones no necesarias

`--framework-version <FRAMEWORK_VERSION>`

Especifica la versión del SDK de .NET Core. Esta opción le permite seleccionar una versión de un marco concreto más allá del marco de trabajo especificado en la opción `-f|--framework`.

`-h|--help`

Muestra información de ayuda.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso al almacenamiento de paquetes en tiempo de ejecución. Si no se especifica, el valor predeterminado es el subdirectorio *store* del directorio de instalación de .NET Core de perfil de usuario.

`--skip-optimization`

Omite la fase de optimización.

`--skip-symbols`

Omite la generación de símbolos. Actualmente, solo se pueden generar símbolos en Windows y Linux.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

El directorio de trabajo que usa el comando. Si no se especifica, usa el subdirectorio *obj* del directorio actual.

## <a name="examples"></a>Ejemplos

Almacenamiento de los paquetes especificados en el archivo de proyecto *packages.csproj* para .NET Core 2.0.0:

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

Almacenamiento de los paquetes especificados en *packages.csproj* sin optimización:

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a>Vea también

- [Runtime package store](../deploying/runtime-store.md) (Almacenamiento de paquetes en tiempo de ejecución)
