---
title: 'Instalación de .NET Core en SLES 12 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en SLES 12.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 314688d60fb77e1b569dd037fb1d78c3f1f94dbc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645656"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="4b939-103">Administrador de paquetes de SLES 12: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4b939-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="4b939-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en SLES 12.</span><span class="sxs-lookup"><span data-stu-id="4b939-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="4b939-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b939-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="4b939-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b939-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="4b939-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="4b939-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="4b939-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="4b939-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="4b939-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="4b939-109">Install required dependencies.</span></span>

<span data-ttu-id="4b939-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="4b939-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="4b939-111">Abra un terminal y ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b939-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="4b939-112">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4b939-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="4b939-113">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b939-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="4b939-114">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b939-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="4b939-115">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b939-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="4b939-116">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4b939-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="4b939-117">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b939-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="4b939-118">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4b939-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="4b939-119">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b939-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="4b939-120">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b939-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="4b939-121">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="4b939-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="4b939-122">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="4b939-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="4b939-123">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b939-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="4b939-124">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="4b939-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
