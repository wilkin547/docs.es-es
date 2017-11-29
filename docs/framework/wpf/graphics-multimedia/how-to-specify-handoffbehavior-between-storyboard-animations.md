---
title: "Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 323ea563aec7bc7ad0abec2372e3af977c7e38eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Cómo: Especificar HandoffBehavior entre animaciones de guión gráfico
Este ejemplo muestra cómo especificar el comportamiento de entrega entre animaciones de guión gráfico. El <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> propiedad de <xref:System.Windows.Media.Animation.BeginStoryboard> especifica cómo las animaciones nuevas interactúan con otras existentes que ya se han aplicado a una propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea dos botones que aumentan cuando se mueve el cursor del mouse sobre ellos y disminuyen de tamaño cuando el cursor se mueve inmediatamente. Si el mouse sobre un botón y, a continuación, quitar rápidamente el cursor, la segunda animación se aplicará antes de que finalice la primera de ellas. Es cuando se superponen dos animaciones así que puede ver la diferencia entre el <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valores de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> y <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina las animaciones superpuestas que produce una transición más suave entre las animaciones mientras que un valor de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> hace que la nueva animación reemplace inmediatamente la animación anteriormente superpuesta.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animación y temporización](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Temas de procedimientos](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
