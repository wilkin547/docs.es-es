---
title: Procedimiento Conectar varios eventos con un único controlador de eventos en Windows Forms
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
ms.openlocfilehash: 869ef0d7717ca64209bc61c2ae22ce929edcec5e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967872"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="bb685-102">Filtrar Conectar varios eventos con un único controlador de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb685-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="bb685-103">En el diseño de aplicaciones, puede que sea necesario para usar un único controlador de eventos para varios eventos o tener varios eventos de realizar el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bb685-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="bb685-104">Por ejemplo, a menudo es ahorrar mucho tiempo si un comando de menú producen el mismo evento que un botón en el formulario si expone la misma funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="bb685-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="bb685-105">Puede hacerlo mediante el uso de la vista eventos de la ventana Propiedades de C# o mediante el `Handles` palabra clave y el **nombre de la clase** y **nombre del método** listas desplegables en el Editor de código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bb685-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="bb685-106">Para conectar varios eventos con un único controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb685-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="bb685-107">Haga clic en el formulario y elija **ver código**.</span><span class="sxs-lookup"><span data-stu-id="bb685-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="bb685-108">Desde el **nombre de la clase** cuadro de lista desplegable, seleccione uno de los controles que desea agregar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bb685-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="bb685-109">Desde el **nombre del método** cuadro de lista desplegable, seleccione uno de los eventos que desea que el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bb685-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="bb685-110">El Editor de código se inserta el controlador de eventos adecuado y coloca el punto de inserción dentro del método.</span><span class="sxs-lookup"><span data-stu-id="bb685-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="bb685-111">En el ejemplo siguiente, es el <xref:System.Windows.Forms.Control.Click> eventos para el <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="bb685-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="bb685-112">Agregue los otros eventos que desea que administran el `Handles` cláusula.</span><span class="sxs-lookup"><span data-stu-id="bb685-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="bb685-113">Agregue el código adecuado para el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bb685-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="bb685-114">Para conectar varios eventos con un único controlador de eventos en C\#</span><span class="sxs-lookup"><span data-stu-id="bb685-114">To connect multiple events to a single event handler in C\#</span></span>
  
1.  <span data-ttu-id="bb685-115">Seleccione el control al que desea conectarse a un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bb685-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="bb685-116">En la ventana Propiedades, haga clic en el **eventos** botón (![botón eventos](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="bb685-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="bb685-117">Haga clic en el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="bb685-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="bb685-118">En la sección de valor junto al nombre del evento, haga clic en el botón de lista desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="bb685-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="bb685-119">Seleccione el controlador de eventos apropiado en la lista.</span><span class="sxs-lookup"><span data-stu-id="bb685-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="bb685-120">Se agregará código al formulario para enlazar el evento al controlador de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="bb685-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb685-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb685-121">See also</span></span>
- [<span data-ttu-id="bb685-122">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb685-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="bb685-123">Información general sobre controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="bb685-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
