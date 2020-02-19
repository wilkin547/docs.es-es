---
title: 'Cómo: Crear una forma mediante una clase PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452050"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Cómo: Crear una forma mediante una clase PathGeometry
En este ejemplo se muestra cómo crear una forma mediante la clase <xref:System.Windows.Media.PathGeometry>. <xref:System.Windows.Media.PathGeometry> objetos se componen de uno o varios objetos <xref:System.Windows.Media.PathFigure>; cada <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente. Cada <xref:System.Windows.Media.PathFigure> se compone de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales representa una parte conectada de la figura o forma. Los tipos de segmento incluyen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>y <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa una <xref:System.Windows.Media.PathGeometry> para crear un triángulo. El <xref:System.Windows.Media.PathGeometry> se muestra utilizando un elemento <xref:System.Windows.Shapes.Path>.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 La siguiente ilustración muestra la forma creada en el ejemplo anterior.  
  
 ![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Triángulo creado con PathGeometry  
  
 En el ejemplo anterior se mostró cómo crear una forma relativamente simple, un triángulo. También se puede utilizar una <xref:System.Windows.Media.PathGeometry> para crear formas más complejas, como arcos y curvas. Para obtener ejemplos, vea [crear un arco elíptico](how-to-create-an-elliptical-arc.md), [crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md)y [crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md).  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Información general sobre geometría](geometry-overview.md)
- [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
