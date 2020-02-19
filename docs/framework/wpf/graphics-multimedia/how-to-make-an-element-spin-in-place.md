---
title: 'Cómo: Hacer que un elemento gire en su posición'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452797"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="5ac2c-102">Cómo: Hacer que un elemento gire en su posición</span><span class="sxs-lookup"><span data-stu-id="5ac2c-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="5ac2c-103">En este ejemplo se muestra cómo hacer que un elemento gire mediante un <xref:System.Windows.Media.RotateTransform> y un <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="5ac2c-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="5ac2c-104">En el ejemplo siguiente se aplica el <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del elemento.</span><span class="sxs-lookup"><span data-stu-id="5ac2c-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="5ac2c-105">En el ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="5ac2c-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="5ac2c-106">Para hacer que el elemento gire en su lugar, en el ejemplo se establece la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del elemento en el punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="5ac2c-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ac2c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ac2c-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="5ac2c-108">Para obtener el ejemplo completo, que incluye más ejemplos de transformación, vea [ejemplo de transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="5ac2c-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac2c-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ac2c-109">See also</span></span>

- [<span data-ttu-id="5ac2c-110">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="5ac2c-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5ac2c-111">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="5ac2c-111">Transforms Overview</span></span>](transforms-overview.md)
