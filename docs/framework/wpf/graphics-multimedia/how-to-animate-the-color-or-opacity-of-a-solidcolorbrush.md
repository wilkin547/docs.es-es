---
title: 'Cómo: Animar el color o la opacidad de un objeto SolidColorBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452888"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="6ab5f-102">Cómo: Animar el color o la opacidad de un objeto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="6ab5f-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="6ab5f-103">En este ejemplo se muestra cómo animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de una <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ab5f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ab5f-104">Example</span></span>  
 <span data-ttu-id="6ab5f-105">En el ejemplo siguiente se usan tres animaciones para animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de una <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="6ab5f-106">La primera animación, una <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el Mouse entra en el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="6ab5f-107">La siguiente animación, otra <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="6ab5f-108">La animación final, una <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0,0 cuando se presiona el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="6ab5f-109">Para obtener un ejemplo más completo, en el que se muestra cómo animar distintos tipos de pinceles, vea el [ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="6ab5f-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="6ab5f-110">Para obtener más información acerca de la animación, consulte [información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6ab5f-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="6ab5f-111">Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo se usa un objeto <xref:System.Windows.Media.Animation.Storyboard> para aplicar sus animaciones.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="6ab5f-112">Sin embargo, al aplicar una animación única en el código, es más fácil utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="6ab5f-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="6ab5f-113">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="6ab5f-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab5f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ab5f-114">See also</span></span>

- [<span data-ttu-id="6ab5f-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="6ab5f-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6ab5f-116">Información general sobre objetos Storyboard</span><span class="sxs-lookup"><span data-stu-id="6ab5f-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="6ab5f-117">Ejemplo de pinceles</span><span class="sxs-lookup"><span data-stu-id="6ab5f-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
