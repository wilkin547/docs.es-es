---
title: Procedimiento Crear varios subtrazados en un PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: d7b3d24f8d947d342a2af5484a6620c8379ac664
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638358"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="20ce4-102">Procedimiento Crear varios subtrazados en un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="20ce4-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="20ce4-103">En este ejemplo se muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="20ce4-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="20ce4-104">Para crear varios subtrazados, cree un <xref:System.Windows.Media.PathFigure> para cada subtrazado.</span><span class="sxs-lookup"><span data-stu-id="20ce4-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20ce4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20ce4-105">Example</span></span>  
 <span data-ttu-id="20ce4-106">El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.</span><span class="sxs-lookup"><span data-stu-id="20ce4-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="20ce4-107">El ejemplo siguiente muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="20ce4-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="20ce4-108">Cada `M` crea una subruta de acceso nuevo para que el ejemplo crea dos subtrazados cada dibuja un triángulo.</span><span class="sxs-lookup"><span data-stu-id="20ce4-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="20ce4-109">(Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="20ce4-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="20ce4-110">Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="20ce4-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ce4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ce4-111">See also</span></span>
- [<span data-ttu-id="20ce4-112">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="20ce4-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
