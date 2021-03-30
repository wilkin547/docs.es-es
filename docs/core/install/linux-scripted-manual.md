---
title: 'Instalación manual de .NET en Linux: .NET'
description: Muestra cómo instalar el SDK y el entorno de ejecución de .NET sin un administrador de paquetes en Linux. Use el script de instalación o extraiga manualmente los archivos binarios.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6840814627be0124d7b3855f08a433eab76eac4a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873918"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a>Instalación manual del SDK y el entorno de ejecución de .NET

.NET es compatible con Linux. En este artículo se describe cómo instalar .NET en Linux mediante el script de instalación o la extracción de los archivos binarios. Para obtener una lista de las distribuciones que admiten el administrador de paquetes integrado, consulte [Instalación de .NET en Linux](linux.md).

También puede instalar .NET con un snap. Para obtener más información, consulte [Instalación del SDK y el entorno de ejecución de .NET con un snap](linux-snap.md).

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a>Versiones de .NET

En la tabla siguiente se enumeran las versiones de .NET (y .NET Core):

| ✔️ Admitida | ❌ No admitida |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1 (LTS)   | 2.2           |
| 2.1 (LTS)   | 2,0           |
|             | 1,1           |
|             | 1,0           |

Para obtener más información sobre el ciclo de vida de las versiones de .NET, consulte la [directiva de compatibilidad de .NET Core y .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="dependencies"></a>Dependencias

Al instalar .NET, es posible que las dependencias específicas no estén instaladas, como cuando se realiza la [instalación manual](#manual-install). En la lista siguiente se detallan las distribuciones de Linux que son compatibles con Microsoft y que contienen dependencias que es posible que deba instalar. Consulte la página de la distribución para obtener más información:

- [Alpine](linux-alpine.md#dependencies)
- [Debian](linux-debian.md#dependencies)
- [CentOS](linux-centos.md#dependencies)
- [Fedora](linux-fedora.md#dependencies)
- [RHEL](linux-rhel.md#dependencies)
- [SLES](linux-sles.md#dependencies)
- [Ubuntu](linux-ubuntu.md#dependencies)

Para obtener información genérica sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/main/Documentation/self-contained-linux-apps.md).

### <a name="rpm-dependencies"></a>Dependencias de RPM

Si su distribución no aparece en la lista anterior y se basa en RPM, puede que necesite las siguientes dependencias:

- krb5-libs
- libicu
- openssl-libs

Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.

### <a name="deb-dependencies"></a>Dependencias de DEB

Si su distribución no aparece en la lista anterior y se basa en Debian, puede que necesite las siguientes dependencias:

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu67
- libssl1.1
- libstdc++6
- zlib1g

### <a name="common-dependencies"></a>Dependencias comunes

En el caso de las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- [libgdiplus (versión 6.0.1 o posterior)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Instalación con script

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**. Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.

El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Para instalar el entorno de ejecución de .NET en lugar del SDK, use el parámetro `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica. El comando siguiente instala el SDK de .NET 5.0.

```bash
./dotnet-install.sh -c 5.0
```

Para más información, consulte la [referencia de los scripts de dotnet-install](../tools/dotnet-install-script.md).

## <a name="manual-install"></a>Instalación manual

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

Como alternativa a los administradores de paquetes, puede descargar e instalar manualmente el SDK y el entorno de ejecución. La instalación manual se suele usar como parte de las pruebas de integración continua o en distribuciones de Linux no admitidas. Para un desarrollador o usuario, es mejor usar un administrador de paquetes.

Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente. En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:

- ✔️ [Descargas de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1)
- ✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet/2.1)
- [Todas las descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet)

A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET. Luego, asegúrese de que .NET esté en PATH.

Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET. Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo. El nombre del archivo puede ser distinto en función de lo que haya descargado.

**Use los siguientes comandos para extraer el entorno de ejecución o el SDK que descargó**. Recuerde cambiar el valor de `DOTNET_FILE` por el nombre del archivo:

```bash
DOTNET_FILE=dotnet-sdk-5.0.102-linux-x64.tar.gz
export DOTNET_ROOT=$HOME/dotnet

mkdir -p "$DOTNET_ROOT" && tar zxf "$DOTNET_FILE" -C "$DOTNET_ROOT"

export PATH=$PATH:$DOTNET_ROOT
```

> [!TIP]
> Los comandos `export` anteriores solo hacen que los de la CLI de .NET estén disponibles para la sesión del terminal en la que se ha ejecutado.
>
> Puede editar el perfil del shell para agregar los comandos de forma permanente. Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente. Por ejemplo:
>
> - **Shell de Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Shell de Korn**: *~/.kshrc* or *.profile*
> - **Shell de Z**: *~/.zshrc* or *.zprofile*
>
> Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente. Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.
>
> Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.

Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para habilitar la finalización con tabulación para la CLI de .NET](../tools/enable-tab-autocomplete.md)
- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
