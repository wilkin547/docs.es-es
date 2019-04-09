---
title: Filtrar Aplicar varias transformaciones a un modelo 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 7a6a0dd4942eb2430ff79ab5df4a171a4064ac1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186386"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a>Filtrar Aplicar varias transformaciones a un modelo 3D
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Media3D.RotateTransform3D> y un <xref:System.Windows.Media.Media3D.ScaleTransform3D> girar y cambiar la escala de un modelo 3D. El código siguiente muestra cómo aplicar estas transformaciones a la <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D> en XAML.  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 Mediante código:  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo en XAML.  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 A continuación es el ejemplo completo en el código.  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Transformar la escala de un modelo 3D](how-to-transform-the-scale-of-a-3-d-model.md)
