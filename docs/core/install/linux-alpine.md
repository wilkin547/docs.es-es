---
title: 'Instalación de .NET en Alpine: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Alpine.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970855"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="7169f-103">Instalación del SDK y el entorno de ejecución de .NET en Alpine</span><span class="sxs-lookup"><span data-stu-id="7169f-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="7169f-104">En este artículo se describe cómo instalar .NET en Alpine.</span><span class="sxs-lookup"><span data-stu-id="7169f-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="7169f-105">Cuando una versión de Alpine no es compatible, .NET deja de ser compatible con esa versión.</span><span class="sxs-lookup"><span data-stu-id="7169f-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="7169f-106">Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.</span><span class="sxs-lookup"><span data-stu-id="7169f-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a><span data-ttu-id="7169f-107">Instalar</span><span class="sxs-lookup"><span data-stu-id="7169f-107">Install</span></span>

<span data-ttu-id="7169f-108">No hay instaladores disponibles para Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="7169f-108">Installers aren't available for Alpine Linux.</span></span> <span data-ttu-id="7169f-109">Debe instalar .NET de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="7169f-109">You must install .NET in one of the following ways:</span></span>

- [<span data-ttu-id="7169f-110">Paquete de snaps</span><span class="sxs-lookup"><span data-stu-id="7169f-110">Snap package</span></span>](linux-snap.md)
- [<span data-ttu-id="7169f-111">Instalación con scripts con _install-dotnet.sh_</span><span class="sxs-lookup"><span data-stu-id="7169f-111">Scripted install with _install-dotnet.sh_</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="7169f-112">Extracción binaria manual</span><span class="sxs-lookup"><span data-stu-id="7169f-112">Manual binary extraction</span></span>](linux-scripted-manual.md#manual-install)

## <a name="supported-distributions"></a><span data-ttu-id="7169f-113">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="7169f-113">Supported distributions</span></span>

<span data-ttu-id="7169f-114">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Alpine en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="7169f-114">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="7169f-115">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="7169f-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="7169f-116">El símbolo ✔️ indica que todavía se admite la versión de Alpine o de .NET.</span><span class="sxs-lookup"><span data-stu-id="7169f-116">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="7169f-117">El símbolo ❌ indica que la versión de Alpine o de .NET no se admite en esa versión de Alpine.</span><span class="sxs-lookup"><span data-stu-id="7169f-117">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="7169f-118">Si una versión de Alpine y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="7169f-118">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="7169f-119">Alpine</span><span class="sxs-lookup"><span data-stu-id="7169f-119">Alpine</span></span>  | <span data-ttu-id="7169f-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-120">.NET Core 2.1</span></span> | <span data-ttu-id="7169f-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-121">.NET Core 3.1</span></span> | <span data-ttu-id="7169f-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-122">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="7169f-123">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="7169f-123">✔️ 3.12</span></span> | <span data-ttu-id="7169f-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-124">✔️ 2.1</span></span>        | <span data-ttu-id="7169f-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-125">✔️ 3.1</span></span>        | <span data-ttu-id="7169f-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-126">✔️ 5.0</span></span> |
| <span data-ttu-id="7169f-127">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="7169f-127">✔️ 3.11</span></span> | <span data-ttu-id="7169f-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-128">✔️ 2.1</span></span>        | <span data-ttu-id="7169f-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-129">✔️ 3.1</span></span>        | <span data-ttu-id="7169f-130">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-130">✔️ 5.0</span></span> |
| <span data-ttu-id="7169f-131">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="7169f-131">✔️ 3.10</span></span> | <span data-ttu-id="7169f-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-132">✔️ 2.1</span></span>        | <span data-ttu-id="7169f-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-133">✔️ 3.1</span></span>        | <span data-ttu-id="7169f-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-134">❌ 5.0</span></span> |
| <span data-ttu-id="7169f-135">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="7169f-135">❌ 3.9</span></span>  | <span data-ttu-id="7169f-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-136">✔️ 2.1</span></span>        | <span data-ttu-id="7169f-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-137">✔️ 3.1</span></span>        | <span data-ttu-id="7169f-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-138">❌ 5.0</span></span> |
| <span data-ttu-id="7169f-139">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="7169f-139">❌ 3.8</span></span>  | <span data-ttu-id="7169f-140">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7169f-140">✔️ 2.1</span></span>        | <span data-ttu-id="7169f-141">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7169f-141">✔️ 3.1</span></span>        | <span data-ttu-id="7169f-142">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7169f-142">❌ 5.0</span></span> |

<span data-ttu-id="7169f-143">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="7169f-143">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="7169f-144">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="7169f-144">The downloads for these still remain published:</span></span>

- <span data-ttu-id="7169f-145">3.0</span><span class="sxs-lookup"><span data-stu-id="7169f-145">3.0</span></span>
- <span data-ttu-id="7169f-146">2.2</span><span class="sxs-lookup"><span data-stu-id="7169f-146">2.2</span></span>
- <span data-ttu-id="7169f-147">2.0</span><span class="sxs-lookup"><span data-stu-id="7169f-147">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="7169f-148">Dependencias</span><span class="sxs-lookup"><span data-stu-id="7169f-148">Dependencies</span></span>

<span data-ttu-id="7169f-149">Para .NET en Alpine Linux es necesario que estén instaladas las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="7169f-149">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="7169f-150">icu-libs</span><span class="sxs-lookup"><span data-stu-id="7169f-150">icu-libs</span></span>
- <span data-ttu-id="7169f-151">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7169f-151">krb5-libs</span></span>
- <span data-ttu-id="7169f-152">libgcc</span><span class="sxs-lookup"><span data-stu-id="7169f-152">libgcc</span></span>
- <span data-ttu-id="7169f-153">libintl</span><span class="sxs-lookup"><span data-stu-id="7169f-153">libintl</span></span>
- <span data-ttu-id="7169f-154">libssl1.1 (Alpine 3.9 o superior)</span><span class="sxs-lookup"><span data-stu-id="7169f-154">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="7169f-155">libssl1.0 (Alpine 3.8 o inferior)</span><span class="sxs-lookup"><span data-stu-id="7169f-155">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="7169f-156">libstdc++</span><span class="sxs-lookup"><span data-stu-id="7169f-156">libstdc++</span></span>
- <span data-ttu-id="7169f-157">zlib</span><span class="sxs-lookup"><span data-stu-id="7169f-157">zlib</span></span>

## <a name="next-steps"></a><span data-ttu-id="7169f-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7169f-158">Next steps</span></span>

- [<span data-ttu-id="7169f-159">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="7169f-159">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="7169f-160">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7169f-160">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
