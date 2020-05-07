---
title: 'Instalación de .NET Core en Linux CentOS 8 con el administrador de paquetes: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en CentOS 8.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728508"
---
# <a name="centos-8-package-manager---install-net-core"></a><span data-ttu-id="0e606-103">Administrador de paquetes de CentOS 8: instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0e606-103">CentOS 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="0e606-104">En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="0e606-104">This article describes how to use a package manager to install .NET Core on CentOS 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="0e606-105">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0e606-105">Install the .NET Core SDK</span></span>

<span data-ttu-id="0e606-106">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e606-106">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="0e606-107">Instalación del entorno de ejecución de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e606-107">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="0e606-108">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e606-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="0e606-109">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0e606-109">Install the .NET Core Runtime</span></span>

<span data-ttu-id="0e606-110">En el terminal, ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e606-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="0e606-111">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="0e606-111">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
