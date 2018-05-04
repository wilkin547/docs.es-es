---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 6f2ba8540a38f8e30d3d968f5e2c891c850053aa
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a>Requisitos previos para .NET Core en Windows

En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Windows. Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:

* [Línea de comandos](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>Versiones admitidas de Windows de .NET Core

.NET Core es compatible con las siguientes versiones de:

* Windows 7 SP1
* Windows 8.1
* Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores
* Windows Server 2008 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2012 SP1 (Servidor completo o Server Core)
* Windows Server 2012 R2 (servidor completo o Server Core)
* Windows Server 2016 (Servidor completo, Server Core o Nano Server)

Vea el artículo [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x.

Vea el artículo [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x.

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016. Esta dependencia se instala automáticamente si usa el instalador de .NET Core.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:

* A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).
* Al implementar una aplicación de .NET Core independiente.
* Al compilar el producto desde el origen.
* Al instalar .NET Core a través de un archivo *.zip*. Esto puede incluir servidores de compilación, integración continua o implementación continua.

> [!NOTE]
> *En Windows 8.1 y versiones anteriores, o Windows Server 2012 R2 y versiones anteriores:* Asegúrese de que la instalación de Windows está actualizada e incluye [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), que puede instalarse a través de Windows Update. Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.

## <a name="prerequisites-with-visual-studio-2017"></a>Requisitos previos con Visual Studio 2017

Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core. [Visual Studio 2017](#visual-studio-2017) proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.

Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Para desarrollar aplicaciones de .NET Core 2.x en Visual Studio 2017:

 1. [Descargue e instale Visual Studio 2017 versión 15.3.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-15-3-workloads.jpg)

Después de instalar el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio 2017 usará .NET Core 1.x de forma predeterminada. Instale el SDK de .NET Core 2.x para obtener compatibilidad con .NET Core 2.x en Visual Studio 2017.

 2. Instale el [SDK de .NET Core 2.x](https://www.microsoft.com/net/download/core).
 3. Redestine los proyectos de .NET Core 1.x nuevos o existentes a .NET Core 2.x siguiendo estas instrucciones:
    * En el menú **Proyecto**, elija **Propiedades**.
    * En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.0**.

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino “.NET Core 2.0” seleccionado](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Una vez haya instalado el SDK de .NET Core 2.x, Visual Studio 2017 usará el SDK de .NET Core 2.x de manera predeterminada y admitirá las siguientes acciones:

* Apertura, compilación y ejecución de proyectos de .NET Core 1.x existentes.
* Redestinación de proyectos de .NET Core 1.x a .NET Core 2.x, compilación y ejecución.
* Creación de proyectos de .NET Core 2.x.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017 RTM (versión 15.0.26228.4) o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **“desarrollo multiplataforma de .NET Core”** (en la sección **Otros conjuntos de herramientas**) seleccionada.

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:
  > * Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.
  > * Los proyectos están basados en project.json, que está en desuso.
>
> Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).
---

> [!TIP]
> Para comprobar la versión de Visual Studio 2017, haga lo siguiente:
>
> * En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
> * En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.
>   * Para las aplicaciones de .NET Core 2.1 Preview 1, Visual Studio 2017 versión 15.6 Preview 6 o una versión superior.
>   * Para las aplicaciones de .NET Core 2.0, debe ser Visual Studio 2017 versión 15.3 o una versión superior.
>   * Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.
