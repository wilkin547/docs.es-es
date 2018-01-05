---
title: "Cómo: Crear una geometría combinada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee77da00604b7e4965cc376748606b6bd0e92ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a>Cómo: Crear una geometría combinada
En este ejemplo se muestra cómo combinar las geometrías. Para combinar dos geometrías, utilice un <xref:System.Windows.Media.CombinedGeometry> objeto. Establecer su <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> propiedades con las dos geometrías para combinar y establecer el <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> propiedad, que determina cómo las geometrías se combinan entre sí, para `Union`, `Intersect`, `Exclude`, o `Xor`.  
  
 Para crear una geometría compuesta de dos o más objetos Geometry, use un <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación de geometría de `Exclude`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Modo de combinación de resultados de la exclusión](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Exclusión de geometría combinada  
  
 En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Intersect`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Modo de combinación de resultados de la intersección](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Geometría combinada forman una intersección  
  
 En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Union`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Unión de geometría combinada  
  
 En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Xor`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
Geometría combinada Xor
