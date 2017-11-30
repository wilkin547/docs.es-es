---
title: "Cómo: Definir un rectángulo usando una clase RectangleGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678d6f36c02c63825782b9f1c860285450a6a9f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Cómo: Definir un rectángulo usando una clase RectangleGeometry
En este ejemplo se describe cómo utilizar el <xref:System.Windows.Media.RectangleGeometry> clase para describir un rectángulo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.RectangleGeometry>.  La posición relativa y las dimensiones del rectángulo se definen mediante un <xref:System.Windows.Rect> estructura. La posición relativa es `50,50` y el alto y el ancho son ambos `25` crear un cuadrado. Se pinta el interior del rectángulo con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pincel y su contorno se pinta con un <xref:System.Windows.Media.Brushes.Black%2A> trazo con un grosor de `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Aunque este ejemplo usa un <xref:System.Windows.Shapes.Path> elemento que se va a representar el <xref:System.Windows.Media.RectangleGeometry>, hay muchas otras formas de usar <xref:System.Windows.Media.RectangleGeometry> objetos. Por ejemplo, un <xref:System.Windows.Media.RectangleGeometry> puede utilizarse para especificar el <xref:System.Windows.UIElement.Clip%2A> de un <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de un <xref:System.Windows.Media.GeometryDrawing>.  
  
 Otras clases de geometrías simples incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>. Estos objetos Geometry, así como las más complejas, también pueden crearse mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
