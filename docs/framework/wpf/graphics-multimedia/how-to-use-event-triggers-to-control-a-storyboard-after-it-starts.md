---
title: 'Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186702"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="72e92-102">Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="72e92-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="72e92-103">En este ejemplo se <xref:System.Windows.Media.Animation.Storyboard> muestra cómo controlar una después de que se inicia.</span><span class="sxs-lookup"><span data-stu-id="72e92-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="72e92-104">Para iniciar <xref:System.Windows.Media.Animation.Storyboard> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante <xref:System.Windows.Media.Animation.BeginStoryboard>, use , que distribuye las animaciones a los objetos y propiedades que animan y, a continuación, inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="72e92-105">Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre especificando su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, lo convierte en un guión gráfico controlable.</span><span class="sxs-lookup"><span data-stu-id="72e92-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="72e92-106">A continuación, puede controlar interactivamente el guión gráfico después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="72e92-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="72e92-107">Utilice las siguientes acciones <xref:System.Windows.EventTrigger> de guión gráfico junto con objetos para controlar un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="72e92-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="72e92-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: reanuda un guión gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="72e92-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="72e92-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="72e92-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: avanza un guión gráfico hasta el final de su período de relleno, si tiene uno.</span><span class="sxs-lookup"><span data-stu-id="72e92-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="72e92-112"><xref:System.Windows.Media.Animation.StopStoryboard>: detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="72e92-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: elimina el guión gráfico, liberando recursos.</span><span class="sxs-lookup"><span data-stu-id="72e92-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="72e92-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72e92-114">Example</span></span>

<span data-ttu-id="72e92-115">En el ejemplo siguiente se usan acciones de guión gráfico controlables para controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="72e92-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="72e92-116">Para ver un ejemplo de control de un guión gráfico mediante código, vea [Controlar un guión gráfico después de que comience a usar sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="72e92-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="72e92-117">Para obtener ejemplos adicionales, consulte la Galería de ejemplos de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="72e92-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="72e92-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72e92-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="72e92-119">Controlar un guión gráfico una vez iniciado mediante métodos interactivos</span><span class="sxs-lookup"><span data-stu-id="72e92-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="72e92-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="72e92-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="72e92-121">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="72e92-121">Storyboards Overview</span></span>](storyboards-overview.md)
