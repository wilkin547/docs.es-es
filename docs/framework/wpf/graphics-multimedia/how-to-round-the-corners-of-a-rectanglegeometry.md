---
title: "C&#243;mo: Redondear las esquinas de un RectangleGeometry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "esquinas, redondeo"
  - "gráficos, redondear las esquinas de objetos RectangleGeometry"
  - "RectangleGeometry (clase), redondear esquinas"
  - "redondear las esquinas de objetos RectangleGeometry"
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Redondear las esquinas de un RectangleGeometry
Para redondear las esquinas de un objeto <xref:System.Windows.Media.RectangleGeometry>, establezca las propiedades <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> en un valor mayor que cero.  Cuanto mayores sean los valores, más redondeadas serán las esquinas del rectángulo.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran varios objetos <xref:System.Windows.Media.RectangleGeometry> con distintos valores de <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  Los objetos <xref:System.Windows.Media.RectangleGeometry> se muestran mediante elementos <xref:System.Windows.Shapes.Path>.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rectángulos con diferentes valores de RadiusX y RadiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm\_rounded")  
Rectángulos con esquinas redondeadas  
  
## Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)