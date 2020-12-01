---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032903"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="3b740-101">SPA: SpaServices y NodeServices ya no vuelven al registrador de la consola</span><span class="sxs-lookup"><span data-stu-id="3b740-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="3b740-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> y <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> no mostrarán los registros de la consola a menos que el registro esté configurado.</span><span class="sxs-lookup"><span data-stu-id="3b740-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3b740-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3b740-103">Version introduced</span></span>

<span data-ttu-id="3b740-104">3.0</span><span class="sxs-lookup"><span data-stu-id="3b740-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3b740-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="3b740-105">Old behavior</span></span>

<span data-ttu-id="3b740-106">Antes, `Microsoft.AspNetCore.SpaServices` y `Microsoft.AspNetCore.NodeServices` creaban de forma automática un registrador de consola cuando el registro no estaba configurado.</span><span class="sxs-lookup"><span data-stu-id="3b740-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3b740-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="3b740-107">New behavior</span></span>

<span data-ttu-id="3b740-108">`Microsoft.AspNetCore.SpaServices` y `Microsoft.AspNetCore.NodeServices` no mostrarán los registros de la consola a menos que el registro esté configurado.</span><span class="sxs-lookup"><span data-stu-id="3b740-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3b740-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="3b740-109">Reason for change</span></span>

<span data-ttu-id="3b740-110">Existe la necesidad de alinearse con el modo de implementar el registro en otros paquetes de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b740-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3b740-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3b740-111">Recommended action</span></span>

<span data-ttu-id="3b740-112">Si se requiere el comportamiento anterior, agregue `services.AddLogging(builder => builder.AddConsole())` al método `Setup.ConfigureServices` para configurar el registro de la consola.</span><span class="sxs-lookup"><span data-stu-id="3b740-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="3b740-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="3b740-113">Category</span></span>

<span data-ttu-id="3b740-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3b740-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b740-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3b740-115">Affected APIs</span></span>

<span data-ttu-id="3b740-116">None</span><span class="sxs-lookup"><span data-stu-id="3b740-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
