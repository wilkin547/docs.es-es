---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617290"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="6abcc-101">Algunas API WorkFlow de arrastrar y colocar están obsoletas</span><span class="sxs-lookup"><span data-stu-id="6abcc-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="6abcc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6abcc-102">Details</span></span>

<span data-ttu-id="6abcc-103">Esta API WorkFlow de arrastrar y colocar está obsoleta y generará advertencias del compilador si la aplicación se vuelve a compilar en 4.5.</span><span class="sxs-lookup"><span data-stu-id="6abcc-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6abcc-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6abcc-104">Suggestion</span></span>

<span data-ttu-id="6abcc-105">En su lugar, se deben usar las API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> nuevas compatibles con operaciones con varios objetos.</span><span class="sxs-lookup"><span data-stu-id="6abcc-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="6abcc-106">También es posible suprimir las advertencias de compilación o usar un compilador anterior para evitarlas.</span><span class="sxs-lookup"><span data-stu-id="6abcc-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="6abcc-107">Las API siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="6abcc-107">The APIs are still supported.</span></span>

| <span data-ttu-id="6abcc-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6abcc-108">Name</span></span>    | <span data-ttu-id="6abcc-109">Valor</span><span class="sxs-lookup"><span data-stu-id="6abcc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6abcc-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6abcc-110">Scope</span></span>   | <span data-ttu-id="6abcc-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6abcc-111">Minor</span></span>       |
| <span data-ttu-id="6abcc-112">Versión</span><span class="sxs-lookup"><span data-stu-id="6abcc-112">Version</span></span> | <span data-ttu-id="6abcc-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6abcc-113">4.5</span></span>         |
| <span data-ttu-id="6abcc-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="6abcc-114">Type</span></span>    | <span data-ttu-id="6abcc-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6abcc-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6abcc-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6abcc-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
