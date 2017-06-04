---
title: "C&#243;mo: Dibujar una secuencia de curvas spline de B&#233;zier | Microsoft Docs"
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
  - "curvas spline de Bézier, dibujar secuencia"
  - "curvas spline, dibujar Bézier"
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Dibujar una secuencia de curvas spline de B&#233;zier
Puede utilizar el método <xref:System.Drawing.Graphics.DrawBeziers%2A> de la clase <xref:System.Drawing.Graphics> para dibujar una secuencia de curvas spline de Bézier conectadas.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja una curva formada por dos curvas spline de Bézier conectadas.  El extremo de la primera curva spline de Bézier es el punto de inicio de la segunda curva spline de Bézier.  
  
 En la ilustración siguiente se muestran la curvas spline conectadas y los siete puntos.  
  
 ![B&#45;spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Curvas spline de Bézier en GDI\+](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)   
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)