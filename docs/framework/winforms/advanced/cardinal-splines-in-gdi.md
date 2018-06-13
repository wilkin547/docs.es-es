---
title: Curvas spline cardinales en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 93ae09c72415fa489e62f753e51e5a3ffcfb2425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517970"
---
# <a name="cardinal-splines-in-gdi"></a>Curvas spline cardinales en GDI+
Una curva spline cardinal es una secuencia de curvas individuales combinadas para formar una curva mayor. La curva spline se especifica mediante una matriz de puntos y un parámetro de tensión. Una curva spline cardinal pasa suavemente por cada punto de la matriz; hay sin esquinas definidas y ningún cambio abrupto en la tensión de la curva. En la siguiente ilustración muestra un conjunto de puntos y una curva spline cardinal que pasa por cada punto en el conjunto.  
  
 ![Curva cardinal Spline](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Curvas spline física y matemática  
 Una curva spline física es un trozo fino de madera u otros materiales flexible. Antes de la llegada de b-spline matemática, los diseñadores utilizaban curvas spline físicas para dibujar curvas. Un diseñador podría colocar la curva spline en una hoja de papel y anclarlo a un conjunto determinado de puntos. El diseñador, a continuación, podría crear una curva dibujando a lo largo de la curva spline con un lápiz o un lápiz. Un conjunto determinado de puntos podría generar una variedad de curvas, según las propiedades de la curva spline física. Por ejemplo, una curva spline con una resistencia alta a doblar generaría una curva distinta que una curva spline extremadamente flexible.  
  
 Las fórmulas para curvas spline matemáticas se basan en las propiedades de barras flexibles, por lo que las curvas creadas por curvas spline matemáticas son similares a las curvas que han generado una vez curvas spline físicas. Como curvas spline físicas de distinta tensión generan curvas diferentes a través de un conjunto determinado de puntos, curvas spline matemáticas con valores diferentes para el parámetro de tensión generan curvas diferentes a través de un conjunto determinado de puntos. La siguiente ilustración muestra cuatro curvas spline cardinales que pasan por el mismo conjunto de puntos. Se muestra la tensión de cada curva spline. Una tensión de 0 se corresponde con una tensión física infinita, forzar la curva a tomar el camino más corto (líneas rectas) entre los puntos. Una tensión de 1 corresponde a ninguna tensión física, lo que permite la curva spline tomar la ruta de acceso de menor curvatura total. Con valores de tensión superiores a 1, la curva se comporta como un muelle comprimido, empuja para tomar una ruta más larga.  
  
 ![Curvas spline cardinales](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 Las cuatro curvas spline en la ilustración anterior comparten la misma línea tangente en el punto inicial. La tangente es la línea que se dibuja desde el punto de partida hasta el siguiente punto a lo largo de la curva. Del mismo modo, la tangente compartida en el punto final es la línea que se dibuja desde el punto final hasta el punto anterior en la curva.  
  
 Para dibujar una curva spline cardinal, necesita una instancia de la <xref:System.Drawing.Graphics> (clase), un <xref:System.Drawing.Pen>y una matriz de <xref:System.Drawing.Point> objetos de la instancia de la <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.DrawCurve%2A> método, que se dibuja la curva spline, y el <xref:System.Drawing.Pen> almacena los atributos de la curva spline, como el color y ancho de línea. La matriz de <xref:System.Drawing.Point> objetos almacena los puntos que pasará la curva. En el ejemplo de código siguiente se muestra cómo dibujar una curva spline cardinal que atraviesa los puntos en `myPointArray`. El tercer parámetro es la tensión.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vea también  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
