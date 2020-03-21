---
title: 'Cómo: Aplicar un dibujo a un modelo 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112185"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="3b172-102">Cómo: Aplicar un dibujo a un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="3b172-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="3b172-103">En este ejemplo se <xref:System.Windows.Media.DrawingBrush> muestra <xref:System.Windows.Media.Media3D.Material> cómo utilizar a como aplicado a un modelo 3D.</span><span class="sxs-lookup"><span data-stu-id="3b172-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="3b172-104">El código siguiente <xref:System.Windows.Media.DrawingGroup> define a <xref:System.Windows.Media.DrawingBrush>como el contenido de un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b172-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="3b172-105">Se <xref:System.Windows.Media.DrawingBrush> establece como <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> la <xref:System.Windows.Media.Media3D.DiffuseMaterial> propiedad del aplicado a un plano 3D.</span><span class="sxs-lookup"><span data-stu-id="3b172-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="3b172-106">A menudo es deseable definir objetos complejos y valores como el dibujo siguiente como recursos que se pueden reutilizar y simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="3b172-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="3b172-107">Consulta [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3b172-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="3b172-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b172-108">Example</span></span>

<span data-ttu-id="3b172-109">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="3b172-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="3b172-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b172-110">See also</span></span>

- [<span data-ttu-id="3b172-111">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="3b172-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="3b172-112">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="3b172-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="3b172-113">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="3b172-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="3b172-114">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="3b172-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
