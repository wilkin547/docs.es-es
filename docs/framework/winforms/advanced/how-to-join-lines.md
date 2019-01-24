---
title: Procedimiento Unir líneas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 55551a78f37a5179b24eda28a9fc5d0a0c640a9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543388"
---
# <a name="how-to-join-lines"></a>Procedimiento Unir líneas
Una unión de líneas es el área común que está formado por dos líneas cuyos extremos se juntan o se superponen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona tres estilos de unión de línea: ángulo, bisel y redondo. Estilo de línea de combinación es una propiedad de la <xref:System.Drawing.Pen> clase. Cuando se especifica un estilo de unión de línea para un <xref:System.Drawing.Pen> objeto, que se aplicará a todas las líneas conectadas en cualquier estilo de unión <xref:System.Drawing.Drawing2D.GraphicsPath> dibujado con ese lápiz del objeto.  
  
 La siguiente ilustración muestra los resultados del ejemplo de unión de línea biselada.  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Ejemplo  
 Puede especificar el estilo de unión de línea mediante la <xref:System.Drawing.Pen.LineJoin%2A> propiedad de la <xref:System.Drawing.Pen> clase. El ejemplo muestra una combinación de línea biselada entre una línea horizontal y una línea vertical. En el código siguiente, el valor <xref:System.Drawing.Drawing2D.LineJoin.Bevel> asignado a la <xref:System.Drawing.Pen.LineJoin%2A> propiedad es un miembro de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración. Los demás miembros de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración son <xref:System.Drawing.Drawing2D.LineJoin.Miter> y <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
