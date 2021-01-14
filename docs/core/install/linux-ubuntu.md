---
title: 'Instalación de .NET en Ubuntu: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 14e5e9548d4aa09a586e2038f3e35a489ee65cd2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970778"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="560dc-103">Instalación del SDK y el entorno de ejecución de .NET en Ubuntu</span><span class="sxs-lookup"><span data-stu-id="560dc-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="560dc-104">.NET es compatible con Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="560dc-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="560dc-105">En este artículo se describe cómo instalar .NET en Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="560dc-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="560dc-106">Cuando una versión de Ubuntu no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="560dc-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="560dc-107">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="560dc-107">Supported distributions</span></span>

<span data-ttu-id="560dc-108">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Ubuntu en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="560dc-108">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="560dc-109">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Ubuntu llegue al final del ciclo de vida](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="560dc-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="560dc-110">El símbolo ✔️ indica que todavía se admite la versión de Ubuntu o de .NET.</span><span class="sxs-lookup"><span data-stu-id="560dc-110">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="560dc-111">El símbolo ❌ indica que la versión de Ubuntu o de .NET no se admite en esa versión de Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="560dc-111">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="560dc-112">Si una versión de Ubuntu y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="560dc-112">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="560dc-113">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="560dc-113">Ubuntu</span></span>                   | <span data-ttu-id="560dc-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-114">.NET Core 2.1</span></span> | <span data-ttu-id="560dc-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-115">.NET Core 3.1</span></span> | <span data-ttu-id="560dc-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="560dc-117">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="560dc-117">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="560dc-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-118">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-119">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-120">✔️ 5.0</span></span> |
| <span data-ttu-id="560dc-121">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="560dc-121">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="560dc-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-122">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-123">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-124">✔️ 5.0</span></span> |
| <span data-ttu-id="560dc-125">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="560dc-125">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="560dc-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-126">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-127">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-127">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-128">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-128">✔️ 5.0</span></span> |
| <span data-ttu-id="560dc-129">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="560dc-129">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="560dc-130">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-130">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-131">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-131">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-132">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-132">❌ 5.0</span></span> |
| <span data-ttu-id="560dc-133">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="560dc-133">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="560dc-134">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-134">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-135">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-135">❌ 3.1</span></span>        | <span data-ttu-id="560dc-136">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-136">❌ 5.0</span></span> |
| <span data-ttu-id="560dc-137">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="560dc-137">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="560dc-138">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-138">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-139">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-139">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-140">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-140">✔️ 5.0</span></span> |
| <span data-ttu-id="560dc-141">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="560dc-141">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="560dc-142">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-142">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-143">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-143">❌ 3.1</span></span>        | <span data-ttu-id="560dc-144">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-144">❌ 5.0</span></span> |
| <span data-ttu-id="560dc-145">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="560dc-145">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="560dc-146">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-146">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-147">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-147">❌ 3.1</span></span>        | <span data-ttu-id="560dc-148">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-148">❌ 5.0</span></span> |
| <span data-ttu-id="560dc-149">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="560dc-149">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="560dc-150">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-150">❌ 2.1</span></span>        | <span data-ttu-id="560dc-151">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-151">❌ 3.1</span></span>        | <span data-ttu-id="560dc-152">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-152">❌ 5.0</span></span> |
| <span data-ttu-id="560dc-153">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="560dc-153">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="560dc-154">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="560dc-154">✔️ 2.1</span></span>        | <span data-ttu-id="560dc-155">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="560dc-155">✔️ 3.1</span></span>        | <span data-ttu-id="560dc-156">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="560dc-156">✔️ 5.0</span></span> |

<span data-ttu-id="560dc-157">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="560dc-157">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="560dc-158">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="560dc-158">The downloads for these still remain published:</span></span>

- <span data-ttu-id="560dc-159">3.0</span><span class="sxs-lookup"><span data-stu-id="560dc-159">3.0</span></span>
- <span data-ttu-id="560dc-160">2.2</span><span class="sxs-lookup"><span data-stu-id="560dc-160">2.2</span></span>
- <span data-ttu-id="560dc-161">2.0</span><span class="sxs-lookup"><span data-stu-id="560dc-161">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="560dc-162">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="560dc-162">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="2010-"></a><span data-ttu-id="560dc-163">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="560dc-163">20.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="2004-"></a><span data-ttu-id="560dc-164">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="560dc-164">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="560dc-165">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-165">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="560dc-166">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-166">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="560dc-167">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-167">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="560dc-168">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="560dc-168">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="560dc-169">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-169">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="560dc-170">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-170">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="560dc-171">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="560dc-171">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="560dc-172">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="560dc-172">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="560dc-173">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="560dc-173">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="560dc-174">Uso de APT para actualizar .NET</span><span class="sxs-lookup"><span data-stu-id="560dc-174">Use APT to update .NET</span></span>

<span data-ttu-id="560dc-175">Cuando hay disponible una nueva versión de revisión para .NET, basta con actualizarla mediante APT con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="560dc-175">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="560dc-176">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="560dc-176">APT troubleshooting</span></span>

<span data-ttu-id="560dc-177">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar APT para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="560dc-177">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="560dc-178">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="560dc-178">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="560dc-179">No se puede encontrar el paquete \\ No se han podido instalar algunos paquetes</span><span class="sxs-lookup"><span data-stu-id="560dc-179">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="560dc-180">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="560dc-180">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="560dc-181">Dependencias</span><span class="sxs-lookup"><span data-stu-id="560dc-181">Dependencies</span></span>

<span data-ttu-id="560dc-182">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="560dc-182">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="560dc-183">Pero si instala manualmente .NET o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="560dc-183">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="560dc-184">libc6</span><span class="sxs-lookup"><span data-stu-id="560dc-184">libc6</span></span>
- <span data-ttu-id="560dc-185">libgcc1</span><span class="sxs-lookup"><span data-stu-id="560dc-185">libgcc1</span></span>
- <span data-ttu-id="560dc-186">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="560dc-186">libgssapi-krb5-2</span></span>
- <span data-ttu-id="560dc-187">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-187">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="560dc-188">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-188">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="560dc-189">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-189">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="560dc-190">libicu66 (para 20.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-190">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="560dc-191">libssl1.0.0 (para 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-191">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="560dc-192">libssl1.1 (para 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="560dc-192">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="560dc-193">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="560dc-193">libstdc++6</span></span>
- <span data-ttu-id="560dc-194">zlib1g</span><span class="sxs-lookup"><span data-stu-id="560dc-194">zlib1g</span></span>

<span data-ttu-id="560dc-195">Para las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="560dc-195">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="560dc-196">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="560dc-196">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="560dc-197">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="560dc-197">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="560dc-198">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="560dc-198">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="560dc-199">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="560dc-199">Next steps</span></span>

- [<span data-ttu-id="560dc-200">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="560dc-200">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="560dc-201">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="560dc-201">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
