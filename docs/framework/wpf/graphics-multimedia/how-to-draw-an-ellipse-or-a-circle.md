---
title: 'Cómo: Dibujar una elipse o un círculo'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452927"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Cómo: Dibujar una elipse o un círculo
En este ejemplo se muestra cómo dibujar elipses y círculos mediante el elemento <xref:System.Windows.Shapes.Ellipse>. Para dibujar una elipse, cree un elemento <xref:System.Windows.Shapes.Ellipse> y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>. Utilice su propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> para especificar el <xref:System.Windows.Media.Brush> que se utiliza para pintar el interior de la elipse. Utilice su propiedad <xref:System.Windows.Shapes.Shape.Stroke%2A> para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el contorno de la elipse. La propiedad <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> especifica el grosor del contorno de la elipse.  
  
 Para dibujar un círculo, convierta el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del elemento <xref:System.Windows.Shapes.Ellipse> igual entre sí.  
  
 En el ejemplo siguiente se dibujan cuatro elementos <xref:System.Windows.Shapes.Ellipse> dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Aunque en este ejemplo se usa una <xref:System.Windows.Controls.Canvas> para contener los puntos suspensivos, se pueden usar elementos Ellipse (y todos los demás elementos Shape) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
