---
title: 'Instalación de .NET Core en openSUSE: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 24f0a5b5278d038c2f941b0984efcacd91dcbe31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619473"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="07a09-103">Instalación del SDK de .NET Core o de .NET Core Runtime en openSUSE</span><span class="sxs-lookup"><span data-stu-id="07a09-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="07a09-104">.NET Core es compatible con openSUSE.</span><span class="sxs-lookup"><span data-stu-id="07a09-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="07a09-105">En este artículo se describe cómo instalar .NET Core en openSUSE.</span><span class="sxs-lookup"><span data-stu-id="07a09-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="07a09-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="07a09-106">Supported distributions</span></span>

<span data-ttu-id="07a09-107">En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="07a09-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="07a09-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="07a09-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="07a09-109">Una ✔️ indica que todavía se admite la versión de openSUSE o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07a09-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="07a09-110">Una ❌ indica que la versión de openSUSE o de .NET Core no se admite en esa versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="07a09-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="07a09-111">Cuando una versión de openSUSE y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="07a09-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="07a09-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="07a09-112">openSUSE</span></span>                   | <span data-ttu-id="07a09-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="07a09-113">.NET Core 2.1</span></span> | <span data-ttu-id="07a09-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="07a09-114">.NET Core 3.1</span></span> | <span data-ttu-id="07a09-115">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="07a09-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="07a09-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="07a09-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="07a09-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="07a09-117">✔️ 2.1</span></span>        | <span data-ttu-id="07a09-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="07a09-118">✔️ 3.1</span></span>        | <span data-ttu-id="07a09-119">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="07a09-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="07a09-120">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="07a09-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="07a09-121">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="07a09-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="07a09-122">3.0</span><span class="sxs-lookup"><span data-stu-id="07a09-122">3.0</span></span>
- <span data-ttu-id="07a09-123">2.2</span><span class="sxs-lookup"><span data-stu-id="07a09-123">2.2</span></span>
- <span data-ttu-id="07a09-124">2.0</span><span class="sxs-lookup"><span data-stu-id="07a09-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="07a09-125">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="07a09-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="07a09-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="07a09-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="07a09-127">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="07a09-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="07a09-128">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07a09-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="07a09-129">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="07a09-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="07a09-130">Snap</span><span class="sxs-lookup"><span data-stu-id="07a09-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="07a09-131">Dependencias</span><span class="sxs-lookup"><span data-stu-id="07a09-131">Dependencies</span></span>

<span data-ttu-id="07a09-132">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="07a09-132">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="07a09-133">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="07a09-133">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="07a09-134">krb5</span><span class="sxs-lookup"><span data-stu-id="07a09-134">krb5</span></span>
- <span data-ttu-id="07a09-135">libicu</span><span class="sxs-lookup"><span data-stu-id="07a09-135">libicu</span></span>
- <span data-ttu-id="07a09-136">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="07a09-136">libopenssl1_0_0</span></span>

<span data-ttu-id="07a09-137">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="07a09-137">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="07a09-138">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="07a09-138">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="07a09-139">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="07a09-139">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="07a09-140">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="07a09-140">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="07a09-141">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="07a09-141">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="07a09-142">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="07a09-142">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="07a09-143">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="07a09-143">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="07a09-144">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="07a09-144">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="07a09-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="07a09-145">Next steps</span></span>

- [<span data-ttu-id="07a09-146">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="07a09-146">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
