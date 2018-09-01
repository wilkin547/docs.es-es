---
title: 'Cómo: Crear un arco elíptico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 7ca7d06aa25f8dfae648d8c54c8b95cc277ffbf9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393840"
---
# <a name="how-to-create-an-elliptical-arc"></a>Cómo: Crear un arco elíptico
En este ejemplo se muestra cómo dibujar un arco elíptico. Para crear un arco elíptico, utilice el <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.ArcSegment> clases.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes, se dibuja un arco elíptico desde (10,100) hasta (200,100). El arco tiene un <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por 50 píxeles independientes del dispositivo un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 grados, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> de `true`y un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede usar la sintaxis de atributo para describir una ruta de acceso.  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar un arco elíptico explícitamente mediante etiquetas de objeto. La siguiente es equivalente al anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Este ejemplo forma parte de un ejemplo mayor. Para obtener un ejemplo completo, vea el [ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vea también  
 [Crear una curva Bézier cuadrática](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
