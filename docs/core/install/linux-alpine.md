---
title: 'Instalación de .NET Core en Alpine: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Alpine.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: bbaf4ee9020dcd33c894b5376bf04ad65db8d378
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84771492"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="aedef-103">Instalación del SDK de .NET Core o .NET Core Runtime en Alpine</span><span class="sxs-lookup"><span data-stu-id="aedef-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="aedef-104">En este artículo se explica cómo instalar .NET Core en Alpine.</span><span class="sxs-lookup"><span data-stu-id="aedef-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="aedef-105">Cuando una versión de Alpine no es compatible, .NET Core deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="aedef-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="aedef-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="aedef-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="aedef-107">No hay instaladores para Alpine.</span><span class="sxs-lookup"><span data-stu-id="aedef-107">There are no installers for Alpine.</span></span> <span data-ttu-id="aedef-108">Debe usar el [script de instalación](#scripted-install) o seguir las instrucciones de [instalación manual](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="aedef-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="aedef-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="aedef-109">Supported distributions</span></span>

<span data-ttu-id="aedef-110">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Alpine en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="aedef-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="aedef-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="aedef-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="aedef-112">Una ✔️ indica que todavía se admite la versión de Alpine o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aedef-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="aedef-113">Una ❌ indica que la versión de Alpine o de .NET Core no se admite en esa versión de Alpine.</span><span class="sxs-lookup"><span data-stu-id="aedef-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="aedef-114">Cuando una versión de Alpine y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="aedef-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="aedef-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="aedef-115">Alpine</span></span>                   | <span data-ttu-id="aedef-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-116">.NET Core 2.1</span></span> | <span data-ttu-id="aedef-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-117">.NET Core 3.1</span></span> | <span data-ttu-id="aedef-118">.NET 5 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="aedef-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="aedef-119">✔️ 3.12</span></span>  | <span data-ttu-id="aedef-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-120">✔️ 2.1</span></span>        | <span data-ttu-id="aedef-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-121">✔️ 3.1</span></span>        | <span data-ttu-id="aedef-122">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aedef-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="aedef-123">✔️ 3.11</span></span>  | <span data-ttu-id="aedef-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-124">✔️ 2.1</span></span>        | <span data-ttu-id="aedef-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-125">✔️ 3.1</span></span>        | <span data-ttu-id="aedef-126">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aedef-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="aedef-127">✔️ 3.10</span></span>  | <span data-ttu-id="aedef-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-128">✔️ 2.1</span></span>        | <span data-ttu-id="aedef-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-129">✔️ 3.1</span></span>        | <span data-ttu-id="aedef-130">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aedef-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="aedef-131">✔️ 3.9</span></span>   | <span data-ttu-id="aedef-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-132">✔️ 2.1</span></span>        | <span data-ttu-id="aedef-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-133">✔️ 3.1</span></span>        | <span data-ttu-id="aedef-134">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="aedef-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="aedef-135">❌ 3.8</span></span>   | <span data-ttu-id="aedef-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="aedef-136">✔️ 2.1</span></span>        | <span data-ttu-id="aedef-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="aedef-137">❌ 3.1</span></span>        | <span data-ttu-id="aedef-138">❌ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aedef-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="aedef-139">Las siguientes versiones de .NET Core ya no se admiten,</span><span class="sxs-lookup"><span data-stu-id="aedef-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="aedef-140">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="aedef-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="aedef-141">3.0</span><span class="sxs-lookup"><span data-stu-id="aedef-141">3.0</span></span>
- <span data-ttu-id="aedef-142">2.2</span><span class="sxs-lookup"><span data-stu-id="aedef-142">2.2</span></span>
- <span data-ttu-id="aedef-143">2.0</span><span class="sxs-lookup"><span data-stu-id="aedef-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="aedef-144">Dependencias</span><span class="sxs-lookup"><span data-stu-id="aedef-144">Dependencies</span></span>

<span data-ttu-id="aedef-145">.NET Core en Alpine Linux exige que estén instaladas las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="aedef-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="aedef-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="aedef-146">icu-libs</span></span>
- <span data-ttu-id="aedef-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="aedef-147">krb5-libs</span></span>
- <span data-ttu-id="aedef-148">libintl</span><span class="sxs-lookup"><span data-stu-id="aedef-148">libintl</span></span>
- <span data-ttu-id="aedef-149">libssl1.1 (Alpine 3.9 o superior)</span><span class="sxs-lookup"><span data-stu-id="aedef-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="aedef-150">libssl1.0 (Alpine 3.8)</span><span class="sxs-lookup"><span data-stu-id="aedef-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="aedef-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="aedef-151">libstdc++</span></span>
- <span data-ttu-id="aedef-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="aedef-152">lttng-ust</span></span>
- <span data-ttu-id="aedef-153">numactl (opcional)</span><span class="sxs-lookup"><span data-stu-id="aedef-153">numactl (optional)</span></span>
- <span data-ttu-id="aedef-154">zlib</span><span class="sxs-lookup"><span data-stu-id="aedef-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="aedef-155">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="aedef-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="aedef-156">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="aedef-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="aedef-157">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="aedef-157">Next steps</span></span>

- [<span data-ttu-id="aedef-158">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="aedef-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
