---
title: 'Instalación de .NET en Fedora: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Fedora.
author: adegeo
ms.author: adegeo
ms.date: 02/17/2021
ms.openlocfilehash: efaad4788db2200b1a47f9b4ae2414730588c6ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255767"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="765be-103">Instalación del SDK y el entorno de ejecución de .NET en Fedora</span><span class="sxs-lookup"><span data-stu-id="765be-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="765be-104">.NET es compatible con Fedora. En este artículo se describe cómo instalar .NET en Fedora.</span><span class="sxs-lookup"><span data-stu-id="765be-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="765be-105">Cuando una versión de Fedora no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="765be-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="765be-106">Para obtener más información sobre cómo instalar .NET sin un administrador de paquetes, consulte uno de los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="765be-106">For more information on installing .NET without a package manager, see one of the following articles:</span></span>

- [<span data-ttu-id="765be-107">Instalación del SDK y el entorno de ejecución de .NET con un snap</span><span class="sxs-lookup"><span data-stu-id="765be-107">Install the .NET SDK or the .NET Runtime with Snap.</span></span>](linux-snap.md)
- [<span data-ttu-id="765be-108">Instalación del SDK y el entorno de ejecución de .NET con un script</span><span class="sxs-lookup"><span data-stu-id="765be-108">Install the .NET SDK or the .NET Runtime with a script.</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="765be-109">Instalación manual del SDK y el entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="765be-109">Install the .NET SDK or the .NET Runtime manually.</span></span>](linux-scripted-manual.md#manual-install)

## <a name="install-net-50"></a><span data-ttu-id="765be-110">Instalación de .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="765be-110">Install .NET 5.0</span></span>

<span data-ttu-id="765be-111">La última versión de .NET disponible en los repositorios de paquetes predeterminados para Fedora es .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="765be-111">The latest version of .NET available in the default package repositories for Fedora is .NET 5.0.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="765be-112">Instalación de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="765be-112">Install .NET Core 3.1</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="765be-113">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="765be-113">Supported distributions</span></span>

<span data-ttu-id="765be-114">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="765be-114">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="765be-115">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="765be-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="765be-116">El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.</span><span class="sxs-lookup"><span data-stu-id="765be-116">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="765be-117">El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.</span><span class="sxs-lookup"><span data-stu-id="765be-117">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="765be-118">Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="765be-118">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="765be-119">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="765be-119">.NET Version</span></span>  | <span data-ttu-id="765be-120">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="765be-120">Fedora 33 ✔️</span></span> | <span data-ttu-id="765be-121">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="765be-121">32 ✔️</span></span> | <span data-ttu-id="765be-122">31 ❌</span><span class="sxs-lookup"><span data-stu-id="765be-122">31 ❌</span></span> | <span data-ttu-id="765be-123">30 ❌</span><span class="sxs-lookup"><span data-stu-id="765be-123">30 ❌</span></span> | <span data-ttu-id="765be-124">29 ❌</span><span class="sxs-lookup"><span data-stu-id="765be-124">29 ❌</span></span> | <span data-ttu-id="765be-125">28 ❌</span><span class="sxs-lookup"><span data-stu-id="765be-125">28 ❌</span></span> | <span data-ttu-id="765be-126">27 ❌</span><span class="sxs-lookup"><span data-stu-id="765be-126">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="765be-127">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="765be-127">.NET 5.0</span></span>      | <span data-ttu-id="765be-128">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-128">✔️</span></span>        | <span data-ttu-id="765be-129">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-129">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="765be-130">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="765be-130">.NET Core 3.1</span></span> | <span data-ttu-id="765be-131">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-131">✔️</span></span>        | <span data-ttu-id="765be-132">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-132">✔️</span></span> | <span data-ttu-id="765be-133">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-133">✔️</span></span>|<span data-ttu-id="765be-134">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-134">✔️</span></span> |<span data-ttu-id="765be-135">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-135">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="765be-136">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="765be-136">.NET Core 2.1</span></span> | <span data-ttu-id="765be-137">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-137">✔️</span></span>        | <span data-ttu-id="765be-138">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-138">✔️</span></span> | <span data-ttu-id="765be-139">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-139">✔️</span></span>|<span data-ttu-id="765be-140">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-140">✔️</span></span> |<span data-ttu-id="765be-141">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-141">✔️</span></span> |<span data-ttu-id="765be-142">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-142">✔️</span></span>  |<span data-ttu-id="765be-143">✔️</span><span class="sxs-lookup"><span data-stu-id="765be-143">✔️</span></span> |

<span data-ttu-id="765be-144">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="765be-144">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="765be-145">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="765be-145">The downloads for these still remain published:</span></span>

- <span data-ttu-id="765be-146">3.0</span><span class="sxs-lookup"><span data-stu-id="765be-146">3.0</span></span>
- <span data-ttu-id="765be-147">2.2</span><span class="sxs-lookup"><span data-stu-id="765be-147">2.2</span></span>
- <span data-ttu-id="765be-148">2.0</span><span class="sxs-lookup"><span data-stu-id="765be-148">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="765be-149">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="765be-149">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="765be-150">Dependencias</span><span class="sxs-lookup"><span data-stu-id="765be-150">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="765be-151">Instalación en distribuciones anteriores</span><span class="sxs-lookup"><span data-stu-id="765be-151">Install on older distributions</span></span>

<span data-ttu-id="765be-152">Las versiones anteriores de Fedora no contienen .NET Core en los repositorios de paquetes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="765be-152">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="765be-153">Puede instalar .NET con un [snap](linux-snap.md), mediante el [script _dotnet-install.sh_](linux-scripted-manual.md#scripted-install) o con el repositorio de Microsoft para instalar .NET:</span><span class="sxs-lookup"><span data-stu-id="765be-153">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="765be-154">En primer lugar, agregue la clave de firma de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="765be-154">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="765be-155">Después, agregue el repositorio de paquetes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="765be-155">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="765be-156">El origen del repositorio se basa en la versión que tenga de Fedora.</span><span class="sxs-lookup"><span data-stu-id="765be-156">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="765be-157">Versión de Fedora</span><span class="sxs-lookup"><span data-stu-id="765be-157">Fedora Version</span></span> | <span data-ttu-id="765be-158">Repositorio de paquetes</span><span class="sxs-lookup"><span data-stu-id="765be-158">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="765be-159">31</span><span class="sxs-lookup"><span data-stu-id="765be-159">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="765be-160">30</span><span class="sxs-lookup"><span data-stu-id="765be-160">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="765be-161">29</span><span class="sxs-lookup"><span data-stu-id="765be-161">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="765be-162">28</span><span class="sxs-lookup"><span data-stu-id="765be-162">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="765be-163">27</span><span class="sxs-lookup"><span data-stu-id="765be-163">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="765be-164">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="765be-164">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="765be-165">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="765be-165">Troubleshoot the package manager</span></span>

<span data-ttu-id="765be-166">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar el administrador de paquetes para instalar .NET o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="765be-166">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="765be-167">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="765be-167">Unable to find package</span></span>

<span data-ttu-id="765be-168">Para obtener más información sobre cómo instalar .NET sin un administrador de paquetes, consulte uno de los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="765be-168">For more information on installing .NET without a package manager, see one of the following articles:</span></span>

- [<span data-ttu-id="765be-169">Instalación del SDK y el entorno de ejecución de .NET con un snap</span><span class="sxs-lookup"><span data-stu-id="765be-169">Install the .NET SDK or the .NET Runtime with Snap.</span></span>](linux-snap.md)
- [<span data-ttu-id="765be-170">Instalación del SDK y el entorno de ejecución de .NET con un script</span><span class="sxs-lookup"><span data-stu-id="765be-170">Install the .NET SDK or the .NET Runtime with a script.</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="765be-171">Instalación manual del SDK y el entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="765be-171">Install the .NET SDK or the .NET Runtime manually.</span></span>](linux-scripted-manual.md#manual-install)

### <a name="failed-to-fetch"></a><span data-ttu-id="765be-172">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="765be-172">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="765be-173">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="765be-173">Next steps</span></span>

- [<span data-ttu-id="765be-174">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="765be-174">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="765be-175">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="765be-175">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
