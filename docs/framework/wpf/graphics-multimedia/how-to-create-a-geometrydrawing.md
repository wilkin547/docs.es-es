---
title: "C&#243;mo: Crear un objeto GeometryDrawing | Microsoft Docs"
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
  - "clases, GeometryDrawing"
  - "GeometryDrawing (clase)"
  - "gráficos, GeometryDrawing (clase)"
  - "formas representables"
  - "formas, representables"
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear un objeto GeometryDrawing
En este ejemplo se muestra cómo crear y mostrar un objeto <xref:System.Windows.Media.GeometryDrawing>.  <xref:System.Windows.Media.GeometryDrawing> permite crear la forma con un relleno y un contorno asociando un objeto <xref:System.Windows.Media.Pen> y <xref:System.Windows.Media.Brush> a un objeto <xref:System.Windows.Media.Geometry>.  <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la estructura de la forma, <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe el relleno de la forma y <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe el contorno de la forma.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.GeometryDrawing> para representar una forma.  La forma se describe mediante un objeto <xref:System.Windows.Media.GeometryGroup> y dos objetos <xref:System.Windows.Media.EllipseGeometry>.  El interior de la forma se pinta con <xref:System.Windows.Media.LinearGradientBrush> y su contorno se dibuja con un objeto <xref:System.Windows.Media.Pen> con la propiedad <xref:System.Windows.Media.Brushes.Black%2A>.  <xref:System.Windows.Media.GeometryDrawing> se muestra utilizando <xref:System.Windows.Media.ImageDrawing> y un elemento <xref:System.Windows.Controls.Image>.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 En la siguiente ilustración se muestra el objeto <xref:System.Windows.Media.GeometryDrawing> resultante.  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
  
 Para crear complejos más dibujos, puede combinar varios objetos de dibujo en un mismo dibujo compuesto utilizando un <xref:System.Windows.Media.DrawingGroup>.  
  
## Vea también  
 <xref:System.Windows.Media.DrawingGroup>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Crear un dibujo compuesto](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)