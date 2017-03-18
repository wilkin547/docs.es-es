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
ms.sourcegitcommit: e374b924bf78d62227cb9607641130dfd9128186
ms.openlocfilehash: 6383a0ce253f6f7000ed8a81b29b9e1d58914acc
ms.lasthandoff: 03/06/2017

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

## <a name="prerequisites-with-visual-studio-2017"></a>Requisitos previos con Visual Studio 2017

Puede usar cualquier editor que prefiera para desarrollar aplicaciones .NET Core con el SDK de .NET Core. En cambio, si quiere desarrollar aplicaciones .NET Core en Windows en un entorno de desarrollo integrado, puede usar [Visual Studio 2017](#visual-studio-2017).

Para usar Visual Studio 2017 para desarrollar aplicaciones .NET Core, necesitará tener la versión más reciente de Visual Studio instalada con el conjunto de herramientas **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionado.

Hay diferentes ediciones de Visual Studio 2017. Puede descargar [Visual Studio Community 2017](https://www.visualstudio.com/vs/visual-studio-2017/#downloadvs) gratis para empezar.  Para obtener más información sobre el proceso de instalación de Visual Studio, vea [Install Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) (Instalación de Visual Studio 2017).

Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546
