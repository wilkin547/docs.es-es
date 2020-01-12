---
title: 'Instalación de .NET Core en el administrador de paquetes de Linux RHEL 8.1: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 8.1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714373"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="549db-103">Administrador de paquetes de RHEL 8.1: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="549db-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="549db-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="549db-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="549db-105">.NET Core 3.1 todavía no está disponible para RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="549db-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="549db-106">RHEL 8.0 no incluye .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="549db-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="549db-107">Use el comando `yum upgrade` para actualizar a RHEL 8.1.</span><span class="sxs-lookup"><span data-stu-id="549db-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="549db-108">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="549db-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="549db-109">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="549db-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="549db-110">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="549db-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="549db-111">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="549db-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="549db-112">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="549db-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="549db-113">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="549db-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="549db-114">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="549db-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="549db-115">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="549db-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="549db-116">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="549db-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="549db-117">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="549db-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="549db-118">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="549db-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="549db-119">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="549db-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="549db-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="549db-120">See also</span></span>

- [<span data-ttu-id="549db-121">Uso de .NET Core 3.0 en Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="549db-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
