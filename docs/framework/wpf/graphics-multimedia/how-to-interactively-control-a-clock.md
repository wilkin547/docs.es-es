---
title: Procedimiento Controlar interactivamente un reloj
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951345"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="1f903-102">Procedimiento Controlar interactivamente un reloj</span><span class="sxs-lookup"><span data-stu-id="1f903-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="1f903-103">La <xref:System.Windows.Media.Animation.Clock> propiedad de <xref:System.Windows.Media.Animation.ClockController> un objeto permite iniciar, pausar, reanudar, buscar, avanzar el reloj hasta su período de relleno y detener el reloj interactivamente.</span><span class="sxs-lookup"><span data-stu-id="1f903-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="1f903-104">Solo se puede controlar interactivamente el reloj raíz de un árbol de control de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1f903-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f903-105">Hay otras maneras de controlar interactivamente animaciones que no requieren que trabaje directamente con los relojes: también puede usar guiones gráficos.</span><span class="sxs-lookup"><span data-stu-id="1f903-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="1f903-106">Los guiones gráficos se admiten tanto en el marcado como en el código.</span><span class="sxs-lookup"><span data-stu-id="1f903-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="1f903-107">Para obtener un ejemplo, vea [animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md) o la [información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f903-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="1f903-108">En el ejemplo siguiente, se usan varios botones para controlar interactivamente un reloj de animación.</span><span class="sxs-lookup"><span data-stu-id="1f903-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f903-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f903-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1f903-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f903-110">See also</span></span>

- [<span data-ttu-id="1f903-111">Animar una propiedad utilizando un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="1f903-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="1f903-112">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="1f903-112">Animation Overview</span></span>](animation-overview.md)
