---
title: "Cómo: Controlar interactivamente un reloj"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: debe65ef1587171dc2f324a19da4b43e7274c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="3a20f-102">Cómo: Controlar interactivamente un reloj</span><span class="sxs-lookup"><span data-stu-id="3a20f-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="3a20f-103">A <xref:System.Windows.Media.Animation.Clock> del objeto <xref:System.Windows.Media.Animation.ClockController> propiedad le permite interactivamente iniciar, pausar, reanudar, buscar, avanzar el reloj hasta su período de relleno y detener el reloj.</span><span class="sxs-lookup"><span data-stu-id="3a20f-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="3a20f-104">Solo el reloj de raíz de un árbol de control de tiempo puede controlarse de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="3a20f-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a20f-105">Hay otras maneras de controlar interactivamente las animaciones que no requieran que trabajar directamente con relojes: también puede utilizar guiones gráficos.</span><span class="sxs-lookup"><span data-stu-id="3a20f-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="3a20f-106">Guiones gráficos se admiten en código y marcado.</span><span class="sxs-lookup"><span data-stu-id="3a20f-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="3a20f-107">Para obtener un ejemplo, vea [animar una propiedad mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) o [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3a20f-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="3a20f-108">En el ejemplo siguiente, se utilizan varios botones para controlar interactivamente un reloj de animación.</span><span class="sxs-lookup"><span data-stu-id="3a20f-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a20f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a20f-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="3a20f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a20f-110">See Also</span></span>  
 [<span data-ttu-id="3a20f-111">Animar una propiedad utilizando un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="3a20f-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="3a20f-112">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="3a20f-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
