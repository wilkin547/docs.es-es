---
title: 'Cómo: Trasladar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111977"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="94920-102">Cómo: Trasladar un elemento</span><span class="sxs-lookup"><span data-stu-id="94920-102">How to: Translate an Element</span></span>
<span data-ttu-id="94920-103">En este ejemplo se muestra cómo traducir <xref:System.Windows.Media.TranslateTransform>(mover) un elemento mediante un archivo .</span><span class="sxs-lookup"><span data-stu-id="94920-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="94920-104">La <xref:System.Windows.Media.TranslateTransform> clase es especialmente útil para mover elementos dentro de paneles que no admiten el posicionamiento absoluto.</span><span class="sxs-lookup"><span data-stu-id="94920-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="94920-105">Por ejemplo, al <xref:System.Windows.Media.TranslateTransform> aplicar <xref:System.Windows.UIElement.RenderTransform%2A> a la propiedad de un elemento, <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel>puede mover un elemento dentro de un o .</span><span class="sxs-lookup"><span data-stu-id="94920-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="94920-106">Utilice <xref:System.Windows.Media.TranslateTransform.X%2A> la propiedad <xref:System.Windows.Media.TranslateTransform> de la para especificar la cantidad, en píxeles, para mover el elemento a lo largo del eje X.</span><span class="sxs-lookup"><span data-stu-id="94920-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="94920-107">Utilice <xref:System.Windows.Media.TranslateTransform.Y%2A> la propiedad para especificar la cantidad, en píxeles, para mover el elemento a lo largo del eje Y.</span><span class="sxs-lookup"><span data-stu-id="94920-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="94920-108">Por último, <xref:System.Windows.Media.TranslateTransform> aplique <xref:System.Windows.UIElement.RenderTransform%2A> la propiedad a la propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="94920-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="94920-109">En el ejemplo <xref:System.Windows.Media.TranslateTransform> siguiente se usa a para mover un elemento 50 píxeles a la derecha y 50 píxeles hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="94920-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94920-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94920-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="94920-111">Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="94920-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94920-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94920-112">See also</span></span>

- [<span data-ttu-id="94920-113">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="94920-113">Transforms Overview</span></span>](transforms-overview.md)
