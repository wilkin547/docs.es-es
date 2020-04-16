---
title: Herramientas para desarrolladores de .NET y .NET Core de Azure
description: Obtenga las herramientas para empezar a usar las bibliotecas .NET de Azure desde un entorno de Windows, Linux y Mac.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433167"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a>Herramientas para desarrolladores de .NET y .NET Core de Azure

## <a name="sdk-downloads"></a>Descargas de SDK

Las bibliotecas de Azure para .NET se implementan como [paquetes NuGet.](https://www.nuget.org/packages?q=windowsazureofficial) Consulte la Referencia de [la API](/dotnet/api/overview/azure/?view=azure-dotnet) para obtener instrucciones de instalación organizadas por el servicio Azure.

## <a name="development-tools"></a>Herramientas de desarrollo

Visual Studio tiene herramientas para muchos servicios de Azure integrados. Algunos servicios de Azure tienen herramientas o emuladores adicionales disponibles, como el Explorador de [Azure Storage](https://azure.microsoft.com/features/storage-explorer/). Consulte la documentación del servicio de Azure para ver si es necesario las herramientas adicionales.

Estas instrucciones instalan el entorno de desarrollo de inicio recomendado para el sistema operativo.

## <a name="windows"></a>[Windows](#tab/windows)

Las versiones de Visual Studio 2017 y versiones posteriores tienen compatibilidad integrada para el desarrollo de Azure. Los pasos siguientes describen habilitar la compatibilidad de desarrollo de Azure en Visual Studio.

Para Visual Studio 2015 y versiones anteriores, <a href="vs2015-install.md">siga estas instrucciones.</a>

### <a name="step-1-download-visual-studio-2019"></a>Paso 1: Descargar Visual Studio 2019

Puede omitir este paso si ya tiene Visual Studio 2019 instalado.

> [!div class="nextstepaction"]
> [Descargar Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Paso 2: Instalación de las dos cargas de trabajo de Azure

En el instalador de Visual Studio, instale Visual Studio (o modifique una instalación existente). Asegúrese de que las cargas de trabajo de desarrollo y *ASP.NET y desarrollo web* de *Azure* están seleccionadas.

### <a name="step-3-develop-with-net-on-azure"></a>Paso 3: Desarrollo con .NET en Azure

Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="macos"></a>[macOS](#tab/macos)

Visual Studio para Mac tiene todo lo que necesita para el desarrollo de Azure.

### <a name="step-1-download-visual-studio-for-mac"></a>Paso 1: Descarga de Visual Studio para Mac

> [!div class="nextstepaction"]
> [Descargar Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

Durante la instalación, las herramientas de Azure se seleccionan de forma predeterminada.

## <a name="linux"></a>[Linux](#tab/linux)

Visual Studio Code tiene todo lo que necesita para el desarrollo de Azure en Linux.

### <a name="step-1-download-the-net-core-sdk"></a>Step 1: Descarga del SDK de .NET Core

El SDK y las herramientas de línea de comandos de las aplicaciones .NET Core.

> [!div class="nextstepaction"]
> [Download .NET Core SDK](https://dotnet.microsoft.com/download) (Descarga del SDK de .NET Core)

### <a name="step-2-visual-studio-code"></a>Paso 2: Visual Studio Code

Edite y depure aplicaciones .NET Core en cualquier sistema operativo: Windows, Mac y Linux.

> [!div class="nextstepaction"]
> [Descarga de Visual Studio Code](https://code.visualstudio.com)

---
