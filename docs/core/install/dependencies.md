---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448898"
---
# <a name="net-core-dependencies-and-requirements"></a>Dependencias y requisitos de .NET Core

En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.

## <a name="supported-operating-systems"></a>Sistemas operativos admitidos

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Las versiones siguientes de Windows son compatibles con .NET Core 3.1:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                            | Versión                        | Arquitecturas   |
| ----------------------------- | ------------------------------ | --------------- |
| Cliente Windows                | 7 SP1 y posteriores, y 8.1                    | x64, x86        |
| Cliente de Windows 10             | Versión 1607 y posteriores                  | x64, x86        |
| Windows Server                | 2012 R2 y posteriores                       | x64, x86        |
| Nano Server                   | Versión 1803 y posteriores                  | x64, ARM32      |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

Las versiones siguientes de Windows son compatibles con .NET Core 3.0:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                            | Versión                        | Arquitecturas   |
| ----------------------------- | ------------------------------ | --------------- |
| Cliente Windows                | 7 SP1 y posteriores, y 8.1                    | x64, x86        |
| Cliente de Windows 10             | Versión 1607 y posteriores                  | x64, x86        |
| Windows Server                | 2012 R2 y posteriores                       | x64, x86        |
| Nano Server                   | Versión 1803 y posteriores                  | x64, ARM32      |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

Las versiones siguientes de Windows son compatibles con .NET Core 2.2:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                            | Versión                        | Arquitecturas   |
| ----------------------------- | ------------------------------ | --------------- |
| Cliente Windows                | 7 SP1 y posteriores, y 8.1                    | x64, x86        |
| Cliente de Windows 10             | Versión 1607 y posteriores                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 y posteriores                   | x64, x86        |
| Nano Server                   | Versión 1803 y posteriores                   | x64, ARM32      |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Las versiones siguientes de Windows son compatibles con .NET Core 2.1:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                            | Versión                        | Arquitecturas   |
| ----------------------------- | ------------------------------ | --------------- |
| Cliente Windows                | 7 SP1 y posteriores, y 8.1                    | x64, x86        |
| Cliente de Windows 10             | Versión 1607 y posteriores                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 y posteriores                   | x64, x86        |
| Nano Server                   | Versión 1803 y posteriores                  | x64,            |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7, Vista, 8.1, Server 2008 R2

Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:

- Windows 7 SP1
- Windows Vista SP2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Instale el software siguiente:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:

> El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo. Intente volver a instalar el programa para corregir este problema.
>
> \- o -
>
> La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 considera Linux como un único sistema operativo. Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.

.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                             | Versión               | Arquitecturas    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7 (o posterior)                    | x64 |
| Oracle Linux                   | 7 (o posterior)                    | x64 |
| Fedora                         | 29+                   | x64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | x64 |
| openSUSE                       | 15+                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.10 y posteriores                 | x64, ARM64 |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

> [!IMPORTANT]
> La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior. No todas las distribuciones de Linux cumplen este requisito. Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 considera a Linux como un único sistema operativo. Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.

.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                             | Versión               | Arquitecturas    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7 (o posterior)                    | x64 |
| Oracle Linux                   | 7 (o posterior)                    | x64 |
| Fedora                         | 29+                   | x64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | x64 |
| openSUSE                       | 15+                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 considera a Linux como un único sistema operativo. Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.

.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                             |  Versión                |  Arquitecturas   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | x64 |
| CentOS                         |  7                      | x64 |
| Oracle Linux                   |  7                      | x64 |
| Fedora                         |  29, 30                 | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 18.10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | x64 |
| openSUSE                       |  15+                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 considera a Linux como un único sistema operativo. Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.

.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                             |  Versión                |  Arquitecturas   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | x64 |
| CentOS                         |  7 (o posterior)                     | x64 |
| Oracle Linux                   |  7 (o posterior)                     | x64 |
| Fedora                         |  29+                    | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 19.04 y 19.10    | x64, ARM32 |
| Linux Mint                     |  17 y posteriores                    | x64 |
| openSUSE                       |  15+                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

## <a name="linux-distribution-dependencies"></a>Dependencias de distribución de Linux

En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.

> [!IMPORTANT]
> Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.

### <a name="ubuntu"></a>Ubuntu

Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:

- liblttng-ust0
- libcurl3 (para 14.x y 16.x)
- libcurl4 (para 18.x)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52 (para 14.x)
- libicu55 (para 16.x)
- libicu57 (para 17.x)
- libicu60 (para 18.x)

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:

- libgdiplus (versión 6.0.1 o posteriores)

> [!WARNING]
> La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus. Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS y Fedora

Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.

En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:

- libunwind
- libuuid

Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- libgdiplus (versión 6.0.1 o posteriores)

> [!WARNING]
> La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus. Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

::: zone-end

::: zone pivot="os-macos"

.NET Core es compatible con las versiones siguientes de macOS:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| Versión de .NET Core | macOS                 | Arquitecturas |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13 y posteriores)  | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13 y posteriores)  | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 y posteriores)       | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 y posteriores)       | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a>libgdiplus

Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.

Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS. Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>Pasos siguientes

- Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.
- Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).
