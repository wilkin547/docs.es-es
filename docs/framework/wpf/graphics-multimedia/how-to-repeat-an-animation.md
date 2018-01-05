---
title: "Cómo: Repetir una animación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 591053d479b7d26757eb071f08ed4216fc0d57fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-repeat-an-animation"></a>Cómo: Repetir una animación
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> para controlar el comportamiento de repetición de una animación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> controla cuántas veces una animación repite su duración simple. Mediante el uso de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar que un <xref:System.Windows.Media.Animation.Timeline> se repite un número determinado de veces (un número de iteraciones) o durante un período de tiempo especificado. En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para llenar el número solicitado o la duración.  
  
 De forma predeterminada, las escalas de tiempo tienen un número de repeticiones de 1,0, lo que significa que se reproduce una vez y no se repiten. Sin embargo, si establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la escala de tiempo se repite indefinidamente.  
  
 En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para controlar el comportamiento de repetición de una animación. En el ejemplo se anima la <xref:System.Windows.FrameworkElement.Width%2A> propiedad de cinco rectángulos con cada rectángulo con un tipo diferente del comportamiento de repetición.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Para obtener un ejemplo completo, vea [ejemplo de comportamiento de tiempo de animación](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>Vea también  
 [Acumular valores de animaciones durante la repetición de ciclos](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Especificar si una escala de tiempo se invierte automáticamente](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Animación y temporización](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Ejemplo del comportamiento del control de tiempo de la animación](http://go.microsoft.com/fwlink/?LinkID=159970)
