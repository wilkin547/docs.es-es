---
title: 'Instalación de .NET en Debian: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Debian.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 683d0a9c47edf3cf9c47426d659e778eeb6f84df
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031896"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="3ae7f-103">Instalación del SDK y el entorno de ejecución de .NET en Debian</span><span class="sxs-lookup"><span data-stu-id="3ae7f-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="3ae7f-104">En este artículo se describe cómo instalar .NET en Debian.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="3ae7f-105">Cuando una versión de Debian no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="3ae7f-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="3ae7f-107">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="3ae7f-107">Supported distributions</span></span>

<span data-ttu-id="3ae7f-108">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Debian en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="3ae7f-109">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="3ae7f-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="3ae7f-110">El símbolo ✔️ indica que todavía se admite la versión de Debian o de .NET.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="3ae7f-111">El símbolo ❌ indica que la versión de Debian o de .NET no se admite en esa versión de Debian.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="3ae7f-112">Si una versión de Debian y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="3ae7f-113">Debian</span><span class="sxs-lookup"><span data-stu-id="3ae7f-113">Debian</span></span>                   | <span data-ttu-id="3ae7f-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-114">.NET Core 2.1</span></span> | <span data-ttu-id="3ae7f-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-115">.NET Core 3.1</span></span> | <span data-ttu-id="3ae7f-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="3ae7f-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="3ae7f-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-118">✔️ 2.1</span></span>        | <span data-ttu-id="3ae7f-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-119">✔️ 3.1</span></span>        | <span data-ttu-id="3ae7f-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-120">✔️ 5.0</span></span> |
| <span data-ttu-id="3ae7f-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="3ae7f-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-122">✔️ 2.1</span></span>        | <span data-ttu-id="3ae7f-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-123">✔️ 3.1</span></span>        | <span data-ttu-id="3ae7f-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-124">✔️ 5.0</span></span> |
| <span data-ttu-id="3ae7f-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="3ae7f-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-126">✔️ 2.1</span></span>        | <span data-ttu-id="3ae7f-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-127">❌ 3.1</span></span>        | <span data-ttu-id="3ae7f-128">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-128">❌ 5.0</span></span> |

<span data-ttu-id="3ae7f-129">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="3ae7f-130">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="3ae7f-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="3ae7f-131">3.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-131">3.0</span></span>
- <span data-ttu-id="3ae7f-132">2.2</span><span class="sxs-lookup"><span data-stu-id="3ae7f-132">2.2</span></span>
- <span data-ttu-id="3ae7f-133">2.0</span><span class="sxs-lookup"><span data-stu-id="3ae7f-133">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="3ae7f-134">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="3ae7f-134">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3ae7f-135">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="3ae7f-135">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="3ae7f-136">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="3ae7f-136">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="3ae7f-137">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="3ae7f-137">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="3ae7f-138">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="3ae7f-138">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="3ae7f-139">SDK o entorno de ejecución de actualización de APT</span><span class="sxs-lookup"><span data-stu-id="3ae7f-139">APT update SDK or runtime</span></span>

<span data-ttu-id="3ae7f-140">Cuando hay disponible una nueva versión de revisión para .NET, basta con actualizarla mediante APT con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ae7f-140">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="3ae7f-141">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="3ae7f-141">APT troubleshooting</span></span>

<span data-ttu-id="3ae7f-142">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar APT para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-142">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="3ae7f-143">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="3ae7f-143">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="3ae7f-144">No se puede encontrar el paquete \\ No se han podido instalar algunos paquetes</span><span class="sxs-lookup"><span data-stu-id="3ae7f-144">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="3ae7f-145">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="3ae7f-145">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="3ae7f-146">Snap</span><span class="sxs-lookup"><span data-stu-id="3ae7f-146">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="3ae7f-147">Dependencias</span><span class="sxs-lookup"><span data-stu-id="3ae7f-147">Dependencies</span></span>

<span data-ttu-id="3ae7f-148">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-148">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="3ae7f-149">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="3ae7f-149">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="3ae7f-150">libc6</span><span class="sxs-lookup"><span data-stu-id="3ae7f-150">libc6</span></span>
- <span data-ttu-id="3ae7f-151">libgcc1</span><span class="sxs-lookup"><span data-stu-id="3ae7f-151">libgcc1</span></span>
- <span data-ttu-id="3ae7f-152">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="3ae7f-152">libgssapi-krb5-2</span></span>
- <span data-ttu-id="3ae7f-153">libicu52 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-153">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="3ae7f-154">libicu57 (para 9.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-154">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="3ae7f-155">libicu63 (para 10.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-155">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="3ae7f-156">libicu67 (para 11.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-156">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="3ae7f-157">libssl1.0.0 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-157">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="3ae7f-158">libssl1.1 (para 9.x-11.x)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-158">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="3ae7f-159">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="3ae7f-159">libstdc++6</span></span>
- <span data-ttu-id="3ae7f-160">zlib1g</span><span class="sxs-lookup"><span data-stu-id="3ae7f-160">zlib1g</span></span>

<span data-ttu-id="3ae7f-161">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ae7f-161">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="3ae7f-162">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="3ae7f-162">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="3ae7f-163">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-163">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="3ae7f-164">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="3ae7f-164">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="3ae7f-165">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="3ae7f-165">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="3ae7f-166">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="3ae7f-166">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="3ae7f-167">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ae7f-167">Next steps</span></span>

- [<span data-ttu-id="3ae7f-168">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3ae7f-168">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
