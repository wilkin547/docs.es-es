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
ms.openlocfilehash: 2b74b03137d5a450fb1e436a514877d1a17229ad
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654255"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier
Puede usar el <xref:System.Drawing.Graphics.DrawBeziers%2A> método de la <xref:System.Drawing.Graphics> conectado de clase para dibujar una secuencia de curvas spline de Bézier.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja una curva que consta de dos curvas spline de Bézier conectadas. El punto de conexión de la primera curva spline de Bézier es el punto inicial de la segunda curva spline de Bézier.  
  
 La siguiente ilustración muestra las curvas spline conectada junto con los siete puntos:  
  
 ![Gráfico que muestra las curvas spline conectada junto con los siete puntos.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Curvas spline de Bézier en GDI+](bezier-splines-in-gdi.md)
- [Crear y dibujar curvas](constructing-and-drawing-curves.md)
