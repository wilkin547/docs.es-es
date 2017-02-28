---
title: Requisitos previos para .NET Core en Windows | Microsoft Docs
description: "Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core."
keywords: .NET Core, Windows, requisitos previos, dependencias, Visual Studio
author: mairaw
ms.author: mairaw
ms.date: 01/05/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: a8019c9fc25ef458aa555743e61cd83a3beb11ed
ms.openlocfilehash: b5c088da7d1155414a08995ae0d72154af891190
ms.lasthandoff: 02/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Requisitos previos para .NET Core en Windows

En este artículo se muestra qué dependencias necesita para implementar y ejecutar aplicaciones .NET Core en máquinas con Windows y desarrollar con Visual Studio.

## <a name="supported-windows-versions"></a>Versiones admitidas de Windows

.NET Core es compatible con las siguientes versiones de Windows:

* Windows 7 SP1
* Windows 8.1
* Windows 10 
* Windows Server 2008 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2012 SP1 (Servidor completo o Server Core)
* Windows Server 2012 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2016 (Servidor completo, Server Core o Nano Server)

Puede ver el conjunto completo de [sistemas operativos compatibles](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) en las [notas de la versión de .NET Core 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core requiere Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016. Esta dependencia se instala automáticamente si utiliza el instalador de .NET Core. Sin embargo, debe instalar manualmente [Visual C++ Redistributable para Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145) si instala .NET Core a través del [script del instalador](https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-install-script) o implementa una aplicación independiente de .NET Core.

> [!NOTE]
> <em>Solo para máquinas con Windows 7 y Windows Server 2008:</em><br>
> Asegúrese de que la instalación de Windows está actualizada y que incluye la revisión [KB2533623](https://support.microsoft.com/en-us/kb/2533623) instalada a través de Windows Update.

## <a name="prerequisites-with-visual-studio"></a>Requisitos previos con Visual Studio

Puede usar cualquier editor que prefiera para desarrollar aplicaciones .NET Core con el SDK de .NET Core. Sin embargo, si desea desarrollar aplicaciones .NET Core en Windows con Visual Studio, hay dos versiones que puede usar:

* [Visual Studio 2015](#visual-studio-2015)
* [Visual Studio 2017 RC](#visual-studio-2017-rc)

Los proyectos creados con Visual Studio 2015 se basarán en project.json de forma predeterminada, mientras que los proyectos creados con Visual Studio 2017 RC siempre se basarán en MSBuild. Para más información sobre los cambios de formato, consulte [High-level overview of changes](./preview3/tools/layering.md) (Información general de alto nivel sobre los cambios).

### <a name="visual-studio-2015"></a>Visual Studio 2015

Si desea usar Visual Studio 2015 para desarrollar aplicaciones .NET Core, necesitará:

* Visual Studio 2015 Update 3.3 o posterior.

   Hay diferentes [ediciones](https://www.visualstudio.com/vs/compare) de Visual Studio 2015. Puede descargar [Visual Studio Community 2015](https://www.visualstudio.com/downloads/) gratis para empezar. 

   Para comprobar que está ejecutando [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx), haga lo siguiente:

   * En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
   * En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, el número de versión debe ser 14.0.25424.00 o posterior e incluir "Update 3".
   * Si no tiene esta actualización, primero debe descargar e instalar [Visual Studio 2015 Update 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).
   * Si tiene la actualización 3, pero el número de versión es menor que 14.0.25424.00, necesita descargar e instalar [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx).

   Puede leer más acerca de los cambios de Update 3 en las [notas de la versión](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

* Extensión del Administrador de paquetes NuGet para Visual Studio

   NuGet es el administrador de paquetes para la plataforma de desarrollo de Microsoft incluido .NET Core. Necesita [NuGet 3.5.0-beta](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) o superior para crear aplicaciones .NET Core.

* Herramientas de .NET Core Preview 2

   Descargue e instale las [herramientas de .NET Core 1.0.1 - VS 2015 Preview 2][sdk]. 

   El paquete de herramientas de .NET Core instala .NET Core, plantillas de proyecto y otras herramientas para Visual Studio 2015.

   > [!NOTE]
   > Actualmente, no puede descargar un instalador sin conexión para las [herramientas de .NET Core 1.0.1 - VS 2015 Preview 2][sdk]. En su lugar, tiene que descargar el [programa previo regular][sdk] y ejecutarlo con una opción de línea de comandos (como `/layout c:\path`) para obtener un diseño sin conexión. Después, se puede utilizar como un instalador sin conexión: solo debe ejecutar el archivo ejecutable en la ruta de acceso local. Tenga en cuenta que dado que es un diseño completo, este procedimiento descarga todos los paquetes de todos los idiomas admitidos y ocupa aproximadamente 1 GB.

### <a name="visual-studio-2017-rc"></a>Visual Studio 2017 RC

Si desea usar Visual Studio 2017 RC para desarrollar aplicaciones de .NET Core, debe tener la versión más reciente de Visual Studio RC instalada con la carga de trabajo ".NET Core y Docker (Preview)" seleccionada. 

Hay diferentes ediciones de Visual Studio 2017 RC. Puede descargar [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/#downloadvs) gratis para empezar.  Para más información sobre el proceso de instalación de Visual Studio, vea [Install Visual Studio 2017 RC](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) (Instalación de Visual Studio 2017 RC).

Para comprobar que está ejecutando la versión más reciente de Visual Studio 2017 RC, haga lo siguiente:

* En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
* En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, el número de versión debe ser 15.0.26020.0 o posterior.

Puede leer más acerca de los cambios en Visual Studio 2017 RC en las [notas de la versión](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546

