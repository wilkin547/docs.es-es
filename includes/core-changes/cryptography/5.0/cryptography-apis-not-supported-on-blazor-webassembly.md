---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406158"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="731ee-101">No se admiten las API de System.Security.Cryptography en Blazor WebAssembly</span><span class="sxs-lookup"><span data-stu-id="731ee-101">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="731ee-102">Las API de <xref:System.Security.Cryptography> inician una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución cuando se ejecutan en un explorador.</span><span class="sxs-lookup"><span data-stu-id="731ee-102"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

#### <a name="change-description"></a><span data-ttu-id="731ee-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="731ee-103">Change description</span></span>

<span data-ttu-id="731ee-104">En versiones anteriores de .NET, la mayoría de las API de <xref:System.Security.Cryptography> no están disponibles para las aplicaciones de Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="731ee-104">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="731ee-105">A partir de .NET 5.0, las aplicaciones de Blazor WebAssembly tienen como destino el área expuesta de la API de .NET 5 completa, sin embargo, no se admiten todas las API de .NET 5 debido a las restricciones de espacio aislado del explorador.</span><span class="sxs-lookup"><span data-stu-id="731ee-105">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="731ee-106">En .NET 5.0 y versiones posteriores, las API de <xref:System.Security.Cryptography> no compatibles inician una excepción <xref:System.PlatformNotSupportedException> cuando se ejecutan en WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="731ee-106">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="731ee-107">El [analizador de compatibilidad de plataformas](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) marcará todas las llamadas a las API afectadas al compilar un proyecto que admita la plataforma del explorador.</span><span class="sxs-lookup"><span data-stu-id="731ee-107">The [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="731ee-108">Este analizador se ejecuta de forma predeterminada en las aplicaciones .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="731ee-108">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="731ee-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="731ee-109">Reason for change</span></span>

<span data-ttu-id="731ee-110">Microsoft no puede enviar OpenSSL como una dependencia en la configuración de Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="731ee-110">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="731ee-111">Se intentó solucionar este error realizando la integración con la API de `SubtleCrypto` del explorador.</span><span class="sxs-lookup"><span data-stu-id="731ee-111">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="731ee-112">Sin embargo, requirió importantes cambios en la API que dificultaron su integración.</span><span class="sxs-lookup"><span data-stu-id="731ee-112">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="731ee-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="731ee-113">Version introduced</span></span>

<span data-ttu-id="731ee-114">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="731ee-114">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="731ee-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="731ee-115">Recommended action</span></span>

<span data-ttu-id="731ee-116">En este momento no hay ninguna solución alternativa adecuada que sugerir.</span><span class="sxs-lookup"><span data-stu-id="731ee-116">There are no good workarounds to suggest at this time.</span></span>

#### <a name="category"></a><span data-ttu-id="731ee-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="731ee-117">Category</span></span>

- <span data-ttu-id="731ee-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="731ee-118">ASP.NET Core</span></span>
- <span data-ttu-id="731ee-119">Criptografía</span><span class="sxs-lookup"><span data-stu-id="731ee-119">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="731ee-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="731ee-120">Affected APIs</span></span>

<span data-ttu-id="731ee-121">Todas las API de <xref:System.Security.Cryptography?displayProperty=fullName>, excepto las siguientes:</span><span class="sxs-lookup"><span data-stu-id="731ee-121">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

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

#### Affected APIs

- `T:System.Security.Cryptography`

-->
