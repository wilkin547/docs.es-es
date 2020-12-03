---
title: 'Cambio importante: No se admiten las API de System.Security.Cryptography en Blazor WebAssembly'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde las API de criptografía inician una excepción cuando se ejecutan en un explorador.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760123"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="13ede-103">No se admiten las API de System.Security.Cryptography en Blazor WebAssembly</span><span class="sxs-lookup"><span data-stu-id="13ede-103">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="13ede-104">Las API de <xref:System.Security.Cryptography> inician una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución cuando se ejecutan en un explorador.</span><span class="sxs-lookup"><span data-stu-id="13ede-104"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

## <a name="change-description"></a><span data-ttu-id="13ede-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="13ede-105">Change description</span></span>

<span data-ttu-id="13ede-106">En versiones anteriores de .NET, la mayoría de las API de <xref:System.Security.Cryptography> no están disponibles para las aplicaciones de Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="13ede-106">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="13ede-107">A partir de .NET 5.0, las aplicaciones de Blazor WebAssembly tienen como destino el área expuesta de la API de .NET 5 completa, sin embargo, no se admiten todas las API de .NET 5 debido a las restricciones de espacio aislado del explorador.</span><span class="sxs-lookup"><span data-stu-id="13ede-107">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="13ede-108">En .NET 5.0 y versiones posteriores, las API de <xref:System.Security.Cryptography> no compatibles inician una excepción <xref:System.PlatformNotSupportedException> cuando se ejecutan en WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="13ede-108">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="13ede-109">El [analizador de compatibilidad de plataformas](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) marcará todas las llamadas a las API afectadas al compilar un proyecto que admita la plataforma del explorador.</span><span class="sxs-lookup"><span data-stu-id="13ede-109">The [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="13ede-110">Este analizador se ejecuta de forma predeterminada en las aplicaciones .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="13ede-110">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="13ede-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="13ede-111">Reason for change</span></span>

<span data-ttu-id="13ede-112">Microsoft no puede enviar OpenSSL como una dependencia en la configuración de Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="13ede-112">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="13ede-113">Se intentó solucionar este error realizando la integración con la API de `SubtleCrypto` del explorador.</span><span class="sxs-lookup"><span data-stu-id="13ede-113">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="13ede-114">Sin embargo, requirió importantes cambios en la API que dificultaron su integración.</span><span class="sxs-lookup"><span data-stu-id="13ede-114">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="13ede-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="13ede-115">Version introduced</span></span>

<span data-ttu-id="13ede-116">5.0</span><span class="sxs-lookup"><span data-stu-id="13ede-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="13ede-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="13ede-117">Recommended action</span></span>

<span data-ttu-id="13ede-118">En este momento no hay ninguna solución alternativa adecuada que sugerir.</span><span class="sxs-lookup"><span data-stu-id="13ede-118">There are no good workarounds to suggest at this time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="13ede-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="13ede-119">Affected APIs</span></span>

<span data-ttu-id="13ede-120">Todas las API de <xref:System.Security.Cryptography?displayProperty=fullName>, excepto las siguientes:</span><span class="sxs-lookup"><span data-stu-id="13ede-120">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
