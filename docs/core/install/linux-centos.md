---
title: 'Instalación de .NET en CentOS: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en CentOS.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 2c3453c79a1dc31f01577bc0c1b9e320eb307c0a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851684"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="17fb5-103">Instalación del SDK y el entorno de ejecución de .NET en CentOS</span><span class="sxs-lookup"><span data-stu-id="17fb5-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="17fb5-104">.NET es compatible con CentOS.</span><span class="sxs-lookup"><span data-stu-id="17fb5-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="17fb5-105">En este artículo se describe cómo instalar .NET en CentOS.</span><span class="sxs-lookup"><span data-stu-id="17fb5-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="17fb5-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="17fb5-106">Supported distributions</span></span>

<span data-ttu-id="17fb5-107">En la tabla siguiente se muestra una lista de las versiones de .NET admitidas actualmente en CentOS 7 y CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="17fb5-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="17fb5-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="17fb5-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="17fb5-109">El símbolo ✔️ indica que todavía se admite la versión de CentOS o de .NET.</span><span class="sxs-lookup"><span data-stu-id="17fb5-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="17fb5-110">El símbolo ❌ indica que la versión de CentOS o de .NET no se admite en esa versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="17fb5-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="17fb5-111">Si una versión de CentOS y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="17fb5-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="17fb5-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="17fb5-112">CentOS</span></span>                   | <span data-ttu-id="17fb5-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-113">.NET Core 2.1</span></span> | <span data-ttu-id="17fb5-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-114">.NET Core 3.1</span></span> | <span data-ttu-id="17fb5-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="17fb5-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="17fb5-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="17fb5-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="17fb5-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-117">✔️ 2.1</span></span>        | <span data-ttu-id="17fb5-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-118">✔️ 3.1</span></span>        | <span data-ttu-id="17fb5-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="17fb5-119">✔️ 5.0</span></span> |
| <span data-ttu-id="17fb5-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="17fb5-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="17fb5-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-121">✔️ 2.1</span></span>        | <span data-ttu-id="17fb5-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="17fb5-122">✔️ 3.1</span></span>        | <span data-ttu-id="17fb5-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="17fb5-123">✔️ 5.0</span></span> |

<span data-ttu-id="17fb5-124">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="17fb5-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="17fb5-125">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="17fb5-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="17fb5-126">3.0</span><span class="sxs-lookup"><span data-stu-id="17fb5-126">3.0</span></span>
- <span data-ttu-id="17fb5-127">2.2</span><span class="sxs-lookup"><span data-stu-id="17fb5-127">2.2</span></span>
- <span data-ttu-id="17fb5-128">2.0</span><span class="sxs-lookup"><span data-stu-id="17fb5-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="17fb5-129">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="17fb5-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="17fb5-130">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="17fb5-130">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="17fb5-131">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="17fb5-131">CentOS 8 ✔️</span></span>

<span data-ttu-id="17fb5-132">.NET 5.0 está disponible en los repositorios de paquetes predeterminados de CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="17fb5-132">.NET 5.0 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="17fb5-133">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="17fb5-133">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="17fb5-134">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="17fb5-134">Troubleshoot the package manager</span></span>

<span data-ttu-id="17fb5-135">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="17fb5-135">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="17fb5-136">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="17fb5-136">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="17fb5-137">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="17fb5-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="17fb5-138">Snap</span><span class="sxs-lookup"><span data-stu-id="17fb5-138">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="17fb5-139">Dependencias</span><span class="sxs-lookup"><span data-stu-id="17fb5-139">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="17fb5-140">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="17fb5-140">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="17fb5-141">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="17fb5-141">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="17fb5-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="17fb5-142">Next steps</span></span>

- [<span data-ttu-id="17fb5-143">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="17fb5-143">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
