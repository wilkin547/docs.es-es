---
title: 'Cómo: Hacer que un elemento gire en su posición'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a37952af621c79d231b45a247c92d3576a533580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562516"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="f9e62-102">Cómo: Hacer que un elemento gire en su posición</span><span class="sxs-lookup"><span data-stu-id="f9e62-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="f9e62-103">Este ejemplo muestra cómo hacer que un elemento de número utilizando un <xref:System.Windows.Media.RotateTransform> y <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="f9e62-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="f9e62-104">El ejemplo siguiente aplica el <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="f9e62-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="f9e62-105">El ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="f9e62-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="f9e62-106">Para hacer que el elemento gire en su lugar, el ejemplo establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad del elemento en el punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="f9e62-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e62-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9e62-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="f9e62-108">Para obtener el ejemplo completo, que incluye varios ejemplos de transformación, vea [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="f9e62-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e62-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9e62-109">See Also</span></span>  
 [<span data-ttu-id="f9e62-110">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="f9e62-110">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="f9e62-111">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="f9e62-111">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
