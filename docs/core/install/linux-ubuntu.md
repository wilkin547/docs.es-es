---
title: 'Instalación de .NET Core en Ubuntu: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: c590bd89b718a5cd31dae9f83049eac910cb4049
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863896"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="5e334-103">Instalación del SDK de .NET Core o de .NET Core Runtime en Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5e334-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="5e334-104">.NET Core es compatible con Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e334-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="5e334-105">En este artículo se describe cómo instalar .NET Core en Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e334-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="5e334-106">Cuando una versión de Ubuntu no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="5e334-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="5e334-107">Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="5e334-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5e334-108">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="5e334-108">Supported distributions</span></span>

<span data-ttu-id="5e334-109">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Ubuntu en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="5e334-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="5e334-110">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Ubuntu llegue al final del ciclo de vida](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="5e334-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="5e334-111">Una ✔️ indica que todavía se admite la versión de Ubuntu o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e334-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="5e334-112">Una ❌ indica que la versión de Ubuntu o de .NET Core no se admite en esa versión de Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5e334-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="5e334-113">Cuando una versión de Ubuntu y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="5e334-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="5e334-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5e334-114">Ubuntu</span></span>                   | <span data-ttu-id="5e334-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-115">.NET Core 2.1</span></span> | <span data-ttu-id="5e334-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-116">.NET Core 3.1</span></span> | <span data-ttu-id="5e334-117">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="5e334-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5e334-118">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="5e334-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="5e334-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-119">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-120">✔️ 3.1</span></span>        | <span data-ttu-id="5e334-121">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-122">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="5e334-122">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="5e334-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-123">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-124">✔️ 3.1</span></span>        | <span data-ttu-id="5e334-125">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="5e334-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="5e334-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-127">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-128">✔️ 3.1</span></span>        | <span data-ttu-id="5e334-129">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="5e334-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="5e334-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-131">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-132">❌ 3.1</span></span>        | <span data-ttu-id="5e334-133">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-134">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="5e334-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="5e334-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-135">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-136">✔️ 3.1</span></span>        | <span data-ttu-id="5e334-137">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="5e334-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="5e334-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-139">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-140">❌ 3.1</span></span>        | <span data-ttu-id="5e334-141">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="5e334-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="5e334-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-143">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-144">❌ 3.1</span></span>        | <span data-ttu-id="5e334-145">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="5e334-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="5e334-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-147">❌ 2.1</span></span>        | <span data-ttu-id="5e334-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-148">❌ 3.1</span></span>        | <span data-ttu-id="5e334-149">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5e334-150">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="5e334-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="5e334-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5e334-151">✔️ 2.1</span></span>        | <span data-ttu-id="5e334-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5e334-152">✔️ 3.1</span></span>        | <span data-ttu-id="5e334-153">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5e334-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="5e334-154">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="5e334-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="5e334-155">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="5e334-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5e334-156">3.0</span><span class="sxs-lookup"><span data-stu-id="5e334-156">3.0</span></span>
- <span data-ttu-id="5e334-157">2.2</span><span class="sxs-lookup"><span data-stu-id="5e334-157">2.2</span></span>
- <span data-ttu-id="5e334-158">2.0</span><span class="sxs-lookup"><span data-stu-id="5e334-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5e334-159">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="5e334-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="5e334-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e334-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="5e334-161">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-161">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="5e334-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="5e334-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="5e334-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e334-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="5e334-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="5e334-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="5e334-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5e334-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="5e334-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5e334-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="5e334-169">SDK o entorno de ejecución de actualización de APT</span><span class="sxs-lookup"><span data-stu-id="5e334-169">APT update SDK or runtime</span></span>

<span data-ttu-id="5e334-170">Cuando hay disponible una nueva versión de revisión para .NET Core, basta con que la actualice mediante APT con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="5e334-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="5e334-171">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="5e334-171">APT troubleshooting</span></span>

<span data-ttu-id="5e334-172">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar ATP para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e334-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="5e334-173">No se encuentra el elemento</span><span class="sxs-lookup"><span data-stu-id="5e334-173">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="5e334-174">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="5e334-174">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="5e334-175">Snap</span><span class="sxs-lookup"><span data-stu-id="5e334-175">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5e334-176">Dependencias</span><span class="sxs-lookup"><span data-stu-id="5e334-176">Dependencies</span></span>

<span data-ttu-id="5e334-177">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5e334-177">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5e334-178">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="5e334-178">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5e334-179">libc6</span><span class="sxs-lookup"><span data-stu-id="5e334-179">libc6</span></span>
- <span data-ttu-id="5e334-180">libgcc1</span><span class="sxs-lookup"><span data-stu-id="5e334-180">libgcc1</span></span>
- <span data-ttu-id="5e334-181">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="5e334-181">libgssapi-krb5-2</span></span>
- <span data-ttu-id="5e334-182">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-182">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="5e334-183">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-183">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="5e334-184">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-184">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="5e334-185">libicu66 (para 20.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-185">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="5e334-186">libssl1.0.0 (para 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-186">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="5e334-187">libssl1.1 (para 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="5e334-187">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="5e334-188">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="5e334-188">libstdc++6</span></span>
- <span data-ttu-id="5e334-189">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5e334-189">zlib1g</span></span>

<span data-ttu-id="5e334-190">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e334-190">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5e334-191">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="5e334-191">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="5e334-192">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="5e334-192">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5e334-193">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5e334-193">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="5e334-194">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="5e334-194">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5e334-195">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="5e334-195">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5e334-196">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5e334-196">Next steps</span></span>

- [<span data-ttu-id="5e334-197">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5e334-197">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
