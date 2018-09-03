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
ms.openlocfilehash: 60ae01ca63f895bfb1c7aabbe3337596cd13933d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466274"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="02d4c-102">Definir un evento en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4c-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="02d4c-103">Para obtener más información acerca de cómo definir eventos personalizados, vea [eventos](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="02d4c-103">For details about defining custom events, see [Events](../../../../docs/standard/events/index.md).</span></span> <span data-ttu-id="02d4c-104">Si define un evento que no tiene datos asociados, use el tipo base de datos de evento, <xref:System.EventArgs>, y use <xref:System.EventHandler> como delegado de evento.</span><span class="sxs-lookup"><span data-stu-id="02d4c-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="02d4c-105">Todo lo que queda por hacer es definir un miembro de evento y protegido `On` *EventName* método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="02d4c-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="02d4c-106">El fragmento de código siguiente muestra cómo el control personalizado `FlashTrackBar` define un evento personalizado `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="02d4c-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="02d4c-107">Para obtener el código completo para el `FlashTrackBar` de ejemplo, vea el [Cómo: crear un Windows Forms Control que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="02d4c-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02d4c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d4c-108">See also</span></span>

- [<span data-ttu-id="02d4c-109">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4c-109">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
- [<span data-ttu-id="02d4c-110">Eventos</span><span class="sxs-lookup"><span data-stu-id="02d4c-110">Events</span></span>](../../../../docs/standard/events/index.md)
