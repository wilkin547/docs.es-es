---
title: 'Cómo: Crear un arco elíptico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453070"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="4551e-102">Cómo: Crear un arco elíptico</span><span class="sxs-lookup"><span data-stu-id="4551e-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="4551e-103">En este ejemplo se muestra cómo dibujar un arco elíptico. Para crear un arco elíptico, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>y <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="4551e-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4551e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4551e-104">Example</span></span>  
 <span data-ttu-id="4551e-105">En los ejemplos siguientes, se dibuja un arco elíptico de (10.100) a (200.100).</span><span class="sxs-lookup"><span data-stu-id="4551e-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="4551e-106">El arco tiene una <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por píxeles independientes del dispositivo 50, una <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 grados, una <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> configuración de `true`y una <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="4551e-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="4551e-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="4551e-107">[xaml]</span></span>  
  
 <span data-ttu-id="4551e-108">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de atributo para describir una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4551e-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="4551e-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="4551e-109">[xaml]</span></span>  
  
 <span data-ttu-id="4551e-110">(Tenga en cuenta que esta sintaxis de atributo crea realmente un <xref:System.Windows.Media.StreamGeometry>, una versión más ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="4551e-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4551e-111">Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="4551e-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="4551e-112">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar un arco elíptico mediante etiquetas de objeto explícitamente.</span><span class="sxs-lookup"><span data-stu-id="4551e-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="4551e-113">Lo siguiente es equivalente al marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.</span><span class="sxs-lookup"><span data-stu-id="4551e-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="4551e-114">Este ejemplo forma parte de un ejemplo mayor.</span><span class="sxs-lookup"><span data-stu-id="4551e-114">This example is part of a larger sample.</span></span> <span data-ttu-id="4551e-115">Para obtener el ejemplo completo, vea el [ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="4551e-115">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4551e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4551e-116">See also</span></span>

- [<span data-ttu-id="4551e-117">Crear una curva Bézier cuadrática</span><span class="sxs-lookup"><span data-stu-id="4551e-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="4551e-118">Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="4551e-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
