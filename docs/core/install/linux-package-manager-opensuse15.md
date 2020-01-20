---
title: 'Instalación de .NET Core en openSUSE 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740676"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="59cd3-103">Administrador de paquetes de openSUSE 15: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="59cd3-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="59cd3-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="59cd3-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="59cd3-105">Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="59cd3-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="59cd3-106">Registro de la clave y la fuente de Microsoft</span><span class="sxs-lookup"><span data-stu-id="59cd3-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="59cd3-107">Antes de instalar .NET, deberá realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59cd3-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="59cd3-108">Registrar clave de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59cd3-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="59cd3-109">Registrar el repositorio del producto.</span><span class="sxs-lookup"><span data-stu-id="59cd3-109">Register the product repository.</span></span>
- <span data-ttu-id="59cd3-110">Instalar las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="59cd3-110">Install required dependencies.</span></span>

<span data-ttu-id="59cd3-111">Esto solo se debe hacer una vez por máquina.</span><span class="sxs-lookup"><span data-stu-id="59cd3-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="59cd3-112">Abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="59cd3-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="59cd3-113">Error de dependencia con .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="59cd3-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="59cd3-114">La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**.</span><span class="sxs-lookup"><span data-stu-id="59cd3-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="59cd3-115">Use el siguiente comando para instalar las dependencias correctas antes de instalar .NET Core 3.1 o ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="59cd3-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="59cd3-116">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="59cd3-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="59cd3-117">Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59cd3-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="59cd3-118">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="59cd3-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="59cd3-119">La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**.</span><span class="sxs-lookup"><span data-stu-id="59cd3-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="59cd3-120">Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="59cd3-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="59cd3-121">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="59cd3-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="59cd3-122">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="59cd3-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="59cd3-123">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="59cd3-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="59cd3-124">La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**.</span><span class="sxs-lookup"><span data-stu-id="59cd3-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="59cd3-125">Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el runtime de ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="59cd3-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="59cd3-126">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="59cd3-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="59cd3-127">Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="59cd3-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="59cd3-128">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="59cd3-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="59cd3-129">La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**.</span><span class="sxs-lookup"><span data-stu-id="59cd3-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="59cd3-130">Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el runtime de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="59cd3-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="59cd3-131">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="59cd3-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
