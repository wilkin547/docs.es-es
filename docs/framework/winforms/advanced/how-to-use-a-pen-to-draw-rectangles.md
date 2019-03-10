---
title: Filtrar Utilizar lápiz para dibujar rectángulos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 2441687cb36d0780b7fbc935c5cb0edc74bc6ba0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712180"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Filtrar Utilizar lápiz para dibujar rectángulos
Para dibujar rectángulos, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawRectangle%2A> método y el <xref:System.Drawing.Pen> objeto almacena las características de la línea, como el color y ancho.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en (10, 10). El rectángulo tiene un ancho de 100 y un alto de 50. El segundo argumento pasado a la <xref:System.Drawing.Pen.%23ctor%2A> constructor indica que el ancho del lápiz es 5 píxeles.  
  
 Cuando se dibuja el rectángulo, el lápiz está centrado en el límite del rectángulo. Dado que el ancho del lápiz es 5, los lados del rectángulo son 5 píxeles amplia, de modo que 1 píxel se dibuja en el límite, se dibujan 2 píxeles dentro y 2 píxeles se dibujan en el exterior. Para obtener más detalles sobre la alineación del lápiz, consulte [Cómo: Establezca el ancho del lápiz y la alineación](how-to-set-pen-width-and-alignment.md).  
  
 La siguiente ilustración muestra el rectángulo resultante. Las líneas de puntos muestran donde hubiera dibujado el rectángulo si el ancho del lápiz hubiera sido un píxel. La vista ampliada de la esquina superior izquierda del rectángulo muestra que las líneas negras gruesas se centran en las líneas de puntos.  
  
 ![Lápices](./media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
