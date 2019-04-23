---
title: Procedimiento Repetir una animación
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150545"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="aebb1-102">Procedimiento Repetir una animación</span><span class="sxs-lookup"><span data-stu-id="aebb1-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="aebb1-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> con el fin de controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="aebb1-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aebb1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aebb1-104">Example</span></span>  
 <span data-ttu-id="aebb1-105">El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> controla el número de veces que una animación repite su duración simple.</span><span class="sxs-lookup"><span data-stu-id="aebb1-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="aebb1-106">Mediante el uso de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar que un <xref:System.Windows.Media.Animation.Timeline> se repite durante un determinado número de veces (un número de iteraciones) o durante un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="aebb1-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="aebb1-107">En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para rellenar el número solicitado o la duración.</span><span class="sxs-lookup"><span data-stu-id="aebb1-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="aebb1-108">De forma predeterminada, las escalas de tiempo tienen un número de repeticiones de 1,0, lo que significa que se reproducen una vez y no se repiten.</span><span class="sxs-lookup"><span data-stu-id="aebb1-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="aebb1-109">Sin embargo, si establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la escala de tiempo se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="aebb1-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="aebb1-110">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="aebb1-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="aebb1-111">El ejemplo se anima la <xref:System.Windows.FrameworkElement.Width%2A> propiedad cinco rectángulos con cada rectángulo con un tipo diferente del comportamiento de repetición.</span><span class="sxs-lookup"><span data-stu-id="aebb1-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="aebb1-112">Para obtener un ejemplo completo, vea [ejemplo de comportamiento de control de tiempo de animación](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="aebb1-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aebb1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aebb1-113">See also</span></span>

- [<span data-ttu-id="aebb1-114">Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="aebb1-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="aebb1-115">Especificar si una escala de tiempo se invierte automáticamente</span><span class="sxs-lookup"><span data-stu-id="aebb1-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="aebb1-116">Temas de procedimientos de temporización y animación</span><span class="sxs-lookup"><span data-stu-id="aebb1-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="aebb1-117">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="aebb1-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="aebb1-118">Ejemplo del comportamiento del control de tiempo de la animación</span><span class="sxs-lookup"><span data-stu-id="aebb1-118">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
