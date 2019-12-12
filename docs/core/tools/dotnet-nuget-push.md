---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 12/04/2019
ms.openlocfilehash: 5e80295a570adc30a06d86b6735cb0387e39d5a3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74835524"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet nuget push`: inserta un paquete en el servidor y lo publica.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica. El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración. Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet). La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.

## <a name="arguments"></a>Argumentos

* **`ROOT`**

  Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.

## <a name="options"></a>Opciones

* **`-d|--disable-buffering`**

  Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.

* **`--force-english-output`**

  Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--interactive`**

  Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación. Opción disponible a partir del SDK de .NET Core 2.2.

* **`-k|--api-key <API_KEY>`**

  La clave de API para el servidor.

* **`-n|--no-symbols`**

  No inserta símbolos (incluso si está presente).

* **`--no-service-endpoint`**

  No agrega "api/v2/paquete" a la dirección URL de origen. Opción disponible desde el SDK de .NET Core 2.1.

* **`-s|--source <SOURCE>`**

  Especifica la dirección URL del servidor. Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.

* **`--skip-duplicate`**

  Al insertar varios paquetes en un servidor HTTP(S), trata cualquier respuesta de conflicto 409 como una advertencia para que la inserción pueda continuar. Disponible a partir del SDK de .NET Core 3.1.
                                 
* **`-sk|--symbol-api-key <API_KEY>`**

  La clave de API para el servidor de símbolos.

* **`-ss|--symbol-source <SOURCE>`**

  Especifica la dirección URL del servidor de símbolos.

* **`-t|--timeout <TIMEOUT>`**

  Especifica el tiempo de espera para la inserción en un servidor en segundos. El valor predeterminado es 300 segundos (5 minutos). Si se especifica 0 (cero segundos), se aplica el valor predeterminado.

## <a name="examples"></a>Ejemplos

* Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica una clave de API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* Inserta *foo.nupkg* en el origen de inserción predeterminado:

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > Si este comando no funciona, es posible que se deba a un error presente en versiones anteriores del SDK (SDK de .NET Core 2.1 y versiones anteriores).
  > Para solucionar este problema, actualice la versión de su SDK o ejecute el siguiente comando en su lugar: `dotnet nuget push **/*.nupkg`
  
* Envía todos los archivos *.nupkg* aunque un servidor HTTP(S) devuelva una respuesta de conflicto 409:

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
