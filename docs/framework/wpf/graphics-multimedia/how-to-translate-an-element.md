---
title: 'Cómo: Trasladar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 0089f294c54662d1ea4929ec25c08464072cbdde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561948"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="99907-102">Cómo: Trasladar un elemento</span><span class="sxs-lookup"><span data-stu-id="99907-102">How to: Translate an Element</span></span>
<span data-ttu-id="99907-103">Este ejemplo muestra cómo traslación (movimiento) un elemento mediante un <xref:System.Windows.Media.TranslateTransform>.</span><span class="sxs-lookup"><span data-stu-id="99907-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="99907-104">La <xref:System.Windows.Media.TranslateTransform> clase resulta especialmente útil para mover elementos dentro de los paneles que no admiten la posición absoluta.</span><span class="sxs-lookup"><span data-stu-id="99907-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="99907-105">Por ejemplo, aplicando una <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un elemento, puede mover un elemento dentro de un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="99907-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="99907-106">Use la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> para especificar la cantidad, en píxeles, para mover el elemento en el eje x.</span><span class="sxs-lookup"><span data-stu-id="99907-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="99907-107">Use la <xref:System.Windows.Media.TranslateTransform.Y%2A> propiedad para especificar la cantidad, en píxeles, para mover el elemento a lo largo del eje y.</span><span class="sxs-lookup"><span data-stu-id="99907-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="99907-108">Por último, aplique la <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="99907-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="99907-109">En el ejemplo siguiente se usa un <xref:System.Windows.Media.TranslateTransform> para mover un elemento 50 píxeles a la derecha y 50 píxeles hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="99907-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99907-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99907-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="99907-111">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="99907-111">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99907-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="99907-112">See Also</span></span>  
 [<span data-ttu-id="99907-113">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="99907-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
