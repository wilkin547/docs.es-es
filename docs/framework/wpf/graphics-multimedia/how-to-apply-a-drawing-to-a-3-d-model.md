---
title: Procedimiento Aplicar un dibujo a un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855880"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="4ec46-102">Procedimiento Aplicar un dibujo a un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="4ec46-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="4ec46-103">En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.DrawingBrush> un <xref:System.Windows.Media.Media3D.Material> como aplicado a un modelo 3D.</span><span class="sxs-lookup"><span data-stu-id="4ec46-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="4ec46-104">El código siguiente define <xref:System.Windows.Media.DrawingGroup> como el contenido de un. <xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="4ec46-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="4ec46-105">Se establece como la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> propiedad de <xref:System.Windows.Media.Media3D.DiffuseMaterial> que se aplica a un plano 3D. <xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="4ec46-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="4ec46-106">A menudo es conveniente definir objetos y valores complejos como el dibujo siguiente como recursos que se pueden volver a usar y simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="4ec46-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="4ec46-107">Vea [recursos XAML](../advanced/xaml-resources.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4ec46-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="4ec46-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ec46-108">Example</span></span>

<span data-ttu-id="4ec46-109">En el código siguiente se muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="4ec46-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="4ec46-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ec46-110">See also</span></span>

- [<span data-ttu-id="4ec46-111">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="4ec46-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="4ec46-112">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="4ec46-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="4ec46-113">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="4ec46-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="4ec46-114">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="4ec46-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
