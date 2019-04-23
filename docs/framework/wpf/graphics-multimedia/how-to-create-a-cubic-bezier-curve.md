---
title: Procedimiento Crear una curva Bézier cúbica
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115575"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Procedimiento Crear una curva Bézier cúbica
En este ejemplo se muestra cómo crear una curva Bézier cúbica. Para crear una curva Bézier cúbica, use el <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.BezierSegment> clases.  Para mostrar la geometría resultante, utilice un <xref:System.Windows.Shapes.Path> elemento, o utilizarlo con un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>. En los ejemplos siguientes, se dibuja una curva Bézier cúbica desde (10, 100) a (300, 100). La curva tiene puntos de control de (100, 0) y (200, 200).  
  
## <a name="example"></a>Ejemplo  
 [xaml]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de marcado abreviada para describir una ruta de acceso.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar una curva Bézier cúbica mediante etiquetas de objeto. El siguiente ejemplo es equivalente al ejemplo anterior de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vea también

- [Crear un arco elíptico](how-to-create-an-elliptical-arc.md)
- [Crear un LineSegment en una clase PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md)
- [Crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md)
