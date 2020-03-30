---
title: 'Instalación de .NET Core en Fedora 31 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el runtime de .NET Core en Fedora 31.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: e6ead528c441c37d089ebb33719494353de41433
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134249"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="ad552-103">Administrador de paquetes de Fedora 31: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad552-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ad552-104">En este artículo se explica cómo usar un administrador de paquetes para instalar .NET Core en Fedora 31.</span><span class="sxs-lookup"><span data-stu-id="ad552-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="ad552-105">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad552-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="ad552-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad552-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ad552-107">Registrar la clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad552-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="ad552-108">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="ad552-108">Register the product repository.</span></span>
- <span data-ttu-id="ad552-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="ad552-109">Install required dependencies.</span></span>

<span data-ttu-id="ad552-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="ad552-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ad552-111">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad552-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ad552-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad552-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="ad552-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad552-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ad552-114">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad552-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ad552-115">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ad552-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ad552-116">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ad552-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="ad552-117">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad552-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ad552-118">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ad552-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="ad552-119">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad552-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ad552-120">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad552-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ad552-121">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="ad552-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ad552-122">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="ad552-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="ad552-123">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ad552-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="ad552-124">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="ad552-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
