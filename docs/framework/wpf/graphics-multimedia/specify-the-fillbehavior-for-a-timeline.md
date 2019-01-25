---
title: Procedimiento Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 6745cf5d57a341068e93784d5487f21e34f8a64a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530111"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="f9d1e-102">Procedimiento Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad</span><span class="sxs-lookup"><span data-stu-id="f9d1e-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="f9d1e-103">En este ejemplo se muestra cómo especificar el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> para la inactiva <xref:System.Windows.Media.Animation.Timeline> de una propiedad animada.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9d1e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9d1e-104">Example</span></span>  
 <span data-ttu-id="f9d1e-105">El <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> determina lo que ocurre en el valor de una propiedad animada cuando no se está animada, es decir, cuando el <xref:System.Windows.Media.Animation.Timeline> está inactivo, pero su elemento primario <xref:System.Windows.Media.Animation.Timeline> está dentro de su activo o el período de espera.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="f9d1e-106">¿Por ejemplo, se seguirá una propiedad animada final de su valor después de la animación finaliza, o lo hace volver al valor que tenía antes de inicia la animación?</span><span class="sxs-lookup"><span data-stu-id="f9d1e-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="f9d1e-107">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la <xref:System.Windows.FrameworkElement.Width%2A> de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="f9d1e-108">Cada rectángulo usa otra <xref:System.Windows.Media.Animation.Timeline> objeto.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="f9d1e-109">Una <xref:System.Windows.Media.Animation.Timeline> tiene un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> que se establece en <xref:System.Windows.Media.Animation.FillBehavior.Stop>, lo que hace que el ancho del rectángulo se va a volver a su no animado valor cuando la <xref:System.Windows.Media.Animation.Timeline> finaliza.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="f9d1e-110">El otro <xref:System.Windows.Media.Animation.Timeline> tiene un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, lo que hace que el ancho permanezca en su extremo valor cuando la <xref:System.Windows.Media.Animation.Timeline> finaliza.</span><span class="sxs-lookup"><span data-stu-id="f9d1e-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="f9d1e-111">Para obtener un ejemplo completo, vea [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="f9d1e-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d1e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9d1e-112">See also</span></span>
- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="f9d1e-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="f9d1e-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="f9d1e-114">Animación y temporización</span><span class="sxs-lookup"><span data-stu-id="f9d1e-114">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="f9d1e-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f9d1e-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
