---
title: Procedimiento Crear varios subtrazados en un PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638358"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Procedimiento Crear varios subtrazados en un PathGeometry
En este ejemplo se muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>. Para crear varios subtrazados, cree un <xref:System.Windows.Media.PathFigure> para cada subtrazado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 El ejemplo siguiente muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo. Cada `M` crea una subruta de acceso nuevo para que el ejemplo crea dos subtrazados cada dibuja un triángulo.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
