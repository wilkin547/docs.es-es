---
title: Filtrar Utilizar un objeto MatrixTransform para crear transformaciones personalizadas
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 179c7986b6a7021f4e1245aef01eb555108ebf4f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358865"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="5405e-102">Procedimiento Utilizar un objeto MatrixTransform para crear transformaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="5405e-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="5405e-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.MatrixTransform> para trasladar (mover) la posición, stretch y el sesgo de una <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5405e-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5405e-104">Use la <xref:System.Windows.Media.MatrixTransform> clase para crear transformaciones personalizadas no proporcionadas por el <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, o <xref:System.Windows.Media.TranslateTransform> clases.</span><span class="sxs-lookup"><span data-stu-id="5405e-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5405e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5405e-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="5405e-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="5405e-106">See also</span></span>
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="5405e-107">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="5405e-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="5405e-108">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5405e-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="5405e-109">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="5405e-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
