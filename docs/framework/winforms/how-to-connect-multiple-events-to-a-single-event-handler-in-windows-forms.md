---
title: 'Cómo: conectar varios eventos a un solo controlador de eventos'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739610"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="32393-102">Cómo: Conectar varios eventos con un único controlador de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32393-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="32393-103">En el diseño de la aplicación, es posible que sea necesario usar un solo controlador de eventos para varios eventos o que varios eventos realicen el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="32393-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="32393-104">Por ejemplo, a menudo es un eficaz ahorro de tiempo para que un comando de menú genere el mismo evento que un botón en el formulario, si expone la misma funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="32393-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="32393-105">Para ello, puede usar la vista eventos del ventana Propiedades en C# o utilizar la palabra clave `Handles` y los cuadros de lista desplegable nombre de **clase** y nombre de **método** en el editor de código Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="32393-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="32393-106">Para conectar varios eventos a un solo controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32393-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="32393-107">Haga clic con el botón secundario en el formulario y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="32393-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="32393-108">En el cuadro de lista desplegable **nombre de clase** , seleccione uno de los controles que desea que tengan el identificador de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="32393-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="32393-109">En el cuadro de lista desplegable **nombre de método** , seleccione uno de los eventos que desea que controle el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="32393-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="32393-110">El editor de código inserta el controlador de eventos adecuado y coloca el punto de inserción en el método.</span><span class="sxs-lookup"><span data-stu-id="32393-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="32393-111">En el ejemplo siguiente, es el evento <xref:System.Windows.Forms.Control.Click> para el control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="32393-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="32393-112">Anexe los otros eventos que desea que se controlen a la cláusula `Handles`.</span><span class="sxs-lookup"><span data-stu-id="32393-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="32393-113">Agregue el código adecuado al controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="32393-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="32393-114">Para conectar varios eventos a un solo controlador de eventos en C\#</span><span class="sxs-lookup"><span data-stu-id="32393-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="32393-115">Seleccione el control al que desea conectar un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="32393-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="32393-116">En el ventana Propiedades, haga clic en el botón **eventos** (![botón eventos](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="32393-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="32393-117">Haga clic en el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="32393-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="32393-118">En la sección valor junto al nombre del evento, haga clic en el botón desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="32393-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="32393-119">Seleccione en la lista el controlador de eventos adecuado.</span><span class="sxs-lookup"><span data-stu-id="32393-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="32393-120">Se agregará código al formulario para enlazar el evento al controlador de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="32393-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32393-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="32393-121">See also</span></span>

- [<span data-ttu-id="32393-122">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32393-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="32393-123">Información general sobre controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="32393-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
