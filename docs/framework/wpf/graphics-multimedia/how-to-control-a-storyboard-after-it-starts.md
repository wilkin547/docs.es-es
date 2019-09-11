---
title: Procedimiento Controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855867"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="06c91-102">Procedimiento Controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="06c91-102">How to: Control a Storyboard After It Starts</span></span>

<span data-ttu-id="06c91-103">En este ejemplo se muestra cómo usar el código para <xref:System.Windows.Media.Animation.Storyboard> controlar una después de haberse iniciado.</span><span class="sxs-lookup"><span data-stu-id="06c91-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="06c91-104">Para controlar un guion gráfico [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en, <xref:System.Windows.Trigger> use <xref:System.Windows.TriggerAction> los objetos y; para obtener un ejemplo, vea [usar desencadenadores de eventos para controlar un guión gráfico después de su inicio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="06c91-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

<span data-ttu-id="06c91-105">Para iniciar un guion gráfico, use su <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método, que distribuye las animaciones del guión gráfico a las propiedades que animan e inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="06c91-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>

<span data-ttu-id="06c91-106">Para que se pueda controlar un guión gráfico, use <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> el método y especifique **true** como el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="06c91-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="06c91-107">Después, puede usar los métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar o ralentizar el guión gráfico, o bien avanzar hasta su período de relleno.</span><span class="sxs-lookup"><span data-stu-id="06c91-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="06c91-108">A continuación se muestra una lista de los métodos interactivos del guión gráfico:</span><span class="sxs-lookup"><span data-stu-id="06c91-108">The following is a list of the storyboard's interactive methods:</span></span>

- <span data-ttu-id="06c91-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pausa el guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="06c91-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>

- <span data-ttu-id="06c91-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Reanuda un guion gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="06c91-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="06c91-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Establece la velocidad interactiva del guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="06c91-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>

- <span data-ttu-id="06c91-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Busca el guion gráfico en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="06c91-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>

- <span data-ttu-id="06c91-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Busca el guión gráfico en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="06c91-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="06c91-114">A diferencia del <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método, esta operación se procesa antes del siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="06c91-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>

- <span data-ttu-id="06c91-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Hace avanzar el guión gráfico hasta su período de relleno, si tiene uno.</span><span class="sxs-lookup"><span data-stu-id="06c91-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>

- <span data-ttu-id="06c91-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Detiene el guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="06c91-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>

<span data-ttu-id="06c91-117">En el ejemplo siguiente, se usan varios métodos de guion gráfico para controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="06c91-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="06c91-118">Para ver un ejemplo de cómo controlar un guión gráfico mediante desencadenadores con, consulte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [usar desencadenadores de eventos para controlar un guión gráfico después de su inicio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="06c91-118">To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

## <a name="example"></a><span data-ttu-id="06c91-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06c91-119">Example</span></span>

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a><span data-ttu-id="06c91-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="06c91-120">See also</span></span>

- [<span data-ttu-id="06c91-121">Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="06c91-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
