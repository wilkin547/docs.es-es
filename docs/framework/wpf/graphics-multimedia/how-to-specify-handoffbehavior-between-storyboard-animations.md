---
title: 'Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: c4728dc1cb4eeeff55e533b8d91e4512d9cc1d94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560556"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="c7caa-102">Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico</span><span class="sxs-lookup"><span data-stu-id="c7caa-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="c7caa-103">Este ejemplo muestra cómo especificar el comportamiento de entrega entre animaciones de guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="c7caa-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="c7caa-104">El <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> propiedad de <xref:System.Windows.Media.Animation.BeginStoryboard> especifica cómo las animaciones nuevas interactúan con otras existentes que ya se han aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c7caa-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7caa-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7caa-105">Example</span></span>  
 <span data-ttu-id="c7caa-106">En el ejemplo siguiente se crea dos botones que aumentan cuando se mueve el cursor del mouse sobre ellos y disminuyen de tamaño cuando el cursor se mueve inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c7caa-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="c7caa-107">Si el mouse sobre un botón y, a continuación, quitar rápidamente el cursor, la segunda animación se aplicará antes de que finalice la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="c7caa-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="c7caa-108">Es cuando se superponen dos animaciones así que puede ver la diferencia entre el <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valores de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> y <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="c7caa-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="c7caa-109">Un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina las animaciones superpuestas que produce una transición más suave entre las animaciones mientras que un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> hace que la nueva animación reemplace inmediatamente la animación anteriormente superpuesta.</span><span class="sxs-lookup"><span data-stu-id="c7caa-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c7caa-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7caa-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="c7caa-111">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="c7caa-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="c7caa-112">Animación y temporización</span><span class="sxs-lookup"><span data-stu-id="c7caa-112">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="c7caa-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="c7caa-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
