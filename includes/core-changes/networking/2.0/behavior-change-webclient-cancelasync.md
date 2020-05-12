---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859620"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="ec921-101">WebClient.CancelAsync no siempre se cancela inmediatamente</span><span class="sxs-lookup"><span data-stu-id="ec921-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="ec921-102">A partir de .NET Core 2.0, al llamar a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, no se cancela inmediatamente la solicitud si la respuesta ha empezado a recuperar cambios.</span><span class="sxs-lookup"><span data-stu-id="ec921-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ec921-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ec921-103">Change description</span></span>

<span data-ttu-id="ec921-104">Antes, si se llamaba a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, la solicitud se cancelaba inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ec921-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="ec921-105">A partir de .NET Core 2.0, al llamar a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, la solicitud se cancela inmediatamente solo si la respuesta no ha empezado a recuperar cambios.</span><span class="sxs-lookup"><span data-stu-id="ec921-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="ec921-106">Si la respuesta ha empezado a recuperar cambios, la solicitud se cancela solo después de leer una respuesta completa.</span><span class="sxs-lookup"><span data-stu-id="ec921-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="ec921-107">Este cambio se implementó porque la API de <xref:System.Net.WebClient> quedó en desuso en favor de <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="ec921-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ec921-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ec921-108">Version introduced</span></span>

<span data-ttu-id="ec921-109">2.0</span><span class="sxs-lookup"><span data-stu-id="ec921-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ec921-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ec921-110">Recommended action</span></span>

<span data-ttu-id="ec921-111">Use la clase <xref:System.Net.Http.HttpClient?displayProperty=fullName> en lugar de <xref:System.Net.WebClient?displayProperty=fullName>, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="ec921-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="ec921-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="ec921-112">Category</span></span>

<span data-ttu-id="ec921-113">Redes</span><span class="sxs-lookup"><span data-stu-id="ec921-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ec921-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ec921-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
