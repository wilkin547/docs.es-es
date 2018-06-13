---
title: 'Cómo: Definir una duración para una animación'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: df9e12e1bd3a365c3013d0f75df663bd46186ee2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561380"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Cómo: Definir una duración para una animación
A <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y la longitud de ese segmento viene determinados por la escala de tiempo <xref:System.Windows.Duration>. Cuando un <xref:System.Windows.Media.Animation.Timeline> llega al final de su duración, se detiene la reproducción. Si el <xref:System.Windows.Media.Animation.Timeline> tiene escalas de tiempo secundarias, detiene su reproducción. En el caso de una animación, la <xref:System.Windows.Duration> especifica cuánto tiempo tarda la animación en la transición desde su valor inicial hasta su valor final.  
  
 Puede especificar un <xref:System.Windows.Duration> con un tiempo concreto y finito o los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Duración de una animación siempre debe ser un valor de tiempo, porque una animación siempre debe tener una longitud definida, finita, de lo contrario, la animación no sabría cómo realizar la transición entre sus valores de destino. Escalas de tiempo contenedoras (<xref:System.Windows.Media.Animation.TimelineGroup> objetos), como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que significa que finalizan automáticamente cuando detiene la reproducción de su último miembro secundario.  
  
 En el siguiente color de ejemplo, el ancho, alto y el relleno de un <xref:System.Windows.Shapes.Rectangle> se anima. Las duraciones se establecen en escalas de tiempo de animación y el contenedor resultante de efectos de animación como controlar la velocidad percibida de una animación y reemplazar la duración de escalas de tiempo secundarias con la duración de una escala de tiempo contenedora.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Duration>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
