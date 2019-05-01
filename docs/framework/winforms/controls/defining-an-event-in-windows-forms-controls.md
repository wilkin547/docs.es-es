---
title: Definir un evento en los controles de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: 4235c8b3c513509023388112071e78cfd079ec6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972346"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="5cca2-102">Definir un evento en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cca2-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="5cca2-103">Para obtener más información acerca de cómo definir eventos personalizados, vea [eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="5cca2-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="5cca2-104">Si define un evento que no tiene datos asociados, use el tipo base de datos de evento, <xref:System.EventArgs>, y use <xref:System.EventHandler> como delegado de evento.</span><span class="sxs-lookup"><span data-stu-id="5cca2-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="5cca2-105">Todo lo que queda por hacer es definir un miembro de evento y protegido `On` *EventName* método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="5cca2-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="5cca2-106">El fragmento de código siguiente muestra cómo el control personalizado `FlashTrackBar` define un evento personalizado `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="5cca2-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="5cca2-107">Para obtener el código completo para el `FlashTrackBar` de ejemplo, vea el [Cómo: Crear un Control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="5cca2-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate   
   ' as the event delegate.          
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined   
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged   
   ' event when the value has actually   
   ' changed. Derived controls can override this method.    
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate   
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined   
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually   
   // changed. Derived controls can override this method.    
   protected virtual void OnValueChanged(EventArgs e) 
   {  
       ValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cca2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cca2-108">See also</span></span>

- [<span data-ttu-id="5cca2-109">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5cca2-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="5cca2-110">Eventos</span><span class="sxs-lookup"><span data-stu-id="5cca2-110">Events</span></span>](../../../standard/events/index.md)
