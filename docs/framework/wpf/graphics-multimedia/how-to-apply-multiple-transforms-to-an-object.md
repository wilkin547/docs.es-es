---
title: Filtrar Aplicar varias transformaciones a un objeto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 26dcd4a64fc7aa2c3cb9cc599ceaef292efb1b6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192769"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="e6a7a-102">Filtrar Aplicar varias transformaciones a un objeto</span><span class="sxs-lookup"><span data-stu-id="e6a7a-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="e6a7a-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.TransformGroup> al grupo de dos o más <xref:System.Windows.Media.Transform> objetos en un elemento compuesto <xref:System.Windows.Media.Transform>.</span><span class="sxs-lookup"><span data-stu-id="e6a7a-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a7a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6a7a-104">Example</span></span>  
 <span data-ttu-id="e6a7a-105">En el ejemplo siguiente se usa un <xref:System.Windows.Media.TransformGroup> para aplicar un <xref:System.Windows.Media.ScaleTransform> y un <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="e6a7a-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a7a-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6a7a-106">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [<span data-ttu-id="e6a7a-107">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="e6a7a-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="e6a7a-108">Ejemplo de transformaciones 2D</span><span class="sxs-lookup"><span data-stu-id="e6a7a-108">2-D Transforms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=158252)
