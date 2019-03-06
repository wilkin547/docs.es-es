---
title: Filtrar Hacer que un elemento UIElement sea transparente o semitransparente
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370532"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="5c357-102">Filtrar Hacer que un elemento UIElement sea transparente o semitransparente</span><span class="sxs-lookup"><span data-stu-id="5c357-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="5c357-103">En este ejemplo se muestra cómo realizar una <xref:System.Windows.UIElement> transparente o semitransparente.</span><span class="sxs-lookup"><span data-stu-id="5c357-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="5c357-104">Para hacer un elemento transparente o semitransparente, establezca su <xref:System.Windows.UIElement.Opacity%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5c357-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="5c357-105">Un valor de `0.0` hace que el elemento sea completamente transparente, mientras que un valor de `1.0` hace que el elemento sea completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="5c357-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="5c357-106">Un valor de `0.5` hace que el elemento 50% opaco y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5c357-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="5c357-107">Un elemento <xref:System.Windows.UIElement.Opacity%2A> está establecido en `1.0` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c357-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c357-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c357-108">Example</span></span>  
 <span data-ttu-id="5c357-109">El ejemplo siguiente se establece la <xref:System.Windows.UIElement.Opacity%2A> de un botón para `0.25`, lo que y su contenido (en este caso, el texto del botón) 25% opaco.</span><span class="sxs-lookup"><span data-stu-id="5c357-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="5c357-110">Si el contenido de un elemento tiene su propio <xref:System.Windows.UIElement.Opacity%2A> configuración, esos valores se multiplica frente a los elementos que contienen <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c357-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="5c357-111">En el ejemplo siguiente se establece un botón <xref:System.Windows.UIElement.Opacity%2A> a `0.25`y el <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Image> control contenido en el botón para `0.5`.</span><span class="sxs-lookup"><span data-stu-id="5c357-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="5c357-112">Como resultado, la imagen aparece 12,5% opaco: 0.25 \* 0.5 = 0.125.</span><span class="sxs-lookup"><span data-stu-id="5c357-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="5c357-113">Otra manera de controlar la opacidad de un elemento es establecer la opacidad de la <xref:System.Windows.Media.Brush> que pinta el elemento.</span><span class="sxs-lookup"><span data-stu-id="5c357-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="5c357-114">Este enfoque permite modificar selectivamente la opacidad de partes de un elemento y ofrece ventajas de rendimiento respecto al uso del elemento <xref:System.Windows.UIElement.Opacity%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5c357-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="5c357-115">El ejemplo siguiente se establece la <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush> se usa para pintar el botón <xref:System.Windows.Controls.Control.Background%2A> está establecido en `0.25`.</span><span class="sxs-lookup"><span data-stu-id="5c357-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="5c357-116">Como resultado, el fondo del pincel es opaca al 25%, pero su contenido (el texto del botón) siguen siendo 100% opaco.</span><span class="sxs-lookup"><span data-stu-id="5c357-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="5c357-117">También puede controlar la opacidad de colores individuales dentro de un pincel.</span><span class="sxs-lookup"><span data-stu-id="5c357-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="5c357-118">Para obtener más información acerca de los colores y pinceles, vea [el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5c357-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="5c357-119">Para obtener un ejemplo que muestra cómo animar la opacidad de un elemento, vea [animar la opacidad de un elemento o pincel](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="5c357-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
