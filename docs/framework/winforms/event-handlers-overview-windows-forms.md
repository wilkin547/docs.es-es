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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141697"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="a2c30-102">Información general sobre controladores de eventos (Formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a2c30-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="a2c30-103">Un controlador de eventos es un método que está enlazado a un evento.</span><span class="sxs-lookup"><span data-stu-id="a2c30-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="a2c30-104">Cuando se genera el evento, se ejecuta el código dentro del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2c30-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="a2c30-105">Cada controlador de eventos proporciona dos parámetros que le permiten controlar el evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2c30-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="a2c30-106">En el ejemplo siguiente se <xref:System.Windows.Forms.Button> muestra <xref:System.Windows.Forms.Control.Click> un controlador de eventos para el evento de un control.</span><span class="sxs-lookup"><span data-stu-id="a2c30-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="a2c30-107">El primer`sender`parámetro, , proporciona una referencia al objeto que generó el evento.</span><span class="sxs-lookup"><span data-stu-id="a2c30-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="a2c30-108">El segundo `e`parámetro, , en el ejemplo anterior, pasa un objeto específico del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="a2c30-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="a2c30-109">Al hacer referencia a las propiedades del objeto (y, a veces, a sus métodos), puede obtener información como la ubicación del mouse para eventos del mouse o datos que se transfieren en eventos de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a2c30-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="a2c30-110">Normalmente, cada evento genera un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="a2c30-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="a2c30-111">Algunos controladores de eventos, <xref:System.Windows.Forms.Control.MouseDown> como <xref:System.Windows.Forms.Control.MouseUp> los de los eventos y los, tienen el mismo tipo de objeto para su segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="a2c30-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="a2c30-112">Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.</span><span class="sxs-lookup"><span data-stu-id="a2c30-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="a2c30-113">También puede usar el mismo controlador de eventos para controlar el mismo evento para diferentes controles.</span><span class="sxs-lookup"><span data-stu-id="a2c30-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="a2c30-114">Por ejemplo, si tiene <xref:System.Windows.Forms.RadioButton> un grupo de controles en un formulario, <xref:System.Windows.Forms.Control.Click> podría crear un <xref:System.Windows.Forms.Control.Click> único controlador de eventos para el evento y tener el evento de cada control enlazado al controlador de eventos único.</span><span class="sxs-lookup"><span data-stu-id="a2c30-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="a2c30-115">Para obtener más información, vea [Cómo: conectar varios eventos a un controlador](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)de eventos único en formularios Windows Forms .</span><span class="sxs-lookup"><span data-stu-id="a2c30-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c30-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2c30-116">See also</span></span>

- [<span data-ttu-id="a2c30-117">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2c30-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="a2c30-118">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="a2c30-118">Events Overview</span></span>](events-overview-windows-forms.md)
