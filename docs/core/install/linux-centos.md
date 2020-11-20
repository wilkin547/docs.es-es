---
title: 'Instalación de .NET en CentOS: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en CentOS.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b2ed62d024c6f0d78a4ec64693f1dafeabd8f47b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594637"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="b8057-103">Instalación del SDK y el entorno de ejecución de .NET en CentOS</span><span class="sxs-lookup"><span data-stu-id="b8057-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="b8057-104">.NET es compatible con CentOS.</span><span class="sxs-lookup"><span data-stu-id="b8057-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="b8057-105">En este artículo se describe cómo instalar .NET en CentOS.</span><span class="sxs-lookup"><span data-stu-id="b8057-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b8057-106">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="b8057-106">Supported distributions</span></span>

<span data-ttu-id="b8057-107">En la tabla siguiente se muestra una lista de las versiones de .NET admitidas actualmente en CentOS 7 y CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="b8057-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="b8057-108">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="b8057-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="b8057-109">El símbolo ✔️ indica que todavía se admite la versión de CentOS o de .NET.</span><span class="sxs-lookup"><span data-stu-id="b8057-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="b8057-110">El símbolo ❌ indica que la versión de CentOS o de .NET no se admite en esa versión de CentOS.</span><span class="sxs-lookup"><span data-stu-id="b8057-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="b8057-111">Si una versión de CentOS y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="b8057-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="b8057-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="b8057-112">CentOS</span></span>                   | <span data-ttu-id="b8057-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b8057-113">.NET Core 2.1</span></span> | <span data-ttu-id="b8057-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b8057-114">.NET Core 3.1</span></span> | <span data-ttu-id="b8057-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="b8057-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b8057-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="b8057-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="b8057-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b8057-117">✔️ 2.1</span></span>        | <span data-ttu-id="b8057-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b8057-118">✔️ 3.1</span></span>        | <span data-ttu-id="b8057-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="b8057-119">✔️ 5.0</span></span> |
| <span data-ttu-id="b8057-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="b8057-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="b8057-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b8057-121">✔️ 2.1</span></span>        | <span data-ttu-id="b8057-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b8057-122">✔️ 3.1</span></span>        | <span data-ttu-id="b8057-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="b8057-123">✔️ 5.0</span></span> |

<span data-ttu-id="b8057-124">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="b8057-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="b8057-125">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="b8057-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b8057-126">3.0</span><span class="sxs-lookup"><span data-stu-id="b8057-126">3.0</span></span>
- <span data-ttu-id="b8057-127">2.2</span><span class="sxs-lookup"><span data-stu-id="b8057-127">2.2</span></span>
- <span data-ttu-id="b8057-128">2.0</span><span class="sxs-lookup"><span data-stu-id="b8057-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b8057-129">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="b8057-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="b8057-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="b8057-130">CentOS 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="b8057-131">.NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados, pero .NET Core 3.1 sí.</span><span class="sxs-lookup"><span data-stu-id="b8057-131">.NET 5.0 isn't yet available in the default package repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="b8057-132">Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="b8057-132">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="b8057-133">Las siguientes instrucciones son para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="b8057-133">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/8/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="b8057-134">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="b8057-134">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b8057-135">Solución de problemas del administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="b8057-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="b8057-136">En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="b8057-136">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="b8057-137">No se puede encontrar el paquete</span><span class="sxs-lookup"><span data-stu-id="b8057-137">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="b8057-138">No se pudo capturar el elemento</span><span class="sxs-lookup"><span data-stu-id="b8057-138">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="b8057-139">Snap</span><span class="sxs-lookup"><span data-stu-id="b8057-139">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b8057-140">Dependencias</span><span class="sxs-lookup"><span data-stu-id="b8057-140">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="b8057-141">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="b8057-141">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b8057-142">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="b8057-142">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b8057-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b8057-143">Next steps</span></span>

- [<span data-ttu-id="b8057-144">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b8057-144">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
