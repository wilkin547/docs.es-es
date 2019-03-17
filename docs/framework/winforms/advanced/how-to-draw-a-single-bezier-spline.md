---
title: Procedimiento Dibujar un único B&#233;Spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 0731595dc25b1afb4b3dbcc7eedbfb92ef32d267
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "58126284"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Procedimiento Dibujar un único B&#233;Spline de Bézier
Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un punto de conexión.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja una curva spline de Bézier con el punto inicial (10, 100) y el punto de conexión (200, 100). Los puntos de control son (100, 10) y (150, 150).  
  
 La siguiente ilustración muestra la curva spline de Bézier resultante junto con su punto de inicio y puntos de control de punto de conexión. La ilustración también muestra las forma convexa de spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.  
  
 ![Ilustración de una curva Bézier Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Curvas spline de Bézier en GDI+](bezier-splines-in-gdi.md)
- [Cómo: Dibujar una secuencia de curvas spline de Bézier](how-to-draw-a-sequence-of-bezier-splines.md)
