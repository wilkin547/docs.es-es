---
title: Procedimiento Crear varios subtrazados en un objeto PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 286075448cd6a343f8a7b15b2b5005f840f68e1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111753"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Procedimiento Crear varios subtrazados en un objeto PathGeometry
En este ejemplo se muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>. Para crear varios subtrazados, cree un <xref:System.Windows.Media.PathFigure> para cada subtrazado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 El ejemplo siguiente muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo. Cada `M` crea una subruta de acceso nuevo para que el ejemplo crea dos subtrazados cada dibuja un triángulo.  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre geometría](geometry-overview.md)
