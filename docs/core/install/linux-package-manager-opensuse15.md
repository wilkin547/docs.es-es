---
title: 'Instalación de .NET Core en openSUSE 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: aaece5e3554ab567cf82c23265c8fba1656298d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920765"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="13f35-103">Administrador de paquetes de openSUSE 15: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="13f35-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="13f35-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="13f35-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="13f35-105">Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="13f35-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="13f35-106">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="13f35-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="13f35-107">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13f35-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="13f35-108">Registrar la clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13f35-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="13f35-109">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="13f35-109">Register the product repository.</span></span>
- <span data-ttu-id="13f35-110">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="13f35-110">Install required dependencies.</span></span>

<span data-ttu-id="13f35-111">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="13f35-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="13f35-112">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="13f35-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="13f35-113">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="13f35-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="13f35-114">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="13f35-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="13f35-115">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="13f35-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="13f35-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="13f35-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="13f35-117">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="13f35-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="13f35-118">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="13f35-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="13f35-119">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="13f35-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="13f35-120">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="13f35-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="13f35-121">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="13f35-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="13f35-122">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="13f35-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="13f35-123">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="13f35-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="13f35-124">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="13f35-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="13f35-125">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="13f35-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
