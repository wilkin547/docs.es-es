---
title: 'Instalación de .NET Core en CentOS: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en CentOS.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 6b1bad3a6c967483bb683866de84c9e5077a336f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619512"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-centos"></a><span data-ttu-id="7635b-103">Instalación del SDK de .NET Core o .NET Core Runtime en CentOS</span><span class="sxs-lookup"><span data-stu-id="7635b-103">Install .NET Core SDK or .NET Core Runtime on CentOS</span></span>

<span data-ttu-id="7635b-104">.NET Core es compatible con CentOS.</span><span class="sxs-lookup"><span data-stu-id="7635b-104">.NET Core is supported on CentOS.</span></span> <span data-ttu-id="7635b-105">En este artículo se describe cómo instalar .NET Core en CentOS.</span><span class="sxs-lookup"><span data-stu-id="7635b-105">This article describes how to install .NET Core on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="7635b-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="7635b-106">Supported distributions</span></span>

<span data-ttu-id="7635b-107">En la tabla siguiente se muestra una lista de las versiones de .NET Core admitidas actualmente en CentOS 7 y CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="7635b-107">The following table is a list of currently supported .NET Core releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="7635b-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="7635b-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="7635b-109">Una ✔️ indica que todavía se admite la versión de CentOS o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7635b-109">A ✔️ indicates that the version of CentOS or .NET Core is still supported.</span></span>
- <span data-ttu-id="7635b-110">Una ❌ indica que la versión de CentOS o de .NET Core no se admite en esa versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="7635b-110">A ❌ indicates that the version of CentOS or .NET Core isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="7635b-111">Cuando una versión de CentOS y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="7635b-111">When both a version of CentOS and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="7635b-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="7635b-112">CentOS</span></span>                   | <span data-ttu-id="7635b-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7635b-113">.NET Core 2.1</span></span> | <span data-ttu-id="7635b-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7635b-114">.NET Core 3.1</span></span> | <span data-ttu-id="7635b-115">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="7635b-115">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="7635b-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="7635b-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="7635b-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7635b-117">✔️ 2.1</span></span>        | <span data-ttu-id="7635b-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7635b-118">✔️ 3.1</span></span>        | <span data-ttu-id="7635b-119">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="7635b-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="7635b-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="7635b-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="7635b-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7635b-121">✔️ 2.1</span></span>        | <span data-ttu-id="7635b-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7635b-122">✔️ 3.1</span></span>        | <span data-ttu-id="7635b-123">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="7635b-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="7635b-124">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="7635b-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="7635b-125">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="7635b-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="7635b-126">3.0</span><span class="sxs-lookup"><span data-stu-id="7635b-126">3.0</span></span>
- <span data-ttu-id="7635b-127">2.2</span><span class="sxs-lookup"><span data-stu-id="7635b-127">2.2</span></span>
- <span data-ttu-id="7635b-128">2.0</span><span class="sxs-lookup"><span data-stu-id="7635b-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7635b-129">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="7635b-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="7635b-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="7635b-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="7635b-131">.NET Core 3.1 está disponible en los repositorios de paquetes predeterminados de CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="7635b-131">.NET Core 3.1 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="7635b-132">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="7635b-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-31](includes/linux-install-31-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="7635b-133">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="7635b-133">Troubleshoot the package manager</span></span>

<span data-ttu-id="7635b-134">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7635b-134">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="7635b-135">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="7635b-135">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="7635b-136">Snap</span><span class="sxs-lookup"><span data-stu-id="7635b-136">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="7635b-137">Dependencias</span><span class="sxs-lookup"><span data-stu-id="7635b-137">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="7635b-138">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="7635b-138">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="7635b-139">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="7635b-139">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="7635b-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7635b-140">Next steps</span></span>

- [<span data-ttu-id="7635b-141">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7635b-141">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
