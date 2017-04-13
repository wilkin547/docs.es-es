---
title: "C&#243;mo: Definir un rect&#225;ngulo usando una clase RectangleGeometry | Microsoft Docs"
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
  - "clases, RectangleGeometry"
  - "gráficos [WPF], rectángulos"
  - "RectangleGeometry (clase)"
  - "rectángulos, crear con la clase RectangleGeometry"
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Definir un rect&#225;ngulo usando una clase RectangleGeometry
En este ejemplo se describe cómo utilizar la clase <xref:System.Windows.Media.RectangleGeometry> para describir un rectángulo.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.RectangleGeometry>.  Una estructura <xref:System.Windows.Rect> define la posición y las dimensiones relativas del rectángulo.  La posición relativa es `50,50`; por su parte, el alto y el ancho son ambos `25`, con lo que se crea un cuadrado.  El interior del rectángulo se pinta con un pincel <xref:System.Windows.Media.Brushes.LemonChiffon%2A> y su contorno se pinta con un trazo <xref:System.Windows.Media.Brushes.Black%2A> cuyo grosor es `1`.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
Objeto RectangleGeometry  
  
 Aunque en este ejemplo se utilizó un elemento <xref:System.Windows.Shapes.Path> para representar <xref:System.Windows.Media.RectangleGeometry>, hay muchas otras maneras de utilizar los objetos <xref:System.Windows.Media.RectangleGeometry>.  Por ejemplo, se puede utilizar <xref:System.Windows.Media.RectangleGeometry> para especificar la propiedad <xref:System.Windows.UIElement.Clip%2A> de <xref:System.Windows.UIElement> o la propiedad <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de <xref:System.Windows.Media.GeometryDrawing>.  
  
 Otras clases de geometrías simples son <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.  Estas geometrías, así como otras complejas, también se pueden crear utilizando una clase <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  
  
## Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)