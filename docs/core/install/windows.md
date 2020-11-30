---
title: Instalación de .NET en Windows
description: Obtenga información sobre las versiones de Windows en las que puede instalar .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 4d3abde965d9a2ab0f86477feeb7c10f274a4b9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715126"
---
# <a name="install-net-on-windows"></a>Instalación de .NET en Windows

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

En este artículo obtendrá información sobre cómo instalar .NET en Windows. .NET está formado por el entorno de ejecución y el SDK. El entorno de ejecución se usa para ejecutar una aplicación de .NET, y puede o no incluirse con la aplicación. El SDK se usa para crear aplicaciones y bibliotecas de .NET. El entorno de ejecución de .NET siempre se instala con el SDK.

La versión más reciente de .NET es la 5.0.

> [!div class="button"]
> [Descarga de .NET](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Versiones compatibles

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Windows en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Windows llega al final del ciclo de vida](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

Las fechas de fin de servicio de Windows 10 están segmentadas por edición. En la tabla que hay a continuación solo se tienen en cuenta las ediciones **Home**, **Pro**, **Pro Education** y **Pro for Workstations**. Para ver detalles específicos, consulte la [hoja informativa sobre el ciclo de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

- Con la marca ✔️ se indica que todavía se admite la versión de Windows o .NET Core.
- Con la marca ❌ se indica que la versión de Windows o .NET Core no se admite en esa versión de Windows.
- Si una versión de Windows y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Sistema operativo                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ Windows 10, versión 2004 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ Windows 10, versión 1909 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ Windows 10, versión 1903 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ Windows 10, versión 1809 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ Windows 10, versión 1803 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ Windows 10, versión 1709 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ Windows 10, versión 1703 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ Windows 10, versión 1607 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ Windows 10, versión 1511 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ Windows 10, versión 1507 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 |

## <a name="unsupported-releases"></a>Versiones no admitidas

Las versiones siguientes de .NET ya ❌ no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="runtime-information"></a>Información en tiempo de ejecución

El entorno de ejecución se usa para ejecutar aplicaciones creadas con .NET. Cuando un autor publica una aplicación, puede incluir el tiempo de ejecución. Si no lo hace, el usuario elige si quiere instalar el tiempo de ejecución.

Hay tres entornos de ejecución distintos que se pueden instalar en Windows:

*Entorno de ejecución de ASP.NET Core*\
Ejecuta aplicaciones de ASP.NET Core. Incluye el entorno de ejecución de .NET.

*Entorno de ejecución de escritorio*\
Ejecuta aplicaciones de escritorio WPF y Windows Forms de .NET para Windows. Incluye el entorno de ejecución de .NET.

*Entorno de ejecución de .NET*\
Este entorno de ejecución es el más sencillo y no incluye ningún otro. Se recomienda encarecidamente instalar el *entorno de ejecución de ASP.NET Core* y el *entorno de ejecución de escritorio* para conseguir la mejor compatibilidad con las aplicaciones de .NET.

> [!div class="button"]
> [Descarga del entorno de ejecución de .NET](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Información del SDK

El SDK se usa para compilar y publicar aplicaciones y bibliotecas de .NET. La instalación del SDK incluye los tres [entornos de ejecución](#runtime-information): el de ASP.NET Core, el de escritorio y el de .NET.

## <a name="dependencies"></a>Dependencias

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[.NET 5.0](#tab/net50)

Las versiones siguientes de Windows son compatibles con .NET 5.0:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                  | Versión       | Arquitecturas   |
|---------------------|---------------|-----------------|
| Cliente de Windows 10   | Versión 1607 y posteriores | x64, x86, ARM64 |
| Cliente Windows      | 7 SP1 y posteriores, y 8.1   | x64, x86        |
| Windows Server      | 2012 R2 y posteriores      | x64, x86        |
| Windows Server Core | 2012 R2 y posteriores      | x64, x86        |
| Nano Server         | Versión 1809 y posteriores | x64             |

Para obtener más información sobre los sistemas operativos compatibles con .NET 5.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET 5.0](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Las versiones siguientes de Windows son compatibles con .NET Core 3.1:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| SO                            | Versión                        | Arquitecturas   |
| ----------------------------- | ------------------------------ | --------------- |
| Cliente Windows                | 7 SP1 y posteriores, y 8.1                    | x64, x86        |
| Cliente de Windows 10             | Versión 1609+                  | x64, x86        |
| Windows Server                | 2012 R2 y posteriores                       | x64, x86        |
| Nano Server                   | Versión 1803 y posteriores                  | x64, ARM32      |

Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

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

*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

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

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2

Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:

- ❌ Windows 7 SP1
- ❌ Windows Vista SP2
- ✔️ Windows 8.1
- ✔️ Windows Server 2008 R2
- ✔️ Windows Server 2012 R2

Instale el software siguiente:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:

> El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo. Intente volver a instalar el programa para corregir este problema.
>
> \- o -
>
> El programa no se puede iniciar porque falta el archivo *api-ms-win-cor-timezone-l1-1-0.dll* en el equipo. Intente volver a instalar el programa para corregir este problema.
>
> \- o -
>
> La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.

## <a name="install-with-powershell-automation"></a>Instalación mediante la automatización de PowerShell

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización de CI y las instalaciones que no son de administrador del entorno de ejecución. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Puede elegir una versión concreta especificando el modificador `Channel`. Incluya el modificador `Runtime` para instalar un entorno de ejecución. De lo contrario, el script instala el SDK.

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

Instale el SDK omitiendo el modificador `-Runtime`. El modificador `-Channel` de este ejemplo está establecido en `Current`, con lo que se instala la versión admitida más reciente.

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a>Instalación con Visual Studio

Si usa Visual Studio para desarrollar aplicaciones de .NET, en la tabla siguiente se describe la versión mínima necesaria de Visual Studio, en función de la versión del SDK de .NET de destino.

| Versión de SDK de .NET      | Versión de Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 5.0                   | Visual Studio 2019, versión 16.8 o posterior. |
| 3.1                   | Visual Studio 2019, versión 16.4 o posterior. |
| 3.0                   | Visual Studio 2019, versión 16.3 o posterior. |
| 2.2                   | Visual Studio 2017, versión 15.9 o posterior. |
| 2.1                   | Visual Studio 2017, versión 15.7 o posterior. |

Si ya tiene Visual Studio instalado, puede comprobar la versión siguiendo los pasos que se detallan a continuación.

01. Abra Visual Studio.
01. Seleccione **Ayuda** > **Acerca de Microsoft Visual Studio**.
01. Lea el número de versión en el cuadro de diálogo **Acerca de**.

Visual Studio puede instalar el SDK y el entorno de ejecución de .NET más recientes.

> [!div class="button"]
> [Descargue Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Selección de una carga de trabajo

Al instalar o modificar Visual Studio, seleccione una de las cargas de trabajo siguientes o más, en función del tipo de aplicación que quiera compilar:

- La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.
- La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.
- La carga de trabajo **Desarrollo de Azure** en la sección **Web y nube**.
- La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Móviles y de escritorio**.

[![Visual Studio 2019 para Windows con la carga de trabajo de .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Instalación junto con Visual Studio Code

Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio. Visual Studio Code está disponible para Windows, macOS y Linux.

Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.

01. [Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).
01. [Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="download-and-manually-install"></a>Descarga e instalación de forma manual

Como alternativa a los instaladores de Windows para .NET, puede descargar e instalar manualmente el SDK o el entorno de ejecución. La instalación manual se suele llevar a cabo durante las pruebas de integración continua. Para un desarrollador o usuario, generalmente es mejor usar un [instalador](https://dotnet.microsoft.com/download/dotnet-core).

Tanto el SDK como el entorno de ejecución de .NET se pueden instalar manualmente una vez que se han descargado. Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente. En primer lugar, descargue una versión binaria del SDK o del entorno de ejecución de uno de los siguientes sitios:

- ✔️ [Descargas de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Todas las descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Cree un directorio en el que se extraerá .NET; por ejemplo, `%USERPROFILE%\dotnet`. Después, extraiga el archivo ZIP descargado en ese directorio.

De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET no usarán la versión de .NET instalada de esta manera y debe elegir explícitamente usarla. Para ello, cambie las variables de entorno con las que se inicia una aplicación:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.

Cuando `DOTNET_MULTILEVEL_LOOKUP` se establece en `0`, .NET ignora cualquier versión de .NET instalada de forma global. Elimine esa configuración de entorno para que .NET tenga en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación. La ubicación predeterminada suele ser `C:\Program Files\dotnet`, en la que los instaladores instalan .NET.

## <a name="docker"></a>Docker

Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host. Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.

.NET se puede ejecutar en un contenedor de Docker. Las imágenes oficiales de Docker en .NET se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET](https://hub.docker.com/_/microsoft-dotnet). Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.

Microsoft ofrece imágenes que se adaptan a escenarios específicos. Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.

Para obtener más información sobre el uso de .NET en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para comprobar que .NET ya está instalado](how-to-detect-installed-versions.md?pivots=os-windows).
- [Tutorial: Tutorial Hola mundo](../tutorials/with-visual-studio.md).
- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).
