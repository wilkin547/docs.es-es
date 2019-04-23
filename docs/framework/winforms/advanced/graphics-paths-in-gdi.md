---
title: Trazados de gráficos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140509"
---
# <a name="graphics-paths-in-gdi"></a>Trazados de gráficos en GDI+
Las rutas de acceso se crean mediante la combinación de líneas, rectángulos y curvas simples. Recuerde que en el [información general sobre gráficos de Vector](vector-graphics-overview.md) que los siguientes bloques de creación básicos han demostrado para ser útiles para dibujar imágenes:  
  
-   Líneas  
  
-   Rectángulos  
  
-   Botón de puntos suspensivos  
  
-   Arcos  
  
-   Polígonos  
  
-   Curvas spline cardinales  
  
-   Curvas spline de Bézier  
  
 En GDI +, el <xref:System.Drawing.Drawing2D.GraphicsPath> objeto le permite recopilar una secuencia de estos bloques de creación en una sola unidad. A continuación, se puede dibujar toda la secuencia de líneas, rectángulos, polígonos y curvas con una llamada a la <xref:System.Drawing.Graphics.DrawPath%2A> método de la <xref:System.Drawing.Graphics> clase. La siguiente ilustración muestra una ruta de acceso creado mediante la combinación de una línea, un arco, una curva spline de Bézier y una curva spline cardinal.  
  
 ![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Uso de una ruta de acceso  
 El <xref:System.Drawing.Drawing2D.GraphicsPath> clase proporciona los métodos siguientes para crear una secuencia de elementos que se va a dibujar: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (para curvas spline cardinales), y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>. Cada uno de estos métodos está sobrecargada; es decir, cada método es compatible con varias listas de parámetros. Por ejemplo, una variación de la <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> método recibe cuatro enteros y otra variación de la <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> método recibe dos <xref:System.Drawing.Point> objetos.  
  
 Los métodos para agregar líneas, rectángulos y curvas spline de Bézier a una ruta de acceso tienen varios métodos asociados que agregan varios elementos a la ruta de acceso en una sola llamada: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>. Además, el <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> disponen de métodos, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, que agregan una curva cerrada o un gráfico circular a la ruta de acceso.  
  
 Para dibujar un trazado, necesita un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Pen> objeto y un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawPath%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea utilizada para representar la ruta de acceso. La <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena la secuencia de líneas y curvas que conforman la ruta de acceso. El <xref:System.Drawing.Pen> objeto y el <xref:System.Drawing.Drawing2D.GraphicsPath> objeto se pasan como argumentos para el <xref:System.Drawing.Graphics.DrawPath%2A> método. El ejemplo siguiente dibuja una ruta de acceso que consta de una línea, una elipse y una curva spline de Bézier:  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 La siguiente ilustración muestra la ruta de acceso.  
  
 ![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Además de agregar líneas, rectángulos y curvas en una ruta de acceso, puede agregar rutas de acceso a una ruta de acceso. Esto le permite combinar trazados existentes para formar las rutas de acceso largas y complejas.  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Hay otros dos elementos que puede agregar a una ruta de acceso: cadenas y sectores. Un gráfico circular es una parte del interior de una elipse. El ejemplo siguiente crea una ruta de acceso de un arco, una curva spline cardinal, una cadena y un gráfico circular:  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 La siguiente ilustración muestra la ruta de acceso. Tenga en cuenta que no tiene una ruta de acceso que se puede conectar se separan del arco, curva spline cardinal, cadena y circulares.  
  
 ![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md)
- [Crear y dibujar trazados](constructing-and-drawing-paths.md)
