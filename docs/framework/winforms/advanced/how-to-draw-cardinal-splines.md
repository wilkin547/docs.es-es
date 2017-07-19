---
title: "C&#243;mo: Dibujar curvas spline cardinales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "curvas spline cardinales, dibujar"
  - "dibujar, curvas spline cardinales"
  - "gráficos, curvas spline cardinales"
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Dibujar curvas spline cardinales
Una curva spline cardinal es una curva que pasa suavemente por un determinado conjunto de puntos.  Para dibujar una curva spline cardinal, cree un objeto <xref:System.Drawing.Graphics> y pase la dirección de una matriz de puntos al método <xref:System.Drawing.Graphics.DrawCurve%2A>.  
  
### Dibujar una curva spline cardinal en forma de campana  
  
-   En el siguiente ejemplo se dibuja una curva spline cardinal en forma de campana que pasa por cinco puntos designados.  En la siguiente ilustración se muestran la curva y los cinco puntos.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### Dibujar una curva spline cardinal cerrada  
  
-   Utilice el método <xref:System.Drawing.Graphics.DrawClosedCurve%2A> de la clase <xref:System.Drawing.Graphics> para dibujar una curva spline cardinal cerrada.  En una curva spline cardinal cerrada, la curva pasa por el último punto de la matriz y conecta con el primer punto de la matriz.  En el siguiente ejemplo se dibuja una curva spline cardinal cerrada que pasa por seis puntos designados.  En la ilustración siguiente se muestran la curva spline cardinal cerrada y los seis puntos.  
  
 ![Curva spline cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### Cambiar la inclinación de una curva spline cardinal  
  
-   Se puede cambiar la inclinación de una curva spline cardinal pasando un argumento de tensión al método <xref:System.Drawing.Graphics.DrawCurve%2A>.  En el siguiente ejemplo se dibujan tres curvas spline cardinales que pasan por el mismo conjunto de puntos.  En la ilustración siguiente se muestran las tres curvas spline con sus valores de tensión.  Observe que cuando la tensión es 0, los puntos quedan conectados por líneas rectas.  
  
 ![Curva spline cardinal](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## Compilar el código  
 Los ejemplos anteriores están diseñados para formularios Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)