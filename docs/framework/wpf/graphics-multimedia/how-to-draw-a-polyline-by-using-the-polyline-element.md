---
title: 'Cómo: Dibujar una polilínea mediante el uso del elemento Polyline'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452966"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="bcbef-102">Cómo: Dibujar una polilínea mediante el uso del elemento Polyline</span><span class="sxs-lookup"><span data-stu-id="bcbef-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="bcbef-103">En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el elemento <xref:System.Windows.Shapes.Polyline>.</span><span class="sxs-lookup"><span data-stu-id="bcbef-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="bcbef-104">Para dibujar una polilínea, cree un elemento <xref:System.Windows.Shapes.Polyline> y utilice su propiedad <xref:System.Windows.Shapes.Polyline.Points%2A> para especificar los vértices de la forma.</span><span class="sxs-lookup"><span data-stu-id="bcbef-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="bcbef-105">Por último, use las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> para describir el contorno de la polilínea porque una línea sin trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="bcbef-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcbef-106">Dado que el elemento <xref:System.Windows.Shapes.Polyline> no es una forma cerrada, la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> no tiene ningún efecto, aunque cierre deliberadamente el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="bcbef-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="bcbef-107">Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un elemento <xref:System.Windows.Shapes.Polygon>.</span><span class="sxs-lookup"><span data-stu-id="bcbef-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="bcbef-108">En el ejemplo siguiente se dibujan dos elementos <xref:System.Windows.Shapes.Polyline> dentro de un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="bcbef-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcbef-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcbef-109">Example</span></span>  
 <span data-ttu-id="bcbef-110">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="bcbef-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="bcbef-111">Aunque en este ejemplo se usa una <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede utilizar elementos Polyline (y todos los demás elementos Shape) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.</span><span class="sxs-lookup"><span data-stu-id="bcbef-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="bcbef-112">Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="bcbef-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbef-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcbef-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="bcbef-114">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="bcbef-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="bcbef-115">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="bcbef-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
