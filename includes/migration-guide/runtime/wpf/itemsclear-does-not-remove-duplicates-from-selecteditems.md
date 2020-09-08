---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496402"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="b08b8-101">Items.Clear no quita los duplicados de SelectedItems</span><span class="sxs-lookup"><span data-stu-id="b08b8-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="b08b8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b08b8-102">Details</span></span>

<span data-ttu-id="b08b8-103">Supongamos que un Selector (con la selección múltiple habilitada) tiene duplicados en su colección <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>: el mismo elemento aparece más de una vez.</span><span class="sxs-lookup"><span data-stu-id="b08b8-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="b08b8-104">Si esos elementos se quitan del origen de datos (por ejemplo, mediante una llamada a Items.Clear), no se quitan de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; solo se quita la primera instancia.</span><span class="sxs-lookup"><span data-stu-id="b08b8-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="b08b8-105">Además, el uso posterior de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (como SelectedItems.Clear()) puede tener problemas, como una excepción <xref:System.ArgumentException?displayProperty=fullName>, porque <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contiene elementos que ya no están en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b08b8-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b08b8-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b08b8-106">Suggestion</span></span>

<span data-ttu-id="b08b8-107">Si es posible, actualice a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="b08b8-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="b08b8-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b08b8-108">Name</span></span>    | <span data-ttu-id="b08b8-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b08b8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b08b8-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b08b8-110">Scope</span></span>   |<span data-ttu-id="b08b8-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b08b8-111">Minor</span></span>|
|<span data-ttu-id="b08b8-112">Versión</span><span class="sxs-lookup"><span data-stu-id="b08b8-112">Version</span></span>|<span data-ttu-id="b08b8-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b08b8-113">4.5</span></span>|
|<span data-ttu-id="b08b8-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="b08b8-114">Type</span></span>|<span data-ttu-id="b08b8-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b08b8-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b08b8-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b08b8-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
