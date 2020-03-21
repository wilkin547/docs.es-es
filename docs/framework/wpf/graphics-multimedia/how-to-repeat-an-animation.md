---
title: 'Cómo: Repetir una animación'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141554"
---
# <a name="how-to-repeat-an-animation"></a>Cómo: Repetir una animación
En este ejemplo se <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> muestra <xref:System.Windows.Media.Animation.Timeline> cómo utilizar la propiedad de a para controlar el comportamiento de repetición de una animación.  
  
## <a name="example"></a>Ejemplo  
 La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad <xref:System.Windows.Media.Animation.Timeline> de un controla cuántas veces una animación repite su duración simple. Mediante <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>el uso de <xref:System.Windows.Media.Animation.Timeline> , puede especificar que una repetición para un cierto número de veces (un recuento de iteraciones) o para un período de tiempo especificado. En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para completar el recuento o la duración solicitados.  
  
 De forma predeterminada, las escalas de tiempo tienen un recuento de repetición de 1,0, lo que significa que se reproducen una vez y no se repiten. Sin embargo, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> si establece <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>la propiedad de a a , la línea de tiempo se repite indefinidamente.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> se muestra cómo utilizar la propiedad para controlar el comportamiento de repetición de una animación. En el ejemplo <xref:System.Windows.FrameworkElement.Width%2A> se anima la propiedad de cinco rectángulos con cada rectángulo mediante un tipo diferente de comportamiento de repetición.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Para ver el ejemplo completo, vea Ejemplo de comportamiento de [temporización](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)de animación .  
  
## <a name="see-also"></a>Consulte también

- [Acumular valores de animaciones durante la repetición de ciclos](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Especificar si una escala de tiempo se invierte automáticamente](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Temas "Cómo..." de animación y control de tiempo](animation-and-timing-how-to-topics.md)
- [Información general sobre animaciones](animation-overview.md)
- [Ejemplo del comportamiento del control de tiempo de la animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
