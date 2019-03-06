---
title: Procedimiento Crear varios subtrazados en un PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353379"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Filtrar Crear varios subtrazados en un PathGeometry
En este ejemplo se muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>. Para crear varios subtrazados, cree un <xref:System.Windows.Media.PathFigure> para cada subtrazado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 El ejemplo siguiente muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo. Cada `M` crea una subruta de acceso nuevo para que el ejemplo crea dos subtrazados cada dibuja un triángulo.  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre geometría](geometry-overview.md)
