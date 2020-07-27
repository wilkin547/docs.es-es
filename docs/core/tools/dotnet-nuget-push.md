---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 608cd05d94dd6b5cdc53d582cfaa0407f011ff37
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925519"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet nuget push`: inserta un paquete en el servidor y lo publica.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica. El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración. Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.

El comando inserta un paquete existente. No crea un paquete. Para crear un paquete, use [`dotnet pack`](dotnet-pack.md).

## <a name="arguments"></a>Argumentos

- **`ROOT`**

  Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.

## <a name="options"></a>Opciones

- **`-d|--disable-buffering`**

  Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.

- **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación. Opción disponible a partir del SDK de .NET Core 2.2.

- **`-k|--api-key <API_KEY>`**

  La clave de API para el servidor.

- **`-n|--no-symbols true`**

  No inserta símbolos (incluso si está presente).

- **`--no-service-endpoint`**

  No agrega "api/v2/paquete" a la dirección URL de origen. Opción disponible desde el SDK de .NET Core 2.1.

- **`-s|--source <SOURCE>`**

  Especifica la dirección URL del servidor. Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.

- **`--skip-duplicate`**

  Al insertar varios paquetes en un servidor HTTP(S), trata cualquier respuesta de conflicto 409 como una advertencia para que la inserción pueda continuar. Disponible a partir del SDK de .NET Core 3.1.

- **`-sk|--symbol-api-key <API_KEY>`**

  La clave de API para el servidor de símbolos.

- **`-ss|--symbol-source <SOURCE>`**

  Especifica la dirección URL del servidor de símbolos.

- **`-t|--timeout <TIMEOUT>`**

  Especifica el tiempo de espera para la inserción en un servidor en segundos. El valor predeterminado es 300 segundos (5 minutos). Si se especifica 0 (cero segundos), se aplica el valor predeterminado.

## <a name="examples"></a>Ejemplos

- Inserte *foo.nupkg* en el origen de inserción predeterminado y especifique una clave de API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- Inserte *foo.nupkg* en el servidor de NuGet oficial y especifique una clave de API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- Inserte *foo.nupkg* en el origen de inserción predeterminado:

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- Inserte *foo.symbols.nupkp* en el origen de símbolos predeterminado:

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- Inserte *foo.nupkg* en el origen de inserción predeterminado y especifique un tiempo de espera de 360 segundos:

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- Inserte todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > Si este comando no funciona, es posible que se deba a un error presente en versiones anteriores del SDK (SDK de .NET Core 2.1 y versiones anteriores).
  > Para solucionar este problema, actualice la versión de su SDK o ejecute el siguiente comando en su lugar: `dotnet nuget push **/*.nupkg`

- Inserte todos los archivos *.nupkg*, aunque un servidor HTTP(S) devuelva una respuesta de conflicto 409:

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- Inserte todos los archivos *.nupkg*  del directorio actual en un directorio de fuente local:

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  Este comando no almacena paquetes en una estructura de carpetas jerárquica, lo que se recomienda para optimizar el rendimiento. Para obtener más información, vea [Fuentes locales](/nuget/hosting-packages/local-feeds).  
