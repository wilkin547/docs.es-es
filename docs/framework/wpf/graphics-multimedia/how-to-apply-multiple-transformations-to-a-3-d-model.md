---
title: Filtrar Aplicar varias transformaciones a un modelo 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: d18b9bc78e011796f9d9e6d535f3dc949bd5a0f8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352469"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="c813d-102">Filtrar Aplicar varias transformaciones a un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="c813d-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="c813d-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Media3D.RotateTransform3D> y un <xref:System.Windows.Media.Media3D.ScaleTransform3D> girar y cambiar la escala de un modelo 3D.</span><span class="sxs-lookup"><span data-stu-id="c813d-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="c813d-104">El código siguiente muestra cómo aplicar estas transformaciones a la <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D> en XAML.</span><span class="sxs-lookup"><span data-stu-id="c813d-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="c813d-105">Mediante código:</span><span class="sxs-lookup"><span data-stu-id="c813d-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="c813d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c813d-106">Example</span></span>  
 <span data-ttu-id="c813d-107">El código siguiente muestra el ejemplo completo en XAML.</span><span class="sxs-lookup"><span data-stu-id="c813d-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c813d-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c813d-108">Example</span></span>  
 <span data-ttu-id="c813d-109">A continuación es el ejemplo completo en el código.</span><span class="sxs-lookup"><span data-stu-id="c813d-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c813d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c813d-110">See also</span></span>
- [<span data-ttu-id="c813d-111">Transformar la escala de un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="c813d-111">Transform the Scale of a 3-D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
