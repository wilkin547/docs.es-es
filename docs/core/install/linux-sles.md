---
title: 'Instalación de .NET en SLES: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en SLES.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 558574116aac2a3c755481069641e81a435a2a43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506886"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a><span data-ttu-id="43afb-103">Instalación del SDK y el entorno de ejecución de .NET en SLES</span><span class="sxs-lookup"><span data-stu-id="43afb-103">Install the .NET SDK or the .NET Runtime on SLES</span></span>

<span data-ttu-id="43afb-104">.NET es compatible con SLES.</span><span class="sxs-lookup"><span data-stu-id="43afb-104">.NET is supported on SLES.</span></span> <span data-ttu-id="43afb-105">En este artículo se describe cómo instalar .NET en SLES.</span><span class="sxs-lookup"><span data-stu-id="43afb-105">This article describes how to install .NET on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="43afb-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="43afb-106">Supported distributions</span></span>

<span data-ttu-id="43afb-107">En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente en SLES 12 SP2 y SLES 15.</span><span class="sxs-lookup"><span data-stu-id="43afb-107">The following table is a list of currently supported .NET releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="43afb-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="43afb-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="43afb-109">El símbolo ✔️ indica que todavía se admite la versión de SLES o de .NET.</span><span class="sxs-lookup"><span data-stu-id="43afb-109">A ✔️ indicates that the version of SLES or .NET is still supported.</span></span>
- <span data-ttu-id="43afb-110">El símbolo ❌ indica que la versión de SLES o de .NET no se admite en esa versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="43afb-110">A ❌ indicates that the version of SLES or .NET isn't supported on that SLES release.</span></span>
- <span data-ttu-id="43afb-111">Si una versión de SLES y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="43afb-111">When both a version of SLES and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="43afb-112">SLES</span><span class="sxs-lookup"><span data-stu-id="43afb-112">SLES</span></span>                   | <span data-ttu-id="43afb-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="43afb-113">.NET Core 2.1</span></span> | <span data-ttu-id="43afb-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="43afb-114">.NET Core 3.1</span></span> | <span data-ttu-id="43afb-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="43afb-115">.NET 5.0</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="43afb-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="43afb-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="43afb-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="43afb-117">✔️ 2.1</span></span>        | <span data-ttu-id="43afb-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="43afb-118">✔️ 3.1</span></span>        | <span data-ttu-id="43afb-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="43afb-119">✔️ 5.0</span></span> |
| <span data-ttu-id="43afb-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="43afb-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="43afb-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="43afb-121">✔️ 2.1</span></span>        | <span data-ttu-id="43afb-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="43afb-122">✔️ 3.1</span></span>        | <span data-ttu-id="43afb-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="43afb-123">✔️ 5.0</span></span> |

<span data-ttu-id="43afb-124">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="43afb-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="43afb-125">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="43afb-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="43afb-126">3.0</span><span class="sxs-lookup"><span data-stu-id="43afb-126">3.0</span></span>
- <span data-ttu-id="43afb-127">2.2</span><span class="sxs-lookup"><span data-stu-id="43afb-127">2.2</span></span>
- <span data-ttu-id="43afb-128">2.0</span><span class="sxs-lookup"><span data-stu-id="43afb-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="43afb-129">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="43afb-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="43afb-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="43afb-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="43afb-131">Actualmente, el paquete de instalación del repositorio de Microsoft de SLES 15 instala el archivo *microsoft-prod.repo* en el directorio incorrecto, lo que impide que zypper pueda encontrar los paquetes de .NET.</span><span class="sxs-lookup"><span data-stu-id="43afb-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET packages.</span></span> <span data-ttu-id="43afb-132">Para corregir este problema, cree un symlink en el directorio apropiado.</span><span class="sxs-lookup"><span data-stu-id="43afb-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="43afb-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="43afb-133">SLES 12 ✔️</span></span>

<span data-ttu-id="43afb-134">.NET necesita SP2 como mínimo para la familia SLES 12.</span><span class="sxs-lookup"><span data-stu-id="43afb-134">.NET requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="43afb-135">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="43afb-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="43afb-136">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="43afb-136">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="43afb-137">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="43afb-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="43afb-138">Dependencias</span><span class="sxs-lookup"><span data-stu-id="43afb-138">Dependencies</span></span>

<span data-ttu-id="43afb-139">Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="43afb-139">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="43afb-140">Pero si instala manualmente .NET o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:</span><span class="sxs-lookup"><span data-stu-id="43afb-140">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="43afb-141">krb5</span><span class="sxs-lookup"><span data-stu-id="43afb-141">krb5</span></span>
- <span data-ttu-id="43afb-142">libicu</span><span class="sxs-lookup"><span data-stu-id="43afb-142">libicu</span></span>
- <span data-ttu-id="43afb-143">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="43afb-143">libopenssl1_1</span></span>

<span data-ttu-id="43afb-144">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="43afb-144">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="43afb-145">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="43afb-145">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="43afb-146">En el caso de las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="43afb-146">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="43afb-147">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="43afb-147">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="43afb-148">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="43afb-148">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="43afb-149">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="43afb-149">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="43afb-150">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="43afb-150">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="43afb-151">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="43afb-151">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="43afb-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="43afb-152">Next steps</span></span>

- [<span data-ttu-id="43afb-153">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="43afb-153">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
