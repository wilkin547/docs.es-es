---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620533"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridView con AllowCustomPaging establecido en true puede desencadenar el evento PageIndexChanging al salir de la última página de la vista

#### <a name="details"></a>Detalles

Un error en .NET Framework 4.5 hace que en ocasiones no se desencadene <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> para los elementos <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> en los que se ha habilitado <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework. Como una solución alternativa, la aplicación puede realizar una BindGrid explícita en cualquier método <code>Page_Load</code> que cumpla estas condiciones (la <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> está en la última página y Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> es diferente de <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>). Como alternativa, la aplicación se puede modificar para permitir la paginación (en lugar de la paginación personalizada), dado que ese escenario no ilustra el problema.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
