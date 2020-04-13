---
ms.openlocfilehash: b736ab743a628fdcbc53c5ee51551e5dad986885
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888150"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="a06c5-101">El evento CellFormatting no se produce si se muestra información en pantalla.</span><span class="sxs-lookup"><span data-stu-id="a06c5-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="a06c5-102">Ahora, <xref:System.Windows.Forms.DataGridView> muestra información en pantalla del texto y los errores de una celda cuando se mantiene el mouse sobre ella y cuando se selecciona mediante el teclado.</span><span class="sxs-lookup"><span data-stu-id="a06c5-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="a06c5-103">Si se muestra información en pantalla, no se produce el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a06c5-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a06c5-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a06c5-104">Change description</span></span>

<span data-ttu-id="a06c5-105">Antes de .NET Core 3.1, un elemento <xref:System.Windows.Forms.DataGridView> con la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> establecida en `true` mostraba información en pantalla del texto y los errores de una celda cuando se mantenía el mouse sobre ella.</span><span class="sxs-lookup"><span data-stu-id="a06c5-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="a06c5-106">La información en pantalla no se mostraba si la celda se seleccionaba mediante el teclado (por ejemplo, mediante la tecla Tab, teclas de método abreviado o las teclas de dirección).</span><span class="sxs-lookup"><span data-stu-id="a06c5-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="a06c5-107">Si el usuario editaba una celda y, luego, mientras el elemento <xref:System.Windows.Forms.DataGridView> aún estaba en modo de edición, mantenía el mouse sobre una celda que no tenía establecida la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>, se producía un evento <xref:System.Windows.Forms.DataGridView.CellFormatting> para dar formato al texto de la celda para su presentación en ella.</span><span class="sxs-lookup"><span data-stu-id="a06c5-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="a06c5-108">Para cumplir los estándares de accesibilidad, a partir de .NET Core 3.1, un elemento <xref:System.Windows.Forms.DataGridView> que tenga la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> establecida en `true` muestra información en pantalla del texto y los errores de una celda no solo cuando se mantiene el mouse sobre la celda, sino también cuando se selecciona mediante el teclado.</span><span class="sxs-lookup"><span data-stu-id="a06c5-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="a06c5-109">Como consecuencia de este cambio, el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>*no* se produce cuando se mantiene el mouse sobre las celdas que no tienen establecida la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> mientras <xref:System.Windows.Forms.DataGridView> está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a06c5-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="a06c5-110">El evento no se produce porque el contenido de la celda se muestra como información en pantalla en lugar de mostrarse en la celda.</span><span class="sxs-lookup"><span data-stu-id="a06c5-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a06c5-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a06c5-111">Version introduced</span></span>

<span data-ttu-id="a06c5-112">3.1</span><span class="sxs-lookup"><span data-stu-id="a06c5-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a06c5-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a06c5-113">Recommended action</span></span>

<span data-ttu-id="a06c5-114">Refactorice cualquier código que dependa del evento <xref:System.Windows.Forms.DataGridView.CellFormatting> mientras <xref:System.Windows.Forms.DataGridView> está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a06c5-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="a06c5-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="a06c5-115">Category</span></span>

<span data-ttu-id="a06c5-116">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a06c5-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a06c5-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a06c5-117">Affected APIs</span></span>

<span data-ttu-id="a06c5-118">None</span><span class="sxs-lookup"><span data-stu-id="a06c5-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis.

-->
