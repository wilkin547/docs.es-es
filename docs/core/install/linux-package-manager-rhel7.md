---
title: 'Instalación de .NET Core en RHEL 7 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: d1f1372b32c7b2471a96492d48aab5533dadb64a
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134201"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="96ce9-103">Administrador de paquetes de RHEL 7: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96ce9-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="96ce9-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="96ce9-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="96ce9-105">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="96ce9-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="96ce9-106">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="96ce9-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="96ce9-107">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="96ce9-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="96ce9-108">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96ce9-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="96ce9-109">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96ce9-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="96ce9-110">Para habilitar el canal dotnet de RHEL 7 e instalarlo, ejecute los comandos siguientes en el terminal.</span><span class="sxs-lookup"><span data-stu-id="96ce9-110">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="96ce9-111">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="96ce9-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="96ce9-112">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="96ce9-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="96ce9-113">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="96ce9-113">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="96ce9-114">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96ce9-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="96ce9-115">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96ce9-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="96ce9-116">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="96ce9-116">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-dotnet-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

## <a name="see-also"></a><span data-ttu-id="96ce9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="96ce9-117">See also</span></span>

- [<span data-ttu-id="96ce9-118">Uso de .NET Core 3.1 en Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="96ce9-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.1/html/getting_started_guide/gs_install_dotnet)
