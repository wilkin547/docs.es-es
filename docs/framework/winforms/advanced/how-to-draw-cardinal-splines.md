---
title: "Cómo: Dibujar curvas spline cardinales"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c47ff269cb1c367abee0be197fdc80485fb37b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-cardinal-splines"></a>Cómo: Dibujar curvas spline cardinales
Una curva spline cardinal es una curva que pasa suavemente por un determinado conjunto de puntos. Para dibujar una curva spline cardinal, cree un <xref:System.Drawing.Graphics> objeto y pasar la dirección de una matriz de puntos para la <xref:System.Drawing.Graphics.DrawCurve%2A> método.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Dibujar una curva Cardinal Spline en forma de campana  
  
-   En el ejemplo siguiente se dibuja una curva spline cardinal en forma de campana que pasa por cinco puntos designados. En la siguiente ilustración se muestra la curva y cinco puntos.  
  
     ![Curva cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Dibujar una curva Cardinal Spline cerrada  
  
-   Use la <xref:System.Drawing.Graphics.DrawClosedCurve%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar una curva spline cardinal cerrada. En una curva spline cardinal cerrada, la curva continúa hasta el último punto de la matriz y se conecta con el primer punto de la matriz. En el ejemplo siguiente se dibuja una curva spline cardinal cerrada que pasan a través de seis puntos designados. La siguiente ilustración muestra la curva spline cerrada y los seis puntos.  
  
 ![Curva cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Cambiar la curva de una curva Cardinal Spline  
  
-   Cambiar la manera en que se dobla una curva spline cardinal pasando un argumento de tensión para el <xref:System.Drawing.Graphics.DrawCurve%2A> método. En el ejemplo siguiente se dibuja tres curvas spline cardinales que pasan por el mismo conjunto de puntos. La siguiente ilustración muestra las tres curvas spline junto con sus valores de tensión. Tenga en cuenta que cuando la tensión es 0, los puntos se conectan mediante líneas rectas.  
  
 ![Curva cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
