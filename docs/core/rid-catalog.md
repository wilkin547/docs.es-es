---
title: "Catálogo de identificadores de entorno de ejecución (RID) de .NET Core"
description: "Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 067f9cfc283a14b7ea59a7454b7f593ce6eb5806
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
# <a name="net-core-rid-catalog"></a>Catálogo de identificadores de entorno de ejecución (RID) de .NET Core

RID es la abreviatura de *identificador de entorno de ejecución*. Los valores de RID se usan para identificar las plataformas de destino donde se ejecuta la aplicación.
Los paquetes de .NET los usan para presentar los recursos específicos de la plataforma en los paquetes de NuGet. Los valores siguientes son ejemplos de RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.
En el caso de los paquetes con dependencias nativas, el RID designa las plataformas en las que se puede restauran el paquete.

Los RID se pueden establecer en el elemento `<RuntimeIdentifier>` del archivo del proyecto. También se usan a través de la opción `--runtime` con los [comandos de la CLI de .NET Core](./tools/index.md) siguientes:

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

Los RID que representan sistemas operativos concretos normalmente siguen este patrón: `[os].[version]-[architecture]-[additional qualifiers]`, donde:

- `[os]` es el moniker del sistema operativo o de plataforma. Por ejemplo: `ubuntu`.

- `[version]` es la versión del sistema operativo en formato de número de versión separado por punto (`.`). Por ejemplo: `15.10`.

  - La versión **no** se debe tratar como versiones de marketing, debido a que, a menudo, representan varias versiones discretas del sistema operativo con un área expuesta de API de plataforma diferente.

- `[architecture]` es la arquitectura de procesador. Por ejemplo: `x86`, `x64`, `arm` o `arm64`.

- `[additional qualifiers]` diferencia aún más las distintas plataformas. Por ejemplo: `aot` o `corert`.

## <a name="rid-graph"></a>Grafo de RID

El grado de RID o el grafo de reserva de entorno de ejecución es una lista de RID compatibles entre sí. Los RID se definen en el paquete [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/). Pude ver la lista de RID compatibles y el grafo de RID en el archivo [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), que se encuentra en el repositorio de CoreFX. En este archivo puede ver que todos los RID, excepto el RID de base, contienen una instrucción `"#import"`. Estas instrucciones indican los RID compatibles.

Cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para el entorno de ejecución especificado.
Si no se encuentra una coincidencia exacta, NuGet vuelve al grafo hasta encontrar el sistema compatible más cercano según el grafo de RID.

El ejemplo siguiente es la entrada real del RID `osx.10.12-x64`:

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

El RID anterior especifica que `osx.10.12-x64` importa `osx.10.11-x64`. Por tanto, cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para `osx.10.12-x64` en el paquete. Si NuGet no puede encontrar el entorno de ejecución específico, puede restaurar, por ejemplo, los paquetes que especifican entornos de ejecución `osx.10.11-x64`.

En el ejemplo siguiente se muestra un grafo de RID ligeramente más grande que también se define en el archivo *runtime.json*:

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

A la larga, todos los RID se asignarán de vuelta al RID `any` raíz.

Hay algunas consideraciones sobre los RID que debe tener en cuenta cuando trabaja con ellos:

- Los RID son **cadenas opacas** y se deben tratar como cajas negras.
- No compile RID mediante programación.
- Use RID que ya estén definidos para la plataforma.
- Los RID deben ser específicos, por lo que no se recomienda presuponer nada a partir del valor de RID real.

## <a name="using-rids"></a>Uso de los RID

Para poder usar los RID, debe saber cuáles son los RID que existen. Se agregan valores nuevos a la plataforma de manera habitual.
Para obtener la versión más reciente y completa, consulte el archivo [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) que se encuentra en el repositorio CoreFX.

El SDK de .NET Core 2.0 presenta el concepto de RID portátiles. Se trata de valores nuevos agregados al grafo de RID que no están vinculados a una versión específica o a una distribución de SO específica. Resultan especialmente útiles cuando se trabaja con varias distribuciones de Linux.

En la lista siguiente se muestran los RID más comunes que se usan en cada SO. No se abarcan los valores `arm` o `corert`.

## <a name="windows-rids"></a>RID de Windows

- Portátil
  - `win-x86`
  - `win-x64`
- Windows 7/Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8/Windows Server 2012
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- Windows 8.1/Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10/Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

Vea [requisitos previos para .NET Core en Windows](windows-prerequisites.md) para obtener más información.

## <a name="linux-rids"></a>RID de Linux

- Portátil
  - `linux-x64`
- CentOS
  - `centos-x64`
  - `centos.7-x64`
- Debian
  - `debian-x64`
  - `debian.8-x64`
- Fedora
  - `fedora-x64`
  - `fedora.24-x64`
  - `fedora.25-x64` (.NET Core 2.0 o versiones posteriores)
  - `fedora.26-x64` (.NET Core 2.0 o versiones posteriores)
- Gentoo (.NET Core 2.0 o versiones posteriores)
  - `gentoo-x64`
- openSUSE
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- Oracle Linux
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- Red Hat Enterprise Linux
  - `rhel-x64`
  - `rhel.6-x64` (.NET Core 2.0 o versiones posteriores)
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - `rhel.7.3-x64` (.NET Core 2.0 o versiones posteriores)
  - `rhel.7.4-x64` (.NET Core 2.0 o versiones posteriores)
- Tizen (.NET Core 2.0 o versiones posteriores)
  - `tizen`
- Ubuntu
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- Derivados de Ubuntu
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - `linuxmint.18.1-x64` (.NET Core 2.0 o versiones posteriores)

Vea [requisitos previos para .NET Core en Linux](linux-prerequisites.md) para obtener más información.

## <a name="macos-rids"></a>macOS RID

RID macOS use la marca de "OSX" anterior.

- `osx-x64`(.NET core 2.0 o versiones posteriores, la versión mínima es `osx.10.12-x64`)
- `osx.10.10-x64`
- `osx.10.11-x64`
- `osx.10.12-x64` (.NET Core 1.1 o versiones posteriores)
- `osx.10.13-x64`

Vea [requisitos previos para .NET Core en macOS](macos-prerequisites.md) para obtener más información.

## <a name="android-rids-net-core-20-or-later-versions"></a>RID de Android (.NET Core 2.0 o versiones posteriores)

- `android`
- `android.21`

## <a name="see-also"></a>Vea también

[Identificadores de entorno de ejecución](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
