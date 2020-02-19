---
title: 'Cómo: Dibujar un rectángulo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452940"
---
# <a name="how-to-draw-a-rectangle"></a>Cómo: Dibujar un rectángulo
En este ejemplo se muestra cómo dibujar un rectángulo mediante el elemento <xref:System.Windows.Shapes.Rectangle>.  
  
 Para dibujar un rectángulo, cree un elemento <xref:System.Windows.Shapes.Rectangle> y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>. Para pintar el interior del rectángulo, establezca su <xref:System.Windows.Shapes.Shape.Fill%2A>. Para asignar un contorno al rectángulo, use sus propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Para dar al rectángulo esquinas redondeadas, especifique las propiedades <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> opcionales. Las propiedades <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> establecen los radios de los ejes x e y de la elipse que se usa para redondear los vértices del rectángulo.  
  
 En el ejemplo siguiente, se dibujan dos elementos <xref:System.Windows.Shapes.Rectangle> en una <xref:System.Windows.Controls.Canvas>. El primer rectángulo tiene un <xref:System.Windows.Media.Brushes.Blue%2A> interior. El segundo rectángulo tiene un <xref:System.Windows.Media.Brushes.Blue%2A> interior, un esquema <xref:System.Windows.Media.Brushes.Black%2A> y esquinas redondeadas.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener los rectángulos, puede utilizar elementos de rectángulo (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto. De hecho, los rectángulos son especialmente útiles para proporcionar el fondo para partes de los paneles de <xref:System.Windows.Controls.Grid>. Para obtener un ejemplo, vea la [información general](../advanced/table-overview.md)de la tabla.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Rectangle>
- [Ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre las tablas](../advanced/table-overview.md)
