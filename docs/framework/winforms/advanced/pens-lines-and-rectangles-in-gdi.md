---
title: Lápices, líneas y rectángulos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 84752773c0b56d9684dc31620d463d4ddccf9dad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641402"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Lápices, líneas y rectángulos en GDI+
Para dibujar líneas con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , deberá crear un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona los métodos que realmente realizan el dibujo, y el <xref:System.Drawing.Pen> objeto almacena atributos, como el estilo, ancho y color de línea.  
  
## <a name="drawing-a-line"></a>Dibujar una línea  
 Para dibujar una línea, llame a la <xref:System.Drawing.Graphics.DrawLine%2A> método de la <xref:System.Drawing.Graphics> objeto. El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawLine%2A> método. El ejemplo siguiente dibuja una línea desde el punto (4, 2) para el punto (12, 6):  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos. Por ejemplo, puede crear dos <xref:System.Drawing.Point> objetos y pase el <xref:System.Drawing.Point> objetos como argumentos para el <xref:System.Drawing.Graphics.DrawLine%2A> método:  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Creación de un lápiz  
 Puede especificar ciertos atributos al construir un <xref:System.Drawing.Pen> objeto. Por ejemplo, una `Pen` constructor permite especificar el color y ancho. En el ejemplo siguiente se dibuja una línea azul de ancho 2 de (0, 0) a (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Las líneas discontinuas y extremos de línea  
 El <xref:System.Drawing.Pen> objeto también expone propiedades, como <xref:System.Drawing.Pen.DashStyle%2A>, que puede usar para especificar las características de la línea. En el ejemplo siguiente se dibuja una línea discontinua de (100, 50) a (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Puede usar las propiedades de la <xref:System.Drawing.Pen> objeto para establecer muchos más atributos de la línea. El <xref:System.Drawing.Pen.StartCap%2A> y <xref:System.Drawing.Pen.EndCap%2A> propiedades especifican la apariencia de los extremos de la línea; los extremos pueden ser sin formato, cuadrados, redondeado, triangular, o una forma personalizada. El <xref:System.Drawing.Pen.LineJoin%2A> propiedad le permite especificar si líneas conectadas son ángulo (unidas con esquinas en ángulo), biseladas, redondeadas o recorta. La siguiente ilustración muestra las líneas con varios estilos de extremo y combinación.  
  
 ![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Dibuja un rectángulo  
 Dibujar rectángulos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es similar a dibujar las líneas. Para dibujar un rectángulo, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona un <xref:System.Drawing.Graphics.DrawRectangle%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el color y ancho de línea. El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawRectangle%2A> método. En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en (100, 50), un ancho de 80 y un alto de 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos. Por ejemplo, puede construir un <xref:System.Drawing.Rectangle> objeto y pase el <xref:System.Drawing.Rectangle> de objeto para el <xref:System.Drawing.Graphics.DrawRectangle%2A> método como argumento:  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Un <xref:System.Drawing.Rectangle> objeto tiene propiedades y métodos para manipular y recopilar información sobre el rectángulo. Por ejemplo, el <xref:System.Drawing.Rectangle.Inflate%2A> y <xref:System.Drawing.Rectangle.Offset%2A> métodos cambian el tamaño y posición del rectángulo. El <xref:System.Drawing.Rectangle.IntersectsWith%2A> método indica si el rectángulo forma una intersección con otra dada rectángulo y el <xref:System.Drawing.Rectangle.Contains%2A> método indica si un punto determinado está dentro del rectángulo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [Cómo: Crear un lápiz](how-to-create-a-pen.md)
- [Cómo: Dibujar una línea en un formulario de Windows](how-to-draw-a-line-on-a-windows-form.md)
- [Cómo: Dibujar una forma con contorno](how-to-draw-an-outlined-shape.md)
