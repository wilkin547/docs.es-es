---
title: 'Cómo: Dibujar un rectángulo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 100f1a8062628e892e9a71b988bb2a8754ea6bad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561051"
---
# <a name="how-to-draw-a-rectangle"></a>Cómo: Dibujar un rectángulo
Este ejemplo muestra cómo dibujar un rectángulo con el <xref:System.Windows.Shapes.Rectangle> elemento.  
  
 Para dibujar un rectángulo, cree un <xref:System.Windows.Shapes.Rectangle> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>. Para pintar el interior del rectángulo, establezca su <xref:System.Windows.Shapes.Shape.Fill%2A>. Para conceder a un esquema de rectángulo, utilice su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades.  
  
 Para dar el rectángulo esquinas redondeadas, especifique el valor opcional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades. El <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades establecen los radios de ejes x y y de la elipse que se utiliza para redondear los vértices del rectángulo.  
  
 En el ejemplo siguiente, dos <xref:System.Windows.Shapes.Rectangle> se dibujan un <xref:System.Windows.Controls.Canvas>. El primer rectángulo tiene una <xref:System.Windows.Media.Brushes.Blue%2A> interiores. El segundo rectángulo tiene una <xref:System.Windows.Media.Brushes.Blue%2A> interiores, un <xref:System.Windows.Media.Brushes.Black%2A> contorno y esquinas redondeadas.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para que contenga los rectángulos, puede usar elementos de rectángulo (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto. De hecho, los rectángulos son particularmente útiles para proporcionar fondos para partes de <xref:System.Windows.Controls.Grid> paneles. Para obtener un ejemplo, vea el [información general de la tabla](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Rectangle>  
 [Ejemplo de elementos de forma](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)
