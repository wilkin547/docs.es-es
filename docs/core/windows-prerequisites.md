---
title: Requisitos previos de .NET Core
description: Requisitos previos de .NET Core
keywords: .NET, .NET Core
author: billwagner
manager: wpickett
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 130b94a745b0e3222e205d8af26194239130ec9c
ms.openlocfilehash: 04018ec65272745ef98a2a96eb30009bcf44cb2e

---

# <a name="prerequisites-for-windows-development"></a>Requisitos previos para el desarrollo de Windows

Se requiere el desarrollo de .NET Core en Windows con Visual Studio:

* Una versión compatible del cliente o sistema operativo Windows.
* Visual Studio 2015 Update 3.3 o una versión posterior
* Extensión del Administrador de paquetes NuGet para Visual Studio
* Herramientas de .NET Core Preview 2

## <a name="supported-windows-versions"></a>Versiones admitidas de Windows

.NET Core es compatible con las siguientes versiones de Windows:

* Windows 7 SP1
* Windows 8.1
*  Windows 10 
* Windows Server 2008 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2012 SP1 (Servidor completo o Server Core)
* Windows Server 2012 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2016 (Servidor completo, Server Core o Nano Server)

Puede ver el conjunto completo de [sistemas operativos compatibles](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) en las [notas de la versión de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core requiere VC++ Redistributable cuando se ejecuta en Windows. Lo instala automáticamente el instalador de .NET Core. Debe instalar manualmente Visual C++ Redistributable si instala .NET Core a través del script del instalador (`dotnet-install.ps1`). 

La versión de Visual C++ Reditributable varía según la versión de Windows.

* Windows 10
    * [Visual C++ Redistributable para Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145)
* Windows 7+ (no Windows 10)
    * Asegúrese de que la instalación de Windows está actualizada y que incluye la revisión [KB2533623](https://support.microsoft.com/en-us/kb/2533623) instalada a través de Windows Update.
    * [Actualización de Universal CRT](https://www.microsoft.com/en-us/download/details.aspx?id=48234) (puede obtener más información sobre las novedades de CRT Universal en [esta entrada de blog](https://blogs.msdn.microsoft.com/vcblog/2015/03/03/introducing-the-universal-crt/))

## <a name="visual-studio"></a>Visual Studio

Necesita Visual Studio 2015 para desarrollar aplicaciones .NET Core. Puede descargar [Visual Studio Community 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs) de manera gratuita. 

Compruebe que se está ejecutando [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx):

* En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
* En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, el número de versión debe ser 14.0.25424.00 o posterior e incluir "Update 3".
* Si no tiene esta actualización, primero debe descargar e instalar [Visual Studio 2015 Update 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).
* Si tiene la actualización 3, pero el número de versión es menor que 14.0.25424.00, necesita descargar e instalar [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx).

Puede leer más acerca de los cambios de Update 3 en las [notas de la versión](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

## <a name="nuget-manager-extension-for-visual-studio"></a>Extensión del Administrador de paquetes NuGet para Visual Studio

NuGet es el administrador de paquetes para la plataforma de desarrollo de Microsoft incluido .NET Core. Necesita [NuGet 3.5.0](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) o superior para crear aplicaciones .NET Core.

## <a name="net-core-tools-for-visual-studio-2015"></a>Herramientas de .NET Core para Visual Studio 2015

Descargue e instale el [SDK] de [las herramientas de .NET Core 1.0.1 - VS 2015 Preview 2]. 

El paquete de herramientas de .NET Core instala .NET Core, plantillas de proyecto y otras herramientas para Visual Studio 2015.

> [!NOTE]
Actualmente, no puede descargar un instalador sin conexión para el [SDK] de las [herramientas de .NET Core 1.0.1 - VS 2015 Preview 2]. En su lugar, tiene que descargar el [SDK] del [programa previo regular] y ejecutarlo con la opción de línea de comandos (como `/layout c:\path`) para obtener un diseño sin conexión. Después, se puede utilizar como un instalador sin conexión: solo debe ejecutar el archivo ejecutable en la ruta de acceso local. Tenga en cuenta que dado que es un diseño completo, este procedimiento descarga todos los paquetes de todos los idiomas admitidos y ocupa aproximadamente 1 GB.

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546



<!--HONumber=Nov16_HO1-->


