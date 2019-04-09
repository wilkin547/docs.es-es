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
ms.openlocfilehash: baf4e6cb3b2a40b1b792ae12e78cb9f878a738ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124311"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="f8cbd-102">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="f8cbd-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="f8cbd-103">Los pasos básicos para reemplazar un evento definido en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] son idénticos y se resumen en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="f8cbd-104">Para reemplazar un evento heredado</span><span class="sxs-lookup"><span data-stu-id="f8cbd-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="f8cbd-105">Invalidar protegido `On` *EventName* método.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="f8cbd-106">Llame a la `On` *EventName* método de la clase base desde invalidado `On` *EventName* método, por lo que los delegados registrados reciban el evento.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="f8cbd-107">El <xref:System.Windows.Forms.Control.Paint> evento se explica en detalle aquí porque cada control de Windows Forms debe reemplazar el <xref:System.Windows.Forms.Control.Paint> eventos que hereda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="f8cbd-108">La base de <xref:System.Windows.Forms.Control> no sabe cómo debe dibujarse un control derivado de clase y no proporciona ninguna lógica de dibujo en el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="f8cbd-109">El <xref:System.Windows.Forms.Control.OnPaint%2A> método <xref:System.Windows.Forms.Control> simplemente envía el <xref:System.Windows.Forms.Control.Paint> eventos a los receptores de eventos registrado.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="f8cbd-110">Si ha trabajado en el ejemplo de [Cómo: Desarrollar un Control de formularios de Windows Simple](how-to-develop-a-simple-windows-forms-control.md), ha visto un ejemplo de cómo reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="f8cbd-111">El fragmento de código siguiente procede de ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="f8cbd-112">El <xref:System.Windows.Forms.PaintEventArgs> clase contiene los datos de la <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="f8cbd-113">Tiene dos propiedades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <span data-ttu-id="f8cbd-114">es el rectángulo que se va a pintar y el <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad hace referencia a un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-114">is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f8cbd-115">Las clases en el <xref:System.Drawing?displayProperty=nameWithType> espacio de nombres se administran las clases que proporcionan acceso a la funcionalidad de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], la nueva biblioteca de gráficos de Windows.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="f8cbd-116">La <xref:System.Drawing.Graphics> objeto tiene métodos para dibujar puntos, cadenas, líneas, arcos, elipses y muchas otras formas.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="f8cbd-117">Un control invoca su <xref:System.Windows.Forms.Control.OnPaint%2A> método cada vez que necesita cambiar su apariencia visual.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="f8cbd-118">Este método a su vez provoca la <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8cbd-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8cbd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8cbd-119">See also</span></span>

- [<span data-ttu-id="f8cbd-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="f8cbd-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="f8cbd-121">Representar un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8cbd-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="f8cbd-122">Definir un evento</span><span class="sxs-lookup"><span data-stu-id="f8cbd-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
