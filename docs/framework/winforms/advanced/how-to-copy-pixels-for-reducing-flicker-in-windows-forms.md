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
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Cómo: Copiar píxeles para reducir el parpadeo en formularios Windows Forms
Al animar un gráfico simple, los usuarios a veces pueden encontrar parpadeo u otros efectos visuales indeseables. Una manera de limitar este problema es utilizar un proceso "bitblt" en el gráfico. Bitblt es la "transferencia de bloque de bits" de los datos de color de un rectángulo de origen de píxeles a un rectángulo de destino de píxeles.  
  
 Con Windows Forms, bitblt <xref:System.Drawing.Graphics.CopyFromScreen%2A> se realiza <xref:System.Drawing.Graphics> mediante el método de la clase. En los parámetros del método, especifique el origen y el destino (como puntos), el tamaño del área que se va a copiar y el objeto gráfico utilizado para dibujar la nueva forma.  
  
 En el ejemplo siguiente, se dibuja una <xref:System.Windows.Forms.Control.Paint> forma en el formulario en su controlador de eventos. A continuación, se utiliza el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método para duplicar la forma.  
  
> [!NOTE]
> Establecer la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> del `true` formulario en hará que <xref:System.Windows.Forms.Control.Paint> el código basado en gráficos en el evento se almacena en búfer doble. Aunque esto no tendrá ninguna ganancia de rendimiento discernible al usar el código siguiente, es algo a tener en cuenta cuando se trabaja con código de manipulación de gráficos más complejo.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
 El código anterior se ejecuta <xref:System.Windows.Forms.Control.Paint> en el controlador de eventos del formulario para que los gráficos persistan cuando se vuelve a dibujar el formulario. Por lo tanto, no llame a <xref:System.Windows.Forms.Form.Load> métodos relacionados con gráficos en el controlador de eventos, porque el contenido dibujado no se volverá a dibujar si otro formulario cambia de tamaño u oscurece el formulario.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
