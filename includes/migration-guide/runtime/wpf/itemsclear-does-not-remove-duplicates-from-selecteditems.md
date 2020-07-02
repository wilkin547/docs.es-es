---
ms.openlocfilehash: 75f176133697056bab9349ba1d18d7a0e1aa7da2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620529"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="105d2-101">Items.Clear no quita los duplicados de SelectedItems</span><span class="sxs-lookup"><span data-stu-id="105d2-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="105d2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="105d2-102">Details</span></span>

<span data-ttu-id="105d2-103">Supongamos que un Selector (con la selección múltiple habilitada) tiene duplicados en su colección <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>: el mismo elemento aparece más de una vez.</span><span class="sxs-lookup"><span data-stu-id="105d2-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="105d2-104">Si esos elementos se quitan del origen de datos (por ejemplo, mediante una llamada a Items.Clear), no se quitan de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; solo se quita la primera instancia.</span><span class="sxs-lookup"><span data-stu-id="105d2-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="105d2-105">Además, el uso posterior de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (como SelectedItems.Clear()) puede tener problemas, como una excepción <xref:System.ArgumentException?displayProperty=fullName>, porque <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contiene elementos que ya no están en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="105d2-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="105d2-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="105d2-106">Suggestion</span></span>

<span data-ttu-id="105d2-107">Si es posible, actualice a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="105d2-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="105d2-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="105d2-108">Name</span></span>    | <span data-ttu-id="105d2-109">Valor</span><span class="sxs-lookup"><span data-stu-id="105d2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="105d2-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="105d2-110">Scope</span></span>   |<span data-ttu-id="105d2-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="105d2-111">Minor</span></span>|
|<span data-ttu-id="105d2-112">Versión</span><span class="sxs-lookup"><span data-stu-id="105d2-112">Version</span></span>|<span data-ttu-id="105d2-113">4.5</span><span class="sxs-lookup"><span data-stu-id="105d2-113">4.5</span></span>|
|<span data-ttu-id="105d2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="105d2-114">Type</span></span>|<span data-ttu-id="105d2-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="105d2-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="105d2-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="105d2-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
