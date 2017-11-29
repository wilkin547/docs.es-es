---
title: "Cómo: Crear un objeto GeometryDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f0fa86a9786e5440db9fec0cee76c5ed28363b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-geometrydrawing"></a>Cómo: Crear un objeto GeometryDrawing
Este ejemplo muestra cómo crear y mostrar un <xref:System.Windows.Media.GeometryDrawing>. A <xref:System.Windows.Media.GeometryDrawing> le permite crear forma con un relleno y un contorno asociando un <xref:System.Windows.Media.Pen> y un <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>. El <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la estructura de la forma, el <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe el relleno de la forma y el <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe el contorno de la forma.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.GeometryDrawing> para representar una forma. Describe la forma un <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos. Se pinta el interior de la forma con un <xref:System.Windows.Media.LinearGradientBrush> y su contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. El <xref:System.Windows.Media.GeometryDrawing> se muestra con un <xref:System.Windows.Media.ImageDrawing> y un <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 La ilustración siguiente muestra los resultantes <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Para crear dibujos más complejos, puede combinar varios objetos de dibujo en un compuesto único dibujo utilizando un <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingGroup>  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Crear un dibujo compuesto](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
