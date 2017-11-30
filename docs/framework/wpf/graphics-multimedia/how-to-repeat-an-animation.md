---
title: "Cómo: Repetir una animación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2f942771e01c2b7fae989f73779672edb8ba2f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="f34a5-102">Cómo: Repetir una animación</span><span class="sxs-lookup"><span data-stu-id="f34a5-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="f34a5-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> para controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="f34a5-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f34a5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f34a5-104">Example</span></span>  
 <span data-ttu-id="f34a5-105">El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> controla cuántas veces una animación repite su duración simple.</span><span class="sxs-lookup"><span data-stu-id="f34a5-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="f34a5-106">Mediante el uso de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar que un <xref:System.Windows.Media.Animation.Timeline> se repite un número determinado de veces (un número de iteraciones) o durante un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="f34a5-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="f34a5-107">En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para llenar el número solicitado o la duración.</span><span class="sxs-lookup"><span data-stu-id="f34a5-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="f34a5-108">De forma predeterminada, las escalas de tiempo tienen un número de repeticiones de 1,0, lo que significa que se reproduce una vez y no se repiten.</span><span class="sxs-lookup"><span data-stu-id="f34a5-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="f34a5-109">Sin embargo, si establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la escala de tiempo se repite indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="f34a5-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="f34a5-110">En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para controlar el comportamiento de repetición de una animación.</span><span class="sxs-lookup"><span data-stu-id="f34a5-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="f34a5-111">En el ejemplo se anima la <xref:System.Windows.FrameworkElement.Width%2A> propiedad de cinco rectángulos con cada rectángulo con un tipo diferente del comportamiento de repetición.</span><span class="sxs-lookup"><span data-stu-id="f34a5-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="f34a5-112">Para obtener un ejemplo completo, vea [ejemplo de comportamiento de tiempo de animación](http://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="f34a5-112">For the complete sample, see [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f34a5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f34a5-113">See Also</span></span>  
 [<span data-ttu-id="f34a5-114">Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="f34a5-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="f34a5-115">Especificar si una escala de tiempo se invierte automáticamente</span><span class="sxs-lookup"><span data-stu-id="f34a5-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="f34a5-116">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f34a5-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="f34a5-117">Animación y temporización</span><span class="sxs-lookup"><span data-stu-id="f34a5-117">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="f34a5-118">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="f34a5-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="f34a5-119">Ejemplo del comportamiento del control de tiempo de la animación</span><span class="sxs-lookup"><span data-stu-id="f34a5-119">Animation Timing Behavior Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159970)
