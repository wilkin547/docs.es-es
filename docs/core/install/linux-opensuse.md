---
title: 'Instalación de .NET Core en openSUSE: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 3a2ff1ca1519428f42c88048dde22aa11baaaa01
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324756"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="c97ab-103">Instalación del SDK de .NET Core o de .NET Core Runtime en openSUSE</span><span class="sxs-lookup"><span data-stu-id="c97ab-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="c97ab-104">.NET Core es compatible con openSUSE.</span><span class="sxs-lookup"><span data-stu-id="c97ab-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="c97ab-105">En este artículo se describe cómo instalar .NET Core en openSUSE.</span><span class="sxs-lookup"><span data-stu-id="c97ab-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="c97ab-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="c97ab-106">Supported distributions</span></span>

<span data-ttu-id="c97ab-107">En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="c97ab-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="c97ab-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="c97ab-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="c97ab-109">Una ✔️ indica que todavía se admite la versión de openSUSE o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c97ab-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="c97ab-110">Una ❌ indica que la versión de openSUSE o de .NET Core no se admite en esa versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="c97ab-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="c97ab-111">Cuando una versión de openSUSE y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="c97ab-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="c97ab-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c97ab-112">openSUSE</span></span>                   | <span data-ttu-id="c97ab-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c97ab-113">.NET Core 2.1</span></span> | <span data-ttu-id="c97ab-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c97ab-114">.NET Core 3.1</span></span> | <span data-ttu-id="c97ab-115">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="c97ab-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c97ab-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="c97ab-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="c97ab-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c97ab-117">✔️ 2.1</span></span>        | <span data-ttu-id="c97ab-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c97ab-118">✔️ 3.1</span></span>        | <span data-ttu-id="c97ab-119">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c97ab-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="c97ab-120">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="c97ab-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="c97ab-121">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="c97ab-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c97ab-122">3.0</span><span class="sxs-lookup"><span data-stu-id="c97ab-122">3.0</span></span>
- <span data-ttu-id="c97ab-123">2.2</span><span class="sxs-lookup"><span data-stu-id="c97ab-123">2.2</span></span>
- <span data-ttu-id="c97ab-124">2.0</span><span class="sxs-lookup"><span data-stu-id="c97ab-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c97ab-125">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="c97ab-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="c97ab-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="c97ab-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c97ab-127">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="c97ab-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="c97ab-128">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c97ab-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="c97ab-129">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="c97ab-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="c97ab-130">Snap</span><span class="sxs-lookup"><span data-stu-id="c97ab-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="c97ab-131">Dependencias</span><span class="sxs-lookup"><span data-stu-id="c97ab-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="c97ab-132">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="c97ab-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="c97ab-133">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="c97ab-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="c97ab-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c97ab-134">Next steps</span></span>

- [<span data-ttu-id="c97ab-135">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c97ab-135">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
