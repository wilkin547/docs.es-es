---
title: 'Cómo: Crear una forma mediante una clase PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452050"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="4e8ba-102">Cómo: Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="4e8ba-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="4e8ba-103">En este ejemplo se muestra cómo crear una forma mediante la clase <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="4e8ba-104"><xref:System.Windows.Media.PathGeometry> objetos se componen de uno o varios objetos <xref:System.Windows.Media.PathFigure>; cada <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="4e8ba-105">Cada <xref:System.Windows.Media.PathFigure> se compone de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales representa una parte conectada de la figura o forma.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="4e8ba-106">Los tipos de segmento incluyen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>y <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e8ba-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e8ba-107">Example</span></span>  
 <span data-ttu-id="4e8ba-108">En el ejemplo siguiente se usa una <xref:System.Windows.Media.PathGeometry> para crear un triángulo.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="4e8ba-109">El <xref:System.Windows.Media.PathGeometry> se muestra utilizando un elemento <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="4e8ba-110">La siguiente ilustración muestra la forma creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="4e8ba-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="4e8ba-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="4e8ba-112">Triángulo creado con PathGeometry</span><span class="sxs-lookup"><span data-stu-id="4e8ba-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="4e8ba-113">En el ejemplo anterior se mostró cómo crear una forma relativamente simple, un triángulo.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="4e8ba-114">También se puede utilizar una <xref:System.Windows.Media.PathGeometry> para crear formas más complejas, como arcos y curvas.</span><span class="sxs-lookup"><span data-stu-id="4e8ba-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="4e8ba-115">Para obtener ejemplos, vea [crear un arco elíptico](how-to-create-an-elliptical-arc.md), [crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md)y [crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="4e8ba-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="4e8ba-116">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="4e8ba-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8ba-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e8ba-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="4e8ba-118">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="4e8ba-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="4e8ba-119">Ejemplo de geometrías</span><span class="sxs-lookup"><span data-stu-id="4e8ba-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
