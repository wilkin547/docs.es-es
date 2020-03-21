---
title: 'Cómo: Repetir una animación'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141554"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="18d7f-102">Cómo: Repetir una animación</span><span class="sxs-lookup"><span data-stu-id="18d7f-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="18d7f-103">En este ejemplo se <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> muestra <xref:System.Windows.Media.Animation.Timeline> cómo utilizar la propiedad de a para controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="18d7f-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18d7f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18d7f-104">Example</span></span>  
 <span data-ttu-id="18d7f-105">La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad <xref:System.Windows.Media.Animation.Timeline> de un controla cuántas veces una animación repite su duración simple.</span><span class="sxs-lookup"><span data-stu-id="18d7f-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="18d7f-106">Mediante <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>el uso de <xref:System.Windows.Media.Animation.Timeline> , puede especificar que una repetición para un cierto número de veces (un recuento de iteraciones) o para un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="18d7f-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="18d7f-107">En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para completar el recuento o la duración solicitados.</span><span class="sxs-lookup"><span data-stu-id="18d7f-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="18d7f-108">De forma predeterminada, las escalas de tiempo tienen un recuento de repetición de 1,0, lo que significa que se reproducen una vez y no se repiten.</span><span class="sxs-lookup"><span data-stu-id="18d7f-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="18d7f-109">Sin embargo, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> si establece <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>la propiedad de a a , la línea de tiempo se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="18d7f-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="18d7f-110">En el ejemplo siguiente <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> se muestra cómo utilizar la propiedad para controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="18d7f-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="18d7f-111">En el ejemplo <xref:System.Windows.FrameworkElement.Width%2A> se anima la propiedad de cinco rectángulos con cada rectángulo mediante un tipo diferente de comportamiento de repetición.</span><span class="sxs-lookup"><span data-stu-id="18d7f-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="18d7f-112">Para ver el ejemplo completo, vea Ejemplo de comportamiento de [temporización](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)de animación .</span><span class="sxs-lookup"><span data-stu-id="18d7f-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d7f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18d7f-113">See also</span></span>

- [<span data-ttu-id="18d7f-114">Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="18d7f-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="18d7f-115">Especificar si una escala de tiempo se invierte automáticamente</span><span class="sxs-lookup"><span data-stu-id="18d7f-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="18d7f-116">Temas "Cómo..." de animación y control de tiempo</span><span class="sxs-lookup"><span data-stu-id="18d7f-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="18d7f-117">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="18d7f-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="18d7f-118">Ejemplo del comportamiento del control de tiempo de la animación</span><span class="sxs-lookup"><span data-stu-id="18d7f-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
