---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394272"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="45c14-101">Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="45c14-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="45c14-102">En la versión ASP.NET Core 3.0 se han quitado las [API MemoryCacheOptions](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) obsoletas.</span><span class="sxs-lookup"><span data-stu-id="45c14-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="45c14-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="45c14-103">Change description</span></span>

<span data-ttu-id="45c14-104">Este cambio es una continuación de [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="45c14-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="45c14-105">Para obtener información, vea [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).</span><span class="sxs-lookup"><span data-stu-id="45c14-105">For discussion, see [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="45c14-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="45c14-106">Version introduced</span></span>

<span data-ttu-id="45c14-107">3.0</span><span class="sxs-lookup"><span data-stu-id="45c14-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="45c14-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="45c14-108">Old behavior</span></span>

<span data-ttu-id="45c14-109">La propiedad `MemoryCacheOptions.CompactOnMemoryPressure` estaba disponible.</span><span class="sxs-lookup"><span data-stu-id="45c14-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="45c14-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="45c14-110">New behavior</span></span>

<span data-ttu-id="45c14-111">Se ha quitado la propiedad `MemoryCacheOptions.CompactOnMemoryPressure`.</span><span class="sxs-lookup"><span data-stu-id="45c14-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="45c14-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="45c14-112">Reason for change</span></span>

<span data-ttu-id="45c14-113">La compactación automática de la caché provocaba problemas.</span><span class="sxs-lookup"><span data-stu-id="45c14-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="45c14-114">Para evitar un comportamiento inesperado, solo se debe compactar la caché cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="45c14-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="45c14-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="45c14-115">Recommended action</span></span>

<span data-ttu-id="45c14-116">Para compactar la caché, realice la conversión a un tipo heredado `MemoryCache` y llame a `Compact` cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="45c14-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="45c14-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="45c14-117">Category</span></span>

<span data-ttu-id="45c14-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="45c14-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="45c14-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="45c14-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
