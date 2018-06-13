---
title: 'Cómo: Redondear las esquinas de un RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: e4f1d37e2c0f26967affff14ed6475fc8c0cb28c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561646"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Cómo: Redondear las esquinas de un RectangleGeometry
Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero. Cuanto mayores sean los valores, más redondeadas serán las esquinas del rectángulo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración. El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran con <xref:System.Windows.Shapes.Path> elementos.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rectángulos con diferentes valores de RadiusX&#47;configuración RadiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")  
Rectángulos con esquinas redondeadas  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
