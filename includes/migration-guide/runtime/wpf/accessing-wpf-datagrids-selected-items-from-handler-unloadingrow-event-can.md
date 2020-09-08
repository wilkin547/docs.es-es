---
ms.openlocfilehash: 1487e32ffca7b4bbebb5edac7efc8961ac05723b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497613"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="82bee-101">El acceso a los elementos seleccionados de un control DataGrid de WPF desde un controlador del evento UnloadingRow del control DataGrid puede producir una excepción NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="82bee-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="82bee-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="82bee-102">Details</span></span>

<span data-ttu-id="82bee-103">Debido a un error de .NET Framework 4.5, los controladores de eventos para los eventos <xref:System.Windows.Controls.DataGrid> en los que se elimina una fila pueden provocar que se inicie una excepción <xref:System.NullReferenceException?displayProperty=fullName> si tienen acceso a las propiedades <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> de <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="82bee-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="82bee-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="82bee-104">Suggestion</span></span>

<span data-ttu-id="82bee-105">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82bee-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="82bee-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="82bee-106">Name</span></span>    | <span data-ttu-id="82bee-107">Valor</span><span class="sxs-lookup"><span data-stu-id="82bee-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="82bee-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="82bee-108">Scope</span></span>   |<span data-ttu-id="82bee-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="82bee-109">Minor</span></span>|
|<span data-ttu-id="82bee-110">Versión</span><span class="sxs-lookup"><span data-stu-id="82bee-110">Version</span></span>|<span data-ttu-id="82bee-111">4.5</span><span class="sxs-lookup"><span data-stu-id="82bee-111">4.5</span></span>|
|<span data-ttu-id="82bee-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="82bee-112">Type</span></span>|<span data-ttu-id="82bee-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="82bee-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="82bee-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="82bee-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.Controls.DataGrid.UnloadingRow`
- `E:System.Windows.Controls.DataGrid.UnloadingRowDetails`

-->
