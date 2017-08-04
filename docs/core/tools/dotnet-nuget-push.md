---
title: 'Comando dotnet-nuget-push: CLI de .NET Core'
description: El comando dotnet-nuget-push inserta un paquete en el servidor y lo publica.
keywords: dotnet-nuget-push, CLI, comando de la CLI, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83da967d9d7432fcb422b88344ff597d45fc9e85
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-push"></a>dotnet-nuget push

## <a name="name"></a>Name

`dotnet-nuget push`: inserta un paquete en el servidor y lo publica.

## <a name="synopsis"></a>Sinopsis

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica. El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración. Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.

## <a name="arguments"></a>Argumentos

`ROOT`

Especifica la ruta de acceso al paquete y su clave de API para insertar el paquete en el servidor.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-s|--source <SOURCE>`

Especifica la dirección URL del servidor. Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.

`--symbols-source <SOURCE>`

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

Inserta todos los archivos *.nupkg* del directorio actual en el origen de inserción predeterminado, con un nivel máximo de detalle:

`dotnet nuget push *.nupkg --verbosity detailed`

