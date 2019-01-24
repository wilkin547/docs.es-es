---
title: Procedimiento Definir un rectángulo usando una clase RectangleGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511651"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="7dbf3-102">Procedimiento Definir un rectángulo usando una clase RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="7dbf3-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="7dbf3-103">En este ejemplo se describe cómo usar el <xref:System.Windows.Media.RectangleGeometry> clase para describir un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dbf3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dbf3-104">Example</span></span>  
 <span data-ttu-id="7dbf3-105">El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="7dbf3-106">La posición relativa y las dimensiones del rectángulo se definen mediante un <xref:System.Windows.Rect> estructura.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="7dbf3-107">Es la posición relativa `50,50` y el alto y ancho son ambos `25` creación de un cuadrado.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="7dbf3-108">El interior del rectángulo se pinta con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pincel y su contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> con un grosor de trazo de `1`.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="7dbf3-109">![Una clase RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="7dbf3-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="7dbf3-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="7dbf3-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="7dbf3-111">Aunque este ejemplo usa un <xref:System.Windows.Shapes.Path> elemento para representar el <xref:System.Windows.Media.RectangleGeometry>, hay muchas otras formas de usar <xref:System.Windows.Media.RectangleGeometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="7dbf3-112">Por ejemplo, un <xref:System.Windows.Media.RectangleGeometry> puede utilizarse para especificar el <xref:System.Windows.UIElement.Clip%2A> de un <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="7dbf3-113">Otras clases de geometría simple incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="7dbf3-114">Estas geometrías, así como otras más complejas, también se pueden crear mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7dbf3-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dbf3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dbf3-115">See also</span></span>
- [<span data-ttu-id="7dbf3-116">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="7dbf3-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="7dbf3-117">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="7dbf3-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="7dbf3-118">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="7dbf3-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
