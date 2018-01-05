---
title: "Cómo: Crear varios subtrazados en un PathGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7945728386c01d6137cbc422f0d7fb410a18d57e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="78e34-102">Cómo: Crear varios subtrazados en un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="78e34-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="78e34-103">Este ejemplo muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="78e34-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="78e34-104">Para crear varios subtrazados, se crea un <xref:System.Windows.Media.PathFigure> para cada subruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="78e34-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78e34-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78e34-105">Example</span></span>  
 <span data-ttu-id="78e34-106">El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.</span><span class="sxs-lookup"><span data-stu-id="78e34-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="78e34-107">En el ejemplo siguiente se muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="78e34-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="78e34-108">Cada `M` crea una subruta de acceso nuevo de modo que en el ejemplo se crea dos subtrazados cada dibuja un triángulo.</span><span class="sxs-lookup"><span data-stu-id="78e34-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="78e34-109">(Tenga en cuenta que la sintaxis de este atributo se crea realmente una <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="78e34-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="78e34-110">Para más información, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="78e34-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e34-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="78e34-111">See Also</span></span>  
 [<span data-ttu-id="78e34-112">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="78e34-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
