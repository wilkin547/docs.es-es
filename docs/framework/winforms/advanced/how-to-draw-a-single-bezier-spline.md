---
title: 'Cómo: dibujar una sola B&#233;curva Spline de Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521341"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>Cómo: dibujar una sola B&#233;curva Spline de Bézier
Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un punto de conexión.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja una curva spline de Bézier con un punto de inicio (10, 100) y punto de conexión (200, 100). Los puntos de control son (100, 10) y (150, 150).  
  
 La siguiente ilustración muestra la curva spline de Bézier resultante junto con su punto inicial, puntos de control y punto de conexión. La ilustración también muestra convexa de la curva spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.  
  
 ![B-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [Curvas spline de Bézier en GDI+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [Dibujar una secuencia de curvas spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
