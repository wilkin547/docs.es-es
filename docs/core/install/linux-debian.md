---
title: 'Instalación de .NET Core en Debian: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: d4a54a8a5354a1430141d2c06d4aa90dbafc3edf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134944"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="aca01-103">Instalación del SDK de .NET Core o de .NET Core Runtime en Debian</span><span class="sxs-lookup"><span data-stu-id="aca01-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="aca01-104">En este artículo se describe cómo instalar .NET Core en Debian.</span><span class="sxs-lookup"><span data-stu-id="aca01-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="aca01-105">Cuando una versión de Debian no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="aca01-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="aca01-106">Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="aca01-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="aca01-107">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="aca01-107">Supported distributions</span></span>

<span data-ttu-id="aca01-108">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Debian en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="aca01-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="aca01-109">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="aca01-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="aca01-110">Una ✔️ indica que todavía se admite la versión de Debian o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aca01-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="aca01-111">Una ❌ indica que la versión de Debian o de .NET Core no se admite en esa versión de Debian.</span><span class="sxs-lookup"><span data-stu-id="aca01-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="aca01-112">Cuando una versión de Debian y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="aca01-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="aca01-113">Debian</span><span class="sxs-lookup"><span data-stu-id="aca01-113">Debian</span></span>                   | <span data-ttu-id="aca01-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="aca01-114">.NET Core 2.1</span></span> | <span data-ttu-id="aca01-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="aca01-115">.NET Core 3.1</span></span> | <span data-ttu-id="aca01-116">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="aca01-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="aca01-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="aca01-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="aca01-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aca01-118">✔️ 2.1</span></span>        | <span data-ttu-id="aca01-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aca01-119">✔️ 3.1</span></span>        | <span data-ttu-id="aca01-120">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aca01-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aca01-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="aca01-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="aca01-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aca01-122">✔️ 2.1</span></span>        | <span data-ttu-id="aca01-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aca01-123">✔️ 3.1</span></span>        | <span data-ttu-id="aca01-124">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aca01-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aca01-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="aca01-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="aca01-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aca01-126">✔️ 2.1</span></span>        | <span data-ttu-id="aca01-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="aca01-127">❌ 3.1</span></span>        | <span data-ttu-id="aca01-128">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aca01-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="aca01-129">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="aca01-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="aca01-130">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="aca01-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="aca01-131">3.0</span><span class="sxs-lookup"><span data-stu-id="aca01-131">3.0</span></span>
- <span data-ttu-id="aca01-132">2.2</span><span class="sxs-lookup"><span data-stu-id="aca01-132">2.2</span></span>
- <span data-ttu-id="aca01-133">2.0</span><span class="sxs-lookup"><span data-stu-id="aca01-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="aca01-134">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="aca01-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="aca01-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="aca01-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="aca01-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="aca01-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="aca01-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="aca01-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="aca01-138">SDK o entorno de ejecución de actualización de APT</span><span class="sxs-lookup"><span data-stu-id="aca01-138">APT update SDK or runtime</span></span>

<span data-ttu-id="aca01-139">Cuando hay disponible una nueva versión de revisión para .NET Core, basta con que la actualice mediante APT con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="aca01-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="aca01-140">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="aca01-140">APT troubleshooting</span></span>

<span data-ttu-id="aca01-141">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar ATP para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aca01-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="aca01-142">No se puede encontrar el paquete \\ No se han podido instalar algunos paquetes</span><span class="sxs-lookup"><span data-stu-id="aca01-142">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="aca01-143">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="aca01-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="aca01-144">Snap</span><span class="sxs-lookup"><span data-stu-id="aca01-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="aca01-145">Dependencias</span><span class="sxs-lookup"><span data-stu-id="aca01-145">Dependencies</span></span>

<span data-ttu-id="aca01-146">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="aca01-146">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="aca01-147">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="aca01-147">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="aca01-148">libc6</span><span class="sxs-lookup"><span data-stu-id="aca01-148">libc6</span></span>
- <span data-ttu-id="aca01-149">libgcc1</span><span class="sxs-lookup"><span data-stu-id="aca01-149">libgcc1</span></span>
- <span data-ttu-id="aca01-150">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="aca01-150">libgssapi-krb5-2</span></span>
- <span data-ttu-id="aca01-151">libicu52 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-151">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="aca01-152">libicu57 (para 9.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-152">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="aca01-153">libicu63 (para 10.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-153">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="aca01-154">libicu67 (para 11.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-154">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="aca01-155">libssl1.0.0 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-155">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="aca01-156">libssl1.1 (para 9.x-11.x)</span><span class="sxs-lookup"><span data-stu-id="aca01-156">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="aca01-157">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="aca01-157">libstdc++6</span></span>
- <span data-ttu-id="aca01-158">zlib1g</span><span class="sxs-lookup"><span data-stu-id="aca01-158">zlib1g</span></span>

<span data-ttu-id="aca01-159">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca01-159">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="aca01-160">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="aca01-160">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="aca01-161">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="aca01-161">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="aca01-162">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="aca01-162">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="aca01-163">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="aca01-163">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="aca01-164">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="aca01-164">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="aca01-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="aca01-165">Next steps</span></span>

- [<span data-ttu-id="aca01-166">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="aca01-166">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
