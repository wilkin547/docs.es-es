---
title: 'Instalación de .NET Core en Fedora 32 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el runtime de .NET Core en Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624955"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="b23e5-103">Administrador de paquetes de Fedora 32: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b23e5-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="b23e5-104">En este artículo se explica cómo usar un administrador de paquetes para instalar .NET Core en Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="b23e5-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="b23e5-105">A partir de Fedora 32, .NET Core 3.1 está disponible en los repositorios de paquetes predeterminados de Fedora.</span><span class="sxs-lookup"><span data-stu-id="b23e5-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b23e5-106">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b23e5-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="b23e5-107">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b23e5-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="b23e5-108">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="b23e5-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b23e5-109">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b23e5-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="b23e5-110">Instalación del entorno de ejecución de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b23e5-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="b23e5-111">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="b23e5-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b23e5-112">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b23e5-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="b23e5-113">Instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b23e5-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="b23e5-114">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="b23e5-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b23e5-115">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="b23e5-115">How to install other versions</span></span>

<span data-ttu-id="b23e5-116">Para instalar otras versiones de .NET Core, instale manualmente el [SDK de .NET Core](sdk.md?pivots=os-linux#download-and-manually-install) o el [entorno de ejecución de .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="b23e5-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
