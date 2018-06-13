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
ms.openlocfilehash: fc41158e9a3d5d331b391f0f28701612012becf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537221"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="0dca5-102">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="0dca5-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="0dca5-103">Los pasos básicos para reemplazar un evento definido en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] son idénticos y se resumen en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="0dca5-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="0dca5-104">Para reemplazar un evento heredado</span><span class="sxs-lookup"><span data-stu-id="0dca5-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="0dca5-105">Invalidar el protegido `On` *EventName* método.</span><span class="sxs-lookup"><span data-stu-id="0dca5-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="0dca5-106">Llame a la `On` *EventName* método de la clase base desde el invalidado `On` *EventName* método, para que los delegados registrados reciban el evento.</span><span class="sxs-lookup"><span data-stu-id="0dca5-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="0dca5-107">El <xref:System.Windows.Forms.Control.Paint> eventos se explica con detalle aquí porque cada control de formularios Windows Forms debe reemplazar el <xref:System.Windows.Forms.Control.Paint> eventos que hereda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="0dca5-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="0dca5-108">La base de <xref:System.Windows.Forms.Control> clase no sabe cómo debe dibujarse un control derivado y no proporciona ninguna lógica de dibujo en el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0dca5-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0dca5-109">El <xref:System.Windows.Forms.Control.OnPaint%2A> método <xref:System.Windows.Forms.Control> simplemente envía el <xref:System.Windows.Forms.Control.Paint> evento a los receptores de eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="0dca5-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="0dca5-110">Si ha trabajado en el ejemplo en [Cómo: desarrollar un Control de Windows Forms Simple](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), ha visto un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0dca5-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0dca5-111">El siguiente fragmento de código se toma del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0dca5-111">The following code fragment is taken from that sample.</span></span>  
  
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
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="0dca5-112">El <xref:System.Windows.Forms.PaintEventArgs> clase contiene datos para el <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="0dca5-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="0dca5-113">Tiene dos propiedades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0dca5-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="0dca5-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> es el rectángulo que se va a pintar y el <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad hace referencia a un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="0dca5-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="0dca5-115">Las clases en el <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres se administran las clases que proporcionan acceso a la funcionalidad de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], la nueva biblioteca gráfica de Windows.</span><span class="sxs-lookup"><span data-stu-id="0dca5-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="0dca5-116">La <xref:System.Drawing.Graphics> objeto tiene métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.</span><span class="sxs-lookup"><span data-stu-id="0dca5-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="0dca5-117">Un control invoca su <xref:System.Windows.Forms.Control.OnPaint%2A> método siempre que sea necesario para cambiar su apariencia visual.</span><span class="sxs-lookup"><span data-stu-id="0dca5-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="0dca5-118">Este método provoca a su vez el <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="0dca5-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dca5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dca5-119">See Also</span></span>  
 [<span data-ttu-id="0dca5-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="0dca5-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="0dca5-121">Representar un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dca5-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="0dca5-122">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dca5-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
