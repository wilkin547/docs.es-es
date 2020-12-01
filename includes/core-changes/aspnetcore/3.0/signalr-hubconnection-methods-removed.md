---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032880"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="ebe21-101">SignalR: se han quitado los métodos ResetSendPing y ResetTimeout de HubConnection</span><span class="sxs-lookup"><span data-stu-id="ebe21-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="ebe21-102">Los métodos `ResetSendPing` y `ResetTimeout` se han quitado de la API `HubConnection` de SignalR.</span><span class="sxs-lookup"><span data-stu-id="ebe21-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="ebe21-103">Estos métodos se diseñaron originalmente solo para uso interno, pero se hicieron públicos en ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ebe21-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="ebe21-104">Estos métodos no estarán disponibles a partir de ASP.NET Core 3.0, versión preliminar 4.</span><span class="sxs-lookup"><span data-stu-id="ebe21-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="ebe21-105">Para obtener información, vea [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span><span class="sxs-lookup"><span data-stu-id="ebe21-105">For discussion, see [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ebe21-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ebe21-106">Version introduced</span></span>

<span data-ttu-id="ebe21-107">3.0</span><span class="sxs-lookup"><span data-stu-id="ebe21-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ebe21-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="ebe21-108">Old behavior</span></span>

<span data-ttu-id="ebe21-109">Las API estaban disponibles.</span><span class="sxs-lookup"><span data-stu-id="ebe21-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ebe21-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="ebe21-110">New behavior</span></span>

<span data-ttu-id="ebe21-111">Las API se quitan.</span><span class="sxs-lookup"><span data-stu-id="ebe21-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ebe21-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="ebe21-112">Reason for change</span></span>

<span data-ttu-id="ebe21-113">Estos métodos se diseñaron originalmente solo para uso interno, pero se hicieron públicos en ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ebe21-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ebe21-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ebe21-114">Recommended action</span></span>

<span data-ttu-id="ebe21-115">No use estos métodos.</span><span class="sxs-lookup"><span data-stu-id="ebe21-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="ebe21-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="ebe21-116">Category</span></span>

<span data-ttu-id="ebe21-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ebe21-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ebe21-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ebe21-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
