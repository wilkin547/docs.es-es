---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620538"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="4735b-101">El evento Page.LoadComplete ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos</span><span class="sxs-lookup"><span data-stu-id="4735b-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="4735b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4735b-102">Details</span></span>

<span data-ttu-id="4735b-103">El evento <xref:System.Web.UI.Page.LoadComplete> ya no hace que el control <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> llame al enlace de datos cuando se producen cambios al crear, actualizar o eliminar parámetros.</span><span class="sxs-lookup"><span data-stu-id="4735b-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="4735b-104">Este cambio elimina un viaje superfluo a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos, como <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> y <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4735b-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="4735b-105">Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento <xref:System.Web.UI.Page.LoadComplete>.</span><span class="sxs-lookup"><span data-stu-id="4735b-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4735b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4735b-106">Suggestion</span></span>

<span data-ttu-id="4735b-107">Si se necesita un enlace de datos, invóquelo manualmente en un evento anterior en la devolución.</span><span class="sxs-lookup"><span data-stu-id="4735b-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="4735b-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4735b-108">Name</span></span>    | <span data-ttu-id="4735b-109">Valor</span><span class="sxs-lookup"><span data-stu-id="4735b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4735b-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4735b-110">Scope</span></span>   |<span data-ttu-id="4735b-111">Borde</span><span class="sxs-lookup"><span data-stu-id="4735b-111">Edge</span></span>|
|<span data-ttu-id="4735b-112">Versión</span><span class="sxs-lookup"><span data-stu-id="4735b-112">Version</span></span>|<span data-ttu-id="4735b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4735b-113">4.5</span></span>|
|<span data-ttu-id="4735b-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="4735b-114">Type</span></span>|<span data-ttu-id="4735b-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4735b-115">Runtime</span></span>|
