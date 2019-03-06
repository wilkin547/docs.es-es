---
title: Filtrar Crear una geometría combinada
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364793"
---
# <a name="how-to-create-a-combined-geometry"></a>Procedimiento Crear una geometría combinada
En este ejemplo se muestra cómo se combinan las geometrías. Para combinar dos geometrías, utilice un <xref:System.Windows.Media.CombinedGeometry> objeto. Establezca su <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> propiedades con las dos geometrías para combinar y establecer el <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> propiedad, que determina cómo se se combinan las geometrías juntos, para `Union`, `Intersect`, `Exclude`, o `Xor`.  
  
 Para crear una geometría compuesta de dos o más geometrías, utilice un <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación de geometría `Exclude`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Modo de combinación de los resultados de la exclusión](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Exclusión de geometría combinada  
  
 En el marcado siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Intersect`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Modo de combinación de los resultados de la intersección](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Geometría combinada forman una intersección  
  
 En el marcado siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Union`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Unión de geometría combinada  
  
 En el marcado siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Xor`.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
Xor geometría combinada
