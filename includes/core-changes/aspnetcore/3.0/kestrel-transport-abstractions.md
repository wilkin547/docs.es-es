---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721737"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="3690a-101">Kestrel: las abstracciones de transporte se han quitado y se han hecho públicas</span><span class="sxs-lookup"><span data-stu-id="3690a-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="3690a-102">Como parte del desplazamiento de las API de "pubternal", las API de la capa de transporte de Kestrel se exponen como una interfaz pública en la biblioteca de `Microsoft.AspNetCore.Connections.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="3690a-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3690a-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3690a-103">Version introduced</span></span>

<span data-ttu-id="3690a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="3690a-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3690a-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="3690a-105">Old behavior</span></span>

- <span data-ttu-id="3690a-106">Las abstracciones relacionadas con el transporte estaban disponibles en la biblioteca de `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="3690a-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="3690a-107">La propiedad `ListenOptions.NoDelay` estaba disponible.</span><span class="sxs-lookup"><span data-stu-id="3690a-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3690a-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="3690a-108">New behavior</span></span>

- <span data-ttu-id="3690a-109">La interfaz de `IConnectionListener` se presentaba en la biblioteca de `Microsoft.AspNetCore.Connections.Abstractions` para exponer la funcionalidad más usada de la biblioteca de `...Transport.Abstractions`.</span><span class="sxs-lookup"><span data-stu-id="3690a-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="3690a-110">`NoDelay` está ahora disponible en opciones de transporte (`LibuvTransportOptions` y `SocketTransportOptions`).</span><span class="sxs-lookup"><span data-stu-id="3690a-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="3690a-111">`SchedulingMode` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="3690a-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3690a-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="3690a-112">Reason for change</span></span>

<span data-ttu-id="3690a-113">ASP.NET Core 3.0 se ha desplazado de las API de "pubternal".</span><span class="sxs-lookup"><span data-stu-id="3690a-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3690a-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3690a-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="3690a-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="3690a-115">Category</span></span>

<span data-ttu-id="3690a-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3690a-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3690a-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3690a-117">Affected APIs</span></span>

<span data-ttu-id="3690a-118">None</span><span class="sxs-lookup"><span data-stu-id="3690a-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
