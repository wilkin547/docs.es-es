---
title: 'Instalación de .NET Core en el administrador de paquetes de Ubuntu 18.04: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en Ubuntu 18.04.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: f590430ea10dc7188c32814641aca739b04ffa50
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595656"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="51a60-103">Administrador de paquetes de Ubuntu 18.04: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="51a60-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="51a60-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en Ubuntu 18.04.</span><span class="sxs-lookup"><span data-stu-id="51a60-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="51a60-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="51a60-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="51a60-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51a60-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="51a60-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="51a60-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="51a60-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="51a60-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="51a60-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="51a60-109">Install required dependencies.</span></span>

<span data-ttu-id="51a60-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="51a60-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="51a60-111">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="51a60-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="51a60-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="51a60-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51a60-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="51a60-114">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-114">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="51a60-115">Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-sdk-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="51a60-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="51a60-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="51a60-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="51a60-117">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="51a60-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="51a60-118">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-118">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="51a60-119">Si recibe un mensaje de error similar a **No se puede encontrar el paquete aspnetcore-runtime-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="51a60-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="51a60-120">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="51a60-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="51a60-121">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51a60-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="51a60-122">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-122">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="51a60-123">Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-runtime-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="51a60-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="51a60-124">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="51a60-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="51a60-125">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="51a60-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="51a60-126">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51a60-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="51a60-127">No se encuentra el elemento</span><span class="sxs-lookup"><span data-stu-id="51a60-127">Unable to locate</span></span>

<span data-ttu-id="51a60-128">Si recibe un mensaje de error similar a **No se puede encontrar el paquete (el paquete .NET Core)** , ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="51a60-129">Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51a60-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="51a60-130">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="51a60-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
