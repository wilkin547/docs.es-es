---
title: "Cómo: Definir una duración para una animación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="dabba-102">Cómo: Definir una duración para una animación</span><span class="sxs-lookup"><span data-stu-id="dabba-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="dabba-103">A <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y la longitud de ese segmento viene determinados por la escala de tiempo <xref:System.Windows.Duration>.</span><span class="sxs-lookup"><span data-stu-id="dabba-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="dabba-104">Cuando un <xref:System.Windows.Media.Animation.Timeline> llega al final de su duración, se detiene la reproducción.</span><span class="sxs-lookup"><span data-stu-id="dabba-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="dabba-105">Si el <xref:System.Windows.Media.Animation.Timeline> tiene escalas de tiempo secundarias, detiene su reproducción.</span><span class="sxs-lookup"><span data-stu-id="dabba-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="dabba-106">En el caso de una animación, la <xref:System.Windows.Duration> especifica cuánto tiempo tarda la animación en la transición desde su valor inicial hasta su valor final.</span><span class="sxs-lookup"><span data-stu-id="dabba-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="dabba-107">Puede especificar un <xref:System.Windows.Duration> con un tiempo concreto y finito o los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>.</span><span class="sxs-lookup"><span data-stu-id="dabba-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="dabba-108">Duración de una animación siempre debe ser un valor de tiempo, porque una animación siempre debe tener una longitud definida, finita, de lo contrario, la animación no sabría cómo realizar la transición entre sus valores de destino.</span><span class="sxs-lookup"><span data-stu-id="dabba-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="dabba-109">Escalas de tiempo contenedoras (<xref:System.Windows.Media.Animation.TimelineGroup> objetos), como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que significa que finalizan automáticamente cuando detiene la reproducción de su último miembro secundario.</span><span class="sxs-lookup"><span data-stu-id="dabba-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="dabba-110">En el siguiente color de ejemplo, el ancho, alto y el relleno de un <xref:System.Windows.Shapes.Rectangle> se anima.</span><span class="sxs-lookup"><span data-stu-id="dabba-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="dabba-111">Las duraciones se establecen en escalas de tiempo de animación y el contenedor resultante de efectos de animación como controlar la velocidad percibida de una animación y reemplazar la duración de escalas de tiempo secundarias con la duración de una escala de tiempo contenedora.</span><span class="sxs-lookup"><span data-stu-id="dabba-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dabba-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dabba-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dabba-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dabba-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="dabba-114">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="dabba-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
