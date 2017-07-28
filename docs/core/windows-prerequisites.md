---
title: Requisitos previos para .NET Core en Windows
description: "Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core."
keywords: .NET Core, Windows, requisitos previos, dependencias, Visual Studio
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Requisitos previos para .NET Core en Windows

En este artículo se muestra qué dependencias necesita para implementar y ejecutar aplicaciones .NET Core en máquinas Windows y desarrollar con Visual Studio.

## <a name="supported-windows-versions"></a>Versiones admitidas de Windows

.NET Core es compatible con las siguientes versiones de Windows:

* Windows 7 SP1
* Windows 8.1
* Windows 10 
* Windows Server 2008 R2 SP1 (Servidor completo o Server Core)
* Windows Server 2012 SP1 (Servidor completo o Server Core)
* Windows Server 2012 R2 (servidor completo o Server Core)
* Windows Server 2016 (Servidor completo, Server Core o Nano Server)

Consulte las [notas de la versión de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) para ver el conjunto completo de sistemas operativos admitidos.

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core requiere Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016. Esta dependencia se instala automáticamente si utiliza el instalador de .NET Core. En cambio, debe instalar manualmente [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) si instala .NET Core a través del [script del instalador](./tools/dotnet-install-script.md) o implementa una aplicación independiente de .NET Core.

> [!NOTE]
> <em>Solo para máquinas con Windows 7 y Windows Server 2008:</em><br>
> Asegúrese de que la instalación de Windows está actualizada y que incluye la revisión [KB2533623](https://support.microsoft.com/help/2533623) instalada a través de Windows Update.

## <a name="prerequisites-with-visual-studio-2017"></a>Requisitos previos con Visual Studio 2017

Puede usar cualquier editor que prefiera para desarrollar aplicaciones .NET Core con el SDK de .NET Core. En cambio, si quiere desarrollar aplicaciones .NET Core en Windows en un entorno de desarrollo integrado, puede usar [Visual Studio 2017](#visual-studio-2017).

> [!IMPORTANT]
> Aunque es posible usar Visual Studio 2015 con una versión preliminar de las herramientas de .NET Core, estos proyectos se basarán en *project.json*, que ahora está en desuso. Visual Studio 2017 usa archivos de proyecto basados en MSBuild. Para más información sobre los cambios de formato, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).

Para usar Visual Studio 2017 para desarrollar aplicaciones .NET Core, necesitará tener la versión más reciente de Visual Studio instalada con el conjunto de herramientas **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionado.
![Captura de pantalla de instalación de Visual Studio 2017 con la carga de trabajo de "desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs_workloads.jpg)

Hay diferentes ediciones de Visual Studio 2017. Puede descargar [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) gratis para empezar.  Para obtener más información sobre el proceso de instalación de Visual Studio, vea [Install Visual Studio 2017](/visualstudio/install/install-visual-studio) (Instalación de Visual Studio 2017).

Para comprobar que ejecuta la versión más reciente de Visual Studio 2017, haga lo siguiente:

 * En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
 * En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, el número de versión debe ser 15.0.26228.4 o posterior.

Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).

