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
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182043"
---
# <a name="overriding-the-onpaint-method"></a>Reemplazar el método OnPaint
Los pasos básicos para reemplazar cualquier evento definido en .NET Framework son idénticos y se resumen en la lista siguiente.  
  
#### <a name="to-override-an-inherited-event"></a>Para anular un evento heredado  
  
1. Invalidar el `On`protegido *EventName* método.  
  
2. Llame al método *EventName* de la `On`clase base desde el método *EventName* invalidado, para que los delegados registrados reciban el evento. `On`  
  
 El <xref:System.Windows.Forms.Control.Paint> evento se describe en detalle aquí porque <xref:System.Windows.Forms.Control.Paint> cada control de <xref:System.Windows.Forms.Control>formularios Windows Forms debe invalidar el evento del que hereda . La <xref:System.Windows.Forms.Control> clase base no sabe cómo se debe dibujar un control derivado <xref:System.Windows.Forms.Control.OnPaint%2A> y no proporciona ninguna lógica de pintura en el método. El <xref:System.Windows.Forms.Control.OnPaint%2A> método <xref:System.Windows.Forms.Control> de simplemente <xref:System.Windows.Forms.Control.Paint> distribuye el evento a los receptores de eventos registrados.  
  
 Si ha trabajado a través del ejemplo en [Cómo: desarrollar un](how-to-develop-a-simple-windows-forms-control.md)control de <xref:System.Windows.Forms.Control.OnPaint%2A> formularios Windows Forms simple , ha visto un ejemplo de invalidación del método. El siguiente fragmento de código se toma de ese ejemplo.  
  
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
  
 La <xref:System.Windows.Forms.PaintEventArgs> clase contiene <xref:System.Windows.Forms.Control.Paint> datos para el evento. Tiene dos propiedades, como se muestra en el código siguiente.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>es el rectángulo que se <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> va a <xref:System.Drawing.Graphics> pintar, y la propiedad hace referencia a un objeto. Las clases <xref:System.Drawing?displayProperty=nameWithType> del espacio de nombres son clases administradas que proporcionan acceso a la funcionalidad de GDI+, la nueva biblioteca de gráficos de Windows. El <xref:System.Drawing.Graphics> objeto tiene métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.  
  
 Un control invoca <xref:System.Windows.Forms.Control.OnPaint%2A> su método cada vez que necesita cambiar su visualización visual. Este método a su <xref:System.Windows.Forms.Control.Paint> vez provoca el evento.  
  
## <a name="see-also"></a>Consulte también

- [Eventos](../../../standard/events/index.md)
- [Representar un control de formularios Windows Forms](rendering-a-windows-forms-control.md)
- [Definir un evento en los controles de formularios Windows Forms](defining-an-event-in-windows-forms-controls.md)
