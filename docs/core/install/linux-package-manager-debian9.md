---
title: 'Instalación de .NET Core en Debian 9 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en Debian 9.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 2e45698d6b87499a54a25b6779ec1a767a2ece6b
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645376"
---
# <a name="debian-9-package-manager---install-net-core"></a><span data-ttu-id="e3c14-103">Administrador de paquetes de Debian 9: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e3c14-103">Debian 9 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="e3c14-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en Debian 9.</span><span class="sxs-lookup"><span data-stu-id="e3c14-104">This article describes how to use a package manager to install .NET Core on Debian 9.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="e3c14-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e3c14-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="e3c14-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3c14-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="e3c14-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="e3c14-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="e3c14-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e3c14-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="e3c14-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="e3c14-109">Install required dependencies.</span></span>

<span data-ttu-id="e3c14-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="e3c14-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="e3c14-111">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3c14-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e3c14-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e3c14-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="e3c14-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3c14-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="e3c14-114">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3c14-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e3c14-115">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e3c14-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="e3c14-116">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e3c14-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="e3c14-117">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3c14-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e3c14-118">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e3c14-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="e3c14-119">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3c14-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="e3c14-120">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3c14-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="e3c14-121">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="e3c14-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="e3c14-122">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="e3c14-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="e3c14-123">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e3c14-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="e3c14-124">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="e3c14-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
