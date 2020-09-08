---
ms.openlocfilehash: a84d72813a46d6bb39f4710b35d2c9dc859e30ef
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496289"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="43cca-101">El evento Page.LoadComplete ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos</span><span class="sxs-lookup"><span data-stu-id="43cca-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="43cca-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="43cca-102">Details</span></span>

<span data-ttu-id="43cca-103">El evento <xref:System.Web.UI.Page.LoadComplete> ya no hace que el control <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> llame al enlace de datos cuando se producen cambios al crear, actualizar o eliminar parámetros.</span><span class="sxs-lookup"><span data-stu-id="43cca-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="43cca-104">Este cambio elimina un viaje superfluo a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos, como <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> y <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="43cca-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="43cca-105">Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento <xref:System.Web.UI.Page.LoadComplete>.</span><span class="sxs-lookup"><span data-stu-id="43cca-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="43cca-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="43cca-106">Suggestion</span></span>

<span data-ttu-id="43cca-107">Si se necesita un enlace de datos, invóquelo manualmente en un evento anterior en la devolución.</span><span class="sxs-lookup"><span data-stu-id="43cca-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="43cca-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="43cca-108">Name</span></span>    | <span data-ttu-id="43cca-109">Valor</span><span class="sxs-lookup"><span data-stu-id="43cca-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="43cca-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="43cca-110">Scope</span></span>   |<span data-ttu-id="43cca-111">Borde</span><span class="sxs-lookup"><span data-stu-id="43cca-111">Edge</span></span>|
|<span data-ttu-id="43cca-112">Versión</span><span class="sxs-lookup"><span data-stu-id="43cca-112">Version</span></span>|<span data-ttu-id="43cca-113">4.5</span><span class="sxs-lookup"><span data-stu-id="43cca-113">4.5</span></span>|
|<span data-ttu-id="43cca-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="43cca-114">Type</span></span>|<span data-ttu-id="43cca-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="43cca-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="43cca-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="43cca-116">Affected APIs</span></span>

<span data-ttu-id="43cca-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="43cca-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
