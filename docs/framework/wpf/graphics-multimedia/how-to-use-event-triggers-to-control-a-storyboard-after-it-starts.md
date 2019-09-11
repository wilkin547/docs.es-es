---
title: Procedimiento Usar desencadenadores de eventos para controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855848"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="edba8-102">Procedimiento Usar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="edba8-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="edba8-103">En este ejemplo se muestra cómo controlar <xref:System.Windows.Media.Animation.Storyboard> una después de iniciarse.</span><span class="sxs-lookup"><span data-stu-id="edba8-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="edba8-104">Para iniciar <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante, use <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="edba8-105">Si asigna <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, lo convierte en un guión gráfico controlable.</span><span class="sxs-lookup"><span data-stu-id="edba8-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="edba8-106">Después, puede controlar interactivamente el guión gráfico una vez que se inicia.</span><span class="sxs-lookup"><span data-stu-id="edba8-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="edba8-107">Use las siguientes acciones de guion gráfico <xref:System.Windows.EventTrigger> junto con objetos para controlar un guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="edba8-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="edba8-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Reanuda un guion gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="edba8-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="edba8-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="edba8-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si tiene uno.</span><span class="sxs-lookup"><span data-stu-id="edba8-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="edba8-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guion gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="edba8-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico, liberando recursos.</span><span class="sxs-lookup"><span data-stu-id="edba8-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="edba8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edba8-114">Example</span></span>

<span data-ttu-id="edba8-115">En el ejemplo siguiente se usan acciones de guion gráfico controlables para controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="edba8-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="edba8-116">Para ver un ejemplo de cómo controlar un guión gráfico mediante código, vea [controlar un guión gráfico después de comenzar a usar sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="edba8-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="edba8-117">Para obtener más ejemplos, vea la [Galería de ejemplo de animación](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="edba8-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

## <a name="see-also"></a><span data-ttu-id="edba8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="edba8-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="edba8-119">Controlar un guión gráfico una vez iniciado usando métodos interactivos</span><span class="sxs-lookup"><span data-stu-id="edba8-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="edba8-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="edba8-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="edba8-121">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="edba8-121">Storyboards Overview</span></span>](storyboards-overview.md)
