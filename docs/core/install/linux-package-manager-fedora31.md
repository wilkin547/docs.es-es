---
title: 'Instalación de .NET Core en Fedora 31 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el runtime de .NET Core en Fedora 31.
author: thraka
ms.author: adegeo
ms.date: 12/17/2019
ms.openlocfilehash: 25c670694ed2d9e89fe37cedf0b06efd8bc93293
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116955"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="a29c2-103">Administrador de paquetes de Fedora 31: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a29c2-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="a29c2-104">En este artículo se explica cómo usar un administrador de paquetes para instalar .NET Core en Fedora 31.</span><span class="sxs-lookup"><span data-stu-id="a29c2-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span> <span data-ttu-id="a29c2-105">Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a29c2-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="a29c2-106">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a29c2-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="a29c2-107">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a29c2-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="a29c2-108">Registrar la clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a29c2-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="a29c2-109">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="a29c2-109">Register the product repository.</span></span>
- <span data-ttu-id="a29c2-110">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="a29c2-110">Install required dependencies.</span></span>

<span data-ttu-id="a29c2-111">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="a29c2-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="a29c2-112">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a29c2-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="a29c2-113">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a29c2-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="a29c2-114">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a29c2-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="a29c2-115">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a29c2-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="a29c2-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a29c2-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="a29c2-117">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a29c2-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="a29c2-118">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a29c2-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="a29c2-119">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a29c2-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="a29c2-120">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a29c2-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="a29c2-121">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a29c2-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a29c2-122">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="a29c2-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
