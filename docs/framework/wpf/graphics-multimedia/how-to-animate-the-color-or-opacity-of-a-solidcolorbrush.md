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
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559329"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="e024e-102">Cómo: Animar el color o la opacidad de un objeto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="e024e-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="e024e-103">Este ejemplo muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="e024e-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e024e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e024e-104">Example</span></span>  
 <span data-ttu-id="e024e-105">En el ejemplo siguiente se utiliza tres animaciones para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="e024e-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="e024e-106">La primera animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el mouse entra en el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e024e-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="e024e-107">La siguiente animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e024e-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="e024e-108">La última animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0.0 cuando se presiona el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="e024e-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="e024e-109">Para obtener un ejemplo más completo, que muestra cómo animar tipos diferentes de pinceles, consulte la [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="e024e-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="e024e-110">Para obtener más información acerca de la animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e024e-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="e024e-111">Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar sus animaciones.</span><span class="sxs-lookup"><span data-stu-id="e024e-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="e024e-112">Sin embargo, al aplicar una animación única en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="e024e-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="e024e-113">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="e024e-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e024e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e024e-114">See Also</span></span>  
 [<span data-ttu-id="e024e-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="e024e-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e024e-116">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="e024e-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="e024e-117">Ejemplo de pinceles</span><span class="sxs-lookup"><span data-stu-id="e024e-117">Brushes Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159973)
