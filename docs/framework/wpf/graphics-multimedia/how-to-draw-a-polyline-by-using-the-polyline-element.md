---
title: Procedimiento Dibujar una Polilínea mediante el uso del elemento Polyline
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4f55ecc206be0ef4947923047e796c36131c70ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114851"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedimiento Dibujar una Polilínea mediante el uso del elemento Polyline
En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Para dibujar una polilínea, cree un <xref:System.Windows.Shapes.Polyline> elemento y utilice su <xref:System.Windows.Shapes.Polyline.Points%2A> propiedad para especificar los vértices de la forma. Por último, use el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades para describir la polyline de esquema porque una línea sin un trazo es invisible.  
  
> [!NOTE]
>  Dado que el <xref:System.Windows.Shapes.Polyline> elemento no es una forma cerrada, la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad no tiene ningún efecto, incluso aunque cierre deliberadamente el contorno de la forma. Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, utilice un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 En el ejemplo siguiente se dibuja dos <xref:System.Windows.Shapes.Polyline> elementos dentro de un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Aunque este ejemplo usa un <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede usar elementos polyline (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sean de texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de los elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
