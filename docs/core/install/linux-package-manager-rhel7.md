---
title: 'Instalación de .NET Core en RHEL 7 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 7.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: bcc41bfcd7c6d03038952e3faaf07952c3deb69d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715534"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="8d423-103">Administrador de paquetes de RHEL 7: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8d423-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="8d423-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="8d423-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="8d423-105">.NET Core 3.1 todavía no está disponible para RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="8d423-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="8d423-106">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="8d423-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="8d423-107">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="8d423-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="8d423-108">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="8d423-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="8d423-109">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8d423-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="8d423-110">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8d423-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="8d423-111">Para habilitar el canal dotnet de RHEL 7 e instalarlo, ejecute los comandos siguientes en el terminal.</span><span class="sxs-lookup"><span data-stu-id="8d423-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="8d423-112">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8d423-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="8d423-113">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8d423-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="8d423-114">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d423-114">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="8d423-115">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8d423-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="8d423-116">Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8d423-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="8d423-117">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d423-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="8d423-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d423-118">See also</span></span>

- [<span data-ttu-id="8d423-119">Uso de .NET Core 3.0 en Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="8d423-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
