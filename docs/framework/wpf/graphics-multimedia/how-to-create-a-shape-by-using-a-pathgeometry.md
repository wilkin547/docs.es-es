---
title: Filtrar Crear una forma mediante una clase PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: ce84f2509116207afa200ddf83dcdc1f8101da13
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356248"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Filtrar Crear una forma mediante una clase PathGeometry
En este ejemplo se muestra cómo crear una forma mediante la <xref:System.Windows.Media.PathGeometry> clase. <xref:System.Windows.Media.PathGeometry> los objetos se componen de uno o varios <xref:System.Windows.Media.PathFigure> objetos; cada <xref:System.Windows.Media.PathFigure> representa una "figura" diferentes o forma. Cada <xref:System.Windows.Media.PathFigure> sí se compone de uno o varios <xref:System.Windows.Media.PathSegment> objetos que representan una parte conectada de la figura o forma. Tipos de segmentos incluyen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, y <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.PathGeometry> para crear un triángulo. El <xref:System.Windows.Media.PathGeometry> se muestra mediante un <xref:System.Windows.Shapes.Path> elemento.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 La siguiente ilustración muestra la forma creada en el ejemplo anterior.  
  
 ![Una clase PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Un triángulo que se creó con una clase PathGeometry  
  
 El ejemplo anterior se mostró cómo crear una forma relativamente sencilla, un triángulo. Un <xref:System.Windows.Media.PathGeometry> también se puede usar para crear formas más complejas, incluidos arcos y curvas. Para obtener ejemplos, vea [crear un arco elíptico](how-to-create-an-elliptical-arc.md), [crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md), y [crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md).  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Información general sobre geometría](geometry-overview.md)
- [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989)
