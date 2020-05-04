---
title: 'Instalación de .NET Core en Debian 10 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en Debian 10.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 038f5579f99f700ce47dc67be2fd344f01cf800c
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595625"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="6a05b-103">Administrador de paquetes de Debian 10: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a05b-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="6a05b-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en Debian 10.</span><span class="sxs-lookup"><span data-stu-id="6a05b-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="6a05b-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a05b-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="6a05b-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a05b-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="6a05b-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="6a05b-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="6a05b-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="6a05b-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="6a05b-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="6a05b-109">Install required dependencies.</span></span>

<span data-ttu-id="6a05b-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="6a05b-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="6a05b-111">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a05b-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="6a05b-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a05b-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="6a05b-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a05b-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="6a05b-114">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a05b-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="6a05b-115">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6a05b-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="6a05b-116">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6a05b-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="6a05b-117">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a05b-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="6a05b-118">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a05b-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="6a05b-119">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a05b-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="6a05b-120">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a05b-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="6a05b-121">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="6a05b-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="6a05b-122">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="6a05b-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="6a05b-123">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a05b-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="6a05b-124">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="6a05b-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
