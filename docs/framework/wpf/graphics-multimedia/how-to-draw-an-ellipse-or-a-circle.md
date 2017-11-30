---
title: "Cómo: Dibujar una elipse o un círculo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4da623c34b4c3b84dee0f02d631d032eb1c061d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Cómo: Dibujar una elipse o un círculo
Este ejemplo muestra cómo dibujar elipses y círculos utilizando el <xref:System.Windows.Shapes.Ellipse> elemento. Para dibujar una elipse, cree un <xref:System.Windows.Shapes.Ellipse> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>. Use su <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el interior de la elipse. Use su <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el esquema de la elipse. El <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedad especifica el grosor del contorno de elipse.  
  
 Para dibujar un círculo, realizar la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de la <xref:System.Windows.Shapes.Ellipse> elementos iguales entre sí.  
  
 En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Ellipse> elementos dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para que contenga los puntos suspensivos, puede usar elementos de elipse (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Ejemplo de elementos de forma](http://go.microsoft.com/fwlink/?LinkID=160037)
