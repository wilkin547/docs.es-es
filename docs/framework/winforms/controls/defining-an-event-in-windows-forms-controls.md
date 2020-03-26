---
title: Definir un evento en controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: a4738373b10fbcb1d2406406d30f10b795aeb914
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228843"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="c284e-102">Definir un evento en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c284e-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="c284e-103">Para obtener más información sobre cómo definir eventos personalizados, consulte [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c284e-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="c284e-104">Si define un evento que no tiene datos asociados, use el tipo base de datos de evento, <xref:System.EventArgs>, y use <xref:System.EventHandler> como delegado de evento.</span><span class="sxs-lookup"><span data-stu-id="c284e-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="c284e-105">Todo lo que queda por hacer es `On`definir un miembro de evento y un método *EventName* protegido que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="c284e-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="c284e-106">El fragmento de código siguiente muestra cómo el control personalizado `FlashTrackBar` define un evento personalizado `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="c284e-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="c284e-107">Para obtener el `FlashTrackBar` código completo del ejemplo, vea [Cómo: crear un control](how-to-create-a-windows-forms-control-that-shows-progress.md)de formularios Windows Forms que muestra el progreso .</span><span class="sxs-lookup"><span data-stu-id="c284e-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
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
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c284e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c284e-108">See also</span></span>

- [<span data-ttu-id="c284e-109">Eventos de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c284e-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="c284e-110">Eventos</span><span class="sxs-lookup"><span data-stu-id="c284e-110">Events</span></span>](../../../standard/events/index.md)
