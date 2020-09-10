---
title: Catálogo de identificadores de entorno de ejecución (RID) de .NET Core
description: Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core.
ms.date: 02/22/2019
ms.openlocfilehash: 719c84248b955ec05d7cd9b361c7e5ebea6aa37b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414570"
---
# <a name="net-core-rid-catalog"></a>Catálogo de identificadores de entorno de ejecución (RID) de .NET Core

RID es la abreviatura de *identificador de entorno de ejecución*. Los valores de RID se usan para identificar las plataformas de destino donde se ejecuta la aplicación.
Los paquetes de .NET los usan para presentar los recursos específicos de la plataforma en los paquetes de NuGet. Los valores siguientes son ejemplos de RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.
En el caso de los paquetes con dependencias nativas, el RID designa las plataformas en las que se puede restauran el paquete.

Un único RID se puede establecer en el elemento `<RuntimeIdentifier>` del archivo del proyecto. Se pueden definir varios RID como una lista delimitada por punto y coma en el elemento `<RuntimeIdentifiers>` del archivo del proyecto. También se usan a través de la opción `--runtime` con los [comandos de la CLI de .NET Core](./tools/index.md) siguientes:

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

- `[additional qualifiers]` diferencia aún más las distintas plataformas. Por ejemplo: `aot`.

## <a name="rid-graph"></a>Grafo de RID

El grado de RID o el grafo de reserva de entorno de ejecución es una lista de RID compatibles entre sí. Los RID se definen en el paquete [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/). Puede ver la lista de RID compatibles y el grafo de RID en el archivo [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json), que se encuentra en el repositorio `dotnet/runtime`. En este archivo puede ver que todos los RID, excepto el RID de base, contienen una instrucción `"#import"`. Estas instrucciones indican los RID compatibles.

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

- No intente analizar los RID para recuperar partes de componentes.
- No compile RID mediante programación.
- Use RID que ya estén definidos para la plataforma.
- Los RID deben ser específicos, por lo que no se recomienda presuponer nada a partir del valor de RID real.

## <a name="using-rids"></a>Uso de los RID

Para poder usar los RID, debe saber cuáles son los RID que existen. Se agregan valores nuevos a la plataforma de manera habitual.
Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.

El SDK de .NET Core 2.0 presenta el concepto de RID portátiles. Son nuevos valores agregados al grafo de RID que no están vinculados a una versión específica o distribución del sistema operativo, y son la opción preferida cuando se usa .NET Core 2.0 y versiones posteriores. Resultan especialmente útiles al tratar con varias distribuciones de Linux dado que la mayoría de los RID de distribución se asignan a los RID portátiles.

En la lista siguiente se muestra un pequeño subconjunto de los RID más comunes que se usan con cada sistema operativo.

## <a name="windows-rids"></a>RID de Windows

Solo se muestran los valores comunes. Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.

- Portátil (.NET Core 2.0 o versiones posteriores)
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- Windows 7/Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8.1/Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10/Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

Para obtener más información, vea [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-windows) .

## <a name="linux-rids"></a>RID de Linux

Solo se muestran los valores comunes. Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`. Los dispositivos que ejecutan una distribución que no se muestran en la lista podrían funcionar con uno de los RID portátiles. Por ejemplo, el destino de los dispositivos Raspberry Pi que ejecutan una distribución de Linux se puede establecer con `linux-arm`.

- Portátil (.NET Core 2.0 o versiones posteriores)
  - `linux-x64` (La mayoría de las distribuciones de escritorio como CentOS, Debian, Fedora, Ubuntu y derivados)
  - `linux-musl-x64` (Distribuciones ligeras con [musl](https://wiki.musl-libc.org/projects-using-musl.html) como Alpine Linux)
  - `linux-arm` (Distribuciones de Linux que se ejecutan en ARM, como Raspbian en Raspberry Pi, modelo 2+)
  - `linux-arm64` (Distribuciones de Linux que se ejecutan en ARM de 64 bits, como Ubuntu Server de 64 bits en Raspberry Pi, modelo 3+)
- Red Hat Enterprise Linux
  - `rhel-x64` (Se reemplaza por `linux-x64` para RHEL por encima de la versión 6)
  - `rhel.6-x64` (.NET Core 2.0 o versiones posteriores)
- Tizen (.NET Core 2.0 o versiones posteriores)
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

Para obtener más información, vea [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-linux) .

## <a name="macos-rids"></a>RID de macOS

Los RID de macOS usan la personalización de marca antigua "OSX". Solo se muestran los valores comunes. Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.

- Portátil (.NET Core 2.0 o versiones posteriores)
  - `osx-x64` (La versión mínima del sistema operativo es macOS 10.12 Sierra)
- macOS 10.10  Yosemite
  - `osx.10.10-x64`
- macOS 10.11 El Capitan
  - `osx.10.11-x64`
- macOS 10.12 Sierra (.NET Core 1.1 o versiones posteriores)
  - `osx.10.12-x64`
- macOS 10.13 High Sierra (.NET Core 1.1 o versiones posteriores)
  - `osx.10.13-x64`
- macOS 10.14 Mojave (.NET Core 1.1 o versiones posteriores)
  - `osx.10.14-x64`

Para obtener más información, vea [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-macos) .

## <a name="see-also"></a>Vea también

- [Identificadores de entorno de ejecución](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
