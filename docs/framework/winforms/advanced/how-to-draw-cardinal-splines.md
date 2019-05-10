---
title: Procedimiento para dibujar curvas spline cardinales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 12e938567d529b33ead93e081d380a650a803f23
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626214"
---
# <a name="how-to-draw-cardinal-splines"></a>Procedimiento para dibujar curvas spline cardinales
Una curva spline cardinal es una curva que se pasa sin problemas a través de un conjunto determinado de puntos. Para dibujar una curva spline cardinal, cree un <xref:System.Drawing.Graphics> objeto y pasar la dirección de una matriz de puntos para el <xref:System.Drawing.Graphics.DrawCurve%2A> método.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Dibujar una curva Cardinal Spline en forma de campana  
  
- El ejemplo siguiente dibuja una curva spline cardinal en forma de campana que pasa por cinco puntos designados. La siguiente ilustración muestra la curva y cinco puntos.  
  
     ![Diagrama que muestra una curva spline cardinal en forma de campana.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Dibujar una curva Cardinal Spline cerrada  
  
- Use la <xref:System.Drawing.Graphics.DrawClosedCurve%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar una curva spline cardinal cerrada. En una curva spline cardinal cerrada, la curva continúa hasta el último punto de la matriz y se conecta con el primer punto de la matriz. El ejemplo siguiente dibuja una curva spline cardinal cerrada que pasa por seis puntos designados. La siguiente ilustración muestra la spline cerrada junto con los seis puntos:  
  
 ![Diagrama que muestra una curva spline cardinal cerrada.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Cambiar el plegado de una curva Cardinal Spline  
  
- Cambiar la forma en la inclinación de una curva spline cardinal pasando un argumento de tensión el <xref:System.Drawing.Graphics.DrawCurve%2A> método. El ejemplo siguiente dibuja tres curvas spline cardinales que pasan por el mismo conjunto de puntos. La siguiente ilustración muestra las tres curvas spline junto con sus valores de tensión. Tenga en cuenta que cuando la tensión es 0, los puntos están conectados mediante líneas rectas.  
  
 ![Diagrama que muestra tres curvas spline cardinales.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Crear y dibujar curvas](constructing-and-drawing-curves.md)
