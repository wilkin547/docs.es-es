---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858501"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="97167-101">El acceso a los elementos seleccionados de un control DataGrid de WPF desde un controlador del evento UnloadingRow del control DataGrid puede producir una excepción NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="97167-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="97167-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="97167-102">Details</span></span>|<span data-ttu-id="97167-103">Debido a un error de .NET Framework 4.5, los controladores de eventos para los eventos <xref:System.Windows.Controls.DataGrid> en los que se elimina una fila pueden provocar que se inicie una excepción <xref:System.NullReferenceException?displayProperty=name> si tienen acceso a las propiedades <xref:System.Windows.Controls.DataGrid> o <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="97167-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="97167-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="97167-104">Suggestion</span></span>|<span data-ttu-id="97167-105">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97167-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="97167-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="97167-106">Scope</span></span>|<span data-ttu-id="97167-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="97167-107">Minor</span></span>|
|<span data-ttu-id="97167-108">Versión</span><span class="sxs-lookup"><span data-stu-id="97167-108">Version</span></span>|<span data-ttu-id="97167-109">4.5</span><span class="sxs-lookup"><span data-stu-id="97167-109">4.5</span></span>|
|<span data-ttu-id="97167-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="97167-110">Type</span></span>|<span data-ttu-id="97167-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="97167-111">Runtime</span></span>|
|<span data-ttu-id="97167-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="97167-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
