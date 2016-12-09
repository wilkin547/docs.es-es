---
title: Requisitos previos de .NET Core (herramientas de Preview 3)
description: Requisitos previos de .NET Core (herramientas de Preview 3)
keywords: .NET, .NET Core
author: billwagner
ms.author: wiwagn
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 07b62bd7163193eff8dc8f61fda7a45a924bba2b
ms.openlocfilehash: ee4ccba7c06f0a7f67e3fe59c885febf895235fd

---

# <a name="prerequisites-for-windows-development-preview-3-tooling"></a>Requisitos previos para el desarrollo de Windows (herramientas de Preview 3)

Se requiere el desarrollo de .NET Core en Windows con Visual Studio:

* Una versión compatible del cliente o sistema operativo Windows.
* Visual Studio 2017 RC o posterior
* .NET Core Tooling Preview 3

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

Puede desarrollar aplicaciones .NET Core con cualquier editor mediante las herramientas de la línea de comandos de .NET Core; pero, si quiere usar Visual Studio y Preview 3 de las herramientas de .NET Core, necesitará Visual Studio 2017 RC o posterior. Puede descargar [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/) de manera gratuita. 

Compruebe que ejecuta Visual Studio 2017 RC:

* En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
* En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, el número de versión debe ser 15.0.25831.1 o posterior.

Puede leer más acerca de los cambios en Visual Studio 2017 RC en las [notas de la versión](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

Asegúrese de que instala la carga de trabajo ".NET Core y Docker (versión preliminar)" durante la instalación. Si no lo ha hecho, puede volver a ejecutar el programa de instalación y seleccionarla.



<!--HONumber=Nov16_HO3-->


