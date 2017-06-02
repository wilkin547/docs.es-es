---
title: "C&#243;mo: Crear una geometr&#237;a combinada | Microsoft Docs"
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
  - "combinar geometrías"
  - "geometrías, combinar"
  - "gráficos, combinar geometrías"
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear una geometr&#237;a combinada
En este ejemplo se muestra cómo combinar geometrías.  Para combinar dos geometrías, utilice un objeto <xref:System.Windows.Media.CombinedGeometry>.  Establezca sus propiedades <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> en las dos geometrías que desea combinar y establezca la propiedad <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>, que determina cómo se combinarán entre sí las geometrías, en `Union`, `Intersect`, `Exclude` o `Xor`.  
  
 Para crear una geometría compuesta a partir de dos o más geometrías, utilice un objeto <xref:System.Windows.Media.GeometryGroup>.  
  
## Ejemplo  
 En el ejemplo siguiente, se define un objeto <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación de geometría `Exclude`.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Resultados del modo de combinación Exclude](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.png "mil\_task\_combined\_geometry\_exclude")  
Geometría combinada con el valor Exclude  
  
 En el marcado siguiente, se define una <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación `Intersect`.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Resultados del modo de combinación Intersect](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.png "mil\_task\_combined\_geometry\_intersect")  
Geometría combinada con el valor Intersect  
  
 En el marcado siguiente, se define una <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación `Union`.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
Geometría combinada con el valor Union  
  
 En el marcado siguiente, se define una <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación `Xor`.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
Geometría combinada con el valor Xor