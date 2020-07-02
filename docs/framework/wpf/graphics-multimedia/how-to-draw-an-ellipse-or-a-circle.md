---
title: 'Cómo: Dibujar una elipse o un círculo'
description: Obtenga información sobre cómo dibujar una elipse o un círculo con opciones para el grosor del contorno y el color interior en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853568"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Cómo: Dibujar una elipse o un círculo
En este ejemplo se muestra cómo dibujar elipses y círculos mediante el <xref:System.Windows.Shapes.Ellipse> elemento. Para dibujar una elipse, cree un <xref:System.Windows.Shapes.Ellipse> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> . Utilice la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el interior de la elipse. Utilice la <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el contorno de la elipse. La <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedad especifica el grosor del contorno de la elipse.  
  
 Para dibujar un círculo, haga que <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Shapes.Ellipse> elemento sean iguales entre sí.  
  
 En el ejemplo siguiente se dibujan cuatro <xref:System.Windows.Shapes.Ellipse> elementos dentro de <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener los puntos suspensivos, se pueden usar elementos de elipse (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
