---
title: 'Cómo: Dibujar una polilínea mediante el uso del elemento Polyline'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452966"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Cómo: Dibujar una polilínea mediante el uso del elemento Polyline
En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el elemento <xref:System.Windows.Shapes.Polyline>.  
  
 Para dibujar una polilínea, cree un elemento <xref:System.Windows.Shapes.Polyline> y utilice su propiedad <xref:System.Windows.Shapes.Polyline.Points%2A> para especificar los vértices de la forma. Por último, use las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> para describir el contorno de la polilínea porque una línea sin trazo es invisible.  
  
> [!NOTE]
> Dado que el elemento <xref:System.Windows.Shapes.Polyline> no es una forma cerrada, la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> no tiene ningún efecto, aunque cierre deliberadamente el contorno de la forma. Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un elemento <xref:System.Windows.Shapes.Polygon>.  
  
 En el ejemplo siguiente se dibujan dos elementos <xref:System.Windows.Shapes.Polyline> dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separadas por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Aunque en este ejemplo se usa una <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede utilizar elementos Polyline (y todos los demás elementos Shape) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
