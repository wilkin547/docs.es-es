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
ms.openlocfilehash: c3e7176b0578c8fdc5f4331ad8f3b464f3a88b51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555069"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="632de-102">Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb</span><span class="sxs-lookup"><span data-stu-id="632de-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="632de-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Primitives.Thumb> control para cambiar el tamaño de una <xref:System.Windows.Controls.Canvas> control.</span><span class="sxs-lookup"><span data-stu-id="632de-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="632de-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="632de-104">Example</span></span>  
 <span data-ttu-id="632de-105">El <xref:System.Windows.Controls.Primitives.Thumb> control proporciona la funcionalidad de arrastrar que se puede utilizar para mover o cambiar el tamaño de los controles mediante la supervisión de la <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventos de la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="632de-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="632de-106">El usuario comienza una operación de arrastre presionando el botón primario del mouse cuando se pausa el puntero del mouse en el <xref:System.Windows.Controls.Primitives.Thumb> control.</span><span class="sxs-lookup"><span data-stu-id="632de-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="632de-107">La operación de arrastrar continúa mientras mantiene presionado el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="632de-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="632de-108">Durante la operación de arrastre, el <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> puede aparecer más de una vez.</span><span class="sxs-lookup"><span data-stu-id="632de-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="632de-109">Cada vez que aparezca, la <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> clase proporciona el cambio de posición que se corresponde con el cambio en la posición del mouse.</span><span class="sxs-lookup"><span data-stu-id="632de-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="632de-110">Cuando el usuario suelta el botón primario del mouse, finaliza la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="632de-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="632de-111">La operación de arrastrar sólo proporciona coordenadas nuevas; No volver a colocar automáticamente la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="632de-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="632de-112">El ejemplo siguiente muestra un <xref:System.Windows.Controls.Primitives.Thumb> control que es el elemento secundario de un <xref:System.Windows.Controls.Canvas> control.</span><span class="sxs-lookup"><span data-stu-id="632de-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="632de-113">El controlador de eventos para su <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento proporciona la lógica para mover el <xref:System.Windows.Controls.Primitives.Thumb> y cambiar el tamaño de la <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="632de-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="632de-114">Los controladores de eventos para el <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> evento cambiar el color de la <xref:System.Windows.Controls.Primitives.Thumb> durante una operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="632de-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="632de-115">En el ejemplo siguiente se define la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="632de-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="632de-116">El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> controlador de eventos que se mueve el <xref:System.Windows.Controls.Primitives.Thumb> y cambia el tamaño de la <xref:System.Windows.Controls.Canvas> en respuesta a un movimiento del mouse.</span><span class="sxs-lookup"><span data-stu-id="632de-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="632de-117">El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="632de-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="632de-118">El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="632de-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="632de-119">Para obtener un ejemplo completo, vea [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).</span><span class="sxs-lookup"><span data-stu-id="632de-119">For the complete sample, see [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="632de-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="632de-120">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
