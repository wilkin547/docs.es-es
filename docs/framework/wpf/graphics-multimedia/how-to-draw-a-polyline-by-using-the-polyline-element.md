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
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934963"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedimiento Dibujar una Polilínea mediante el uso del elemento Polyline
En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, <xref:System.Windows.Shapes.Polyline> mediante el elemento.  
  
 Para dibujar una polilínea, cree <xref:System.Windows.Shapes.Polyline> un elemento y use <xref:System.Windows.Shapes.Polyline.Points%2A> su propiedad para especificar los vértices de la forma. Por último, use <xref:System.Windows.Shapes.Shape.Stroke%2A> las <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades y para describir el contorno de la polilínea porque una línea sin trazo es invisible.  
  
> [!NOTE]
> Dado que <xref:System.Windows.Shapes.Polyline> el elemento no es una forma cerrada, <xref:System.Windows.Shapes.Shape.Fill%2A> la propiedad no tiene ningún efecto, aunque cierre deliberadamente el contorno de la forma. Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 En el ejemplo siguiente se <xref:System.Windows.Shapes.Polyline> dibujan dos <xref:System.Windows.Controls.Canvas>elementos dentro de.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separadas por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Aunque en este ejemplo se <xref:System.Windows.Controls.Canvas> usa un para contener las polilíneas, puede utilizar elementos Polyline (y todos los demás elementos Shape) con <xref:System.Windows.Controls.Panel> cualquier <xref:System.Windows.Controls.Control> o que admita contenido que no sea de texto.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Ejemplo de elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
