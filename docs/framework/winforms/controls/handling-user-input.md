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
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934087"
---
# <a name="handling-user-input"></a><span data-ttu-id="334b4-102">Controlar la introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="334b4-102">Handling User Input</span></span>
<span data-ttu-id="334b4-103">En este tema se describen los eventos principales del teclado y <xref:System.Windows.Forms.Control?displayProperty=nameWithType>del mouse proporcionados por.</span><span class="sxs-lookup"><span data-stu-id="334b4-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="334b4-104">Al controlar un evento, los creadores de controles deben reemplazar el método `On`*EventName* protegido en lugar de asociar un delegado al evento.</span><span class="sxs-lookup"><span data-stu-id="334b4-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="334b4-105">Para hacer un repaso de los eventos, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="334b4-105">For a review of events, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="334b4-106">Si no hay ningún dato asociado a un evento, se pasa una instancia de la <xref:System.EventArgs> clase base como argumento `On`al método *eventName* .</span><span class="sxs-lookup"><span data-stu-id="334b4-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="334b4-107">Eventos de teclado</span><span class="sxs-lookup"><span data-stu-id="334b4-107">Keyboard Events</span></span>  
 <span data-ttu-id="334b4-108">Los eventos de teclado comunes que el control puede controlar <xref:System.Windows.Forms.Control.KeyDown>son <xref:System.Windows.Forms.Control.KeyPress>, y <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="334b4-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="334b4-109">Nombre de evento</span><span class="sxs-lookup"><span data-stu-id="334b4-109">Event Name</span></span>|<span data-ttu-id="334b4-110">Método que se va a invalidar</span><span class="sxs-lookup"><span data-stu-id="334b4-110">Method to Override</span></span>|<span data-ttu-id="334b4-111">Descripción del evento</span><span class="sxs-lookup"><span data-stu-id="334b4-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="334b4-112">Se produce únicamente cuando se presiona una tecla por primera vez.</span><span class="sxs-lookup"><span data-stu-id="334b4-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="334b4-113">Se produce cada vez que se presiona una tecla.</span><span class="sxs-lookup"><span data-stu-id="334b4-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="334b4-114">Si se mantiene presionada una tecla, <xref:System.Windows.Forms.Control.KeyPress> se genera un evento con la frecuencia de repetición definida por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="334b4-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="334b4-115">Se produce cuando se suelta una tecla.</span><span class="sxs-lookup"><span data-stu-id="334b4-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="334b4-116">Controlar la entrada mediante teclado es mucho más complejo que invalidar los eventos de la tabla anterior y escapa al ámbito de este tema.</span><span class="sxs-lookup"><span data-stu-id="334b4-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="334b4-117">Para más información, consulte [Datos proporcionados por el usuario en Windows Forms](../user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="334b4-117">For more information, see [User Input in Windows Forms](../user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="334b4-118">Eventos del mouse</span><span class="sxs-lookup"><span data-stu-id="334b4-118">Mouse Events</span></span>  
 <span data-ttu-id="334b4-119">Los eventos del mouse que el control puede controlar <xref:System.Windows.Forms.Control.MouseDown>son <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, y <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="334b4-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="334b4-120">Nombre de evento</span><span class="sxs-lookup"><span data-stu-id="334b4-120">Event Name</span></span>|<span data-ttu-id="334b4-121">Método que se va a invalidar</span><span class="sxs-lookup"><span data-stu-id="334b4-121">Method to Override</span></span>|<span data-ttu-id="334b4-122">Descripción del evento</span><span class="sxs-lookup"><span data-stu-id="334b4-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="334b4-123">Se produce cuando se presiona un botón del mouse mientras el puntero del mouse está sobre el control.</span><span class="sxs-lookup"><span data-stu-id="334b4-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="334b4-124">Se produce cuando el cursor del mouse entra por primera vez en la zona del control.</span><span class="sxs-lookup"><span data-stu-id="334b4-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="334b4-125">Se produce cuando el puntero pasa por encima del control.</span><span class="sxs-lookup"><span data-stu-id="334b4-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="334b4-126">Se produce cuando el puntero sale de la zona del control.</span><span class="sxs-lookup"><span data-stu-id="334b4-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="334b4-127">Se produce cuando el puntero se desplaza por la zona del control.</span><span class="sxs-lookup"><span data-stu-id="334b4-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="334b4-128">Se produce cuando se suelta el botón del mouse mientras el puntero está encima del control o sale de la zona del control.</span><span class="sxs-lookup"><span data-stu-id="334b4-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="334b4-129">En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseDown> cómo invalidar el evento.</span><span class="sxs-lookup"><span data-stu-id="334b4-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="334b4-130">En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseMove> cómo invalidar el evento.</span><span class="sxs-lookup"><span data-stu-id="334b4-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="334b4-131">En el fragmento de código siguiente se muestra un ejemplo de <xref:System.Windows.Forms.Control.MouseUp> cómo invalidar el evento.</span><span class="sxs-lookup"><span data-stu-id="334b4-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="334b4-132">Para obtener el código `FlashTrackBar` fuente completo del ejemplo, consulte [cómo: Cree un control de Windows Forms que muestre](how-to-create-a-windows-forms-control-that-shows-progress.md)el progreso.</span><span class="sxs-lookup"><span data-stu-id="334b4-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334b4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="334b4-133">See also</span></span>

- [<span data-ttu-id="334b4-134">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="334b4-134">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="334b4-135">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="334b4-135">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="334b4-136">Eventos</span><span class="sxs-lookup"><span data-stu-id="334b4-136">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="334b4-137">Datos proporcionados por el usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="334b4-137">User Input in Windows Forms</span></span>](../user-input-in-windows-forms.md)
