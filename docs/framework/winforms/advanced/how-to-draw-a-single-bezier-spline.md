---
title: "C&#243;mo: Dibujar una curva spline de B&#233;zier | Microsoft Docs"
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
  - "curvas spline de Bézier, dibujar"
  - "dibujar, curvas spline de Bézier"
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Dibujar una curva spline de B&#233;zier
Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un extremo.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja una curva spline de Bézier con un punto de inicio \(10, 100\) y un extremo \(200, 100\).  Los puntos de control son \(100, 10\) y \(150, 150\).  
  
 En la ilustración siguiente se muestra la curva spline de Bézier resultante junto con su punto inicial, sus puntos de control y su extremo.  La ilustración muestra también la forma convexa de la curva spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.  
  
 ![B&#45;spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 <xref:System.Drawing.Graphics.DrawBezier%2A>   
 [Curvas spline de Bézier en GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Cómo: Dibujar una secuencia de curvas spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)