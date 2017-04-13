---
title: "C&#243;mo: Crear una curva B&#233;zier c&#250;bica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "curvas Bézier, cúbicas"
  - "crear, curvas Bézier cúbicas"
  - "curvas Bézier cúbicas"
  - "curvas, Bézier cúbicas"
  - "gráficos, curvas Bézier cúbicas"
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear una curva B&#233;zier c&#250;bica
En este ejemplo se muestra cómo crear una curva Bézier cúbica.  Para crear una curva Bézier cúbica, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> y <xref:System.Windows.Media.BezierSegment>.  Para mostrar la geometría resultante, utilice un elemento <xref:System.Windows.Shapes.Path>, o bien utilícelo con <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>.  En los ejemplos siguientes, se dibuja una curva Bézier cúbica desde \(10, 100\) hasta \(300, 100\).  Los puntos de control de la curva son \(100, 0\) y \(200, 200\).  
  
## Ejemplo  
 \[xaml\]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de marcado abreviada para describir un trazado.  
  
 [!code-xml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 \[xaml\]  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede dibujar también una curva Bézier cúbica mediante etiquetas de objeto.  El código siguiente equivale al ejemplo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-xml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Vea también  
 [Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Crear un segmento de línea en una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)   
 [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)   
 [Crea una curva Bézier cuadrática.](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)