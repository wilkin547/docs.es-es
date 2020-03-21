---
title: 'Cómo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141178"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="9739e-102">Cómo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad</span><span class="sxs-lookup"><span data-stu-id="9739e-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="9739e-103">En este ejemplo se <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> muestra cómo <xref:System.Windows.Media.Animation.Timeline> especificar el for el inactivo de una propiedad animada.</span><span class="sxs-lookup"><span data-stu-id="9739e-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9739e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9739e-104">Example</span></span>  
 <span data-ttu-id="9739e-105">La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad <xref:System.Windows.Media.Animation.Timeline> de a determina lo que sucede con el valor de una propiedad <xref:System.Windows.Media.Animation.Timeline> animada cuando no <xref:System.Windows.Media.Animation.Timeline> se está animando, es decir, cuando el está inactivo pero su elemento primario está dentro de su período activo o de retención.</span><span class="sxs-lookup"><span data-stu-id="9739e-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="9739e-106">Por ejemplo, ¿una propiedad animada permanece en su valor final después de que finalice la animación o vuelve al valor que tenía antes de que se iniciara la animación?</span><span class="sxs-lookup"><span data-stu-id="9739e-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="9739e-107">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente <xref:System.Windows.FrameworkElement.Width%2A> se usa a para animar el de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="9739e-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="9739e-108">Cada rectángulo utiliza <xref:System.Windows.Media.Animation.Timeline> un objeto diferente.</span><span class="sxs-lookup"><span data-stu-id="9739e-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="9739e-109">Uno <xref:System.Windows.Media.Animation.Timeline> tiene <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> un que <xref:System.Windows.Media.Animation.FillBehavior.Stop>se establece en , lo que hace que el <xref:System.Windows.Media.Animation.Timeline> ancho del rectángulo vuelva a su valor no animado cuando los extremos.</span><span class="sxs-lookup"><span data-stu-id="9739e-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="9739e-110">El <xref:System.Windows.Media.Animation.Timeline> otro <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> tiene <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>un , lo que hace que <xref:System.Windows.Media.Animation.Timeline> el ancho permanezca en su valor final cuando finaliza.</span><span class="sxs-lookup"><span data-stu-id="9739e-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="9739e-111">Para ver el ejemplo completo, consulte Galería de ejemplos de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="9739e-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9739e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9739e-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="9739e-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="9739e-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9739e-114">Temas "Cómo..." de animación y control de tiempo</span><span class="sxs-lookup"><span data-stu-id="9739e-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
