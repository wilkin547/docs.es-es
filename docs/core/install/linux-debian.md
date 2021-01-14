---
title: 'Instalación de .NET en Debian: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Debian.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 913d8bffdd6c0b5e88a70dae0ec4c8d732e80cc0
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970842"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="a12c9-103">Instalación del SDK y el entorno de ejecución de .NET en Debian</span><span class="sxs-lookup"><span data-stu-id="a12c9-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="a12c9-104">En este artículo se describe cómo instalar .NET en Debian.</span><span class="sxs-lookup"><span data-stu-id="a12c9-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="a12c9-105">Cuando una versión de Debian no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="a12c9-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="a12c9-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="a12c9-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a12c9-107">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="a12c9-107">Supported distributions</span></span>

<span data-ttu-id="a12c9-108">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Debian en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="a12c9-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="a12c9-109">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="a12c9-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="a12c9-110">El símbolo ✔️ indica que todavía se admite la versión de Debian o de .NET.</span><span class="sxs-lookup"><span data-stu-id="a12c9-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="a12c9-111">El símbolo ❌ indica que la versión de Debian o de .NET no se admite en esa versión de Debian.</span><span class="sxs-lookup"><span data-stu-id="a12c9-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="a12c9-112">Si una versión de Debian y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="a12c9-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a12c9-113">Debian</span><span class="sxs-lookup"><span data-stu-id="a12c9-113">Debian</span></span>                   | <span data-ttu-id="a12c9-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-114">.NET Core 2.1</span></span> | <span data-ttu-id="a12c9-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-115">.NET Core 3.1</span></span> | <span data-ttu-id="a12c9-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a12c9-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="a12c9-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="a12c9-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-118">✔️ 2.1</span></span>        | <span data-ttu-id="a12c9-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-119">✔️ 3.1</span></span>        | <span data-ttu-id="a12c9-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-120">✔️ 5.0</span></span> |
| <span data-ttu-id="a12c9-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="a12c9-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="a12c9-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-122">✔️ 2.1</span></span>        | <span data-ttu-id="a12c9-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-123">✔️ 3.1</span></span>        | <span data-ttu-id="a12c9-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-124">✔️ 5.0</span></span> |
| <span data-ttu-id="a12c9-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="a12c9-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="a12c9-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-126">✔️ 2.1</span></span>        | <span data-ttu-id="a12c9-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="a12c9-127">❌ 3.1</span></span>        | <span data-ttu-id="a12c9-128">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-128">❌ 5.0</span></span> |

<span data-ttu-id="a12c9-129">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="a12c9-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a12c9-130">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="a12c9-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a12c9-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-131">3.0</span></span>
- <span data-ttu-id="a12c9-132">2.2</span><span class="sxs-lookup"><span data-stu-id="a12c9-132">2.2</span></span>
- <span data-ttu-id="a12c9-133">2.0</span><span class="sxs-lookup"><span data-stu-id="a12c9-133">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="a12c9-134">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="a12c9-134">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="debian-10-"></a><span data-ttu-id="a12c9-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="a12c9-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="a12c9-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="a12c9-136">Debian 9 ✔️</span></span>

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

## <a name="debian-8-"></a><span data-ttu-id="a12c9-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="a12c9-137">Debian 8 ❌</span></span>

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

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a12c9-138">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="a12c9-138">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="a12c9-139">Uso de APT para actualizar .NET</span><span class="sxs-lookup"><span data-stu-id="a12c9-139">Use APT to update .NET</span></span>

<span data-ttu-id="a12c9-140">Cuando hay disponible una nueva versión de revisión para .NET, basta con actualizarla mediante APT con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a12c9-140">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="a12c9-141">Solución de problemas de APT</span><span class="sxs-lookup"><span data-stu-id="a12c9-141">APT troubleshooting</span></span>

<span data-ttu-id="a12c9-142">En esta sección se proporciona información sobre los errores comunes que puede recibir al usar APT para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="a12c9-142">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a12c9-143">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="a12c9-143">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="a12c9-144">No se puede encontrar el paquete \\ No se han podido instalar algunos paquetes</span><span class="sxs-lookup"><span data-stu-id="a12c9-144">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="a12c9-145">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="a12c9-145">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="a12c9-146">Dependencias</span><span class="sxs-lookup"><span data-stu-id="a12c9-146">Dependencies</span></span>

<span data-ttu-id="a12c9-147">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a12c9-147">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="a12c9-148">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="a12c9-148">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="a12c9-149">libc6</span><span class="sxs-lookup"><span data-stu-id="a12c9-149">libc6</span></span>
- <span data-ttu-id="a12c9-150">libgcc1</span><span class="sxs-lookup"><span data-stu-id="a12c9-150">libgcc1</span></span>
- <span data-ttu-id="a12c9-151">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="a12c9-151">libgssapi-krb5-2</span></span>
- <span data-ttu-id="a12c9-152">libicu52 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-152">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="a12c9-153">libicu57 (para 9.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-153">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="a12c9-154">libicu63 (para 10.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-154">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="a12c9-155">libicu67 (para 11.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-155">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="a12c9-156">libssl1.0.0 (para 8.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-156">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="a12c9-157">libssl1.1 (para 9.x-11.x)</span><span class="sxs-lookup"><span data-stu-id="a12c9-157">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="a12c9-158">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="a12c9-158">libstdc++6</span></span>
- <span data-ttu-id="a12c9-159">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a12c9-159">zlib1g</span></span>

<span data-ttu-id="a12c9-160">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="a12c9-160">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a12c9-161">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="a12c9-161">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="a12c9-162">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="a12c9-162">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="a12c9-163">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="a12c9-163">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a12c9-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a12c9-164">Next steps</span></span>

- [<span data-ttu-id="a12c9-165">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="a12c9-165">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="a12c9-166">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a12c9-166">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
