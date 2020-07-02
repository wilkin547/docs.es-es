---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620533"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="72e90-101">GridView con AllowCustomPaging establecido en true puede desencadenar el evento PageIndexChanging al salir de la última página de la vista</span><span class="sxs-lookup"><span data-stu-id="72e90-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="72e90-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="72e90-102">Details</span></span>

<span data-ttu-id="72e90-103">Un error en .NET Framework 4.5 hace que en ocasiones no se desencadene <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> para los elementos <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> en los que se ha habilitado <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="72e90-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="72e90-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="72e90-104">Suggestion</span></span>

<span data-ttu-id="72e90-105">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72e90-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="72e90-106">Como una solución alternativa, la aplicación puede realizar una BindGrid explícita en cualquier método <code>Page_Load</code> que cumpla estas condiciones (la <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> está en la última página y Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> es diferente de <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="72e90-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="72e90-107">Como alternativa, la aplicación se puede modificar para permitir la paginación (en lugar de la paginación personalizada), dado que ese escenario no ilustra el problema.</span><span class="sxs-lookup"><span data-stu-id="72e90-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="72e90-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="72e90-108">Name</span></span>    | <span data-ttu-id="72e90-109">Valor</span><span class="sxs-lookup"><span data-stu-id="72e90-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="72e90-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="72e90-110">Scope</span></span>   |<span data-ttu-id="72e90-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="72e90-111">Minor</span></span>|
|<span data-ttu-id="72e90-112">Versión</span><span class="sxs-lookup"><span data-stu-id="72e90-112">Version</span></span>|<span data-ttu-id="72e90-113">4.5</span><span class="sxs-lookup"><span data-stu-id="72e90-113">4.5</span></span>|
|<span data-ttu-id="72e90-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="72e90-114">Type</span></span>|<span data-ttu-id="72e90-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="72e90-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="72e90-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="72e90-116">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
