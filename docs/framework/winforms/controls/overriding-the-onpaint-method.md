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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="5ce74-102">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="5ce74-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="5ce74-103">Los pasos básicos para reemplazar cualquier evento definido en .NET Framework son idénticos y se resumen en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ce74-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="5ce74-104">Para anular un evento heredado</span><span class="sxs-lookup"><span data-stu-id="5ce74-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="5ce74-105">Invalidar el `On`protegido *EventName* método.</span><span class="sxs-lookup"><span data-stu-id="5ce74-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="5ce74-106">Llame al método *EventName* de la `On`clase base desde el método *EventName* invalidado, para que los delegados registrados reciban el evento. `On`</span><span class="sxs-lookup"><span data-stu-id="5ce74-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="5ce74-107">El <xref:System.Windows.Forms.Control.Paint> evento se describe en detalle aquí porque <xref:System.Windows.Forms.Control.Paint> cada control de <xref:System.Windows.Forms.Control>formularios Windows Forms debe invalidar el evento del que hereda .</span><span class="sxs-lookup"><span data-stu-id="5ce74-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="5ce74-108">La <xref:System.Windows.Forms.Control> clase base no sabe cómo se debe dibujar un control derivado <xref:System.Windows.Forms.Control.OnPaint%2A> y no proporciona ninguna lógica de pintura en el método.</span><span class="sxs-lookup"><span data-stu-id="5ce74-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5ce74-109">El <xref:System.Windows.Forms.Control.OnPaint%2A> método <xref:System.Windows.Forms.Control> de simplemente <xref:System.Windows.Forms.Control.Paint> distribuye el evento a los receptores de eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="5ce74-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="5ce74-110">Si ha trabajado a través del ejemplo en [Cómo: desarrollar un](how-to-develop-a-simple-windows-forms-control.md)control de <xref:System.Windows.Forms.Control.OnPaint%2A> formularios Windows Forms simple , ha visto un ejemplo de invalidación del método.</span><span class="sxs-lookup"><span data-stu-id="5ce74-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5ce74-111">El siguiente fragmento de código se toma de ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5ce74-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="5ce74-112">La <xref:System.Windows.Forms.PaintEventArgs> clase contiene <xref:System.Windows.Forms.Control.Paint> datos para el evento.</span><span class="sxs-lookup"><span data-stu-id="5ce74-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="5ce74-113">Tiene dos propiedades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ce74-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="5ce74-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>es el rectángulo que se <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> va a <xref:System.Drawing.Graphics> pintar, y la propiedad hace referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="5ce74-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5ce74-115">Las clases <xref:System.Drawing?displayProperty=nameWithType> del espacio de nombres son clases administradas que proporcionan acceso a la funcionalidad de GDI+, la nueva biblioteca de gráficos de Windows.</span><span class="sxs-lookup"><span data-stu-id="5ce74-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="5ce74-116">El <xref:System.Drawing.Graphics> objeto tiene métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.</span><span class="sxs-lookup"><span data-stu-id="5ce74-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="5ce74-117">Un control invoca <xref:System.Windows.Forms.Control.OnPaint%2A> su método cada vez que necesita cambiar su visualización visual.</span><span class="sxs-lookup"><span data-stu-id="5ce74-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="5ce74-118">Este método a su <xref:System.Windows.Forms.Control.Paint> vez provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="5ce74-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce74-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ce74-119">See also</span></span>

- [<span data-ttu-id="5ce74-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="5ce74-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="5ce74-121">Representar un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ce74-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="5ce74-122">Definir un evento en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ce74-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
