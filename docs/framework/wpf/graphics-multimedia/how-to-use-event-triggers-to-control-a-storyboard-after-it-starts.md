---
title: "Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80871d9daeec257351134e9f7a72a10b697e842a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="c8f2f-102">Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="c8f2f-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="c8f2f-103">Este ejemplo muestra cómo controlar un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="c8f2f-104">Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="c8f2f-105">Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, permite que un guión gráfico controlable.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="c8f2f-106">A continuación, podrá controlar interactivamente el guión gráfico después de iniciarse.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="c8f2f-107">Utilice las siguientes acciones de guión gráfico junto con <xref:System.Windows.EventTrigger> objetos que se va a controlar un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="c8f2f-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Se detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="c8f2f-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Se reanuda un guión gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="c8f2f-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="c8f2f-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si lo tiene.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="c8f2f-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="c8f2f-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico para liberar recursos.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8f2f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8f2f-114">Example</span></span>  
 <span data-ttu-id="c8f2f-115">En el ejemplo siguiente se utiliza acciones de guión gráfico controlable para controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c8f2f-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="c8f2f-116">**Nota:** para ver un ejemplo de control de un guión gráfico mediante código, vea [controlar un guión gráfico después de que se inicia utilizando sus métodos interactivos](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="c8f2f-117">Para obtener ejemplos adicionales, consulte la [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="c8f2f-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f2f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f2f-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="c8f2f-119">Controlar un guión gráfico una vez iniciado usando métodos interactivos</span><span class="sxs-lookup"><span data-stu-id="c8f2f-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="c8f2f-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="c8f2f-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="c8f2f-121">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="c8f2f-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
