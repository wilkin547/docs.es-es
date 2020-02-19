---
title: 'Cómo: Crear una curva Bézier cuadrática'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452076"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="10830-102">Cómo: Crear una curva Bézier cuadrática</span><span class="sxs-lookup"><span data-stu-id="10830-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="10830-103">En este ejemplo se muestra cómo crear una curva Bézier cuadrática.</span><span class="sxs-lookup"><span data-stu-id="10830-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="10830-104">Para crear una curva Bézier cuadrática, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>y <xref:System.Windows.Media.QuadraticBezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="10830-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10830-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10830-105">Example</span></span>  
 <span data-ttu-id="10830-106">En los ejemplos siguientes, se dibuja una curva Bézier cuadrática de (10.100) a (300.100).</span><span class="sxs-lookup"><span data-stu-id="10830-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="10830-107">La curva tiene un punto de control de (200.200).</span><span class="sxs-lookup"><span data-stu-id="10830-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="10830-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="10830-108">[xaml]</span></span>  
  
 <span data-ttu-id="10830-109">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de atributo para describir una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="10830-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="10830-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="10830-110">[xaml]</span></span>  
  
 <span data-ttu-id="10830-111">(Tenga en cuenta que esta sintaxis de atributo crea realmente un <xref:System.Windows.Media.StreamGeometry>, una versión más ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="10830-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="10830-112">Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="10830-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="10830-113">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar una curva Bézier cuadrática mediante la sintaxis del elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="10830-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="10830-114">El siguiente ejemplo es equivalente al ejemplo anterior de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10830-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="10830-115">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="10830-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10830-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10830-116">See also</span></span>

- [<span data-ttu-id="10830-117">Crear un arco elíptico</span><span class="sxs-lookup"><span data-stu-id="10830-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="10830-118">Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="10830-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
