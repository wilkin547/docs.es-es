---
title: 'Instalación de .NET en Fedora: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Fedora.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: f7422941af7e39d69d286a0f79920b025c1bf9c0
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031909"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="5289e-103">Instalación del SDK y el entorno de ejecución de .NET en Fedora</span><span class="sxs-lookup"><span data-stu-id="5289e-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="5289e-104">.NET es compatible con Fedora.</span><span class="sxs-lookup"><span data-stu-id="5289e-104">.NET is supported on Fedora.</span></span> <span data-ttu-id="5289e-105">En este artículo se describe cómo instalar .NET en Fedora.</span><span class="sxs-lookup"><span data-stu-id="5289e-105">This article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="5289e-106">Cuando una versión de Fedora no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="5289e-106">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="5289e-107">Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="5289e-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5289e-108">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="5289e-108">Supported distributions</span></span>

<span data-ttu-id="5289e-109">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="5289e-109">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="5289e-110">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="5289e-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="5289e-111">El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.</span><span class="sxs-lookup"><span data-stu-id="5289e-111">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="5289e-112">El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.</span><span class="sxs-lookup"><span data-stu-id="5289e-112">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="5289e-113">Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="5289e-113">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="5289e-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="5289e-114">Fedora</span></span>               | <span data-ttu-id="5289e-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-115">.NET Core 2.1</span></span> | <span data-ttu-id="5289e-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-116">.NET Core 3.1</span></span> | <span data-ttu-id="5289e-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-117">.NET 5.0</span></span> |
|----------------------|---------------|---------------|----------|
| <span data-ttu-id="5289e-118">✔️ [33](#fedora-33-)</span><span class="sxs-lookup"><span data-stu-id="5289e-118">✔️ [33](#fedora-33-)</span></span> | <span data-ttu-id="5289e-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-119">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-120">✔️ 3.1</span></span>        | <span data-ttu-id="5289e-121">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-121">✔️ 5.0</span></span> |
| <span data-ttu-id="5289e-122">✔️ [32](#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="5289e-122">✔️ [32](#fedora-32-)</span></span> | <span data-ttu-id="5289e-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-123">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-124">✔️ 3.1</span></span>        | <span data-ttu-id="5289e-125">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-125">✔️ 5.0</span></span> |
| <span data-ttu-id="5289e-126">❌ [31](#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="5289e-126">❌ [31](#fedora-31-)</span></span> | <span data-ttu-id="5289e-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-127">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-128">✔️ 3.1</span></span>        | <span data-ttu-id="5289e-129">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-129">❌ 5.0</span></span> |
| <span data-ttu-id="5289e-130">❌ [30](#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="5289e-130">❌ [30](#fedora-30-)</span></span> | <span data-ttu-id="5289e-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-131">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-132">✔️ 3.1</span></span>        | <span data-ttu-id="5289e-133">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-133">❌ 5.0</span></span> |
| <span data-ttu-id="5289e-134">❌ [29](#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="5289e-134">❌ [29](#fedora-29-)</span></span> | <span data-ttu-id="5289e-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-135">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-136">✔️ 3.1</span></span>        | <span data-ttu-id="5289e-137">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-137">❌ 5.0</span></span> |
| <span data-ttu-id="5289e-138">❌ [28](#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="5289e-138">❌ [28](#fedora-28-)</span></span> | <span data-ttu-id="5289e-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-139">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-140">❌ 3.1</span></span>        | <span data-ttu-id="5289e-141">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-141">❌ 5.0</span></span> |
| <span data-ttu-id="5289e-142">❌ [27](#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="5289e-142">❌ [27](#fedora-27-)</span></span> | <span data-ttu-id="5289e-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5289e-143">✔️ 2.1</span></span>        | <span data-ttu-id="5289e-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5289e-144">❌ 3.1</span></span>        | <span data-ttu-id="5289e-145">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5289e-145">❌ 5.0</span></span> |

<span data-ttu-id="5289e-146">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="5289e-146">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="5289e-147">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="5289e-147">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5289e-148">3.0</span><span class="sxs-lookup"><span data-stu-id="5289e-148">3.0</span></span>
- <span data-ttu-id="5289e-149">2.2</span><span class="sxs-lookup"><span data-stu-id="5289e-149">2.2</span></span>
- <span data-ttu-id="5289e-150">2.0</span><span class="sxs-lookup"><span data-stu-id="5289e-150">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="5289e-151">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="5289e-151">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5289e-152">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="5289e-152">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-33-"></a><span data-ttu-id="5289e-153">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="5289e-153">Fedora 33 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="5289e-154">.NET Core 3.1 está disponible en los repositorios de paquetes predeterminados para Fedora 33.</span><span class="sxs-lookup"><span data-stu-id="5289e-154">.NET Core 3.1 is available in the default package repositories for Fedora 33.</span></span> <span data-ttu-id="5289e-155">Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="5289e-155">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="5289e-156">.NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5289e-156">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-32-"></a><span data-ttu-id="5289e-157">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="5289e-157">Fedora 32 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="5289e-158">.NET Core 3.1 está disponible en los repositorios de paquetes predeterminados para Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="5289e-158">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span> <span data-ttu-id="5289e-159">Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="5289e-159">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="5289e-160">.NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5289e-160">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="5289e-161">Fedora 31 ❌</span><span class="sxs-lookup"><span data-stu-id="5289e-161">Fedora 31 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="5289e-162">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="5289e-162">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="5289e-163">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="5289e-163">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="5289e-164">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="5289e-164">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="5289e-165">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="5289e-165">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="5289e-166">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="5289e-166">Troubleshoot the package manager</span></span>

<span data-ttu-id="5289e-167">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5289e-167">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="5289e-168">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="5289e-168">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="5289e-169">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="5289e-169">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="5289e-170">Snap</span><span class="sxs-lookup"><span data-stu-id="5289e-170">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5289e-171">Dependencias</span><span class="sxs-lookup"><span data-stu-id="5289e-171">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="5289e-172">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="5289e-172">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5289e-173">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="5289e-173">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5289e-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5289e-174">Next steps</span></span>

- [<span data-ttu-id="5289e-175">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5289e-175">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
