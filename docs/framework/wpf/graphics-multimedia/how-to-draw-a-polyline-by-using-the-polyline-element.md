---
title: "Cómo: Dibujar una polilínea mediante el uso del elemento Polyline"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5fa8cafdaf7856e95129f648da1d4b4ccb2f54eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Cómo: Dibujar una polilínea mediante el uso del elemento Polyline
Este ejemplo muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el uso de la <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Para dibujar una polilínea, crear un <xref:System.Windows.Shapes.Polyline> elemento y utilice su <xref:System.Windows.Shapes.Polyline.Points%2A> propiedad para especificar los vértices de las formas. Por último, utilice la <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades para describir la polilínea describen porque una línea sin trazo es invisible.  
  
> [!NOTE]
>  Dado que la <xref:System.Windows.Shapes.Polyline> elemento no es una forma cerrada, la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad no tiene ningún efecto, incluso aunque cierre deliberadamente el contorno de forma. Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 En el ejemplo siguiente se dibuja dos <xref:System.Windows.Shapes.Polyline> elementos dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], una sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede usar elementos de polilínea (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Ejemplo de elementos de forma](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
