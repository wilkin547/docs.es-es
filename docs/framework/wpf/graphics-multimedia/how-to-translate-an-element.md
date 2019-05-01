---
title: Procedimiento Trasladar un elemento
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 9c1b873a89820e85efb99789f483c4832fb23cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051447"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="7d45c-102">Procedimiento Trasladar un elemento</span><span class="sxs-lookup"><span data-stu-id="7d45c-102">How to: Translate an Element</span></span>
<span data-ttu-id="7d45c-103">En este ejemplo se muestra cómo trasladar (mover) un elemento mediante el uso de un <xref:System.Windows.Media.TranslateTransform>.</span><span class="sxs-lookup"><span data-stu-id="7d45c-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="7d45c-104">La <xref:System.Windows.Media.TranslateTransform> clase es especialmente útil para mover elementos dentro de paneles que no admiten el posicionamiento absoluto.</span><span class="sxs-lookup"><span data-stu-id="7d45c-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="7d45c-105">Por ejemplo, aplicando un <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un elemento, puede mover un elemento dentro de un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="7d45c-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="7d45c-106">Use la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> para especificar la cantidad, en píxeles, que moverá el elemento a lo largo del eje x.</span><span class="sxs-lookup"><span data-stu-id="7d45c-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="7d45c-107">Use el <xref:System.Windows.Media.TranslateTransform.Y%2A> propiedad para especificar la cantidad, en píxeles, que moverá el elemento a lo largo del eje y.</span><span class="sxs-lookup"><span data-stu-id="7d45c-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="7d45c-108">Por último, aplique el <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="7d45c-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="7d45c-109">En el ejemplo siguiente se usa un <xref:System.Windows.Media.TranslateTransform> para mover un elemento 50 píxeles a la derecho y 50 píxeles hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="7d45c-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d45c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d45c-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="7d45c-111">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="7d45c-111">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d45c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d45c-112">See also</span></span>

- [<span data-ttu-id="7d45c-113">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="7d45c-113">Transforms Overview</span></span>](transforms-overview.md)
