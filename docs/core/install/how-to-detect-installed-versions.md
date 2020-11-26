---
title: 'Comprobación de las versiones de .NET instaladas en Windows, Linux y macOS: .NET'
description: Obtenga información sobre cómo mostrar las versiones de .NET que están instaladas en el equipo. Esto incluye el entorno de ejecución y el SDK de .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 39020a32cdea9b82dc9d30e62e663ebc4ee39ebb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687447"
---
# <a name="how-to-check-that-net-is-already-installed"></a>Cómo comprobar que .NET Core ya está instalado

En este artículo se explica cómo comprobar las versiones del entorno de ejecución y el SDK de .NET que están instaladas en el equipo. Es posible que .NET ya se haya instalado si tiene un entorno de desarrollo integrado, como Visual Studio o Visual Studio para Mac.

Al instalar un SDK, se instala el entorno de ejecución correspondiente.

Si se produce un error en alguno de los comandos de este artículo, no tendrá instalado el entorno de ejecución o el SDK. Para obtener más información, consulte los artículos de instalación para [Windows](windows.md), [macOS](macos.md) o [Linux](linux.md).

## <a name="check-sdk-versions"></a>Comprobación de las versiones del SDK

Se pueden ver las versiones del SDK de .NET que están instaladas actualmente con un terminal. Abra un terminal y ejecute el comando siguiente.

```dotnetcli
dotnet --list-sdks
```

Verá un resultado similar al siguiente.

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
5.0.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
5.0.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
5.0.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a>Comprobación de las versiones del entorno de ejecución

Se pueden ver las versiones del entorno de ejecución de .NET que están instaladas actualmente con el comando siguiente.

```dotnetcli
dotnet --list-runtimes
```

Verá un resultado similar al siguiente.

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a>Buscar carpetas de instalación

Es posible que .NET esté instalado, pero no se haya agregado a la variable `PATH` del sistema operativo o el perfil de usuario. Es posible que no funcione la ejecución de los comandos de las secciones anteriores. Como alternativa, puede comprobar que existen las carpetas de instalación de .NET.

Al instalar .NET desde un instalador o un script, la instalación se efectúa en una carpeta estándar. La mayor parte del tiempo, el instalador o el script que usa para instalar .NET le ofrece la opción de realizar la instalación en otra carpeta. Si decide instalar en una carpeta diferente, ajuste el inicio de la ruta de acceso de la carpeta.

::: zone pivot="os-windows"

- **archivo ejecutable de dotnet**\
_C:\\archivos de programa\\dotnet\\dotnet.exe_

- **.NET SDK**\
_C:\\archivos de programa\\dotnet\\sdk\\{versión}\\_

- **Runtime de .NET**\
_C:\\archivos de programa\\dotnet\\shared\\{tipo de runtime}\\{versión}\\_

::: zone-end

::: zone pivot="os-linux"

- **archivo ejecutable de dotnet**\
_/home/user/share/dotnet/dotnet_

- **.NET SDK**\
_/home/user/share/dotnet/sdk/{versión}/_

- **Runtime de .NET**\
_/home/user/share/dotnet/shared/{tipo de runtime}/{versión}/_

::: zone-end

::: zone pivot="os-macos"

- **archivo ejecutable de dotnet**\
_/usr/local/share/dotnet/dotnet_

- **.NET SDK**\
_/usr/local/share/dotnet/sdk/{versión}/_

- **Runtime de .NET**\
_/usr/local/share/dotnet/shared/{tipo de runtime}/{versión}/_

::: zone-end

## <a name="more-information"></a>Más información

Se pueden ver las versiones del SDK y del entorno de ejecución con el comando `dotnet --info`. También obtendrá otra información relacionada con el entorno, como la versión del sistema operativo y el identificador del entorno de ejecución (RID).

## <a name="next-steps"></a>Pasos siguientes

- [Instalación del SDK y el entorno de ejecución de .NET para Windows](windows.md).
- [Instalación del SDK y el entorno de ejecución de .NET para macOS](macos.md).
- [Instalación del SDK y el entorno de ejecución de .NET para Linux](linux.md).
