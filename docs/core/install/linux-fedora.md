---
title: 'Instalación de .NET en Fedora: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Fedora.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970829"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="8eb50-103">Instalación del SDK y el entorno de ejecución de .NET en Fedora</span><span class="sxs-lookup"><span data-stu-id="8eb50-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="8eb50-104">.NET es compatible con Fedora. En este artículo se describe cómo instalar .NET en Fedora.</span><span class="sxs-lookup"><span data-stu-id="8eb50-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="8eb50-105">Cuando una versión de Fedora no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="8eb50-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a><span data-ttu-id="8eb50-106">Instalación de .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8eb50-106">Install .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="8eb50-107">**Fedora 32**</span><span class="sxs-lookup"><span data-stu-id="8eb50-107">**Fedora 32**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

<span data-ttu-id="8eb50-108">**Fedora 33**</span><span class="sxs-lookup"><span data-stu-id="8eb50-108">**Fedora 33**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="8eb50-109">Instalación de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8eb50-109">Install .NET Core 3.1</span></span>

<span data-ttu-id="8eb50-110">La última versión de .NET disponible en los repositorios de paquetes predeterminados para Fedora es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8eb50-110">The latest version of .NET available in the default package repositories for Fedora is .NET Core 3.1.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="8eb50-111">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="8eb50-111">Supported distributions</span></span>

<span data-ttu-id="8eb50-112">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="8eb50-112">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="8eb50-113">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="8eb50-113">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="8eb50-114">El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.</span><span class="sxs-lookup"><span data-stu-id="8eb50-114">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="8eb50-115">El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.</span><span class="sxs-lookup"><span data-stu-id="8eb50-115">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="8eb50-116">Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="8eb50-116">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="8eb50-117">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="8eb50-117">.NET Version</span></span>  | <span data-ttu-id="8eb50-118">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-118">Fedora 33 ✔️</span></span> | <span data-ttu-id="8eb50-119">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-119">32 ✔️</span></span> | <span data-ttu-id="8eb50-120">31 ❌</span><span class="sxs-lookup"><span data-stu-id="8eb50-120">31 ❌</span></span> | <span data-ttu-id="8eb50-121">30 ❌</span><span class="sxs-lookup"><span data-stu-id="8eb50-121">30 ❌</span></span> | <span data-ttu-id="8eb50-122">29 ❌</span><span class="sxs-lookup"><span data-stu-id="8eb50-122">29 ❌</span></span> | <span data-ttu-id="8eb50-123">28 ❌</span><span class="sxs-lookup"><span data-stu-id="8eb50-123">28 ❌</span></span> | <span data-ttu-id="8eb50-124">27 ❌</span><span class="sxs-lookup"><span data-stu-id="8eb50-124">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="8eb50-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8eb50-125">.NET 5.0</span></span>      | <span data-ttu-id="8eb50-126">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-126">✔️</span></span>        | <span data-ttu-id="8eb50-127">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-127">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="8eb50-128">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8eb50-128">.NET Core 3.1</span></span> | <span data-ttu-id="8eb50-129">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-129">✔️</span></span>        | <span data-ttu-id="8eb50-130">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-130">✔️</span></span> | <span data-ttu-id="8eb50-131">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-131">✔️</span></span>|<span data-ttu-id="8eb50-132">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-132">✔️</span></span> |<span data-ttu-id="8eb50-133">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-133">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="8eb50-134">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8eb50-134">.NET Core 2.1</span></span> | <span data-ttu-id="8eb50-135">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-135">✔️</span></span>        | <span data-ttu-id="8eb50-136">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-136">✔️</span></span> | <span data-ttu-id="8eb50-137">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-137">✔️</span></span>|<span data-ttu-id="8eb50-138">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-138">✔️</span></span> |<span data-ttu-id="8eb50-139">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-139">✔️</span></span> |<span data-ttu-id="8eb50-140">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-140">✔️</span></span>  |<span data-ttu-id="8eb50-141">✔️</span><span class="sxs-lookup"><span data-stu-id="8eb50-141">✔️</span></span> |

<span data-ttu-id="8eb50-142">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="8eb50-142">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="8eb50-143">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="8eb50-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="8eb50-144">3.0</span><span class="sxs-lookup"><span data-stu-id="8eb50-144">3.0</span></span>
- <span data-ttu-id="8eb50-145">2.2</span><span class="sxs-lookup"><span data-stu-id="8eb50-145">2.2</span></span>
- <span data-ttu-id="8eb50-146">2.0</span><span class="sxs-lookup"><span data-stu-id="8eb50-146">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="8eb50-147">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="8eb50-147">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="8eb50-148">Dependencias</span><span class="sxs-lookup"><span data-stu-id="8eb50-148">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="8eb50-149">Instalación en distribuciones anteriores</span><span class="sxs-lookup"><span data-stu-id="8eb50-149">Install on older distributions</span></span>

<span data-ttu-id="8eb50-150">Las versiones anteriores de Fedora no contienen .NET Core en los repositorios de paquetes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8eb50-150">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="8eb50-151">Puede instalar .NET con un [snap](linux-snap.md), mediante el [script _dotnet-install.sh_](linux-scripted-manual.md#scripted-install) o con el repositorio de Microsoft para instalar .NET:</span><span class="sxs-lookup"><span data-stu-id="8eb50-151">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="8eb50-152">En primer lugar, agregue la clave de firma de Microsoft a la lista de claves de confianza.</span><span class="sxs-lookup"><span data-stu-id="8eb50-152">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="8eb50-153">Después, agregue el repositorio de paquetes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8eb50-153">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="8eb50-154">El origen del repositorio se basa en la versión que tenga de Fedora.</span><span class="sxs-lookup"><span data-stu-id="8eb50-154">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="8eb50-155">Versión de Fedora</span><span class="sxs-lookup"><span data-stu-id="8eb50-155">Fedora Version</span></span> | <span data-ttu-id="8eb50-156">Repositorio de paquetes</span><span class="sxs-lookup"><span data-stu-id="8eb50-156">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="8eb50-157">31</span><span class="sxs-lookup"><span data-stu-id="8eb50-157">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="8eb50-158">30</span><span class="sxs-lookup"><span data-stu-id="8eb50-158">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="8eb50-159">29</span><span class="sxs-lookup"><span data-stu-id="8eb50-159">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="8eb50-160">28</span><span class="sxs-lookup"><span data-stu-id="8eb50-160">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="8eb50-161">27</span><span class="sxs-lookup"><span data-stu-id="8eb50-161">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="8eb50-162">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="8eb50-162">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="8eb50-163">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="8eb50-163">Troubleshoot the package manager</span></span>

<span data-ttu-id="8eb50-164">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar el administrador de paquetes para instalar .NET o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8eb50-164">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="8eb50-165">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="8eb50-165">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="8eb50-166">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="8eb50-166">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="8eb50-167">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8eb50-167">Next steps</span></span>

- [<span data-ttu-id="8eb50-168">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="8eb50-168">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="8eb50-169">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8eb50-169">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
