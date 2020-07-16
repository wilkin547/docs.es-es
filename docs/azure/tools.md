---
title: Herramientas para desarrolladores de .NET de Azure
description: Obtenga las herramientas para empezar a usar las bibliotecas .NET de Azure desde un entorno de Windows, Linux y Mac.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174879"
---
# <a name="azure-tools-for-developing-with-net"></a>Azure Tools para desarrollar con .NET

## <a name="sdk-downloads"></a>Descargas de SDK

Las bibliotecas de Azure para .NET se implementan como [paquetes NuGet](https://www.nuget.org/packages?q=windowsazureofficial). Consulte la [referencia de API](/dotnet/api/overview/azure/?view=azure-dotnet) para obtener documentación de referencia organizada por el servicio de Azure.

## <a name="development-tools"></a>Herramientas de desarrollo

Visual Studio tiene integradas herramientas para muchos servicios de Azure. Algunos servicios de Azure disponen de más herramientas o emuladores, como el [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/). Consulte la documentación del servicio de Azure correspondiente para ver las herramientas adicionales si así lo precisa.

Seleccione a continuación el entorno de desarrollo que prefiera.

## <a name="visual-studio-on-windows"></a>[Visual Studio en Windows](#tab/vs)

La versión 2017 y posteriores de Visual Studio incluyen compatibilidad integrada con el desarrollo de Azure. Los siguientes pasos describen cómo habilitar la compatibilidad con el desarrollo de Azure en Visual Studio.

<a href="vs2015-install.md">Siga estas instrucciones</a> con Visual Studio 2015 y versiones anteriores.

### <a name="step-1-download-visual-studio-2019"></a>Paso 1: Descargar Visual Studio 2019

Si ya tiene instalado Visual Studio 2019, puede omitir este paso.

> [!div class="nextstepaction"]
> [Descargar Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Paso 2: Instalación de las dos cargas de trabajo de Azure

En el instalador de Visual Studio, instale Visual Studio (o modifique una instalación existente). Asegúrese de que las cargas de trabajo *Desarrollo de Azure* y *Desarrollo de ASP.NET y web* están seleccionadas.

### <a name="step-3-develop-with-net-on-azure"></a>Paso 3: Desarrollo con .NET en Azure

Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="visual-studio-code-cross-platform"></a>[Visual Studio Code (multiplataforma)](#tab/vscode)

Visual Studio Code tiene todo lo que necesita para el desarrollo multiplataforma de Azure.

### <a name="step-1-download-the-net-core-sdk"></a>Paso 1: Descarga del SDK de .NET Core

El SDK y las herramientas de línea de comandos de las aplicaciones .NET Core.

> [!div class="nextstepaction"]
> [Download .NET Core SDK](https://dotnet.microsoft.com/download) (Descarga del SDK de .NET Core)

### <a name="step-2-visual-studio-code"></a>Paso 2: Visual Studio Code

Edite y depure aplicaciones .NET Core en cualquier sistema operativo: Windows, Mac y Linux.

> [!div class="nextstepaction"]
> [Descargar Visual Studio Code](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a>Paso 3: Extensión de Azure Tools

Instale la extensión de Azure Tools en Visual Studio Code.

> [!div class="nextstepaction"]
> [Instalación de la extensión de Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a>Paso 4: Desarrollo con .NET en Azure

Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service en Linux](/azure/app-service/containers/quickstart-dotnetcore).

---
