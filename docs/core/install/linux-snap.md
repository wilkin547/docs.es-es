---
title: 'Instalación de .NET en Linux con un snap: .NET'
description: Muestra cómo instalar el SDK o el entorno de ejecución de .NET en Linux con un snap.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 741933b5ca6f01d73b388675fe7f8a43c4efb0f9
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970937"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a>Instalación del SDK y el entorno de ejecución de .NET con un snap

Use un paquete de snaps para instalar el SDK o el entorno de ejecución de .NET. Los snaps son una excelente alternativa para el administrador de paquetes integrada en la distribución de Linux. En este artículo se describe cómo instalar .NET mediante un [snap](https://snapcraft.io/dotnet-sdk).

Un snap es una agrupación de una aplicación y sus dependencias que funcionan sin modificaciones en muchas distribuciones de Linux diferentes. Los snaps se reconocen y se instalan desde el almacén de snaps. Para más información sobre Snap, consulte [Introducción a Snap](https://snapcraft.io/docs/getting-started).

> [!CAUTION]
> Los paquetes de snaps no se admiten en WSL2 en Windows 10. Como alternativa, use el [script `dotnet-install`](linux-scripted-manual.md#scripted-install) o el administrador de paquetes para la distribución de WSL2 determinada. No se recomienda, pero puede intentar habilitar los snaps con una [solución no admitida de los foros de snapcraft](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).

## <a name="net-releases"></a>Versiones de .NET

Solo las versiones admitidas ✔️ del SDK de .NET están disponibles mediante snaps. Todas las versiones del entorno de ejecución de .NET están disponibles mediante snaps a partir de la versión 2.1. En la tabla siguiente se enumeran las versiones de .NET (y .NET Core):

| ✔️ Admitida | ❌ No admitida |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1 (LTS)   | 2.2           |
| 2.1 (LTS)   | 2,0           |
|             | 1,1           |
|             | 1,0           |

Para obtener más información sobre el ciclo de vida de las versiones de .NET, consulte la [directiva de compatibilidad de .NET Core y .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="sdk-or-runtime"></a>SDK o entorno de ejecución

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a>Instalar el SDK

Los paquetes de snaps para el SDK de .NET se publican con el mismo identificador: `dotnet-sdk`. Se puede instalar una versión específica del SDK mediante la especificación del canal. El SDK incluye el entorno de ejecución correspondiente. En la tabla siguiente se enumeran los canales:

| Versión de .NET | Canal o paquete de snaps  |
|--------------|--------------------------|
| 5.0          | `5.0` o `latest/stable` |
| 3.1 (LTS)    | `3.1` o `lts/stable`    |
| 2.1 (LTS)    | `2.1`                    |

Use el comando `snap install` para instalar un paquete Snap del SDK de .NET. Use el parámetro `--channel` para indicar qué versión se va a instalar. Si se omite este parámetro, se usa `latest/stable`. En este ejemplo, se especifica `5.0`:

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`. Puede elegir cualquier nombre de `{alias}` que prefiera. Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-sdk.dotnet dotnet50`. Cuando use el comando `dotnet50`, invocará esta versión específica de .NET. Aun así, elegir un alias diferente no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que se use un comando `dotnet`.

## <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

Los paquetes de snaps para el entorno de ejecución de .NET se publican con su propio identificador de paquete. En la tabla siguiente se muestra una lista de los identificadores de paquete:

| Versión de .NET      | Paquete Snap        |
|-------------------|---------------------|
| 5.0               | `dotnet-runtime-50` |
| 3.1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2.1 (LTS)         | `dotnet-runtime-21` |

Use el comando `snap install` para instalar un paquete Snap del entorno de ejecución de .NET. En este ejemplo, se instala .NET 5.0:

```bash
sudo snap install dotnet-runtime-50 --classic
```

A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

El comando tiene el formato `sudo snap alias {package}.{command} {alias}`. Puede elegir cualquier nombre de `{alias}` que prefiera. Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-runtime-50.dotnet dotnet50`. Cuando use el comando `dotnet50`, invocará una versión específica de .NET. Aun así, elegir un alias diferente no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.

## <a name="tlsssl-certificate-errors"></a>Errores de certificado TLS/SSL

Cuando .NET se instala mediante snaps, es posible que en algunas distribuciones no se encuentren los certificados TLS/SSL de .NET y que reciba un error durante la acción `restore`:

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Para resolver este problema, establezca algunas variables de entorno:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

La ubicación del certificado variará en función de la distribución. Estas son las ubicaciones de las distribuciones en las que se ha experimentado el problema.

| Distribución | Ubicación                                            |
|--------------|-----------------------------------------------------|
| **Fedora**   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| **OpenSUSE** | `/etc/ssl/ca-bundle.pem`                            |
| **Solus**    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para habilitar la finalización con tabulación para la CLI de .NET](../tools/enable-tab-autocomplete.md)
- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
