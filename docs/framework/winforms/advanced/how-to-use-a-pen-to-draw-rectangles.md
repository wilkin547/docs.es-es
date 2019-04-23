---
title: Procedimiento para usar un lápiz para dibujar rectángulos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 0e51a1e3a2d14754147dbd36f170127a7e978acd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074617"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Procedimiento para usar un lápiz para dibujar rectángulos
Para dibujar rectángulos, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawRectangle%2A> método y el <xref:System.Drawing.Pen> objeto almacena las características de la línea, como el color y ancho.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en (10, 10). El rectángulo tiene un ancho de 100 y un alto de 50. El segundo argumento pasado a la <xref:System.Drawing.Pen.%23ctor%2A> constructor indica que el ancho del lápiz es 5 píxeles.  
  
 Cuando se dibuja el rectángulo, el lápiz está centrado en el límite del rectángulo. Dado que el ancho del lápiz es 5, los lados del rectángulo son 5 píxeles amplia, de modo que 1 píxel se dibuja en el límite, se dibujan 2 píxeles dentro y 2 píxeles se dibujan en el exterior. Para obtener más detalles sobre la alineación del lápiz, consulte [Cómo: Establezca el ancho del lápiz y la alineación](how-to-set-pen-width-and-alignment.md).  
  
 La siguiente ilustración muestra el rectángulo resultante. Las líneas de puntos muestran donde hubiera dibujado el rectángulo si el ancho del lápiz hubiera sido un píxel. La vista ampliada de la esquina superior izquierda del rectángulo muestra que las líneas negras gruesas se centran en las líneas de puntos.  
  
 ![Captura de pantalla que muestra el rectángulo dibujado con negro y las líneas de puntos.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también

- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
