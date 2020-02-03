---
title: Información general sobre controladores de eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743464"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="c42c1-102">Información general sobre controladores de eventos (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c42c1-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="c42c1-103">Un controlador de eventos es un método que está enlazado a un evento.</span><span class="sxs-lookup"><span data-stu-id="c42c1-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="c42c1-104">Cuando se genera el evento, se ejecuta el código del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c42c1-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="c42c1-105">Cada controlador de eventos proporciona dos parámetros que permiten controlar el evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="c42c1-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="c42c1-106">En el ejemplo siguiente se muestra un controlador de eventos para un evento de <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="c42c1-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="c42c1-107">El primer parámetro,`sender`, proporciona una referencia al objeto que generó el evento.</span><span class="sxs-lookup"><span data-stu-id="c42c1-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="c42c1-108">El segundo parámetro, `e`, en el ejemplo anterior, pasa un objeto específico del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="c42c1-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="c42c1-109">Al hacer referencia a las propiedades del objeto (y, a veces, a sus métodos), puede obtener información como la ubicación del mouse para los eventos del mouse o los datos que se transfieren en los eventos de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="c42c1-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="c42c1-110">Normalmente, cada evento genera un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="c42c1-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="c42c1-111">Algunos controladores de eventos, como los de los eventos <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp>, tienen el mismo tipo de objeto para el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="c42c1-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="c42c1-112">Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.</span><span class="sxs-lookup"><span data-stu-id="c42c1-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="c42c1-113">También puede usar el mismo controlador de eventos para controlar el mismo evento para los diferentes controles.</span><span class="sxs-lookup"><span data-stu-id="c42c1-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="c42c1-114">Por ejemplo, si tiene un grupo de <xref:System.Windows.Forms.RadioButton> controles en un formulario, puede crear un único controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> y hacer que el evento <xref:System.Windows.Forms.Control.Click> de cada control esté enlazado al controlador de eventos único.</span><span class="sxs-lookup"><span data-stu-id="c42c1-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="c42c1-115">Para obtener más información, consulte [Cómo: conectar varios eventos a un solo controlador de eventos en Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c42c1-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42c1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c42c1-116">See also</span></span>

- [<span data-ttu-id="c42c1-117">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c42c1-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="c42c1-118">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="c42c1-118">Events Overview</span></span>](events-overview-windows-forms.md)
