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
ms.workload: dotnet
ms.openlocfilehash: 9b0b027aa34b310413fa02e81149292fabb40f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="34a97-102">Cómo: Dibujar una polilínea mediante el uso del elemento Polyline</span><span class="sxs-lookup"><span data-stu-id="34a97-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="34a97-103">Este ejemplo muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el uso de la <xref:System.Windows.Shapes.Polyline> elemento.</span><span class="sxs-lookup"><span data-stu-id="34a97-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="34a97-104">Para dibujar una polilínea, crear un <xref:System.Windows.Shapes.Polyline> elemento y utilice su <xref:System.Windows.Shapes.Polyline.Points%2A> propiedad para especificar los vértices de las formas.</span><span class="sxs-lookup"><span data-stu-id="34a97-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="34a97-105">Por último, utilice la <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades para describir la polilínea describen porque una línea sin trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="34a97-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34a97-106">Dado que la <xref:System.Windows.Shapes.Polyline> elemento no es una forma cerrada, la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad no tiene ningún efecto, incluso aunque cierre deliberadamente el contorno de forma.</span><span class="sxs-lookup"><span data-stu-id="34a97-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="34a97-107">Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="34a97-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="34a97-108">En el ejemplo siguiente se dibuja dos <xref:System.Windows.Shapes.Polyline> elementos dentro de un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="34a97-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a97-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34a97-109">Example</span></span>  
 <span data-ttu-id="34a97-110">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], una sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.</span><span class="sxs-lookup"><span data-stu-id="34a97-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="34a97-111">Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede usar elementos de polilínea (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.</span><span class="sxs-lookup"><span data-stu-id="34a97-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="34a97-112">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="34a97-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a97-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="34a97-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="34a97-114">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="34a97-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="34a97-115">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="34a97-115">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
