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
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="f6d7c-102">Procedimiento Dibujar una Polilínea mediante el uso del elemento Polyline</span><span class="sxs-lookup"><span data-stu-id="f6d7c-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="f6d7c-103">En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el <xref:System.Windows.Shapes.Polyline> elemento.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="f6d7c-104">Para dibujar una polilínea, cree un <xref:System.Windows.Shapes.Polyline> elemento y utilice su <xref:System.Windows.Shapes.Polyline.Points%2A> propiedad para especificar los vértices de la forma.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="f6d7c-105">Por último, use el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades para describir la polyline de esquema porque una línea sin un trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6d7c-106">Dado que el <xref:System.Windows.Shapes.Polyline> elemento no es una forma cerrada, la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad no tiene ningún efecto, incluso aunque cierre deliberadamente el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="f6d7c-107">Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, utilice un <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="f6d7c-108">En el ejemplo siguiente se dibuja dos <xref:System.Windows.Shapes.Polyline> elementos dentro de un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6d7c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6d7c-109">Example</span></span>  
 <span data-ttu-id="f6d7c-110">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="f6d7c-111">Aunque este ejemplo usa un <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede usar elementos polyline (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sean de texto.</span><span class="sxs-lookup"><span data-stu-id="f6d7c-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="f6d7c-112">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="f6d7c-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d7c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6d7c-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="f6d7c-114">Ejemplo de los elementos de forma</span><span class="sxs-lookup"><span data-stu-id="f6d7c-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="f6d7c-115">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="f6d7c-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
