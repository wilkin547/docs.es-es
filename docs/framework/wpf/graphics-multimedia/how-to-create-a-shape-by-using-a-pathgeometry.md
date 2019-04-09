---
title: Filtrar Crear una forma mediante una clase PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: b0ab703596612524881ab892a1095b0f49cd1551
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159320"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="711ce-102">Filtrar Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="711ce-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="711ce-103">En este ejemplo se muestra cómo crear una forma mediante la <xref:System.Windows.Media.PathGeometry> clase.</span><span class="sxs-lookup"><span data-stu-id="711ce-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <xref:System.Windows.Media.PathGeometry> <span data-ttu-id="711ce-104">los objetos se componen de uno o varios <xref:System.Windows.Media.PathFigure> objetos; cada <xref:System.Windows.Media.PathFigure> representa una "figura" diferentes o forma.</span><span class="sxs-lookup"><span data-stu-id="711ce-104">objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="711ce-105">Cada <xref:System.Windows.Media.PathFigure> sí se compone de uno o varios <xref:System.Windows.Media.PathSegment> objetos que representan una parte conectada de la figura o forma.</span><span class="sxs-lookup"><span data-stu-id="711ce-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="711ce-106">Tipos de segmentos incluyen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, y <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="711ce-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="711ce-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="711ce-107">Example</span></span>  
 <span data-ttu-id="711ce-108">En el ejemplo siguiente se usa un <xref:System.Windows.Media.PathGeometry> para crear un triángulo.</span><span class="sxs-lookup"><span data-stu-id="711ce-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="711ce-109">El <xref:System.Windows.Media.PathGeometry> se muestra mediante un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="711ce-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="711ce-110">La siguiente ilustración muestra la forma creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="711ce-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="711ce-111">![Una clase PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="711ce-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="711ce-112">Un triángulo que se creó con una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="711ce-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="711ce-113">El ejemplo anterior se mostró cómo crear una forma relativamente sencilla, un triángulo.</span><span class="sxs-lookup"><span data-stu-id="711ce-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="711ce-114">Un <xref:System.Windows.Media.PathGeometry> también se puede usar para crear formas más complejas, incluidos arcos y curvas.</span><span class="sxs-lookup"><span data-stu-id="711ce-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="711ce-115">Para obtener ejemplos, vea [crear un arco elíptico](how-to-create-an-elliptical-arc.md), [crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md), y [crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="711ce-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="711ce-116">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="711ce-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711ce-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="711ce-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="711ce-118">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="711ce-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="711ce-119">Ejemplo de geometrías</span><span class="sxs-lookup"><span data-stu-id="711ce-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
