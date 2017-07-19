---
title: "Definir un evento en los controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles personalizados [Windows Forms], eventos mediante código"
  - "eventos [Windows Forms], definir en controles personalizados de Windows Forms"
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Definir un evento en los controles de formularios Windows Forms
Para obtener información detallada sobre cómo definir eventos personalizados, vea [Eventos](../../../../docs/standard/events/index.md).  Si define un evento que no tiene datos asociados, use el tipo base de datos de evento, <xref:System.EventArgs>, y use <xref:System.EventHandler> como delegado de evento.  Todo lo que queda por hacer es definir un miembro de evento y un método `On`*EventName* protegido que genera el evento.  
  
 El fragmento de código siguiente muestra cómo el control personalizado `FlashTrackBar` define un evento personalizado `ValueChanged`.  Para obtener el código completo de la muestra de `FlashTrackBar`, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
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
   protected virtual void OnValueChanged(EventArgs e) {  
      if (ValueChanged != null) {  
         ValueChanged(this, e);  
      }  
   }  
}  
```  
  
## Vea también  
 [Eventos de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Eventos](../../../../docs/standard/events/index.md)   
 [Eventos](../../../../docs/standard/events/index.md)