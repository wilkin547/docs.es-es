---
title: "Cómo: Controlar un guión gráfico una vez iniciado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 051ac6fea73b207fb5ef4d6293c5e996552f1281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="acb75-102">Cómo: Controlar un guión gráfico una vez iniciado</span><span class="sxs-lookup"><span data-stu-id="acb75-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="acb75-103">Este ejemplo muestra cómo utilizar código para controlar un <xref:System.Windows.Media.Animation.Storyboard> después de haberse iniciado.</span><span class="sxs-lookup"><span data-stu-id="acb75-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="acb75-104">Para controlar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> y <xref:System.Windows.TriggerAction> objetos; para obtener un ejemplo, vea [usar desencadenadores de eventos para controlar un guión gráfico después de que se inicia](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="acb75-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="acb75-105">Para iniciar un guión gráfico, utilice su <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método, que distribuye las animaciones del guión gráfico para las propiedades que se animan y se inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb75-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="acb75-106">Para poder controlar un guión gráfico, use la <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método y especifique **true** como segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="acb75-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="acb75-107">A continuación, puede usar métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar el tiempo de espera, o ralentizar el guión gráfico o avanzar a su período de relleno.</span><span class="sxs-lookup"><span data-stu-id="acb75-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="acb75-108">La siguiente es una lista de métodos interactivos del guión gráfico:</span><span class="sxs-lookup"><span data-stu-id="acb75-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="acb75-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Se detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb75-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="acb75-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Se reanuda un guión gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="acb75-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="acb75-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Establece la velocidad interactiva del guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb75-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="acb75-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Busca el guión gráfico la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="acb75-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="acb75-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Busca en el guión gráfico a la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="acb75-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="acb75-114">A diferencia de la <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (método), esta operación se procesa antes del paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="acb75-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="acb75-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Hace avanzar el guión gráfico hasta su período de relleno, si lo tiene.</span><span class="sxs-lookup"><span data-stu-id="acb75-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="acb75-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb75-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="acb75-117">En el ejemplo siguiente, se usan varios métodos de guión gráfico para controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb75-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="acb75-118">**Nota:** para ver un ejemplo de control de un guión gráfico mediante desencadenadores con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [utilizar desencadenadores de eventos para controlar un guión gráfico después de que se inicia](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="acb75-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acb75-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acb75-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="acb75-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="acb75-120">See Also</span></span>  
 [<span data-ttu-id="acb75-121">Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="acb75-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
