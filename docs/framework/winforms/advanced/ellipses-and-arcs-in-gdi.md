---
title: Elipses y arcos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117461"
---
# <a name="ellipses-and-arcs-in-gdi"></a>Elipses y arcos en GDI+
Dibujar elipses y arcos utilizando el <xref:System.Drawing.Graphics.DrawEllipse%2A> y <xref:System.Drawing.Graphics.DrawArc%2A> métodos de la <xref:System.Drawing.Graphics> clase.  
  
## <a name="drawing-an-ellipse"></a>Dibujar una elipse  
 Para dibujar una elipse, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawEllipse%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea utilizada para representar la elipse. El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawEllipse%2A> método. Los argumentos restantes se pasan a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método especifican el rectángulo delimitador de la elipse. La siguiente ilustración muestra una elipse junto con su rectángulo delimitador.  
  
 ![Elipses y arcos](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 En el ejemplo siguiente se dibuja una elipse; rectángulo que tiene un ancho de 80, un alto de 40 y una esquina superior izquierda de (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos. Por ejemplo, puede construir un <xref:System.Drawing.Rectangle> y pase el <xref:System.Drawing.Rectangle> a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método como argumento:  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Dibujar un arco  
 Un arco es una parte de una elipse. Para dibujar un arco, llame a la <xref:System.Drawing.Graphics.DrawArc%2A> método de la <xref:System.Drawing.Graphics> clase. Los parámetros de la <xref:System.Drawing.Graphics.DrawArc%2A> método son los mismos que los parámetros de la <xref:System.Drawing.Graphics.DrawEllipse%2A> método, salvo que <xref:System.Drawing.Graphics.DrawArc%2A> requiere un ángulo inicial y ángulo de barrido. El ejemplo siguiente dibuja un arco con un ángulo inicial de 30 grados y un ángulo de barrido de 180 grados:  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 La siguiente ilustración muestra el arco, la elipse y el rectángulo delimitador.  
  
 ![Elipses y arcos](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Filtrar para crear objetos gráficos para dibujar](how-to-create-graphics-objects-for-drawing.md)
- [Filtrar para crear un lápiz](how-to-create-a-pen.md)
- [Filtrar para dibujar una forma con contorno](how-to-draw-an-outlined-shape.md)
