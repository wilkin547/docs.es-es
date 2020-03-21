---
title: 'Cómo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141178"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Cómo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su período de actividad
En este ejemplo se <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> muestra cómo <xref:System.Windows.Media.Animation.Timeline> especificar el for el inactivo de una propiedad animada.  
  
## <a name="example"></a>Ejemplo  
 La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad <xref:System.Windows.Media.Animation.Timeline> de a determina lo que sucede con el valor de una propiedad <xref:System.Windows.Media.Animation.Timeline> animada cuando no <xref:System.Windows.Media.Animation.Timeline> se está animando, es decir, cuando el está inactivo pero su elemento primario está dentro de su período activo o de retención. Por ejemplo, ¿una propiedad animada permanece en su valor final después de que finalice la animación o vuelve al valor que tenía antes de que se iniciara la animación?  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente <xref:System.Windows.FrameworkElement.Width%2A> se usa a para animar el de dos rectángulos. Cada rectángulo utiliza <xref:System.Windows.Media.Animation.Timeline> un objeto diferente.  
  
 Uno <xref:System.Windows.Media.Animation.Timeline> tiene <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> un que <xref:System.Windows.Media.Animation.FillBehavior.Stop>se establece en , lo que hace que el <xref:System.Windows.Media.Animation.Timeline> ancho del rectángulo vuelva a su valor no animado cuando los extremos. El <xref:System.Windows.Media.Animation.Timeline> otro <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> tiene <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>un , lo que hace que <xref:System.Windows.Media.Animation.Timeline> el ancho permanezca en su valor final cuando finaliza.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Para ver el ejemplo completo, consulte Galería de ejemplos de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Información general sobre animaciones](animation-overview.md)
- [Temas "Cómo..." de animación y control de tiempo](animation-and-timing-how-to-topics.md)
