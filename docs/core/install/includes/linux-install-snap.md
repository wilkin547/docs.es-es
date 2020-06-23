---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602691"
---

[.NET Core está disponible desde el almacén de snaps.](https://snapcraft.io/dotnet-sdk)

Un snap es una agrupación de una aplicación y sus dependencias que funcionan sin modificaciones en muchas distribuciones de Linux diferentes. Los snaps se reconocen y se instalan desde el almacén de snaps. Para más información sobre Snap, consulte [Introducción a Snap](https://snapcraft.io/docs/getting-started).

Solo las versiones admitidas de .NET Core están disponibles mediante Snap.

### <a name="install-the-sdk"></a>Instalación del SDK

Los paquetes Snap para el SDK de .NET Core se publican con el mismo identificador: `dotnet-sdk`. Se puede instalar una versión específica del SDK mediante la especificación del canal. El SDK incluye el entorno de ejecución correspondiente. En la tabla siguiente se enumeran los canales:

| Versión de .NET Core | Paquete Snap             |
|-------------------|--------------------------|
| 3.1 (LTS)         | `3.1` o `latest/stable` |
| 2.1 (LTS)         | `2.1`                    |
| .NET 5.0 (versión preliminar)  | `5.0/beta`               |

Use el comando `snap install` para instalar un paquete Snap del SDK de .NET Core. Use el parámetro `--channel` para indicar qué versión se va a instalar. Si se omite este parámetro, se usa `latest/stable`. En este ejemplo, se especifica `3.1`:

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`. Puede elegir cualquier nombre de `{alias}` que prefiera. Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-sdk.dotnet dotnet31`. Cuando use el comando `dotnet31`, invocará esta versión específica de .NET. Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

Los paquetes Snap de .NET Core Runtime se publican con su propio identificador de paquete. En la tabla siguiente se muestra una lista de los identificadores de paquete:

| Versión de .NET Core | Paquete Snap        |
|-------------------|---------------------|
| 3.1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2.1 (LTS)         | `dotnet-runtime-21` |

Use el comando `snap install` para instalar un paquete Snap de .NET Core Runtime. En este ejemplo, se instala .NET Core 3.1:

```bash
sudo snap install dotnet-runtime-31 --classic
```

A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`. Puede elegir cualquier nombre de `{alias}` que prefiera. Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-runtime-31.dotnet dotnet31`. Cuando use el comando `dotnet31`, invocará esta versión específica de .NET. Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.

### <a name="ssl-certificate-errors"></a>Errores de certificado SSL

Cuando .NET se instala mediante Snap, es posible que en algunas distribuciones no se encuentren los certificados SSL de .NET y que reciba un error similar al siguiente durante la acción `restore`:

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

La ubicación del certificado variará en función de la distribución. Estas son las ubicaciones de las distribuciones en las que hemos experimentado el problema.

* Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE: `/etc/ssl/ca-bundle.pem`
* Solus: `/etc/ssl/certs/ca-certificates.crt`
