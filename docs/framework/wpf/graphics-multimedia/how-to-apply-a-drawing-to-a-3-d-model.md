---
title: Filtrar Aplicar un dibujo a un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125039"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="abf97-102">Filtrar Aplicar un dibujo a un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="abf97-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="abf97-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.DrawingBrush> como el <xref:System.Windows.Media.Media3D.Material> aplicado a un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modelo.</span><span class="sxs-lookup"><span data-stu-id="abf97-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="abf97-104">El código siguiente define un <xref:System.Windows.Media.DrawingGroup> como el contenido de un <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="abf97-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="abf97-105">El <xref:System.Windows.Media.DrawingBrush> se establece como el <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> propiedad de la <xref:System.Windows.Media.Media3D.DiffuseMaterial> aplicado a un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plano.</span><span class="sxs-lookup"><span data-stu-id="abf97-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="abf97-106">**Nota:** A menudo es conveniente definir los objetos complejos y los valores como el siguiente dibujo como recursos que se pueden reutilizar y simplificarán el código.</span><span class="sxs-lookup"><span data-stu-id="abf97-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="abf97-107">Consulte [recursos XAML](../advanced/xaml-resources.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="abf97-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="abf97-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="abf97-108">Example</span></span>  
 <span data-ttu-id="abf97-109">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="abf97-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="abf97-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="abf97-110">See also</span></span>

- [<span data-ttu-id="abf97-111">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="abf97-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="abf97-112">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="abf97-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="abf97-113">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="abf97-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="abf97-114">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="abf97-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
