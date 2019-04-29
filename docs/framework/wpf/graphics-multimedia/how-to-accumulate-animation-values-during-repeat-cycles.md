---
title: Procedimiento Acumular valores de animaciones durante la repetición de ciclos
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 4b739883322751e2df86e13bfd07249abdb10a08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762181"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="6b8ad-102">Procedimiento Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="6b8ad-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="6b8ad-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular valores de animaciones entre ciclos que se repiten.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b8ad-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b8ad-104">Example</span></span>  
 <span data-ttu-id="6b8ad-105">Use el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular los valores base de una animación entre ciclos que se repiten.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="6b8ad-106">Por ejemplo, si establece una animación se repita 9 veces (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") y establezca la propiedad que se va a animar entre 10 y 15 (From = 10 a = 15), la propiedad se anima de 10 a 15 durante el primer ciclo de 15 a 20 durante el ciclo de segundo , de 20 a 25 durante el ciclo de terceros y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="6b8ad-107">Por lo tanto, cada ciclo de animación usa el valor final de la animación desde el ciclo de animación anterior como su valor base.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="6b8ad-108">Puede usar el `IsCumulative` propiedad con animaciones más básicas y la mayoría de las animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="6b8ad-109">Para obtener más información, consulte [información general sobre animaciones](animation-overview.md) y [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6b8ad-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="6b8ad-110">El ejemplo siguiente muestra este comportamiento al animar el ancho de cuatro rectángulos.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="6b8ad-111">El ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b8ad-111">The example:</span></span>  
  
- <span data-ttu-id="6b8ad-112">Anima el primer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="6b8ad-113">Anima el segundo rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad en el valor predeterminado de `false`.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="6b8ad-114">Anima el tercer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="6b8ad-115">Anima el último rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="6b8ad-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6b8ad-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b8ad-116">See also</span></span>

- [<span data-ttu-id="6b8ad-117">Agregar un valor de salida de animación a un valor inicial de animación</span><span class="sxs-lookup"><span data-stu-id="6b8ad-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="6b8ad-118">Repetir una animación</span><span class="sxs-lookup"><span data-stu-id="6b8ad-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="6b8ad-119">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="6b8ad-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6b8ad-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="6b8ad-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6b8ad-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="6b8ad-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
