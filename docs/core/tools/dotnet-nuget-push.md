---
title: 'Comando dotnet nuget push: CLI de .NET Core'
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 090b11646a81859eeadb5fe9d36b43721fc70a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet nuget push`: inserta un paquete en el servidor y lo publica.

## <a name="synopsis"></a>Sinopsis

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a>Description

El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica. El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración. Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.

## <a name="arguments"></a>Argumentos

`ROOT`

Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.

`--symbol-source <SOURCE>`

Especifica la dirección URL del servidor de símbolos.

`-t|--timeout <TIMEOUT>`

Especifica el tiempo de espera para la inserción en un servidor en segundos. El valor predeterminado es 300 segundos (5 minutos). Si se especifica 0 (cero segundos), se aplica el valor predeterminado.

`-k|--api-key <API_KEY>`

La clave de API para el servidor.

`--symbol-api-key <API_KEY>`

La clave de API para el servidor de símbolos.

`-d|--disable-buffering`

Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP (S) para reducir el uso de memoria.

`-n|--no-symbols`

No inserta símbolos (incluso si está presente).

`--force-english-output`

Fuerza que toda la salida registrada esté en inglés.

## <a name="examples"></a>Ejemplos

Inserta *foo.nupkg* para adoptar como predeterminado el origen de inserción, y proporciona la clave de API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Inserta *foo.nupkg* en el origen de inserción personalizado `http://customsource`, y proporciona una clave de API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

Inserta *foo.nupkg* en el origen de inserción predeterminado:

`dotnet nuget push foo.nupkg`

Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:

`dotnet nuget push foo.symbols.nupkg`

Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:

`dotnet nuget push foo.nupkg --timeout 360`

Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:

`dotnet nuget push *.nupkg`

Inserta todos los archivos *.nupkg* del directorio actual en el origen de inserción predeterminado, y especifica un archivo de configuración personalizado *./config/My.Config*:

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
