---
title: Procedimiento Especificar HandoffBehavior entre animaciones de guión gráfico
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: a6da3f58fc6e999f5196cf5d8d3fd00f1098fc50
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745858"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="f4c35-102">Filtrar Especificar HandoffBehavior entre animaciones de guión gráfico</span><span class="sxs-lookup"><span data-stu-id="f4c35-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="f4c35-103">En este ejemplo se muestra cómo especificar el comportamiento de entrega entre animaciones de guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="f4c35-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="f4c35-104">El <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> propiedad de <xref:System.Windows.Media.Animation.BeginStoryboard> especifica cómo las animaciones nuevas interactúan con otras existentes que ya se han aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f4c35-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c35-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4c35-105">Example</span></span>  
 <span data-ttu-id="f4c35-106">El ejemplo siguiente crea dos botones que aumentan cuando se mueve el cursor del mouse sobre ellos y disminuyen de tamaño cuando el cursor se mueve inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="f4c35-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="f4c35-107">Si un botón del mouse y, a continuación, quitar rápidamente el cursor, la segunda animación se aplicará antes de que finalice la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="f4c35-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="f4c35-108">Es si se superponen dos animaciones como esta, que puede ver la diferencia entre el <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valores de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> y <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="f4c35-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="f4c35-109">Un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina las animaciones superpuestas causando una transición más suave entre animaciones, mientras que un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> hace que la nueva animación reemplace inmediatamente la animación que anteriormente se superponen.</span><span class="sxs-lookup"><span data-stu-id="f4c35-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f4c35-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c35-110">See also</span></span>
- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="f4c35-111">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="f4c35-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="f4c35-112">Temas de procedimientos de temporización y animación</span><span class="sxs-lookup"><span data-stu-id="f4c35-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
