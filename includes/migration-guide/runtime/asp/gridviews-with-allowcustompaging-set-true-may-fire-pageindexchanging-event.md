---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497880"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="b36db-101">GridView con AllowCustomPaging establecido en true puede desencadenar el evento PageIndexChanging al salir de la última página de la vista</span><span class="sxs-lookup"><span data-stu-id="b36db-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="b36db-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b36db-102">Details</span></span>

<span data-ttu-id="b36db-103">Un error en .NET Framework 4.5 hace que en ocasiones no se desencadene <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> para los elementos <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> en los que se ha habilitado <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b36db-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b36db-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b36db-104">Suggestion</span></span>

<span data-ttu-id="b36db-105">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b36db-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="b36db-106">Como una solución alternativa, la aplicación puede realizar una BindGrid explícita en cualquier método <code>Page_Load</code> que cumpla estas condiciones (la <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> está en la última página y Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> es diferente de <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="b36db-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="b36db-107">Como alternativa, la aplicación se puede modificar para permitir la paginación (en lugar de la paginación personalizada), dado que ese escenario no ilustra el problema.</span><span class="sxs-lookup"><span data-stu-id="b36db-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="b36db-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b36db-108">Name</span></span>    | <span data-ttu-id="b36db-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b36db-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b36db-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b36db-110">Scope</span></span>   |<span data-ttu-id="b36db-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b36db-111">Minor</span></span>|
|<span data-ttu-id="b36db-112">Versión</span><span class="sxs-lookup"><span data-stu-id="b36db-112">Version</span></span>|<span data-ttu-id="b36db-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b36db-113">4.5</span></span>|
|<span data-ttu-id="b36db-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="b36db-114">Type</span></span>|<span data-ttu-id="b36db-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b36db-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b36db-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b36db-116">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
