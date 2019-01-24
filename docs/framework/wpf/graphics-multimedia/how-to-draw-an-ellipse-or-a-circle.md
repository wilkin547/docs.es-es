---
title: Procedimiento Dibujar una elipse o un círculo
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 7aac743b0cd2119107e48493b3ee9563b81b391d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689122"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Procedimiento Dibujar una elipse o un círculo
En este ejemplo se muestra cómo dibujar elipses y círculos utilizando el <xref:System.Windows.Shapes.Ellipse> elemento. Para dibujar una elipse, cree un <xref:System.Windows.Shapes.Ellipse> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>. Use su <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el interior de la elipse. Use su <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el contorno de la elipse. El <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedad especifica el grosor del contorno de la elipse.  
  
 Para dibujar un círculo, realice el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de la <xref:System.Windows.Shapes.Ellipse> elementos iguales entre sí.  
  
 En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Ellipse> elementos dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Aunque este ejemplo usa un <xref:System.Windows.Controls.Canvas> para contener los puntos suspensivos, puede usar elementos de elipse (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sean de texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de los elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037)
