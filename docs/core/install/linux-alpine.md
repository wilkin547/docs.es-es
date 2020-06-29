---
title: 'Instalación de .NET Core en Alpine: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Alpine.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324825"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="76498-103">Instalación del SDK de .NET Core o .NET Core Runtime en Alpine</span><span class="sxs-lookup"><span data-stu-id="76498-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="76498-104">En este artículo se explica cómo instalar .NET Core en Alpine.</span><span class="sxs-lookup"><span data-stu-id="76498-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="76498-105">Cuando una versión de Alpine no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="76498-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="76498-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="76498-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="76498-107">No hay instaladores para Alpine.</span><span class="sxs-lookup"><span data-stu-id="76498-107">There are no installers for Alpine.</span></span> <span data-ttu-id="76498-108">Debe usar el [script de instalación](#scripted-install) o seguir las instrucciones de [instalación manual](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="76498-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="76498-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="76498-109">Supported distributions</span></span>

<span data-ttu-id="76498-110">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Alpine en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="76498-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="76498-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="76498-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="76498-112">Una ✔️ indica que todavía se admite la versión de Alpine o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="76498-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="76498-113">Una ❌ indica que la versión de Alpine o de .NET Core no se admite en esa versión de Alpine.</span><span class="sxs-lookup"><span data-stu-id="76498-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="76498-114">Cuando una versión de Alpine y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="76498-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="76498-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="76498-115">Alpine</span></span>                   | <span data-ttu-id="76498-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-116">.NET Core 2.1</span></span> | <span data-ttu-id="76498-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-117">.NET Core 3.1</span></span> | <span data-ttu-id="76498-118">.NET 5 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="76498-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="76498-119">✔️ 3.12</span></span>  | <span data-ttu-id="76498-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-120">✔️ 2.1</span></span>        | <span data-ttu-id="76498-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-121">✔️ 3.1</span></span>        | <span data-ttu-id="76498-122">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="76498-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="76498-123">✔️ 3.11</span></span>  | <span data-ttu-id="76498-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-124">✔️ 2.1</span></span>        | <span data-ttu-id="76498-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-125">✔️ 3.1</span></span>        | <span data-ttu-id="76498-126">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="76498-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="76498-127">✔️ 3.10</span></span>  | <span data-ttu-id="76498-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-128">✔️ 2.1</span></span>        | <span data-ttu-id="76498-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-129">✔️ 3.1</span></span>        | <span data-ttu-id="76498-130">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="76498-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="76498-131">✔️ 3.9</span></span>   | <span data-ttu-id="76498-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-132">✔️ 2.1</span></span>        | <span data-ttu-id="76498-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-133">✔️ 3.1</span></span>        | <span data-ttu-id="76498-134">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="76498-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="76498-135">❌ 3.8</span></span>   | <span data-ttu-id="76498-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="76498-136">✔️ 2.1</span></span>        | <span data-ttu-id="76498-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="76498-137">❌ 3.1</span></span>        | <span data-ttu-id="76498-138">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76498-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="76498-139">Las siguientes versiones de .NET Core ya no se admiten,</span><span class="sxs-lookup"><span data-stu-id="76498-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="76498-140">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="76498-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="76498-141">3.0</span><span class="sxs-lookup"><span data-stu-id="76498-141">3.0</span></span>
- <span data-ttu-id="76498-142">2.2</span><span class="sxs-lookup"><span data-stu-id="76498-142">2.2</span></span>
- <span data-ttu-id="76498-143">2.0</span><span class="sxs-lookup"><span data-stu-id="76498-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="76498-144">Dependencias</span><span class="sxs-lookup"><span data-stu-id="76498-144">Dependencies</span></span>

<span data-ttu-id="76498-145">.NET Core en Alpine Linux exige que estén instaladas las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="76498-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="76498-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="76498-146">icu-libs</span></span>
- <span data-ttu-id="76498-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="76498-147">krb5-libs</span></span>
- <span data-ttu-id="76498-148">libintl</span><span class="sxs-lookup"><span data-stu-id="76498-148">libintl</span></span>
- <span data-ttu-id="76498-149">libssl1.1 (Alpine 3.9 o superior)</span><span class="sxs-lookup"><span data-stu-id="76498-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="76498-150">libssl1.0 (Alpine 3.8)</span><span class="sxs-lookup"><span data-stu-id="76498-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="76498-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="76498-151">libstdc++</span></span>
- <span data-ttu-id="76498-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="76498-152">lttng-ust</span></span>
- <span data-ttu-id="76498-153">numactl (opcional)</span><span class="sxs-lookup"><span data-stu-id="76498-153">numactl (optional)</span></span>
- <span data-ttu-id="76498-154">zlib</span><span class="sxs-lookup"><span data-stu-id="76498-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="76498-155">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="76498-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="76498-156">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="76498-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="76498-157">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="76498-157">Next steps</span></span>

- [<span data-ttu-id="76498-158">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="76498-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
