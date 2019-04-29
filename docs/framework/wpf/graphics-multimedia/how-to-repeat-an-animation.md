---
title: Procedimiento Repetir una animación
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942095"
---
# <a name="how-to-repeat-an-animation"></a>Procedimiento Repetir una animación
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> con el fin de controlar el comportamiento de repetición de una animación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> controla el número de veces que una animación repite su duración simple. Mediante el uso de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar que un <xref:System.Windows.Media.Animation.Timeline> se repite durante un determinado número de veces (un número de iteraciones) o durante un período de tiempo especificado. En cualquier caso, la animación pasa por tantas ejecuciones de principio a fin que necesita para rellenar el número solicitado o la duración.  
  
 De forma predeterminada, las escalas de tiempo tienen un número de repeticiones de 1,0, lo que significa que se reproducen una vez y no se repiten. Sin embargo, si establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la escala de tiempo se repite indefinidamente.  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para controlar el comportamiento de repetición de una animación. El ejemplo se anima la <xref:System.Windows.FrameworkElement.Width%2A> propiedad cinco rectángulos con cada rectángulo con un tipo diferente del comportamiento de repetición.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Para obtener un ejemplo completo, vea [ejemplo de comportamiento de control de tiempo de animación](https://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>Vea también

- [Acumular valores de animaciones durante la repetición de ciclos](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Especificar si una escala de tiempo se invierte automáticamente](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Temas de procedimientos de temporización y animación](animation-and-timing-how-to-topics.md)
- [Información general sobre animaciones](animation-overview.md)
- [Ejemplo del comportamiento del control de tiempo de la animación](https://go.microsoft.com/fwlink/?LinkID=159970)
