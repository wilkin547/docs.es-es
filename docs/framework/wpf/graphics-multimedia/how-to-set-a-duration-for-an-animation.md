---
title: Procedimiento Definir una duración para una animación
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: 7a2edbd953f648d5555e5dc50469211a6da066de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497936"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Procedimiento Definir una duración para una animación
Un <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y la longitud de ese segmento viene determinada por la escala de tiempo <xref:System.Windows.Duration>. Cuando un <xref:System.Windows.Media.Animation.Timeline> llega al final de su duración, detiene la reproducción. Si el <xref:System.Windows.Media.Animation.Timeline> tiene objetos Timeline secundarios, detener la reproducción. En el caso de una animación, la <xref:System.Windows.Duration> especifica cuánto tiempo tarda la animación en la transición desde su valor inicial hasta su valor final.  
  
 Puede especificar un <xref:System.Windows.Duration> con una hora específica y finita o los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Duración de una animación siempre debe ser un valor de tiempo, porque una animación siempre debe tener una longitud definida, finita, de lo contrario, la animación no sabría cómo realizar la transición entre sus valores de destino. Escalas de tiempo contenedoras (<xref:System.Windows.Media.Animation.TimelineGroup> objetos), como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que significa que finalizan automáticamente cuando detiene la reproducción de su último miembro secundario.  
  
 En el siguiente color de ejemplo, el ancho, alto y el relleno de un <xref:System.Windows.Shapes.Rectangle> está animada. Las duraciones están establecidas en escalas de tiempo de animación y el contenedor resultante en los efectos de animación como controlar la velocidad de una animación percibida y reemplazar la duración de objetos Timeline secundarios con la duración de un objeto contenedor.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Duration>
- [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
