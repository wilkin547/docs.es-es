---
title: "Cómo: Copiar píxeles para reducir el parpadeo en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17253e21739911d4aa0541fde9ae205b0be1c5a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="8fded-102">Cómo: Copiar píxeles para reducir el parpadeo en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fded-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="8fded-103">Al animar un gráfico sencillo, los usuarios a veces pueden notar parpadeos u otros efectos visuales no deseados.</span><span class="sxs-lookup"><span data-stu-id="8fded-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="8fded-104">Una manera de limitar este problema es utilizar un proceso "bitblt" en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="8fded-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="8fded-105">BitBlt es la "bloque de bits transferencia" de los datos de color de un rectángulo de origen de píxeles a un rectángulo de destino de píxeles.</span><span class="sxs-lookup"><span data-stu-id="8fded-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="8fded-106">Con formularios Windows Forms, bitblt se realiza utilizando la <xref:System.Drawing.Graphics.CopyFromScreen%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="8fded-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="8fded-107">En los parámetros del método, especifique el origen y destino (como puntos), el tamaño del área que desea copiar y el objeto graphics utilizado para dibujar la nueva forma.</span><span class="sxs-lookup"><span data-stu-id="8fded-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="8fded-108">En el ejemplo siguiente, se dibuja una forma en el formulario en su <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8fded-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8fded-109">A continuación, la <xref:System.Drawing.Graphics.CopyFromScreen%2A> método se usa para duplicar la forma.</span><span class="sxs-lookup"><span data-stu-id="8fded-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fded-110">Configuración del formulario <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true` hará que el código basado en gráficos en el <xref:System.Windows.Forms.Control.Paint> evento ser doble búfer.</span><span class="sxs-lookup"><span data-stu-id="8fded-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="8fded-111">Aunque esto no tendrán las mejoras de rendimiento perceptible cuando se usa el código siguiente, es algo a tener en cuenta al trabajar con código más complejo de manipulación de gráficos.</span><span class="sxs-lookup"><span data-stu-id="8fded-111">While this will not have any discernable performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fded-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8fded-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fded-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8fded-113">Compiling the Code</span></span>  
 <span data-ttu-id="8fded-114">El código anterior se ejecuta en el formulario <xref:System.Windows.Forms.Control.Paint> controlador de eventos para que los gráficos se conservan cuando se vuelve a dibujarse el formulario.</span><span class="sxs-lookup"><span data-stu-id="8fded-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="8fded-115">Por lo tanto, no llame a métodos relacionados con gráficos el <xref:System.Windows.Forms.Form.Load> controlador de eventos, porque no se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño o lo ocultan con otra forma.</span><span class="sxs-lookup"><span data-stu-id="8fded-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fded-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fded-116">See Also</span></span>  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="8fded-117">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fded-117">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="8fded-118">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="8fded-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
