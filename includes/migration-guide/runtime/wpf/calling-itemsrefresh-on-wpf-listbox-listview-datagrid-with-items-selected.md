---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620683"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="db1d4-101">Llamar a Items.Refresh en un elemento ListBox o ListView, o una cuadrícula de datos de WPF con elementos seleccionados puede hacer que aparezcan elementos duplicados en el elemento</span><span class="sxs-lookup"><span data-stu-id="db1d4-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="db1d4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="db1d4-102">Details</span></span>

<span data-ttu-id="db1d4-103">En .NET Framework 4.5, llamar a ListBox.Items.Refresh desde el código con elementos seleccionados en un elemento <xref:System.Windows.Controls.ListBox?displayProperty=fullName> puede hacer que los elementos seleccionados se dupliquen en la lista.</span><span class="sxs-lookup"><span data-stu-id="db1d4-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="db1d4-104">Se produce un problema similar con <xref:System.Windows.Controls.ListView?displayProperty=fullName> y <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="db1d4-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="db1d4-105">Este problema se corrigió en .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="db1d4-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db1d4-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="db1d4-106">Suggestion</span></span>

<span data-ttu-id="db1d4-107">Una solución alternativa para este problema consiste en, mediante programación, anular la selección de los elementos antes de llamar a <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> y volver a seleccionarlos después de que la llamada se complete.</span><span class="sxs-lookup"><span data-stu-id="db1d4-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="db1d4-108">Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db1d4-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="db1d4-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="db1d4-109">Name</span></span>    | <span data-ttu-id="db1d4-110">Valor</span><span class="sxs-lookup"><span data-stu-id="db1d4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db1d4-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="db1d4-111">Scope</span></span>   |<span data-ttu-id="db1d4-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="db1d4-112">Minor</span></span>|
|<span data-ttu-id="db1d4-113">Versión</span><span class="sxs-lookup"><span data-stu-id="db1d4-113">Version</span></span>|<span data-ttu-id="db1d4-114">4.5</span><span class="sxs-lookup"><span data-stu-id="db1d4-114">4.5</span></span>|
|<span data-ttu-id="db1d4-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="db1d4-115">Type</span></span>|<span data-ttu-id="db1d4-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="db1d4-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="db1d4-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="db1d4-117">Affected APIs</span></span>

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
