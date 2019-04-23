---
title: Procedimiento Hacer que un elemento gire en su posición
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: aca9bd577f2882e31e8d49abe5eeb5ade86f95f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110669"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="e4cd2-102">Procedimiento Hacer que un elemento gire en su posición</span><span class="sxs-lookup"><span data-stu-id="e4cd2-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="e4cd2-103">En este ejemplo se muestra cómo hacer que un elemento gire mediante el uso de un <xref:System.Windows.Media.RotateTransform> y un <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="e4cd2-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="e4cd2-104">El ejemplo siguiente se aplica el <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="e4cd2-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="e4cd2-105">El ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="e4cd2-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="e4cd2-106">Para hacer que el elemento gire en su lugar, el ejemplo establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad del elemento en el punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="e4cd2-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4cd2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4cd2-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="e4cd2-108">Para el ejemplo completo, que incluye más ejemplos de transformaciones, vea [ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="e4cd2-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cd2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4cd2-109">See also</span></span>

- [<span data-ttu-id="e4cd2-110">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="e4cd2-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e4cd2-111">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="e4cd2-111">Transforms Overview</span></span>](transforms-overview.md)
