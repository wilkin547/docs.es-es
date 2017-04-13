---
title: "Trazados de gr&#225;ficos en GDI+ | Microsoft Docs"
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
  - "dibujar, rutas de acceso"
  - "GDI+, dibujar trazados"
  - "gráficos, rutas de acceso"
  - "rutas de acceso, dibujar"
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Trazados de gr&#225;ficos en GDI+
Los trazados se forman mediante la combinación de líneas, rectángulos y curvas simples.  Recuerde que, tal y como se muestra en [Información general acerca de gráficos vectoriales](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md), los siguientes bloques de creación han resultado ser los más útiles para dibujar imágenes:  
  
-   Líneas  
  
-   Rectángulos  
  
-   Elipses  
  
-   Arcos  
  
-   Polígonos  
  
-   Curvas spline cardinales  
  
-   Curvas spline de Bézier  
  
 En GDI\+, el objeto <xref:System.Drawing.Drawing2D.GraphicsPath> permite recopilar una secuencia de estos bloques de creación en una unidad.  La secuencia completa de líneas, rectángulos, polígonos y curvas puede dibujarse con una llamada al método <xref:System.Drawing.Graphics.DrawPath%2A> de la clase <xref:System.Drawing.Graphics> En la siguiente ilustración se muestra un trazado creado mediante la combinación de una línea, un arco, una curva spline de Bézier y una curva spline cardinal.  
  
 ![Ruta de acceso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.png "Aboutgdip02\_art14")  
  
## Utilizar un trazado  
 La clase <xref:System.Drawing.Drawing2D.GraphicsPath> proporciona los métodos siguientes para crear una secuencia de elementos que se va a dibujar: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> \(para las curvas spline cardinales\) y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.  Cada uno de estos métodos está sobrecargado, es decir, cada método admite varias listas de parámetros distintas.  Por ejemplo, una variación del método <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> recibe cuatro enteros y otra variación del método <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> recibe dos objetos <xref:System.Drawing.Point>.  
  
 Los métodos para agregar líneas, rectángulos y curvas spline de Bézier tienen métodos asociados plurales que agregan varios elementos al trazado en una única llamada: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.  Además, los métodos <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> tienen métodos asociados, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> que agregan una curva cerrada o sector al trazado.  
  
 Para dibujar un trazado son necesarios los objetos <xref:System.Drawing.Graphics>,  <xref:System.Drawing.Pen> y <xref:System.Drawing.Drawing2D.GraphicsPath>.  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawPath%2A>, y el objeto <xref:System.Drawing.Pen> almacena atributos como el ancho y el color de la línea que se utiliza para representar el trazado.  El objeto <xref:System.Drawing.Drawing2D.GraphicsPath> almacena la secuencia de líneas y curvas que componen el trazado.  El objeto <xref:System.Drawing.Pen> y el objeto <xref:System.Drawing.Drawing2D.GraphicsPath> se pasan como argumentos al método <xref:System.Drawing.Graphics.DrawPath%2A>.  En el siguiente ejemplo se dibuja un trazado que consta de una línea, una elipse y una curva spline de Bézier:  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 En la siguiente ilustración se muestra el trazado.  
  
 ![Ruta de acceso](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.png "Aboutgdip02\_art15")  
  
 Además de agregar líneas, rectángulos y curvas a un trazado, se pueden agregar trazados a un trazado.  Esto permite combinar los trazados existentes para formar trazados enormes y complejos.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Existen otros dos elementos que se pueden agregar a un trazado: cadenas y sectores.  Un sector es una parte del interior de una elipse.  En el siguiente ejemplo se crea un trazado a partir de un arco, un curva spline cardinal, una cadena y un sector:  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 En la siguiente ilustración se muestra el trazado.  Tenga en cuenta que un trazado no tiene por qué estar conectado; el arco, la curva spline cardinal, la cadena y el sector están separados.  
  
 ![Rutas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.png "Aboutgdip02\_Art16")  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)