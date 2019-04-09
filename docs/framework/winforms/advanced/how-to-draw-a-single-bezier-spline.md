---
title: Filtrar Dibujar un único B&#233;Spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171683"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Filtrar Dibujar un único B&#233;Spline de Bézier
Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un punto de conexión.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja una curva spline de Bézier con el punto inicial (10, 100) y el punto de conexión (200, 100). Los puntos de control son (100, 10) y (150, 150).  
  
 La siguiente ilustración muestra la curva spline de Bézier resultante junto con su punto de inicio y puntos de control de punto de conexión. La ilustración también muestra las forma convexa de spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.  
  
 ![Ilustración de una curva Bézier Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Curvas spline de Bézier en GDI+](bezier-splines-in-gdi.md)
- [Filtrar para dibujar una secuencia de curvas spline de Bézier](how-to-draw-a-sequence-of-bezier-splines.md)
