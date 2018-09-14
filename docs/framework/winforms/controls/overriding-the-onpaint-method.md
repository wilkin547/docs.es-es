---
title: Reemplazar el método OnPaint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: fbc0a82f82afcc59384246b58437d521d56d708b
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756280"
---
# <a name="overriding-the-onpaint-method"></a>Reemplazar el método OnPaint
Los pasos básicos para reemplazar un evento definido en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] son idénticos y se resumen en la lista siguiente.  
  
#### <a name="to-override-an-inherited-event"></a>Para reemplazar un evento heredado  
  
1.  Invalidar protegido `On` *EventName* método.  
  
2.  Llame a la `On` *EventName* método de la clase base desde invalidado `On` *EventName* método, por lo que los delegados registrados reciban el evento.  
  
 El <xref:System.Windows.Forms.Control.Paint> evento se explica en detalle aquí porque cada control de Windows Forms debe reemplazar el <xref:System.Windows.Forms.Control.Paint> eventos que hereda de <xref:System.Windows.Forms.Control>. La base de <xref:System.Windows.Forms.Control> no sabe cómo debe dibujarse un control derivado de clase y no proporciona ninguna lógica de dibujo en el <xref:System.Windows.Forms.Control.OnPaint%2A> método. El <xref:System.Windows.Forms.Control.OnPaint%2A> método <xref:System.Windows.Forms.Control> simplemente envía el <xref:System.Windows.Forms.Control.Paint> eventos a los receptores de eventos registrado.  
  
 Si ha trabajado en el ejemplo de [Cómo: desarrollar un Control de formularios de Windows Simple](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), ha visto un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método. El fragmento de código siguiente procede de ese ejemplo.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 El <xref:System.Windows.Forms.PaintEventArgs> clase contiene los datos de la <xref:System.Windows.Forms.Control.Paint> eventos. Tiene dos propiedades, como se muestra en el código siguiente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es el rectángulo que se va a pintar y el <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad hace referencia a un <xref:System.Drawing.Graphics> objeto. Las clases en el <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres se administran las clases que proporcionan acceso a la funcionalidad de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], la nueva biblioteca de gráficos de Windows. La <xref:System.Drawing.Graphics> objeto tiene métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.  
  
 Un control invoca su <xref:System.Windows.Forms.Control.OnPaint%2A> método cada vez que necesita cambiar su apariencia visual. Este método a su vez provoca la <xref:System.Windows.Forms.Control.Paint> eventos.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../../docs/standard/events/index.md)  
 [Representar un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [Definir un evento en los controles de Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
