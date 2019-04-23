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
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186594"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="a0aa4-102">Procedimiento Controlar interactivamente un reloj</span><span class="sxs-lookup"><span data-stu-id="a0aa4-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="a0aa4-103">Un <xref:System.Windows.Media.Animation.Clock> del objeto <xref:System.Windows.Media.Animation.ClockController> propiedad permite interactivamente iniciar, pausar, reanudar, buscar, pase el reloj a su período de relleno y detener el reloj.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="a0aa4-104">El reloj de raíz de un árbol de control de tiempo se puede controlar interactivamente.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0aa4-105">Hay otras formas de controlar interactivamente las animaciones que no es necesario trabajar directamente con relojes: también puede usar guiones gráficos.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="a0aa4-106">Los guiones gráficos se admiten en la marcación y código.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="a0aa4-107">Para obtener un ejemplo, vea [animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md) o [información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a0aa4-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="a0aa4-108">En el ejemplo siguiente, se utilizan varios botones para controlar interactivamente un reloj de animación.</span><span class="sxs-lookup"><span data-stu-id="a0aa4-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0aa4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0aa4-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a0aa4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0aa4-110">See also</span></span>

- [<span data-ttu-id="a0aa4-111">Animar una propiedad utilizando un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="a0aa4-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="a0aa4-112">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="a0aa4-112">Animation Overview</span></span>](animation-overview.md)
