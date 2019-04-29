---
title: Procedimiento Aplicar material emisor a un objeto 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: b898148fa07950e3ad1eddcaf9206f7d6a837241
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698985"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="ad418-102">Procedimiento Aplicar material emisor a un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="ad418-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="ad418-103">El ejemplo siguiente muestra cómo usar <xref:System.Windows.Media.Media3D.EmissiveMaterial> para agregar color a un Material existente igual que el color de pincel de EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="ad418-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="ad418-104">El código siguiente muestra <xref:System.Windows.Media.Media3D.DiffuseMaterial> y <xref:System.Windows.Media.Media3D.EmissiveMaterial> aplicados en combinación para agregar azul a la apariencia de DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="ad418-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="ad418-105">En el código de procedimientos:</span><span class="sxs-lookup"><span data-stu-id="ad418-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="ad418-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad418-106">Example</span></span>  
 <span data-ttu-id="ad418-107">El código siguiente muestra el ejemplo completo en XAML.</span><span class="sxs-lookup"><span data-stu-id="ad418-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="ad418-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad418-108">Example</span></span>  
 <span data-ttu-id="ad418-109">A continuación es el ejemplo completo en el código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ad418-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ad418-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad418-110">See also</span></span>

- [<span data-ttu-id="ad418-111">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="ad418-111">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="ad418-112">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="ad418-112">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="ad418-113">Animar propiedades de material en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="ad418-113">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="ad418-114">Aplicar material a la parte anterior y posterior de un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="ad418-114">Apply Material to the Front and Back of a 3-D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
