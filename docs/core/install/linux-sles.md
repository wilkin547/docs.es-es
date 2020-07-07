---
title: 'Instalación de .NET Core en SLES: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en SLES.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 8f64efcc8206b47855871104e5b6914570c06da0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619421"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="3ed18-103">Instalación del SDK o de .NET Core Runtime en SLES</span><span class="sxs-lookup"><span data-stu-id="3ed18-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="3ed18-104">.NET Core es compatible con SLES.</span><span class="sxs-lookup"><span data-stu-id="3ed18-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="3ed18-105">En este artículo se describe cómo instalar .NET Core en SLES.</span><span class="sxs-lookup"><span data-stu-id="3ed18-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="3ed18-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="3ed18-106">Supported distributions</span></span>

<span data-ttu-id="3ed18-107">En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente en SLES 12 SP 2 y SLES 15.</span><span class="sxs-lookup"><span data-stu-id="3ed18-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="3ed18-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="3ed18-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="3ed18-109">Una ✔️ indica que todavía se admite la versión de SLES o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ed18-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="3ed18-110">Una ❌ indica que la versión de SLES o de .NET Core no se admite en esa versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="3ed18-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="3ed18-111">Cuando una versión de SLES y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="3ed18-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="3ed18-112">SLES</span><span class="sxs-lookup"><span data-stu-id="3ed18-112">SLES</span></span>                   | <span data-ttu-id="3ed18-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-113">.NET Core 2.1</span></span> | <span data-ttu-id="3ed18-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-114">.NET Core 3.1</span></span> | <span data-ttu-id="3ed18-115">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="3ed18-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="3ed18-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="3ed18-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="3ed18-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-117">✔️ 2.1</span></span>        | <span data-ttu-id="3ed18-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-118">✔️ 3.1</span></span>        | <span data-ttu-id="3ed18-119">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ed18-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="3ed18-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="3ed18-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="3ed18-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-121">✔️ 2.1</span></span>        | <span data-ttu-id="3ed18-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3ed18-122">✔️ 3.1</span></span>        | <span data-ttu-id="3ed18-123">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ed18-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="3ed18-124">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="3ed18-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="3ed18-125">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="3ed18-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="3ed18-126">3.0</span><span class="sxs-lookup"><span data-stu-id="3ed18-126">3.0</span></span>
- <span data-ttu-id="3ed18-127">2.2</span><span class="sxs-lookup"><span data-stu-id="3ed18-127">2.2</span></span>
- <span data-ttu-id="3ed18-128">2.0</span><span class="sxs-lookup"><span data-stu-id="3ed18-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3ed18-129">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="3ed18-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="3ed18-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="3ed18-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="3ed18-131">Actualmente, el paquete de instalación del repositorio de Microsoft de SLES 15 instala el archivo *microsoft-prod.repo* en el directorio incorrecto, lo que impide que zypper pueda encontrar los paquetes de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ed18-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="3ed18-132">Para corregir este problema, cree un symlink en el directorio apropiado.</span><span class="sxs-lookup"><span data-stu-id="3ed18-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="3ed18-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="3ed18-133">SLES 12 ✔️</span></span>

<span data-ttu-id="3ed18-134">.NET Core necesita SP2 como mínimo para la familia SLES 12.</span><span class="sxs-lookup"><span data-stu-id="3ed18-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="3ed18-135">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="3ed18-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="3ed18-136">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ed18-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="3ed18-137">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="3ed18-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="3ed18-138">Dependencias</span><span class="sxs-lookup"><span data-stu-id="3ed18-138">Dependencies</span></span>

<span data-ttu-id="3ed18-139">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3ed18-139">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="3ed18-140">Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="3ed18-140">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="3ed18-141">krb5</span><span class="sxs-lookup"><span data-stu-id="3ed18-141">krb5</span></span>
- <span data-ttu-id="3ed18-142">libicu</span><span class="sxs-lookup"><span data-stu-id="3ed18-142">libicu</span></span>
- <span data-ttu-id="3ed18-143">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="3ed18-143">libopenssl1_1</span></span>

<span data-ttu-id="3ed18-144">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="3ed18-144">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="3ed18-145">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="3ed18-145">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="3ed18-146">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ed18-146">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="3ed18-147">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="3ed18-147">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="3ed18-148">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="3ed18-148">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="3ed18-149">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="3ed18-149">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="3ed18-150">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="3ed18-150">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="3ed18-151">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="3ed18-151">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="3ed18-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ed18-152">Next steps</span></span>

- [<span data-ttu-id="3ed18-153">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3ed18-153">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
