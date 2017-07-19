---
title: "Curvas spline de B&#233;zier en GDI+ | Microsoft Docs"
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
  - "curvas spline de Bézier"
  - "GDI+, curvas spline de Bézier"
  - "curvas spline, Bézier"
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Curvas spline de B&#233;zier en GDI+
Una curva spline de Bézier es una curva que se especifica con cuatro puntos: dos extremos \(p1 y p2\) y dos puntos de control \(c1 y c2\).  La curva comienza en p1 y acaba en p2.  La curva no pasa por los puntos de control, pero éstos se comportan como imanes y tiran de la curva en ciertas direcciones e influyen en el modo en que la curva se dobla.  En la siguiente ilustración se muestra una curva de Bézier con sus extremos y puntos de control.  
  
 ![Curvas spline de Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.png "Aboutgdip02\_art11a")  
  
 La curva comienza en p1 y avanza hacia el punto de control c1.  La línea tangente a la curva en p1 es la línea que va de p1 a c1.  La línea tangente en el extremo p2 es la línea que va de c2 a p2.  
  
## Dibujar curvas spline de Bézier  
 Para dibujar una curva spline de Bézier, necesita una instancia de la clase <xref:System.Drawing.Graphics> y <xref:System.Drawing.Pen>.  La instancia de la clase <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawBezier%2A> y <xref:System.Drawing.Pen> almacena los atributos, como el ancho y el color, de la línea utilizada para representar la curva.  <xref:System.Drawing.Pen> se pasa como uno de los argumentos del método <xref:System.Drawing.Graphics.DrawBezier%2A>.  El resto de los argumentos que se pasan al método <xref:System.Drawing.Graphics.DrawBezier%2A> son los extremos y los puntos de control.  En el siguiente ejemplo se dibuja una curva spline de Bézier con un punto inicial \(0, 0\), dos puntos de control \(40, 20\) y \(80, 150\), y un extremo \(100, 10\):  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 En la siguiente ilustración se muestra la curva, los puntos de control y dos líneas tangentes.  
  
 ![Curvas spline de Bézier](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.png "Aboutgdip02\_art12")  
  
 Pierre Bézier desarrolló originalmente las curvas spline de Bézier para el diseño en la industria del automóvil.  Desde entonces, han resultado muy útiles en muchos tipos de CAD \(*computer\-aided design*, diseño asistido por computadora\) y también se utilizan para definir los contornos de fuentes.  Las curvas spline de Bézier pueden generar una gran variedad de formas, algunas de las cuales se muestran en la siguiente ilustración.  
  
 ![Rutas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.png "Aboutgdip02\_art13")  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)