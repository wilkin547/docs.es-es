---
title: 'Cómo: Crear una forma mediante una clase PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 6c77844b054dd89a0c3f3cbecd0725968df9ae71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560187"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="36587-102">Cómo: Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="36587-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="36587-103">Este ejemplo muestra cómo crear una forma mediante la <xref:System.Windows.Media.PathGeometry> clase.</span><span class="sxs-lookup"><span data-stu-id="36587-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="36587-104"><xref:System.Windows.Media.PathGeometry> los objetos se componen de uno o varios <xref:System.Windows.Media.PathFigure> objetos; cada <xref:System.Windows.Media.PathFigure> representa un diferentes "figura" o forma.</span><span class="sxs-lookup"><span data-stu-id="36587-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="36587-105">Cada <xref:System.Windows.Media.PathFigure> propio se compone de uno o varios <xref:System.Windows.Media.PathSegment> objetos, cada uno representa una parte conectada de la figura o forma.</span><span class="sxs-lookup"><span data-stu-id="36587-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="36587-106">Tipos de segmentos incluyen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, y <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="36587-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36587-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36587-107">Example</span></span>  
 <span data-ttu-id="36587-108">En el ejemplo siguiente se usa un <xref:System.Windows.Media.PathGeometry> para crear un triángulo.</span><span class="sxs-lookup"><span data-stu-id="36587-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="36587-109">El <xref:System.Windows.Media.PathGeometry> se muestra mediante un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="36587-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="36587-110">La siguiente ilustración muestra la forma creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="36587-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="36587-111">![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="36587-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="36587-112">Un triángulo creado con PathGeometry</span><span class="sxs-lookup"><span data-stu-id="36587-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="36587-113">En el ejemplo anterior se ha explicado cómo crear una forma relativamente simple, un triángulo.</span><span class="sxs-lookup"><span data-stu-id="36587-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="36587-114">Un <xref:System.Windows.Media.PathGeometry> también puede utilizarse para crear formas más complejas, incluidos arcos y curvas.</span><span class="sxs-lookup"><span data-stu-id="36587-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="36587-115">Para obtener ejemplos, vea [crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), y [crear una curva Bézier cuadrática](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="36587-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="36587-116">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="36587-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36587-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36587-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="36587-118">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="36587-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="36587-119">Ejemplo de geometrías</span><span class="sxs-lookup"><span data-stu-id="36587-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
