---
title: Información general sobre controladores de eventos (Formularios Windows Forms)
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
ms.openlocfilehash: cab35250f4fedf0a08dc7198430a668c7428c207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567758"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="97ff2-102">Información general sobre controladores de eventos (Formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="97ff2-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="97ff2-103">Un controlador de eventos es un método que está enlazado a un evento.</span><span class="sxs-lookup"><span data-stu-id="97ff2-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="97ff2-104">Cuando se provoca el evento, se ejecuta el código del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="97ff2-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="97ff2-105">Cada controlador de eventos proporciona dos parámetros que permiten controlar el evento correctamente.</span><span class="sxs-lookup"><span data-stu-id="97ff2-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="97ff2-106">El ejemplo siguiente muestra un controlador de eventos para un <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="97ff2-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="97ff2-107">El primer parámetro,`sender`, proporciona una referencia al objeto que provocó el evento.</span><span class="sxs-lookup"><span data-stu-id="97ff2-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="97ff2-108">El segundo parámetro, `e`, en el ejemplo anterior, pasa un objeto específico al evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="97ff2-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="97ff2-109">Haciendo referencia a las propiedades del objeto (y, a veces, sus métodos), puede obtener información como la ubicación del puntero del mouse para los eventos del mouse o los datos que se transfieren en eventos de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="97ff2-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="97ff2-110">Normalmente, cada evento genera un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="97ff2-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="97ff2-111">Algunos controladores de eventos, como los relativos a la <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp> eventos, tienen el mismo tipo de objeto para el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="97ff2-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="97ff2-112">Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.</span><span class="sxs-lookup"><span data-stu-id="97ff2-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="97ff2-113">También puede usar el mismo controlador de eventos para controlar el mismo evento para los distintos controles.</span><span class="sxs-lookup"><span data-stu-id="97ff2-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="97ff2-114">Por ejemplo, si tiene un grupo de <xref:System.Windows.Forms.RadioButton> controles en un formulario, puede crear un único controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos y tener cada control <xref:System.Windows.Forms.Control.Click> eventos enlazados al controlador de eventos único.</span><span class="sxs-lookup"><span data-stu-id="97ff2-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="97ff2-115">Para obtener más información, vea [Cómo: Conectar varios eventos con un único controlador de eventos en Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="97ff2-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ff2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ff2-116">See also</span></span>
- [<span data-ttu-id="97ff2-117">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97ff2-117">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="97ff2-118">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="97ff2-118">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)
