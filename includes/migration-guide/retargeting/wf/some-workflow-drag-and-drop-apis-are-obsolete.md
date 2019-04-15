---
ms.openlocfilehash: 297af393e86c65e84ea7271d98eab36dbc6dbb0e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234859"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="4da1f-101">Algunas API WorkFlow de arrastrar y colocar están obsoletas</span><span class="sxs-lookup"><span data-stu-id="4da1f-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4da1f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4da1f-102">Details</span></span>|<span data-ttu-id="4da1f-103">Esta API WorkFlow de arrastrar y colocar está obsoleta y generará advertencias del compilador si la aplicación se vuelve a compilar en 4.5.</span><span class="sxs-lookup"><span data-stu-id="4da1f-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>|
|<span data-ttu-id="4da1f-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4da1f-104">Suggestion</span></span>|<span data-ttu-id="4da1f-105">En su lugar, se deben usar las API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> nuevas compatibles con operaciones con varios objetos.</span><span class="sxs-lookup"><span data-stu-id="4da1f-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="4da1f-106">También es posible suprimir las advertencias de compilación o usar un compilador anterior para evitarlas.</span><span class="sxs-lookup"><span data-stu-id="4da1f-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="4da1f-107">Las API siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="4da1f-107">The APIs are still supported.</span></span>|
|<span data-ttu-id="4da1f-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4da1f-108">Scope</span></span>|<span data-ttu-id="4da1f-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4da1f-109">Minor</span></span>|
|<span data-ttu-id="4da1f-110">Versión</span><span class="sxs-lookup"><span data-stu-id="4da1f-110">Version</span></span>|<span data-ttu-id="4da1f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="4da1f-111">4.5</span></span>|
|<span data-ttu-id="4da1f-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="4da1f-112">Type</span></span>|<span data-ttu-id="4da1f-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4da1f-113">Retargeting</span></span>|
|<span data-ttu-id="4da1f-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4da1f-114">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|
