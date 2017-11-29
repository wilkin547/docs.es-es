---
title: "Cómo: Crear un arco elíptico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeb93cefd2e55e80f27922feab788698653f405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="1dcd7-102">Cómo: Crear un arco elíptico</span><span class="sxs-lookup"><span data-stu-id="1dcd7-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="1dcd7-103">Este ejemplo muestra cómo dibujar un arco elíptico. Para crear un arco elíptico, utilice la <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.ArcSegment> clases.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dcd7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1dcd7-104">Example</span></span>  
 <span data-ttu-id="1dcd7-105">En los ejemplos siguientes, se dibuja un arco elíptico desde (10,100) hasta (200,100).</span><span class="sxs-lookup"><span data-stu-id="1dcd7-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="1dcd7-106">El arco tiene un <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por 50 píxeles de independientes del dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 grados, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> de `true`y un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="1dcd7-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="1dcd7-107">[xaml]</span></span>  
  
 <span data-ttu-id="1dcd7-108">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede usar la sintaxis de atributo para describir una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="1dcd7-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="1dcd7-109">[xaml]</span></span>  
  
 <span data-ttu-id="1dcd7-110">(Tenga en cuenta que la sintaxis de este atributo se crea realmente una <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="1dcd7-111">Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="1dcd7-111">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="1dcd7-112">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también se puede dibujar un arco elíptico explícitamente mediante etiquetas de objeto.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="1dcd7-113">El siguiente es equivalente al anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="1dcd7-114">Este ejemplo forma parte de un ejemplo mayor.</span><span class="sxs-lookup"><span data-stu-id="1dcd7-114">This example is part of a larger sample.</span></span> <span data-ttu-id="1dcd7-115">Para obtener un ejemplo completo, vea el [ejemplo geometrías](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="1dcd7-115">For the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dcd7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dcd7-116">See Also</span></span>  
 [<span data-ttu-id="1dcd7-117">Crear una curva Bézier cuadrática</span><span class="sxs-lookup"><span data-stu-id="1dcd7-117">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [<span data-ttu-id="1dcd7-118">Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="1dcd7-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
