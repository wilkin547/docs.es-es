---
title: 'Cómo: Aplicar material emisivo a un objeto 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112159"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="8ced3-102">Cómo: Aplicar material emisivo a un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="8ced3-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="8ced3-103">En el ejemplo siguiente <xref:System.Windows.Media.Media3D.EmissiveMaterial> se muestra cómo se utiliza para agregar color a un material existente igual al color del pincel de EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="8ced3-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="8ced3-104">El código <xref:System.Windows.Media.Media3D.DiffuseMaterial> siguiente <xref:System.Windows.Media.Media3D.EmissiveMaterial> muestra y se aplica en combinación para agregar azul a la apariencia de DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="8ced3-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="8ced3-105">En el código procesal:</span><span class="sxs-lookup"><span data-stu-id="8ced3-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="8ced3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ced3-106">Example</span></span>  
 <span data-ttu-id="8ced3-107">El código siguiente muestra el ejemplo completo en XAML.</span><span class="sxs-lookup"><span data-stu-id="8ced3-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="8ced3-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ced3-108">Example</span></span>  
 <span data-ttu-id="8ced3-109">A continuación se muestra el ejemplo completo en código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8ced3-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8ced3-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ced3-110">See also</span></span>

- [<span data-ttu-id="8ced3-111">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="8ced3-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="8ced3-112">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="8ced3-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="8ced3-113">Animar propiedades de material en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="8ced3-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="8ced3-114">Aplicar material en la parte delantera y trasera de un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="8ced3-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
