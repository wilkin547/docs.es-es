---
title: "Curvas abiertas y cerradas en GDI+ | Microsoft Docs"
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
  - "curvas"
  - "curvas, dibujar"
  - "curvas, rellenar"
  - "GDI+, curvas"
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Curvas abiertas y cerradas en GDI+
En la siguiente ilustración se muestran dos curvas: una abierta y otra cerrada.  
  
 ![Curvas abiertas y cerradas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.png "Aboutgdip02\_art24")  
  
## Interfaz administrada para curvas  
 Las curvas cerradas tienen una parte interior y, por lo tanto, pueden rellenarse con un pincel.  La clase <xref:System.Drawing.Graphics> de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona los métodos siguientes para rellenar formas cerradas y curvas: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A> y <xref:System.Drawing.Graphics.FillRegion%2A>.  Siempre que llame a uno de estos métodos debe pasar uno de los tipos de pincel \(<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> o <xref:System.Drawing.Drawing2D.PathGradientBrush>\) como argumento.  
  
 El método <xref:System.Drawing.Graphics.FillPie%2A> está asociado al método <xref:System.Drawing.Graphics.DrawArc%2A>.  Del mismo modo que el método <xref:System.Drawing.Graphics.DrawArc%2A> dibuja una parte del contorno de una elipse, el método <xref:System.Drawing.Graphics.FillPie%2A> rellena una parte del interior de una elipse.  En el siguiente ejemplo se dibuja un arco y se rellena la parte correspondiente al interior de la elipse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 En la siguiente ilustración se muestra el arco y el sector relleno.  
  
 ![Curvas abiertas y cerradas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.png "Aboutgdip02\_art25")  
  
 El método <xref:System.Drawing.Graphics.FillClosedCurve%2A> está asociado al método <xref:System.Drawing.Graphics.DrawClosedCurve%2A>.  Ambos métodos cierran automáticamente la curva mediante la conexión del extremo con el punto inicial.  En el siguiente ejemplo se dibuja una curva que pasa por \(0, 0\), \(60, 20\) y \(40, 50\).  Después, la curva se cierra automáticamente mediante la conexión de \(40, 50\) con el punto inicial \(0, 0\), y el interior se rellena con un color sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 El método <xref:System.Drawing.Graphics.FillPath%2A> rellena el interior de los sectores independientes de un trazado.  Si un sector de un trazado no forma una forma o una curva cerrada, el método <xref:System.Drawing.Graphics.FillPath%2A> cierra este sector del trazado automáticamente antes de rellenarlo.  En el siguiente ejemplo se dibuja y se rellena un trazado compuesto por un arco, una curva spline cardinal, una cadena y un sector:  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 En la siguiente ilustración se muestra el trazado con y sin el relleno sólido.  Tenga en cuenta que el texto de la cadena tiene contorno, pero no se rellena, con el método <xref:System.Drawing.Graphics.DrawPath%2A>.  El método <xref:System.Drawing.Graphics.FillPath%2A> es el que pinta el interior de los caracteres de la cadena.  
  
 ![Cadena en un trayecto](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.png "Aboutgdip02\_art26")  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)