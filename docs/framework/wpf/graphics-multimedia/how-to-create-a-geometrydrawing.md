---
title: Filtrar Crear un objeto GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 6eb604a8446000ef308c2b5a99480fb6a476c949
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373821"
---
# <a name="how-to-create-a-geometrydrawing"></a>Filtrar Crear un objeto GeometryDrawing
En este ejemplo se muestra cómo crear y mostrar un <xref:System.Windows.Media.GeometryDrawing>. Un <xref:System.Windows.Media.GeometryDrawing> le permite crear de forma con un relleno y el contorno asociando un <xref:System.Windows.Media.Pen> y un <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>. El <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la estructura de la forma, el <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe el relleno de la forma y el <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe el contorno de la forma.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.GeometryDrawing> para representar una forma. Se describe la forma mediante una <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos. Se pinta el interior de la forma con un <xref:System.Windows.Media.LinearGradientBrush> y el contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. El <xref:System.Windows.Media.GeometryDrawing> se muestra mediante un <xref:System.Windows.Media.ImageDrawing> y un <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 La siguiente ilustración muestra resultante <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Para crear dibujos más complejos, puede combinar varios objetos de dibujo en un elemento compuesto de dibujo utilizando un <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.DrawingGroup>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre geometría](geometry-overview.md)
- [Crear un dibujo compuesto](how-to-create-a-composite-drawing.md)
