---
title: 'Instalación de .NET Core en openSUSE 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645662"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="10710-103">Administrador de paquetes de openSUSE 15: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="10710-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="10710-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="10710-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="10710-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="10710-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="10710-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10710-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="10710-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="10710-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="10710-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="10710-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="10710-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="10710-109">Install required dependencies.</span></span>

<span data-ttu-id="10710-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="10710-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="10710-111">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="10710-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="10710-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="10710-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="10710-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10710-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="10710-114">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="10710-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="10710-115">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="10710-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="10710-116">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="10710-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="10710-117">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="10710-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="10710-118">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="10710-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="10710-119">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10710-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="10710-120">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="10710-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="10710-121">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="10710-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="10710-122">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="10710-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="10710-123">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10710-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="10710-124">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="10710-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
