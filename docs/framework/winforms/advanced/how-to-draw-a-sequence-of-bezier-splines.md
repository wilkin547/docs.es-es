---
title: Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 1de2f44be189cb2ff874a748ae6093c945120178
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711806"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier
Puede usar el <xref:System.Drawing.Graphics.DrawBeziers%2A> método de la <xref:System.Drawing.Graphics> conectado de clase para dibujar una secuencia de curvas spline de Bézier.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja una curva que consta de dos curvas spline de Bézier conectadas. El punto de conexión de la primera curva spline de Bézier es el punto inicial de la segunda curva spline de Bézier.  
  
 La siguiente ilustración muestra las curvas spline conectada junto con los siete puntos.  
  
 ![Curva Bézier Spline](./media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Curvas spline de Bézier en GDI+](bezier-splines-in-gdi.md)
- [Crear y dibujar curvas](constructing-and-drawing-curves.md)
