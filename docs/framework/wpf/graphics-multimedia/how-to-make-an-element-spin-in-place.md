---
title: 'Cómo: Hacer que un elemento gire en su posición'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112081"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="d96ae-102">Cómo: Hacer que un elemento gire en su posición</span><span class="sxs-lookup"><span data-stu-id="d96ae-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="d96ae-103">En este ejemplo se muestra cómo hacer <xref:System.Windows.Media.RotateTransform> que <xref:System.Windows.Media.Animation.DoubleAnimation>un elemento gire mediante un archivo y un archivo .</span><span class="sxs-lookup"><span data-stu-id="d96ae-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="d96ae-104">En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente <xref:System.Windows.UIElement.RenderTransform%2A> se aplica la propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="d96ae-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="d96ae-105">En el <xref:System.Windows.Media.Animation.DoubleAnimation> ejemplo se <xref:System.Windows.Media.RotateTransform.Angle%2A> utiliza <xref:System.Windows.Media.RotateTransform>a para animar el archivo .</span><span class="sxs-lookup"><span data-stu-id="d96ae-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="d96ae-106">Para que el elemento gire en su <xref:System.Windows.UIElement.RenderTransformOrigin%2A> lugar, el ejemplo establece la propiedad del elemento en el punto (0.5, 0.5).</span><span class="sxs-lookup"><span data-stu-id="d96ae-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d96ae-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d96ae-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="d96ae-108">Para ver el ejemplo completo, que incluye más ejemplos de transformación, vea Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="d96ae-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96ae-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d96ae-109">See also</span></span>

- [<span data-ttu-id="d96ae-110">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="d96ae-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d96ae-111">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="d96ae-111">Transforms Overview</span></span>](transforms-overview.md)
