---
title: "C&#243;mo: Crear una l&#237;nea mediante la clase LineGeometry | Microsoft Docs"
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
  - "clases, LineGeometry"
  - "gráficos [WPF], líneas"
  - "LineGeometry (clase)"
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Crear una l&#237;nea mediante la clase LineGeometry
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.LineGeometry> para describir una línea.  Sus puntos inicial y final definen un elemento <xref:System.Windows.Media.LineGeometry>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.LineGeometry>.  Se utiliza un elemento <xref:System.Windows.Shapes.Path> para representar la línea.  Puesto que una línea no tiene área, no se especifica la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto <xref:System.Windows.Shapes.Path>; en su lugar se utilizan las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
Objeto LineGeometry dibujado desde \(10,20\) hasta \(100,130\)  
  
 Otras clases de geometrías simples son <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.  Estas geometrías, así como otras complejas, también se pueden crear utilizando una clase <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  Para obtener más información, vea [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)