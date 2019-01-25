---
title: Procedimiento Administrar el desbordamiento de ToolStrip en Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 5f26217c92aef1d568349aefb87dd5a882a0cf28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541162"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="6fe16-102">Procedimiento Administrar el desbordamiento de ToolStrip en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6fe16-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>
<span data-ttu-id="6fe16-103">Cuando todos los elementos en un <xref:System.Windows.Forms.ToolStrip> control no caben en el espacio asignado, puede habilitar la funcionalidad del desbordamiento en el <xref:System.Windows.Forms.ToolStrip> y determinar el comportamiento de desbordamiento específicas de <xref:System.Windows.Forms.ToolStripItem>s.</span><span class="sxs-lookup"><span data-stu-id="6fe16-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>  
  
 <span data-ttu-id="6fe16-104">Al agregar <xref:System.Windows.Forms.ToolStripItem>s que requieren más espacio que se asigna a la <xref:System.Windows.Forms.ToolStrip> dado el tamaño del formulario actual, un <xref:System.Windows.Forms.ToolStripOverflowButton> aparece automáticamente en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6fe16-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="6fe16-105">El <xref:System.Windows.Forms.ToolStripOverflowButton> aparece, y se mueven los elementos con desbordamiento habilitado en el menú de desbordamiento de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6fe16-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="6fe16-106">Esto le permite personalizar y dar prioridad a cómo la <xref:System.Windows.Forms.ToolStrip> elementos ajustar correctamente a tamaños de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="6fe16-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="6fe16-107">También puede cambiar la apariencia de los elementos cuando se dividen en el desbordamiento utilizando el <xref:System.Windows.Forms.ToolStripItem.Placement%2A> y <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> propiedades y el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> eventos.</span><span class="sxs-lookup"><span data-stu-id="6fe16-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="6fe16-108">Si aumenta el formulario en tiempo de diseño o en tiempo de ejecución, más <xref:System.Windows.Forms.ToolStripItem>s pueden mostrarse en el método main <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripOverflowButton> incluso puede que desaparezcan hasta que disminuya el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="6fe16-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="6fe16-109">Para habilitar el desbordamiento en un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6fe16-109">To enable overflow on a ToolStrip control</span></span>  
  
-   <span data-ttu-id="6fe16-110">Asegúrese de que el <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> propiedad no está establecida en `false` para el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6fe16-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="6fe16-111">De manera predeterminada, es `True`.</span><span class="sxs-lookup"><span data-stu-id="6fe16-111">The default is `True`.</span></span>  
  
     <span data-ttu-id="6fe16-112">Cuando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> es `True` (valor predeterminado), un <xref:System.Windows.Forms.ToolStripItem> se envía en el menú de desbordamiento de la lista desplegable cuando el contenido de la <xref:System.Windows.Forms.ToolStripItem> supera el ancho de una horizontal <xref:System.Windows.Forms.ToolStrip> o el alto de una vertical <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6fe16-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="6fe16-113">Para especificar el comportamiento de desbordamiento de un elemento ToolStripItem específico</span><span class="sxs-lookup"><span data-stu-id="6fe16-113">To specify overflow behavior of a specific ToolStripItem</span></span>  
  
-   <span data-ttu-id="6fe16-114">Establecer el <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> propiedad de la <xref:System.Windows.Forms.ToolStripItem> al valor deseado.</span><span class="sxs-lookup"><span data-stu-id="6fe16-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="6fe16-115">Las posibilidades son `Always`, `Never`, y `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="6fe16-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="6fe16-116">El defaultis `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="6fe16-116">The defaultis `AsNeeded`.</span></span>  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6fe16-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fe16-117">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="6fe16-118">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6fe16-118">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="6fe16-119">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6fe16-119">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="6fe16-120">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6fe16-120">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
