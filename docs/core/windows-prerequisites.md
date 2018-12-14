---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
ms.date: 12/05/2018
ms.openlocfilehash: 8f9a823ab3eea15d7e33da6ff00992057c8c4e38
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130935"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Requisitos previos para .NET Core en Windows

En este artículo se muestran las versiones compatibles del sistema operativo para ejecutar aplicaciones .NET Core en Windows. Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:

* [Línea de comandos](tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [Visual Studio Code](https://code.visualstudio.com/)

También, si desarrolla en Windows con Visual Studio 2017, en la sección [Requisitos previos con Visual Studio 2017](#prerequisites-with-visual-studio-2017) puede encontrar más detalles sobre las versiones mínimas compatibles con el desarrollo de .NET Core.

## <a name="net-core-supported-windows-versions"></a>Versiones admitidas de Windows de .NET Core

.NET Core es compatible con las siguientes versiones de:

* Windows 7 SP1
* Windows 8.1
* Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores
* Windows Server 2008 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2012 SP1 (Servidor completo o Server Core)
* Windows Server 2012 R2 (servidor completo o Server Core)
* Windows Server 2016 o versiones posteriores (Servidor completo, Server Core o Nano Server)

## <a name="net-core-supported-operating-systems"></a>Sistemas operativos admitidos por .NET Core

Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:

* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1-supported-os.md)
* [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

Para vínculos de descarga y más información, vaya a [Descargas de .NET](https://www.microsoft.com/net/download) para descargar la versión más reciente o al [archivo de descargas de .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) para versiones anteriores.

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016. Esta dependencia se instala automáticamente si usa el instalador de .NET Core.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:

* A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).
* Al implementar una aplicación de .NET Core independiente.
* Al compilar el producto desde el origen.
* Al instalar .NET Core a través de un archivo *.zip*. Esto puede incluir servidores de compilación, integración continua o implementación continua.

> [!NOTE]
> **Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**
>
> Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update. Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.
>
> **Para Windows 7 o Windows Server 2008 R2:**
>
> Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-with-visual-studio-2017"></a>Requisitos previos con Visual Studio 2017

Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core. Visual Studio 2017 proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.

Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Para desarrollar aplicaciones .NET Core en Visual Studio 2017 con el SDK de .NET Core 2.2:

 1. [Descargue e instale Visual Studio 2017 versión 15.9.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-2017-workloads.jpg)

Una vez instalado el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio habitualmente instala una versión anterior del SDK de .NET Core.
Por ejemplo, Visual Studio 2017 15.9 usa el SDK de .NET Core 2.1 de manera predeterminada una vez que se instala la carga de trabajo.

Para actualizar Visual Studio para que use el SDK de .NET Core 2.2:

 1. Instale el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download).

 1. Si quiere que el proyecto use el entorno de ejecución de .NET Core más reciente, redestine los proyectos de .NET Core nuevos o existentes a .NET Core 2.2 según las instrucciones siguientes:

    * En el menú **Proyecto** , elija **Propiedades**.
    * En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.2**.

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino ".NET Core 2.2" seleccionado](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Una vez que Visual Studio está configurado con el SDK de .NET Core 2.2, puede realizar las siguientes acciones:

* Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.
* Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 2.2, compilarlos y ejecutarlos.
* Crear proyectos de .NET Core 2.2.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017](/visualstudio/install/install-visual-studio) con la carga de trabajo **"Desarrollo multiplataforma de .NET Core"** (en la sección **Otros conjuntos de herramientas**) seleccionada.

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:
  > * Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.
  > * Los proyectos están basados en project.json, que está en desuso.
>
> Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).

---

<a name="vs-mapping"></a>

> [!TIP]
> Para comprobar la versión de Visual Studio, haga lo siguiente:
>
> * En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
> * En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.
>   * Para las aplicaciones de .NET Core 3.0 Preview 1, debe ser Visual Studio 2019 Preview 1 o una versión superior.
>   * Para las aplicaciones de .NET Core 2.2, debe ser Visual Studio 2017 versión 15.9 o una versión superior.
>   * Para las aplicaciones de .NET Core 2.1, debe ser Visual Studio 2017 versión 15.7 o una versión superior.
>   * Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.
