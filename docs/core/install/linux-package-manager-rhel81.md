---
title: 'Instalación de .NET Core en el administrador de paquetes de Linux RHEL 8.1: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 8.1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 3ef639d5b76e81856ec8370d10e098c455ca8b3d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998916"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="37147-103">Administrador de paquetes de RHEL 8.1: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="37147-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="37147-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="37147-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="37147-105">.NET Core 3.1 todavía no está disponible para RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="37147-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="37147-106">RHEL 8.0 no incluye .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="37147-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="37147-107">Use el comando `yum upgrade` para actualizar a RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="37147-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="37147-108">RHEL 8.0 no incluye .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="37147-108">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="37147-109">Use el comando `yum upgrade` para actualizar a RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="37147-109">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="37147-110">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="37147-110">Register your Red Hat subscription</span></span>

<span data-ttu-id="37147-111">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="37147-111">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="37147-112">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="37147-112">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="37147-113">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="37147-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="37147-114">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37147-114">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="37147-115">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37147-115">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="37147-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="37147-116">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="37147-117">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="37147-117">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="37147-118">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37147-118">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="37147-119">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="37147-119">Install the .NET Core Runtime</span></span>

<span data-ttu-id="37147-120">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37147-120">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="37147-121">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37147-121">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="37147-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="37147-122">See also</span></span>

- [<span data-ttu-id="37147-123">Uso de .NET Core 3.0 en Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="37147-123">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
