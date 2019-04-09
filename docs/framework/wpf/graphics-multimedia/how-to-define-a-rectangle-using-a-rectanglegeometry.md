---
title: Filtrar Definir un rectángulo mediante una clase RectangleGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075801"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Filtrar Definir un rectángulo mediante una clase RectangleGeometry
En este ejemplo se describe cómo usar el <xref:System.Windows.Media.RectangleGeometry> clase para describir un rectángulo.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.RectangleGeometry>.  La posición relativa y las dimensiones del rectángulo se definen mediante un <xref:System.Windows.Rect> estructura. Es la posición relativa `50,50` y el alto y ancho son ambos `25` creación de un cuadrado. El interior del rectángulo se pinta con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pincel y su contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> con un grosor de trazo de `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Una clase RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Aunque este ejemplo usa un <xref:System.Windows.Shapes.Path> elemento para representar el <xref:System.Windows.Media.RectangleGeometry>, hay muchas otras formas de usar <xref:System.Windows.Media.RectangleGeometry> objetos. Por ejemplo, un <xref:System.Windows.Media.RectangleGeometry> puede utilizarse para especificar el <xref:System.Windows.UIElement.Clip%2A> de un <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de un <xref:System.Windows.Media.GeometryDrawing>.  
  
 Otras clases de geometría simple incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>. Estas geometrías, así como otras más complejas, también se pueden crear mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre geometría](geometry-overview.md)
- [Crear una forma compuesta](how-to-create-a-composite-shape.md)
- [Crear una forma mediante una clase PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
