---
title: Filtrar Redondear las esquinas de un RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089138"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Filtrar Redondear las esquinas de un RectangleGeometry
Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero. Cuanto mayor sea el valores, más redondeadas serán las esquinas del rectángulo.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración. El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran mediante <xref:System.Windows.Shapes.Path> elementos.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rectángulos con diferentes RadiusX&#47;configuración RadiusY](./media/graphicsmm-rounded.png "graphicsmm_rounded")  
Rectángulos con esquinas redondeadas  
  
## <a name="see-also"></a>Vea también

- [Información general sobre geometría](geometry-overview.md)
- [Crear una forma compuesta](how-to-create-a-composite-shape.md)
- [Crear una forma mediante una clase PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
