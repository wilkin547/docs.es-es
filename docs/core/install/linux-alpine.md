---
title: 'Instalación de .NET en Alpine: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Alpine.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506834"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="085d1-103">Instalación del SDK y el entorno de ejecución de .NET en Alpine</span><span class="sxs-lookup"><span data-stu-id="085d1-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="085d1-104">En este artículo se describe cómo instalar .NET en Alpine.</span><span class="sxs-lookup"><span data-stu-id="085d1-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="085d1-105">Cuando una versión de Alpine no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="085d1-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="085d1-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="085d1-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="085d1-107">No hay instaladores para Alpine.</span><span class="sxs-lookup"><span data-stu-id="085d1-107">There are no installers for Alpine.</span></span> <span data-ttu-id="085d1-108">Debe usar el [script de instalación](#scripted-install) o seguir las instrucciones de [instalación manual](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="085d1-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="085d1-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="085d1-109">Supported distributions</span></span>

<span data-ttu-id="085d1-110">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Alpine en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="085d1-110">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="085d1-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="085d1-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="085d1-112">El símbolo ✔️ indica que todavía se admite la versión de Alpine o de .NET.</span><span class="sxs-lookup"><span data-stu-id="085d1-112">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="085d1-113">El símbolo ❌ indica que la versión de Alpine o de .NET no se admite en esa versión de Alpine.</span><span class="sxs-lookup"><span data-stu-id="085d1-113">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="085d1-114">Si una versión de Alpine y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="085d1-114">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="085d1-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="085d1-115">Alpine</span></span>  | <span data-ttu-id="085d1-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-116">.NET Core 2.1</span></span> | <span data-ttu-id="085d1-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-117">.NET Core 3.1</span></span> | <span data-ttu-id="085d1-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-118">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="085d1-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="085d1-119">✔️ 3.12</span></span> | <span data-ttu-id="085d1-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-120">✔️ 2.1</span></span>        | <span data-ttu-id="085d1-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-121">✔️ 3.1</span></span>        | <span data-ttu-id="085d1-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-122">✔️ 5.0</span></span> |
| <span data-ttu-id="085d1-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="085d1-123">✔️ 3.11</span></span> | <span data-ttu-id="085d1-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-124">✔️ 2.1</span></span>        | <span data-ttu-id="085d1-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-125">✔️ 3.1</span></span>        | <span data-ttu-id="085d1-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-126">✔️ 5.0</span></span> |
| <span data-ttu-id="085d1-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="085d1-127">✔️ 3.10</span></span> | <span data-ttu-id="085d1-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-128">✔️ 2.1</span></span>        | <span data-ttu-id="085d1-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-129">✔️ 3.1</span></span>        | <span data-ttu-id="085d1-130">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-130">❌ 5.0</span></span> |
| <span data-ttu-id="085d1-131">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="085d1-131">❌ 3.9</span></span>  | <span data-ttu-id="085d1-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-132">✔️ 2.1</span></span>        | <span data-ttu-id="085d1-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-133">✔️ 3.1</span></span>        | <span data-ttu-id="085d1-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-134">❌ 5.0</span></span> |
| <span data-ttu-id="085d1-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="085d1-135">❌ 3.8</span></span>  | <span data-ttu-id="085d1-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="085d1-136">✔️ 2.1</span></span>        | <span data-ttu-id="085d1-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="085d1-137">✔️ 3.1</span></span>        | <span data-ttu-id="085d1-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="085d1-138">❌ 5.0</span></span> |

<span data-ttu-id="085d1-139">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="085d1-139">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="085d1-140">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="085d1-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="085d1-141">3.0</span><span class="sxs-lookup"><span data-stu-id="085d1-141">3.0</span></span>
- <span data-ttu-id="085d1-142">2.2</span><span class="sxs-lookup"><span data-stu-id="085d1-142">2.2</span></span>
- <span data-ttu-id="085d1-143">2.0</span><span class="sxs-lookup"><span data-stu-id="085d1-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="085d1-144">Dependencias</span><span class="sxs-lookup"><span data-stu-id="085d1-144">Dependencies</span></span>

<span data-ttu-id="085d1-145">Para .NET en Alpine Linux es necesario que estén instaladas las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="085d1-145">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="085d1-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="085d1-146">icu-libs</span></span>
- <span data-ttu-id="085d1-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="085d1-147">krb5-libs</span></span>
- <span data-ttu-id="085d1-148">libgcc</span><span class="sxs-lookup"><span data-stu-id="085d1-148">libgcc</span></span>
- <span data-ttu-id="085d1-149">libintl</span><span class="sxs-lookup"><span data-stu-id="085d1-149">libintl</span></span>
- <span data-ttu-id="085d1-150">libssl1.1 (Alpine 3.9 o superior)</span><span class="sxs-lookup"><span data-stu-id="085d1-150">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="085d1-151">libssl1.0 (Alpine 3.8 o inferior)</span><span class="sxs-lookup"><span data-stu-id="085d1-151">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="085d1-152">libstdc++</span><span class="sxs-lookup"><span data-stu-id="085d1-152">libstdc++</span></span>
- <span data-ttu-id="085d1-153">zlib</span><span class="sxs-lookup"><span data-stu-id="085d1-153">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="085d1-154">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="085d1-154">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="085d1-155">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="085d1-155">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="085d1-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="085d1-156">Next steps</span></span>

- [<span data-ttu-id="085d1-157">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="085d1-157">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
