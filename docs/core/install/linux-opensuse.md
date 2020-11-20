---
title: 'Instalación de .NET en openSUSE: .NET'
description: En este artículo se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 17012f3689e5834fd1629946767e931cb22a2c1b
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506910"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="21d89-103">Instalación del SDK y el entorno de ejecución de .NET en openSUSE</span><span class="sxs-lookup"><span data-stu-id="21d89-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="21d89-104">.NET es compatible con openSUSE.</span><span class="sxs-lookup"><span data-stu-id="21d89-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="21d89-105">En este artículo se describe cómo instalar .NET en openSUSE.</span><span class="sxs-lookup"><span data-stu-id="21d89-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="21d89-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="21d89-106">Supported distributions</span></span>

<span data-ttu-id="21d89-107">En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="21d89-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="21d89-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="21d89-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="21d89-109">El símbolo ✔️ indica que todavía se admite la versión de openSUSE o de .NET.</span><span class="sxs-lookup"><span data-stu-id="21d89-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="21d89-110">El símbolo ❌ indica que la versión de openSUSE o de .NET no se admite en esa versión de openSUSE.</span><span class="sxs-lookup"><span data-stu-id="21d89-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="21d89-111">Si una versión de openSUSE y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="21d89-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="21d89-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="21d89-112">openSUSE</span></span>                   | <span data-ttu-id="21d89-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21d89-113">.NET Core 2.1</span></span> | <span data-ttu-id="21d89-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="21d89-114">.NET Core 3.1</span></span> | <span data-ttu-id="21d89-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21d89-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="21d89-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="21d89-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="21d89-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="21d89-117">✔️ 2.1</span></span>        | <span data-ttu-id="21d89-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="21d89-118">✔️ 3.1</span></span>        | <span data-ttu-id="21d89-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="21d89-119">✔️ 5.0</span></span> |

<span data-ttu-id="21d89-120">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="21d89-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="21d89-121">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="21d89-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="21d89-122">3.0</span><span class="sxs-lookup"><span data-stu-id="21d89-122">3.0</span></span>
- <span data-ttu-id="21d89-123">2.2</span><span class="sxs-lookup"><span data-stu-id="21d89-123">2.2</span></span>
- <span data-ttu-id="21d89-124">2.0</span><span class="sxs-lookup"><span data-stu-id="21d89-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="21d89-125">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="21d89-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="21d89-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="21d89-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="21d89-127">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="21d89-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="21d89-128">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="21d89-128">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="21d89-129">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="21d89-129">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="21d89-130">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="21d89-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="21d89-131">Snap</span><span class="sxs-lookup"><span data-stu-id="21d89-131">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="21d89-132">Dependencias</span><span class="sxs-lookup"><span data-stu-id="21d89-132">Dependencies</span></span>

<span data-ttu-id="21d89-133">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="21d89-133">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="21d89-134">Pero si instala manualmente .NET o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="21d89-134">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="21d89-135">krb5</span><span class="sxs-lookup"><span data-stu-id="21d89-135">krb5</span></span>
- <span data-ttu-id="21d89-136">libicu</span><span class="sxs-lookup"><span data-stu-id="21d89-136">libicu</span></span>
- <span data-ttu-id="21d89-137">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="21d89-137">libopenssl1_0_0</span></span>

<span data-ttu-id="21d89-138">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="21d89-138">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="21d89-139">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="21d89-139">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="21d89-140">En el caso de las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="21d89-140">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="21d89-141">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="21d89-141">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="21d89-142">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="21d89-142">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="21d89-143">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="21d89-143">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="21d89-144">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="21d89-144">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="21d89-145">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="21d89-145">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="21d89-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="21d89-146">Next steps</span></span>

- [<span data-ttu-id="21d89-147">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="21d89-147">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
