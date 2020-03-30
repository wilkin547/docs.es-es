---
title: 'Instalación de .NET Core en el administrador de paquetes de Linux RHEL 8: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b564a386eb67b6e414a832ad3bca10d3d09022bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134192"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="2abcc-103">Administrador de paquetes de RHEL 8: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2abcc-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="2abcc-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="2abcc-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="2abcc-105">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="2abcc-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="2abcc-106">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="2abcc-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="2abcc-107">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="2abcc-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="2abcc-108">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2abcc-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="2abcc-109">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2abcc-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="2abcc-110">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2abcc-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="2abcc-111">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2abcc-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="2abcc-112">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2abcc-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="2abcc-113">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2abcc-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="2abcc-114">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2abcc-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="2abcc-115">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2abcc-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="2abcc-116">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2abcc-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="2abcc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2abcc-117">See also</span></span>

- [<span data-ttu-id="2abcc-118">Uso de .NET Core 3.1 en Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="2abcc-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
