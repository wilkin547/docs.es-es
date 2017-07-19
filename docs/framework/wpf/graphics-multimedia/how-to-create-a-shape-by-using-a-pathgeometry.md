---
title: "C&#243;mo: Crear una forma mediante una clase PathGeometry | Microsoft Docs"
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
  - "clases, PathGeometry"
  - "gráficos [WPF], formas"
  - "PathGeometry (clase)"
  - "formas, crear con la clase PathGeometry"
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear una forma mediante una clase PathGeometry
En este ejemplo se muestra cómo crear un a forma mediante la clase <xref:System.Windows.Media.PathGeometry>.  Los objetos <xref:System.Windows.Media.PathGeometry> se componen de uno o más objetos <xref:System.Windows.Media.PathFigure>; cada <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente.  Cada <xref:System.Windows.Media.PathFigure>, a su vez, está compuesta de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales representa una parte conectada de la figura o forma.  Los tipos de segmentos incluyen: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment> y <xref:System.Windows.Media.BezierSegment>.  
  
## Ejemplo  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.PathGeometry> para crear un triángulo.  <xref:System.Windows.Media.PathGeometry> se muestra mediante un elemento <xref:System.Windows.Shapes.Path>.  
  
 [!code-xml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 En la ilustración siguiente se muestra la forma creada en el ejemplo anterior.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.png "wcpsdk\_graphicsmm\_pathgeometry\_triangle")  
Triángulo creado con un objeto PathGeometry  
  
 En el ejemplo anterior se ha mostrado cómo crear una forma relativamente simple, un triángulo.  <xref:System.Windows.Media.PathGeometry> también se puede utilizar para crear formas más complejas, incluidos arcos y curvas.  Para obtener ejemplos, vea [Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md) y [Crea una curva Bézier cuadrática.](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Vea también  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Ejemplo Geometries](http://go.microsoft.com/fwlink/?LinkID=159989)