---
title: 'Cómo: Copiar píxeles para reducir el parpadeo'
ms.date: 03/30/2017
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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182584"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="57b66-102">Cómo: Copiar píxeles para reducir el parpadeo en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57b66-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="57b66-103">Al animar un gráfico simple, los usuarios a veces pueden encontrar parpadeo u otros efectos visuales indeseables.</span><span class="sxs-lookup"><span data-stu-id="57b66-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="57b66-104">Una manera de limitar este problema es utilizar un proceso "bitblt" en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="57b66-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="57b66-105">Bitblt es la "transferencia de bloque de bits" de los datos de color de un rectángulo de origen de píxeles a un rectángulo de destino de píxeles.</span><span class="sxs-lookup"><span data-stu-id="57b66-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="57b66-106">Con Windows Forms, bitblt <xref:System.Drawing.Graphics.CopyFromScreen%2A> se realiza <xref:System.Drawing.Graphics> mediante el método de la clase.</span><span class="sxs-lookup"><span data-stu-id="57b66-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="57b66-107">En los parámetros del método, especifique el origen y el destino (como puntos), el tamaño del área que se va a copiar y el objeto gráfico utilizado para dibujar la nueva forma.</span><span class="sxs-lookup"><span data-stu-id="57b66-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="57b66-108">En el ejemplo siguiente, se dibuja una <xref:System.Windows.Forms.Control.Paint> forma en el formulario en su controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="57b66-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="57b66-109">A continuación, se utiliza el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método para duplicar la forma.</span><span class="sxs-lookup"><span data-stu-id="57b66-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57b66-110">Establecer la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> del `true` formulario en hará que <xref:System.Windows.Forms.Control.Paint> el código basado en gráficos en el evento se almacena en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="57b66-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="57b66-111">Aunque esto no tendrá ninguna ganancia de rendimiento discernible al usar el código siguiente, es algo a tener en cuenta cuando se trabaja con código de manipulación de gráficos más complejo.</span><span class="sxs-lookup"><span data-stu-id="57b66-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57b66-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57b66-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="57b66-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="57b66-113">Compiling the Code</span></span>  
 <span data-ttu-id="57b66-114">El código anterior se ejecuta <xref:System.Windows.Forms.Control.Paint> en el controlador de eventos del formulario para que los gráficos persistan cuando se vuelve a dibujar el formulario.</span><span class="sxs-lookup"><span data-stu-id="57b66-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="57b66-115">Por lo tanto, no llame a <xref:System.Windows.Forms.Form.Load> métodos relacionados con gráficos en el controlador de eventos, porque el contenido dibujado no se volverá a dibujar si otro formulario cambia de tamaño u oscurece el formulario.</span><span class="sxs-lookup"><span data-stu-id="57b66-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b66-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57b66-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="57b66-117">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57b66-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="57b66-118">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="57b66-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
