---
title: "Cómo: Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo"
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
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5421ed8b45c21e229d6c2682703cd9c7ee486e27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="71a2b-102">Cómo: Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="71a2b-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="71a2b-103">A <xref:System.Windows.Media.Animation.ClockController> del objeto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> propiedad le permite cambiar la velocidad de un <xref:System.Windows.Media.Animation.Clock> sin modificar el <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> del reloj <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="71a2b-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="71a2b-104">En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.ClockController> se utiliza para modificar de forma interactiva el <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> de un reloj.</span><span class="sxs-lookup"><span data-stu-id="71a2b-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="71a2b-105">El <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> eventos y el reloj <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> propiedad se utiliza para mostrar la velocidad del reloj actual global cada vez que su interactivo <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> se cambia.</span><span class="sxs-lookup"><span data-stu-id="71a2b-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a2b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71a2b-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
