---
title: 'Cómo: Crear un arco elíptico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453070"
---
# <a name="how-to-create-an-elliptical-arc"></a>Cómo: Crear un arco elíptico
En este ejemplo se muestra cómo dibujar un arco elíptico. Para crear un arco elíptico, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>y <xref:System.Windows.Media.ArcSegment>.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes, se dibuja un arco elíptico de (10.100) a (200.100). El arco tiene una <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por píxeles independientes del dispositivo 50, una <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 grados, una <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> configuración de `true`y una <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de atributo para describir una ruta de acceso.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Tenga en cuenta que esta sintaxis de atributo crea realmente un <xref:System.Windows.Media.StreamGeometry>, una versión más ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar un arco elíptico mediante etiquetas de objeto explícitamente. Lo siguiente es equivalente al marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Este ejemplo forma parte de un ejemplo mayor. Para obtener el ejemplo completo, vea el [ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Consulte también

- [Crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md)
- [Crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md)
