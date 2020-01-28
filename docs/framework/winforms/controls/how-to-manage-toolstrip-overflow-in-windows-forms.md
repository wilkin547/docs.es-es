---
title: 'Cómo: Administrar el desbordamiento de ToolStrip'
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
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736146"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="aa103-102">Cómo: Administrar el desbordamiento de ToolStrip en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aa103-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="aa103-103">Cuando todos los elementos de un control <xref:System.Windows.Forms.ToolStrip> no caben en el espacio asignado, puede habilitar la funcionalidad de desbordamiento en el <xref:System.Windows.Forms.ToolStrip> y determinar el comportamiento de desbordamiento de <xref:System.Windows.Forms.ToolStripItem>s específicos.</span><span class="sxs-lookup"><span data-stu-id="aa103-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="aa103-104">Cuando se agregan <xref:System.Windows.Forms.ToolStripItem>que requieren más espacio que el asignado al <xref:System.Windows.Forms.ToolStrip> dado el tamaño actual del formulario, aparece automáticamente una <xref:System.Windows.Forms.ToolStripOverflowButton> en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aa103-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="aa103-105">Aparece el <xref:System.Windows.Forms.ToolStripOverflowButton> y los elementos habilitados para el desbordamiento se mueven al menú desplegable de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="aa103-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="aa103-106">Esto le permite personalizar y priorizar el modo en que los elementos de <xref:System.Windows.Forms.ToolStrip> se ajustan correctamente a distintos tamaños de formulario.</span><span class="sxs-lookup"><span data-stu-id="aa103-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="aa103-107">También puede cambiar la apariencia de los elementos cuando entran en el desbordamiento mediante las propiedades <xref:System.Windows.Forms.ToolStripItem.Placement%2A> y <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> y el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>.</span><span class="sxs-lookup"><span data-stu-id="aa103-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="aa103-108">Si aumenta el tamaño del formulario en tiempo de diseño o en tiempo de ejecución, es posible que se muestren más <xref:System.Windows.Forms.ToolStripItem>s en el <xref:System.Windows.Forms.ToolStrip> principal y el <xref:System.Windows.Forms.ToolStripOverflowButton> incluso desaparecerá hasta que se reduzca el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="aa103-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="aa103-109">Para habilitar el desbordamiento en un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa103-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="aa103-110">Asegúrese de que la propiedad <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> no esté establecida en `false` para el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aa103-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="aa103-111">De manera predeterminada, es `True`.</span><span class="sxs-lookup"><span data-stu-id="aa103-111">The default is `True`.</span></span>

     <span data-ttu-id="aa103-112">Cuando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> se `True` (valor predeterminado), se envía un <xref:System.Windows.Forms.ToolStripItem> al menú de desbordamiento desplegable cuando el contenido del <xref:System.Windows.Forms.ToolStripItem> supera el ancho de un <xref:System.Windows.Forms.ToolStrip> horizontal o el alto de un <xref:System.Windows.Forms.ToolStrip>vertical.</span><span class="sxs-lookup"><span data-stu-id="aa103-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="aa103-113">Para especificar el comportamiento de desbordamiento de un ToolStripItem específico</span><span class="sxs-lookup"><span data-stu-id="aa103-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="aa103-114">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> del <xref:System.Windows.Forms.ToolStripItem> en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="aa103-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="aa103-115">Las posibilidades son `Always`, `Never`y `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="aa103-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="aa103-116">De manera predeterminada, es `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="aa103-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="aa103-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa103-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="aa103-118">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa103-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="aa103-119">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa103-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="aa103-120">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa103-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
