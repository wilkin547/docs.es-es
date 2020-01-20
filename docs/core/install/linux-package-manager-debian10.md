---
title: 'Instalación de .NET Core en Debian 10 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en Debian 10.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 2f3f04ef67115b28b1be91909e88c7ae714260db
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740721"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="e60bf-103">Administrador de paquetes de Debian 10: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e60bf-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="e60bf-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en Debian 10.</span><span class="sxs-lookup"><span data-stu-id="e60bf-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span> <span data-ttu-id="e60bf-105">Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e60bf-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="e60bf-106">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e60bf-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="e60bf-107">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e60bf-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="e60bf-108">Registrar clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e60bf-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="e60bf-109">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="e60bf-109">Register the product repository.</span></span>
- <span data-ttu-id="e60bf-110">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="e60bf-110">Install required dependencies.</span></span>

<span data-ttu-id="e60bf-111">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="e60bf-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="e60bf-112">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e60bf-112">Open a terminal and run the following commands.</span></span>

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e60bf-113">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e60bf-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="e60bf-114">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e60bf-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="e60bf-115">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e60bf-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e60bf-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e60bf-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="e60bf-117">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e60bf-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="e60bf-118">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e60bf-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e60bf-119">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e60bf-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="e60bf-120">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e60bf-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="e60bf-121">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e60bf-121">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="e60bf-122">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="e60bf-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
