---
title: Comando dotnet-nuget-push | Microsoft Docs
description: El comando dotnet-nuget-push inserta un paquete en el servidor y lo publica.
keywords: dotnet-nuget-push, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 54ffd79cc9306ffcc5793990c3dc2e7534ed3f4b
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-push"></a>dotnet-nuget-push

## <a name="name"></a>Nombre

`dotnet-nuget-push`: inserta un paquete en el servidor y lo publica. 

## <a name="synopsis"></a>Sinopsis

```
dotnet nuget push [<package>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-v|--verbosity]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica. El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración. Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizado en el directorio actual.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.

`--symbols-source <SOURCE>`

Especifica la dirección URL del servidor de símbolos.

`-t|--timeout <TIMEOUT>`

Especifica el tiempo de espera para la inserción en un servidor en segundos. El valor predeterminado es 300 segundos (5 minutos). Al especificar 0 también se proporciona este valor predeterminado.

`-k|--api-key <API_KEY>`

La clave de API para el servidor.

`--symbol-api-key <API_KEY>`

La clave de API para el servidor de símbolos.

`-d|--disable-buffering`

Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP (S) para reducir el uso de memoria.

`-n|--no-symbols`

No inserta símbolos (incluso si está presente).

`--force-english-output`

Fuerza a que toda la salida registrada esté en inglés. Además de la flexibilidad de generar la salida en inglés en una máquina cuyo idioma no es el inglés, la coherencia entre plataformas que proporciona esta opción es una característica útil para herramientas automatizadas que extraen los registros del texto.

`--verbosity <LEVEL>`

Muestra esta cantidad de detalles en la salida. El nivel puede ser `normal`, `quiet` o `detailed`.

## <a name="examples"></a>Ejemplos

Inserta foo.nupkg para adoptar como predeterminado el origen de inserción, y proporciona la clave de API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Inserta foo.nupkg para personalizar el origen de inserción `http://customsource`, y proporciona la clave de API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

Inserta foo.nupkg para adoptar como predeterminado el origen de inserción:

`dotnet nuget push foo.nupkg` 

Inserta foo.symbols.nupkp para adoptar como predeterminado el origen de símbolos:

`dotnet nuget push foo.symbols.nupkg`

Inserta foo.nupkg para adoptar como predeterminado el origen de inserción, y especifica un tiempo de espera de 360 segundos:

`dotnet nuget push foo.nupkg --timeout 360`

Inserta todos los archivos .nupkg del directorio actual en el origen de inserción predeterminado:

`dotnet nuget push *.nupkg`

Inserta todos los archivos .nupkg en el directorio actual para adoptar como predeterminado el origen de inserción, y especifica un archivo de configuración personalizado *./config/My.Config*:

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

Inserta todos los archivos .nupkg del directorio actual en el origen de inserción predeterminado, con un nivel máximo de detalle:

`dotnet nuget push *.nupkg --verbosity detailed`

