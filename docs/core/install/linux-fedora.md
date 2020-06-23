---
title: 'Instalación de .NET Core en Fedora: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Fedora.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 52aa9409ec876e0d1eaef22fb739046941fda897
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602841"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="def8f-103">Instalación del SDK o de .NET Core Runtime en Fedora</span><span class="sxs-lookup"><span data-stu-id="def8f-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="def8f-104">.NET Core es compatible con Fedora.</span><span class="sxs-lookup"><span data-stu-id="def8f-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="def8f-105">En este artículo se describe cómo instalar .NET Core en Fedora.</span><span class="sxs-lookup"><span data-stu-id="def8f-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="def8f-106">Cuando una versión de Fedora no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="def8f-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="def8f-107">Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="def8f-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="def8f-108">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="def8f-108">Supported distributions</span></span>

<span data-ttu-id="def8f-109">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Fedora en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="def8f-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="def8f-110">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="def8f-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="def8f-111">Una ✔️ indica que todavía se admite la versión de Fedora o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="def8f-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="def8f-112">Una ❌ indica que la versión de Fedora o de .NET Core no se admite en esa versión de Fedora.</span><span class="sxs-lookup"><span data-stu-id="def8f-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="def8f-113">Cuando una versión de Fedora y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="def8f-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="def8f-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="def8f-114">Fedora</span></span>                   | <span data-ttu-id="def8f-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-115">.NET Core 2.1</span></span> | <span data-ttu-id="def8f-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-116">.NET Core 3.1</span></span> | <span data-ttu-id="def8f-117">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="def8f-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="def8f-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="def8f-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="def8f-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-119">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-120">✔️ 3.1</span></span>        | <span data-ttu-id="def8f-121">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="def8f-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="def8f-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="def8f-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-123">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-124">✔️ 3.1</span></span>        | <span data-ttu-id="def8f-125">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="def8f-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="def8f-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="def8f-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-127">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-128">✔️ 3.1</span></span>        | <span data-ttu-id="def8f-129">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="def8f-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="def8f-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="def8f-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-131">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-132">✔️ 3.1</span></span>        | <span data-ttu-id="def8f-133">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="def8f-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="def8f-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="def8f-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-135">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-136">❌ 3.1</span></span>        | <span data-ttu-id="def8f-137">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="def8f-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="def8f-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="def8f-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="def8f-139">✔️ 2.1</span></span>        | <span data-ttu-id="def8f-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="def8f-140">❌ 3.1</span></span>        | <span data-ttu-id="def8f-141">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="def8f-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="def8f-142">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="def8f-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="def8f-143">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="def8f-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="def8f-144">3.0</span><span class="sxs-lookup"><span data-stu-id="def8f-144">3.0</span></span>
- <span data-ttu-id="def8f-145">2.2</span><span class="sxs-lookup"><span data-stu-id="def8f-145">2.2</span></span>
- <span data-ttu-id="def8f-146">2.0</span><span class="sxs-lookup"><span data-stu-id="def8f-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="def8f-147">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="def8f-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="def8f-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="def8f-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="def8f-149">.NET Core 3.1 está disponible en los repositorios de paquetes predeterminados para Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="def8f-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="def8f-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="def8f-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="def8f-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="def8f-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="def8f-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="def8f-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="def8f-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="def8f-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="def8f-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="def8f-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="def8f-155">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="def8f-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="def8f-156">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="def8f-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="def8f-157">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="def8f-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="def8f-158">Snap</span><span class="sxs-lookup"><span data-stu-id="def8f-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="def8f-159">Dependencias</span><span class="sxs-lookup"><span data-stu-id="def8f-159">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="def8f-160">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="def8f-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="def8f-161">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="def8f-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="def8f-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="def8f-162">Next steps</span></span>

- [<span data-ttu-id="def8f-163">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="def8f-163">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
