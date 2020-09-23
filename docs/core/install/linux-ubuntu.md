---
title: 'Instalación de .NET Core en Ubuntu: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 5c07de20110a1aecf2ec5cb9de88f204625e548d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538467"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="635df-103">Instalación del SDK de .NET Core o de .NET Core Runtime en Ubuntu</span><span class="sxs-lookup"><span data-stu-id="635df-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="635df-104">.NET Core es compatible con Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="635df-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="635df-105">En este artículo se describe cómo instalar .NET Core en Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="635df-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="635df-106">Cuando una versión de Ubuntu no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="635df-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="635df-107">Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="635df-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="635df-108">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="635df-108">Supported distributions</span></span>

<span data-ttu-id="635df-109">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Ubuntu en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="635df-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="635df-110">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Ubuntu llegue al final del ciclo de vida](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="635df-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="635df-111">Una ✔️ indica que todavía se admite la versión de Ubuntu o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="635df-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="635df-112">Una ❌ indica que la versión de Ubuntu o de .NET Core no se admite en esa versión de Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="635df-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="635df-113">Cuando una versión de Ubuntu y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="635df-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="635df-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="635df-114">Ubuntu</span></span>                   | <span data-ttu-id="635df-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-115">.NET Core 2.1</span></span> | <span data-ttu-id="635df-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-116">.NET Core 3.1</span></span> | <span data-ttu-id="635df-117">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="635df-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="635df-118">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="635df-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="635df-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-119">✔️ 2.1</span></span>        | <span data-ttu-id="635df-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-120">✔️ 3.1</span></span>        | <span data-ttu-id="635df-121">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-122">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="635df-122">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="635df-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-123">✔️ 2.1</span></span>        | <span data-ttu-id="635df-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-124">✔️ 3.1</span></span>        | <span data-ttu-id="635df-125">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="635df-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="635df-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-127">✔️ 2.1</span></span>        | <span data-ttu-id="635df-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-128">✔️ 3.1</span></span>        | <span data-ttu-id="635df-129">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="635df-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="635df-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-131">✔️ 2.1</span></span>        | <span data-ttu-id="635df-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-132">❌ 3.1</span></span>        | <span data-ttu-id="635df-133">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-134">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="635df-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="635df-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-135">✔️ 2.1</span></span>        | <span data-ttu-id="635df-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-136">✔️ 3.1</span></span>        | <span data-ttu-id="635df-137">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="635df-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="635df-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-139">✔️ 2.1</span></span>        | <span data-ttu-id="635df-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-140">❌ 3.1</span></span>        | <span data-ttu-id="635df-141">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="635df-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="635df-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-143">✔️ 2.1</span></span>        | <span data-ttu-id="635df-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-144">❌ 3.1</span></span>        | <span data-ttu-id="635df-145">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="635df-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="635df-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-147">❌ 2.1</span></span>        | <span data-ttu-id="635df-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-148">❌ 3.1</span></span>        | <span data-ttu-id="635df-149">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="635df-150">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="635df-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="635df-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="635df-151">✔️ 2.1</span></span>        | <span data-ttu-id="635df-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="635df-152">✔️ 3.1</span></span>        | <span data-ttu-id="635df-153">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="635df-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="635df-154">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="635df-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="635df-155">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="635df-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="635df-156">3.0</span><span class="sxs-lookup"><span data-stu-id="635df-156">3.0</span></span>
- <span data-ttu-id="635df-157">2.2</span><span class="sxs-lookup"><span data-stu-id="635df-157">2.2</span></span>
- <span data-ttu-id="635df-158">2.0</span><span class="sxs-lookup"><span data-stu-id="635df-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="635df-159">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="635df-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="635df-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="635df-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="635df-161">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-161">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="635df-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="635df-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="635df-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="635df-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="635df-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="635df-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="635df-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="635df-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="635df-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="635df-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="635df-169">SDK o entorno de ejecución de actualización de APT</span><span class="sxs-lookup"><span data-stu-id="635df-169">APT update SDK or runtime</span></span>

<span data-ttu-id="635df-170">Cuando hay disponible una nueva versión de revisión para .NET Core, basta con que la actualice mediante APT con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="635df-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="635df-171">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="635df-171">APT troubleshooting</span></span>

<span data-ttu-id="635df-172">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar ATP para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="635df-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="635df-173">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="635df-173">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="635df-174">No se puede encontrar el paquete \\ No se han podido instalar algunos paquetes</span><span class="sxs-lookup"><span data-stu-id="635df-174">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="635df-175">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="635df-175">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="635df-176">Snap</span><span class="sxs-lookup"><span data-stu-id="635df-176">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="635df-177">Dependencias</span><span class="sxs-lookup"><span data-stu-id="635df-177">Dependencies</span></span>

<span data-ttu-id="635df-178">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="635df-178">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="635df-179">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="635df-179">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="635df-180">libc6</span><span class="sxs-lookup"><span data-stu-id="635df-180">libc6</span></span>
- <span data-ttu-id="635df-181">libgcc1</span><span class="sxs-lookup"><span data-stu-id="635df-181">libgcc1</span></span>
- <span data-ttu-id="635df-182">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="635df-182">libgssapi-krb5-2</span></span>
- <span data-ttu-id="635df-183">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="635df-183">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="635df-184">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="635df-184">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="635df-185">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="635df-185">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="635df-186">libicu66 (para 20.x)</span><span class="sxs-lookup"><span data-stu-id="635df-186">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="635df-187">libssl1.0.0 (para 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="635df-187">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="635df-188">libssl1.1 (para 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="635df-188">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="635df-189">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="635df-189">libstdc++6</span></span>
- <span data-ttu-id="635df-190">zlib1g</span><span class="sxs-lookup"><span data-stu-id="635df-190">zlib1g</span></span>

<span data-ttu-id="635df-191">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="635df-191">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="635df-192">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="635df-192">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="635df-193">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="635df-193">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="635df-194">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="635df-194">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="635df-195">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="635df-195">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="635df-196">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="635df-196">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="635df-197">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="635df-197">Next steps</span></span>

- [<span data-ttu-id="635df-198">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="635df-198">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
