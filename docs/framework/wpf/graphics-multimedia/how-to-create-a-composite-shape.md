---
title: "C&#243;mo: Crear una forma compuesta | Microsoft Docs"
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
  - "formas compuestas"
  - "gráficos, formas compuestas"
  - "formas, compuestos"
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear una forma compuesta
En este ejemplo se muestra cómo crear formas compuestas mediante objetos <xref:System.Windows.Media.Geometry> y mostrarlas utilizando un elemento <xref:System.Windows.Shapes.Path>.  En el ejemplo siguiente, se utilizan <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Media.RectangleGeometry> con <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta.  A continuación, las geometrías se dibujan mediante un elemento <xref:System.Windows.Shapes.Path>.  
  
## Ejemplo  
 [!code-xml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 En la ilustración siguiente se muestra la forma creada en el ejemplo anterior.  
  
 ![Geometría compuesta creada mediante GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.png "wcpsdk\_graphicsmm\_compositegeometryexample1")  
Geometría compuesta  
  
 Se pueden crear formas más complejas, tales como polígonos y formas con segmentos curvados, utilizando un objeto <xref:System.Windows.Media.PathGeometry>.  Para obtener un ejemplo que muestra cómo crear una forma mediante <xref:System.Windows.Media.PathGeometry>, vea [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Aunque en este ejemplo se representa una forma en la pantalla mediante un elemento <xref:System.Windows.Shapes.Path>, también se pueden utilizar objetos <xref:System.Windows.Media.Geometry> para describir el contenido de <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>.  Además, se pueden utilizar para el recorte y las pruebas de posicionamiento.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).