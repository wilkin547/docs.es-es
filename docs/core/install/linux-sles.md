---
title: 'Instalación de .NET Core en SLES: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en SLES.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 9816e1f0253be58dc04c1302f334a7ea0b810810
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768408"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="b4fda-103">Instalación del SDK o de .NET Core Runtime en SLES</span><span class="sxs-lookup"><span data-stu-id="b4fda-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="b4fda-104">.NET Core es compatible con SLES.</span><span class="sxs-lookup"><span data-stu-id="b4fda-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="b4fda-105">En este artículo se describe cómo instalar .NET Core en SLES.</span><span class="sxs-lookup"><span data-stu-id="b4fda-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b4fda-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="b4fda-106">Supported distributions</span></span>

<span data-ttu-id="b4fda-107">En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente en SLES 12 SP 2 y SLES 15.</span><span class="sxs-lookup"><span data-stu-id="b4fda-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="b4fda-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="b4fda-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="b4fda-109">Una ✔️ indica que todavía se admite la versión de SLES o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4fda-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="b4fda-110">Una ❌ indica que la versión de SLES o de .NET Core no se admite en esa versión de SLES.</span><span class="sxs-lookup"><span data-stu-id="b4fda-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="b4fda-111">Cuando una versión de SLES y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="b4fda-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b4fda-112">SLES</span><span class="sxs-lookup"><span data-stu-id="b4fda-112">SLES</span></span>                   | <span data-ttu-id="b4fda-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-113">.NET Core 2.1</span></span> | <span data-ttu-id="b4fda-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-114">.NET Core 3.1</span></span> | <span data-ttu-id="b4fda-115">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="b4fda-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b4fda-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="b4fda-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="b4fda-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-117">✔️ 2.1</span></span>        | <span data-ttu-id="b4fda-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-118">✔️ 3.1</span></span>        | <span data-ttu-id="b4fda-119">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b4fda-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b4fda-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="b4fda-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="b4fda-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-121">✔️ 2.1</span></span>        | <span data-ttu-id="b4fda-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b4fda-122">✔️ 3.1</span></span>        | <span data-ttu-id="b4fda-123">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b4fda-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="b4fda-124">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="b4fda-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b4fda-125">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="b4fda-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b4fda-126">3.0</span><span class="sxs-lookup"><span data-stu-id="b4fda-126">3.0</span></span>
- <span data-ttu-id="b4fda-127">2.2</span><span class="sxs-lookup"><span data-stu-id="b4fda-127">2.2</span></span>
- <span data-ttu-id="b4fda-128">2.0</span><span class="sxs-lookup"><span data-stu-id="b4fda-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b4fda-129">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="b4fda-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="b4fda-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="b4fda-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="b4fda-131">Actualmente, el paquete de instalación del repositorio de Microsoft de SLES 15 instala el archivo *microsoft-prod.repo* en el directorio incorrecto, lo que impide que zypper pueda encontrar los paquetes de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4fda-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="b4fda-132">Para corregir este problema, cree un symlink en el directorio apropiado.</span><span class="sxs-lookup"><span data-stu-id="b4fda-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="b4fda-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="b4fda-133">SLES 12 ✔️</span></span>

<span data-ttu-id="b4fda-134">.NET Core necesita SP2 como mínimo para la familia SLES 12.</span><span class="sxs-lookup"><span data-stu-id="b4fda-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b4fda-135">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="b4fda-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="b4fda-136">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4fda-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="b4fda-137">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="b4fda-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="b4fda-138">Dependencias</span><span class="sxs-lookup"><span data-stu-id="b4fda-138">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="b4fda-139">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="b4fda-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b4fda-140">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="b4fda-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b4fda-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b4fda-141">Next steps</span></span>

- [<span data-ttu-id="b4fda-142">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b4fda-142">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
