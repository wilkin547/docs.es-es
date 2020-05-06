---
title: 'Instalación de .NET Core en SLES 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en SLES 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595666"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="f5c6f-103">Administrador de paquetes de SLES 15: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f5c6f-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f5c6f-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en SLES 15.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="f5c6f-105">Adición de la clave y la fuente del repositorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f5c6f-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="f5c6f-106">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5c6f-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f5c6f-107">Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="f5c6f-108">Agregar el repositorio al administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="f5c6f-109">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-109">Install required dependencies.</span></span>

<span data-ttu-id="f5c6f-110">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f5c6f-111">Abra un terminal y ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="f5c6f-112">Actualmente, el paquete de instalación del repositorio de Microsoft de SLES 15 instala el archivo *microsoft-prod.repo* en el directorio incorrecto, lo que impide que zypper pueda encontrar los paquetes de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="f5c6f-113">Para corregir este problema, cree un symlink en el directorio apropiado.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f5c6f-114">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f5c6f-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="f5c6f-115">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f5c6f-116">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f5c6f-117">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f5c6f-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f5c6f-118">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f5c6f-119">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f5c6f-120">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f5c6f-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="f5c6f-121">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f5c6f-122">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f5c6f-123">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="f5c6f-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f5c6f-124">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="f5c6f-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="f5c6f-125">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f5c6f-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f5c6f-126">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="f5c6f-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
