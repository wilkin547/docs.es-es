---
title: B&#233;en GDI + curvas spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107333"
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;en GDI + curvas spline de Bézier
Una curva spline de Bézier es una curva especificada por cuatro puntos: dos puntos finales (p1 y p2) y dos puntos de control (c1 y c2). La curva comienza en p1 y termina en p2. La curva no pasa por los puntos de control, pero los puntos de control se comportan como imanes, extracción de la curva en ciertas direcciones e influyen en el modo en que la curva. La siguiente ilustración muestra una curva de Bézier junto con los extremos y los puntos de control.  
  
 ![Curvas spline de Bézier](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 La curva comienza en p1 y avanza hacia el punto de control c1. La tangente a la curva en p1 es la línea que va de p1 a c1. La línea tangente en el extremo p2 es la línea trazada desde c2 a p2.  
  
## <a name="drawing-bzier-splines"></a>Dibujar curvas spline de Bézier  
 Para dibujar una curva spline de Bézier, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Pen>. La instancia de la <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.DrawBezier%2A> método y el <xref:System.Drawing.Pen> almacena atributos, como el ancho y el color de la línea utilizada para representar la curva. El <xref:System.Drawing.Pen> se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawBezier%2A> método. Los argumentos restantes se pasan a la <xref:System.Drawing.Graphics.DrawBezier%2A> método son los puntos de conexión y los puntos de control. En el ejemplo siguiente se dibuja una curva spline de Bézier con el punto inicial (0, 0), control puntos (40, 20) y (80, 150) y un punto final (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 La siguiente ilustración muestra la curva, los puntos de control y dos líneas tangentes.  
  
 ![Curvas spline de Bézier](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Curvas spline de Bézier se desarrollaron originalmente Pierre Bézier para el diseño en la industria automotriz. Que ya que han demostrado para ser útil en muchos tipos de diseño asistido por ordenador y también se usan para definir los contornos de fuentes. Curvas spline de Bézier puede producir una gran variedad de formas, algunas de las cuales se muestran en la siguiente ilustración.  
  
 ![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Crear y dibujar curvas](constructing-and-drawing-curves.md)
- [Filtrar para crear objetos gráficos para dibujar](how-to-create-graphics-objects-for-drawing.md)
- [Filtrar para crear un lápiz](how-to-create-a-pen.md)
