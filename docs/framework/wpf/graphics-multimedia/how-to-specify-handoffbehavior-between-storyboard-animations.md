---
title: 'Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 6846cde9fd0aa93a0ce57fd2da0f9e1df85ec5a4
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698999"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico
En este ejemplo se muestra cómo especificar el comportamiento de entrega entre animaciones de guión gráfico. El <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> propiedad de <xref:System.Windows.Media.Animation.BeginStoryboard> especifica cómo las animaciones nuevas interactúan con otras existentes que ya se han aplicado a una propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea dos botones que aumentan cuando se mueve el cursor del mouse sobre ellos y disminuyen de tamaño cuando el cursor se mueve inmediatamente. Si un botón del mouse y, a continuación, quitar rápidamente el cursor, la segunda animación se aplicará antes de que finalice la primera de ellas. Es si se superponen dos animaciones como esta, que puede ver la diferencia entre el <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valores de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> y <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina las animaciones superpuestas causando una transición más suave entre animaciones, mientras que un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> hace que la nueva animación reemplace inmediatamente la animación que anteriormente se superponen.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animación y temporización](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
