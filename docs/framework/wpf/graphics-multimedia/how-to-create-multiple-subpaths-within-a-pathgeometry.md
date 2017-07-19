---
title: "C&#243;mo: Crear varios subtrazados en un PathGeometry | Microsoft Docs"
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
  - "gráficos [WPF], subtrazados"
  - "varios subtrazados"
  - "PathGeometry (clase)"
  - "subtrazados"
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear varios subtrazados en un PathGeometry
Este ejemplo muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>.  Para crear varios subtrazados, se crea una figura <xref:System.Windows.Media.PathFigure> para cada uno de ellos.  
  
## Ejemplo  
 En el ejemplo siguiente se crean dos subtrazados, cada uno es un triángulo.  
  
 [!code-xml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 En el ejemplo siguiente se muestra cómo crear varios subtrazados mediante <xref:System.Windows.Shapes.Path> y la sintaxis de atributo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Cada `M` crea un nuevo subtrazado para que el ejemplo cree dos subtrazados, cada uno de los cuales dibuja un triángulo.  
  
 [!code-xml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 \(Tenga en cuenta que, en realidad, esta sintaxis de atributo crea un objeto <xref:System.Windows.Media.StreamGeometry>, que es una versión ligera de <xref:System.Windows.Media.PathGeometry>.  Para obtener más información, vea la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
## Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)