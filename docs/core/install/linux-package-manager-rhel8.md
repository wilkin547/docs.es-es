---
title: 'Instalación de .NET Core en el administrador de paquetes de Linux RHEL 8: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 054494a9b77e1c7803e42c947e067d3eb290f73c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78849799"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="1d29c-103">Administrador de paquetes de RHEL 8: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1d29c-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="1d29c-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="1d29c-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="1d29c-105">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="1d29c-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="1d29c-106">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="1d29c-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="1d29c-107">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="1d29c-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="1d29c-108">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1d29c-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="1d29c-109">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d29c-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="1d29c-110">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1d29c-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="1d29c-111">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d29c-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="1d29c-112">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d29c-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="1d29c-113">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1d29c-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="1d29c-114">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1d29c-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="1d29c-115">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d29c-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="1d29c-116">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1d29c-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="1d29c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d29c-117">See also</span></span>

- [<span data-ttu-id="1d29c-118">Uso de .NET Core 3.1 en Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="1d29c-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
