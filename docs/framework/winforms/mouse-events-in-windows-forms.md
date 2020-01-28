---
title: Eventos del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 4909f56fc3935848fd18bc35c1cb56b5407a24c8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740966"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="6d950-102">Eventos del mouse (ratón) en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d950-102">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="6d950-103">Cuando se controla la entrada de mouse, normalmente desea conocer la ubicación del puntero del mouse y el estado de los botones del mismo.</span><span class="sxs-lookup"><span data-stu-id="6d950-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="6d950-104">En este tema se describe cómo obtener esta información de los eventos del mouse y explica el orden en que se generan los eventos de clic del mouse en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d950-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="6d950-105">Para obtener una lista y una descripción de todos los eventos del mouse, vea [Cómo funciona la entrada del mouse en Windows Forms](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6d950-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="6d950-106">Vea también [información general sobre los controladores de eventos (Windows Forms)](event-handlers-overview-windows-forms.md) y la [información general sobre eventos (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6d950-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="6d950-107">Información del mouse</span><span class="sxs-lookup"><span data-stu-id="6d950-107">Mouse Information</span></span>

<span data-ttu-id="6d950-108">Se envía un <xref:System.Windows.Forms.MouseEventArgs> a los controladores de eventos del mouse relacionados con hacer clic en un botón del mouse y el seguimiento de los movimientos del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d950-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="6d950-109"><xref:System.Windows.Forms.MouseEventArgs> proporciona información sobre el estado actual del mouse, incluida la ubicación del puntero del mouse en coordenadas de cliente, qué botones del mouse se presionan y si se ha desplazado la rueda del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d950-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="6d950-110">Algunos eventos del mouse, como aquellos que simplemente notifican cuando el puntero del mouse entra o sale de los límites de un control, envían un <xref:System.EventArgs> al controlador de eventos sin más información.</span><span class="sxs-lookup"><span data-stu-id="6d950-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="6d950-111">Si quiere conocer el estado actual de los botones del mouse o la ubicación del puntero del mouse y no desea controlar un evento del mouse, también puede usar las propiedades <xref:System.Windows.Forms.Control.MouseButtons%2A> y <xref:System.Windows.Forms.Control.MousePosition%2A> de la clase <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="6d950-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="6d950-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> devuelve información acerca de qué botones del mouse están presionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="6d950-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="6d950-113"><xref:System.Windows.Forms.Control.MousePosition%2A> devuelve las coordenadas de pantalla del puntero del mouse y equivale al valor devuelto por <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="6d950-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="6d950-114">Conversión de coordenadas de pantalla y de cliente</span><span class="sxs-lookup"><span data-stu-id="6d950-114">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="6d950-115">Como alguna información de ubicación del mouse está en coordenadas de cliente y otra está en coordenadas de pantalla, puede que necesite convertir un punto de un sistema de coordenadas a otro.</span><span class="sxs-lookup"><span data-stu-id="6d950-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="6d950-116">Puede hacerlo fácilmente con los métodos <xref:System.Windows.Forms.Control.PointToClient%2A> y <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibles en la clase <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="6d950-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="6d950-117">Comportamiento estándar del evento de clic</span><span class="sxs-lookup"><span data-stu-id="6d950-117">Standard Click Event Behavior</span></span>

<span data-ttu-id="6d950-118">Si quiere controlar los eventos de clic del mouse en el orden correcto, necesita saber el orden en que se generan los eventos de clic en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d950-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="6d950-119">Todos los controles de Windows Forms generan los eventos de clic en el mismo orden cuando se presiona y se suelta un botón del mouse (independientemente de qué botón sea), excepto cuando se indique otra cosa para cada control en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="6d950-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="6d950-120">La siguiente lista muestra el orden de los eventos generados para un único clic del botón del mouse:</span><span class="sxs-lookup"><span data-stu-id="6d950-120">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="6d950-121">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="6d950-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="6d950-122">Evento<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="6d950-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="6d950-123">Evento<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="6d950-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="6d950-124">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="6d950-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="6d950-125">El siguiente es el orden de los eventos que se producen para un clic doble del botón del mouse:</span><span class="sxs-lookup"><span data-stu-id="6d950-125">The following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="6d950-126">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="6d950-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="6d950-127">Evento<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="6d950-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="6d950-128">Evento<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="6d950-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="6d950-129">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="6d950-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="6d950-130">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="6d950-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="6d950-131">Evento<xref:System.Windows.Forms.Control.DoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="6d950-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="6d950-132">(Esto puede variar según si el control en cuestión tiene el bit de estilo <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> establecido en `true` o no.</span><span class="sxs-lookup"><span data-stu-id="6d950-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="6d950-133">Para obtener más información sobre cómo establecer un bit <xref:System.Windows.Forms.ControlStyles>, consulte el método <xref:System.Windows.Forms.Control.SetStyle%2A>).</span><span class="sxs-lookup"><span data-stu-id="6d950-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="6d950-134">Evento<xref:System.Windows.Forms.Control.MouseDoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="6d950-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="6d950-135">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="6d950-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="6d950-136">Para obtener un ejemplo de código que muestra el orden de los eventos de clic del mouse, consulte [Cómo: controlar eventos de entrada del usuario en controles de Windows Forms](how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6d950-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="6d950-137">Controles individuales</span><span class="sxs-lookup"><span data-stu-id="6d950-137">Individual Controls</span></span>

<span data-ttu-id="6d950-138">Los controles siguientes no siguen el comportamiento estándar de los eventos de clic del mouse:</span><span class="sxs-lookup"><span data-stu-id="6d950-138">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <span data-ttu-id="6d950-139">Para el control <xref:System.Windows.Forms.ComboBox>, se produce el comportamiento de eventos que se describe a continuación si el usuario hace clic en el campo de edición, en el botón o en un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="6d950-139">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="6d950-140">Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-140">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-141">Clic con el botón secundario: no se generan eventos</span><span class="sxs-lookup"><span data-stu-id="6d950-141">Right click: No click events raised</span></span>

  - <span data-ttu-id="6d950-142">Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-142">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-143">Doble clic con el botón secundario: no se generan eventos</span><span class="sxs-lookup"><span data-stu-id="6d950-143">Right double-click: No click events raised</span></span>

- <span data-ttu-id="6d950-144">Controles <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> y <xref:System.Windows.Forms.CheckedListBox></span><span class="sxs-lookup"><span data-stu-id="6d950-144"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="6d950-145">Se produce el comportamiento de eventos que se describe a continuación cuando el usuario hace clic en cualquier parte dentro de estos controles.</span><span class="sxs-lookup"><span data-stu-id="6d950-145">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="6d950-146">Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-146">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-147">Clic con el botón secundario: no se generan eventos</span><span class="sxs-lookup"><span data-stu-id="6d950-147">Right click: No click events raised</span></span>

  - <span data-ttu-id="6d950-148">Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="6d950-148">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="6d950-149">Doble clic con el botón secundario: no se generan eventos</span><span class="sxs-lookup"><span data-stu-id="6d950-149">Right double-click: No click events raised</span></span>

- <span data-ttu-id="6d950-150">Control <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="6d950-150"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="6d950-151">Se produce el comportamiento de eventos que se describe a continuación solo cuando el usuario hace clic en los elementos del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6d950-151">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="6d950-152">No se genera ningún evento para los clics que se realizan en cualquier otro lugar del control.</span><span class="sxs-lookup"><span data-stu-id="6d950-152">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="6d950-153">Además de los eventos que se describen más adelante, están los eventos <xref:System.Windows.Forms.ListView.BeforeLabelEdit> y <xref:System.Windows.Forms.ListView.AfterLabelEdit>, que pueden resultarle de interés si quiere usar la validación con el control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6d950-153">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="6d950-154">Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-154">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-155">Clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-155">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-156">Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="6d950-156">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="6d950-157">Doble clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="6d950-157">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="6d950-158">Control <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="6d950-158"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="6d950-159">El comportamiento de eventos que se describe a continuación se produce solo cuando el usuario hace clic en los propios elementos o a la derecha de los elementos en el control <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6d950-159">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="6d950-160">No se genera ningún evento para los clics que se realizan en cualquier otro lugar del control.</span><span class="sxs-lookup"><span data-stu-id="6d950-160">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="6d950-161">Además de los eventos que se describen más adelante, están los eventos <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> y <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, que pueden resultarle de interés si quiere usar la validación con el control <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6d950-161">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="6d950-162">Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-162">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-163">Clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="6d950-163">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="6d950-164">Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="6d950-164">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="6d950-165">Doble clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="6d950-165">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="6d950-166">Comportamiento de dibujo de controles de alternancia</span><span class="sxs-lookup"><span data-stu-id="6d950-166">Painting behavior of toggle controls</span></span>

<span data-ttu-id="6d950-167">Los controles de alternancia, como los controles que derivan de la clase <xref:System.Windows.Forms.ButtonBase>, tienen el siguiente comportamiento de dibujo particular en combinación con los eventos de clic del mouse:</span><span class="sxs-lookup"><span data-stu-id="6d950-167">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="6d950-168">El usuario presiona el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d950-168">The user presses the mouse button.</span></span>

2. <span data-ttu-id="6d950-169">El control se dibuja en estado presionado.</span><span class="sxs-lookup"><span data-stu-id="6d950-169">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="6d950-170">Se genera el evento <xref:System.Windows.Forms.Control.MouseDown>.</span><span class="sxs-lookup"><span data-stu-id="6d950-170">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="6d950-171">El usuario suelta el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d950-171">The user releases the mouse button.</span></span>

5. <span data-ttu-id="6d950-172">El control se dibuja en estado no presionado.</span><span class="sxs-lookup"><span data-stu-id="6d950-172">The control paints in the raised state.</span></span>

6. <span data-ttu-id="6d950-173">Se genera el evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="6d950-173">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="6d950-174">Se genera el evento <xref:System.Windows.Forms.Control.MouseClick>.</span><span class="sxs-lookup"><span data-stu-id="6d950-174">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="6d950-175">Se genera el evento <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="6d950-175">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d950-176">Si el usuario mueve el puntero fuera del control de alternancia mientras el botón del mouse está presionado (sacar el mouse del control <xref:System.Windows.Forms.Button> mientras está presionado), el control de alternancia se dibujará en estado no presionado y solo se produce el evento <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="6d950-176">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="6d950-177">En este caso no se producen los eventos <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick>.</span><span class="sxs-lookup"><span data-stu-id="6d950-177">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d950-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d950-178">See also</span></span>

- [<span data-ttu-id="6d950-179">Entradas mediante el mouse en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d950-179">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
