---
title: Controlar la introducción de datos por el usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: 19bb494d6f478c8cb7adda770f441470c4b2d19f
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45533521"
---
# <a name="handling-user-input"></a><span data-ttu-id="a85a1-102">Controlar la introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="a85a1-102">Handling User Input</span></span>
<span data-ttu-id="a85a1-103">En este tema se describe los principales eventos de teclado y mouse proporcionados por <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a85a1-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a85a1-104">Al controlar un evento, los creadores de controles deben reemplazar el método `On`*EventName* protegido en lugar de asociar un delegado al evento.</span><span class="sxs-lookup"><span data-stu-id="a85a1-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="a85a1-105">Para hacer un repaso de los eventos, vea [Provocar eventos de un componente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="a85a1-105">For a review of events, see [Raising Events from a Component](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a85a1-106">Si no hay ningún dato asociado con un evento, una instancia de la clase base <xref:System.EventArgs> se pasa como argumento a la `On` *EventName* método.</span><span class="sxs-lookup"><span data-stu-id="a85a1-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="a85a1-107">Eventos de teclado</span><span class="sxs-lookup"><span data-stu-id="a85a1-107">Keyboard Events</span></span>  
 <span data-ttu-id="a85a1-108">Los eventos de teclado habituales que pueden controlar son <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, y <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="a85a1-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="a85a1-109">Nombre de evento</span><span class="sxs-lookup"><span data-stu-id="a85a1-109">Event Name</span></span>|<span data-ttu-id="a85a1-110">Método que se va a invalidar</span><span class="sxs-lookup"><span data-stu-id="a85a1-110">Method to Override</span></span>|<span data-ttu-id="a85a1-111">Descripción del evento</span><span class="sxs-lookup"><span data-stu-id="a85a1-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="a85a1-112">Se produce únicamente cuando se presiona una tecla por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a85a1-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="a85a1-113">Se produce cada vez que se presiona una tecla.</span><span class="sxs-lookup"><span data-stu-id="a85a1-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="a85a1-114">Si está presionada una tecla, un <xref:System.Windows.Forms.Control.KeyPress> se provoca el evento a la velocidad de repetición definida por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a85a1-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="a85a1-115">Se produce cuando se suelta una tecla.</span><span class="sxs-lookup"><span data-stu-id="a85a1-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a85a1-116">Controlar la entrada mediante teclado es mucho más complejo que invalidar los eventos de la tabla anterior y escapa al ámbito de este tema.</span><span class="sxs-lookup"><span data-stu-id="a85a1-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="a85a1-117">Para más información, consulte [Datos proporcionados por el usuario en Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a85a1-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="a85a1-118">Eventos del mouse</span><span class="sxs-lookup"><span data-stu-id="a85a1-118">Mouse Events</span></span>  
 <span data-ttu-id="a85a1-119">Los eventos del mouse que pueden controlar son <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, y <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="a85a1-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="a85a1-120">Nombre de evento</span><span class="sxs-lookup"><span data-stu-id="a85a1-120">Event Name</span></span>|<span data-ttu-id="a85a1-121">Método que se va a invalidar</span><span class="sxs-lookup"><span data-stu-id="a85a1-121">Method to Override</span></span>|<span data-ttu-id="a85a1-122">Descripción del evento</span><span class="sxs-lookup"><span data-stu-id="a85a1-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="a85a1-123">Se produce cuando se presiona un botón del mouse mientras el puntero del mouse está sobre el control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="a85a1-124">Se produce cuando el cursor del mouse entra por primera vez en la zona del control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="a85a1-125">Se produce cuando el puntero pasa por encima del control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="a85a1-126">Se produce cuando el puntero sale de la zona del control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="a85a1-127">Se produce cuando el puntero se desplaza por la zona del control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="a85a1-128">Se produce cuando se suelta el botón del mouse mientras el puntero está encima del control o sale de la zona del control.</span><span class="sxs-lookup"><span data-stu-id="a85a1-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="a85a1-129">El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseDown> eventos.</span><span class="sxs-lookup"><span data-stu-id="a85a1-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="a85a1-130">El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseMove> eventos.</span><span class="sxs-lookup"><span data-stu-id="a85a1-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="a85a1-131">El fragmento de código siguiente muestra un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.MouseUp> eventos.</span><span class="sxs-lookup"><span data-stu-id="a85a1-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="a85a1-132">Para obtener el código fuente completo del ejemplo `FlashTrackBar`, vea [Crear un control de Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="a85a1-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a85a1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a85a1-133">See Also</span></span>  
 [<span data-ttu-id="a85a1-134">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a85a1-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="a85a1-135">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a85a1-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="a85a1-136">Eventos</span><span class="sxs-lookup"><span data-stu-id="a85a1-136">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="a85a1-137">Datos proporcionados por el usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a85a1-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
