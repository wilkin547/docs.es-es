---
title: Procedimiento Crea una curva Bézier cuadrática.
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: a5d424f3fda3957bf54d7073d41d9fe2dabb1736
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650098"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>Procedimiento Crea una curva Bézier cuadrática.
En este ejemplo se muestra cómo crear una curva Bézier cuadrática.  Para crear una curva Bézier cuadrática, utilice el <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.QuadraticBezierSegment> clases.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes, se dibuja una curva Bézier cuadrática desde (10,100) hasta (300,100). La curva tiene un punto de control de (200,200).  
  
 [xaml]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede usar la sintaxis de atributo para describir una ruta de acceso.  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 (Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>. Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar una curva Bézier cuadrática mediante la sintaxis de elemento de objeto. El siguiente ejemplo es equivalente al ejemplo anterior de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vea también
- [Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)
- [Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
