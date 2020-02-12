---
title: 'Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124304"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="bd8ee-102">Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb</span><span class="sxs-lookup"><span data-stu-id="bd8ee-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="bd8ee-103">En este ejemplo se muestra cómo usar un control <xref:System.Windows.Controls.Primitives.Thumb> para cambiar el tamaño de un control <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd8ee-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd8ee-104">Example</span></span>  
 <span data-ttu-id="bd8ee-105">El control <xref:System.Windows.Controls.Primitives.Thumb> proporciona funcionalidad de arrastrar que se puede utilizar para desplace o cambiar el tamaño de los controles supervisando los eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> de la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="bd8ee-106">El usuario comienza una operación de arrastre presionando el botón primario del mouse cuando el puntero del mouse se pausa en el control de <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="bd8ee-107">La operación de arrastrar continúa mientras se presiona el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="bd8ee-108">Durante la operación de arrastre, el <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> puede aparecer más de una vez.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="bd8ee-109">Cada vez que se produce, la clase <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> proporciona el cambio en la posición correspondiente al cambio en la posición del mouse.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="bd8ee-110">Cuando el usuario suelta el botón primario del mouse, finaliza la operación de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="bd8ee-111">La operación de arrastre solo proporciona nuevas coordenadas; no cambia automáticamente la posición del <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="bd8ee-112">En el ejemplo siguiente se muestra un control <xref:System.Windows.Controls.Primitives.Thumb> que es el elemento secundario de un control <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="bd8ee-113">El controlador de eventos para su evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> proporciona la lógica para trasladar el <xref:System.Windows.Controls.Primitives.Thumb> y cambiar el tamaño del <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="bd8ee-114">Los controladores de eventos para el evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> cambian el color de la <xref:System.Windows.Controls.Primitives.Thumb> durante una operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="bd8ee-115">En el ejemplo siguiente se define el <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="bd8ee-116">En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> que mueve el <xref:System.Windows.Controls.Primitives.Thumb> y cambia el tamaño del <xref:System.Windows.Controls.Canvas> en respuesta a un movimiento del mouse.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="bd8ee-117">En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="bd8ee-118">En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.</span><span class="sxs-lookup"><span data-stu-id="bd8ee-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="bd8ee-119">Para obtener el ejemplo completo, vea [ejemplo de funcionalidad de arrastre Thumb](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span><span class="sxs-lookup"><span data-stu-id="bd8ee-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8ee-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd8ee-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
