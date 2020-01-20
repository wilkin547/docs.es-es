---
title: 'Instalación de .NET Core en SLES 12 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en SLES 12.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a40180881ec0962d89f03c2c9d7aad9bbb052d2a
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740654"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="44267-103">Administrador de paquetes de SLES 12: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="44267-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="44267-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en SLES 12.</span><span class="sxs-lookup"><span data-stu-id="44267-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span> <span data-ttu-id="44267-105">Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44267-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="44267-106">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44267-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="44267-107">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="44267-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="44267-108">Registrar clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44267-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="44267-109">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="44267-109">Register the product repository.</span></span>
- <span data-ttu-id="44267-110">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="44267-110">Install required dependencies.</span></span>

<span data-ttu-id="44267-111">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="44267-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="44267-112">Abra un terminal y ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="44267-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="44267-113">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="44267-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="44267-114">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="44267-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="44267-115">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="44267-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="44267-116">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="44267-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="44267-117">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="44267-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="44267-118">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="44267-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="44267-119">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="44267-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="44267-120">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="44267-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="44267-121">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="44267-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="44267-122">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="44267-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
