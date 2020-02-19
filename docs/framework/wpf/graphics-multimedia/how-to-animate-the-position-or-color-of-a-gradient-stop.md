---
title: 'Cómo: Animar la posición o color de un punto de degradado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452849"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="0977a-102">Cómo: Animar la posición o color de un punto de degradado</span><span class="sxs-lookup"><span data-stu-id="0977a-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="0977a-103">En este ejemplo se muestra cómo animar el <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.</span><span class="sxs-lookup"><span data-stu-id="0977a-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0977a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0977a-104">Example</span></span>  
 <span data-ttu-id="0977a-105">En el ejemplo siguiente se animan tres delimitadores de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="0977a-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="0977a-106">En el ejemplo se usan tres animaciones, cada una de las cuales anima un delimitador de degradado diferente:</span><span class="sxs-lookup"><span data-stu-id="0977a-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="0977a-107">La primera animación, una <xref:System.Windows.Media.Animation.DoubleAnimation>, anima el primer <xref:System.Windows.Media.GradientStop.Offset%2A> de delimitador de degradado de 0,0 a 1,0 y después vuelve a 0,0.</span><span class="sxs-lookup"><span data-stu-id="0977a-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="0977a-108">Como resultado, el primer color del degradado se desplaza desde el lado izquierdo hasta el lado derecho del rectángulo y, a continuación, vuelve al lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="0977a-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="0977a-109">La segunda animación, una <xref:System.Windows.Media.Animation.ColorAnimation>, anima el <xref:System.Windows.Media.GradientStop.Color%2A> del segundo delimitador de degradado de <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y, a continuación, de nuevo a <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="0977a-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="0977a-110">Como resultado, el color intermedio del degradado cambia de púrpura a amarillo y de nuevo a púrpura.</span><span class="sxs-lookup"><span data-stu-id="0977a-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="0977a-111">La tercera animación, otra <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad del tercer delimitador de degradado <xref:System.Windows.Media.GradientStop.Color%2A> por-1 y, a continuación, hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="0977a-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="0977a-112">Como resultado, el tercer color del degradado se atenúa y vuelve a ser opaco.</span><span class="sxs-lookup"><span data-stu-id="0977a-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="0977a-113">Aunque en este ejemplo se usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar objetos <xref:System.Windows.Media.GradientStop> dentro de un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="0977a-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="0977a-114">Para obtener más ejemplos, vea el [ejemplo brushes](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="0977a-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0977a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0977a-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="0977a-116">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="0977a-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0977a-117">Información general sobre objetos Storyboard</span><span class="sxs-lookup"><span data-stu-id="0977a-117">Storyboards Overview</span></span>](storyboards-overview.md)
