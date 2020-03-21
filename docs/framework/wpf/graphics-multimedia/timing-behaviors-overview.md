---
title: Información general sobre comportamientos de control de tiempo
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145402"
---
# <a name="timing-behaviors-overview"></a>Información general sobre comportamientos de control de tiempo
En este tema se describen los <xref:System.Windows.Media.Animation.Timeline> comportamientos de temporización de animaciones y otros objetos.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas. Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md).  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>Tipos de objetos Timeline  
 A <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo. Proporciona propiedades que permiten especificar la longitud de ese segmento, cuándo debe iniciarse, cuántas veces se repetirá o la velocidad a la que progresará el tiempo en ese segmento, entre otras.  
  
 Las clases que heredan de la clase Timeline proporcionan funcionalidades adicionales, como reproducción de animaciones y multimedia. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona los <xref:System.Windows.Media.Animation.Timeline> siguientes tipos.  
  
|Tipos de objetos Timeline|Descripción|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Clase base <xref:System.Windows.Media.Animation.Timeline> abstracta para objetos que generan valores de salida para animar propiedades.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera la salida de un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Un tipo <xref:System.Windows.Media.Animation.TimelineGroup> de ese <xref:System.Windows.Media.Animation.Timeline> grupo y controla los objetos secundarios.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Un tipo <xref:System.Windows.Media.Animation.ParallelTimeline> que proporciona información de segmentación para los objetos de línea de tiempo que contiene.|  
|<xref:System.Windows.Media.Animation.Timeline>|Clase base abstracta que define los comportamientos de control de tiempo.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Clase abstracta para <xref:System.Windows.Media.Animation.Timeline> objetos que pueden contener otros <xref:System.Windows.Media.Animation.Timeline> objetos.|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>Propiedades que controlan la longitud de un objeto Timeline  
 A <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y la longitud de una línea de tiempo se puede describir de diferentes maneras. La siguiente tabla define varios términos para describir la longitud de un objeto Timeline.  
  
|Término|Descripción|Propiedades||||  
|----------|-----------------|----------------|-|-|-|  
|Duración simple|El intervalo de tiempo que un objeto Timeline tarda en realizar una iteración de avance.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una repetición|El tiempo que tarda una línea de tiempo en <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> reproducirse una vez y, si la propiedad es true, se reproduce hacia atrás una vez.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Período activo|El tiempo que tarda una escala de tiempo en completar <xref:System.Windows.Media.Animation.RepeatBehavior> todas las repeticiones especificadas por su propiedad.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Propiedad Duration  
 Como se ha mencionado previamente, una escala de tiempo representa un segmento de tiempo. La longitud de ese segmento viene <xref:System.Windows.Media.Animation.Timeline.Duration%2A>determinada por la línea de tiempo. Cuando un objeto Timeline llega al final de su duración, detiene la reproducción. Si el objeto Timeline tiene objetos Timeline secundarios, su reproducción también se detiene. En el caso de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> una animación, especifica cuánto tiempo tarda la animación en pasar de su valor inicial a su valor final. La duración de una línea de tiempo a veces se denomina duración *simple,* para distinguir entre la duración de una sola iteración y la duración total de la animación, incluidas las repeticiones. Puede especificar una duración utilizando un valor de <xref:System.Windows.Duration.Automatic%2A> <xref:System.Windows.Duration.Forever%2A>tiempo finito o los valores especiales o . La duración de una animación debe resolverse en un <xref:System.Windows.Duration.TimeSpan%2A> valor, por lo que puede realizar la transición entre valores.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente <xref:System.Windows.Media.Animation.Timeline.Duration%2A> se muestra a con un de cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Las escalas de <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.ParallelTimeline>tiempo del contenedor, <xref:System.Windows.Duration.Automatic%2A>como y , tienen una duración predeterminada de , lo que significa que finalizan automáticamente cuando su último hijo deja de jugar. En el ejemplo <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Timeline.Duration%2A> siguiente se muestra un cuyo se resuelve en <xref:System.Windows.Media.Animation.DoubleAnimation> cinco segundos, el tiempo que tarda todos sus objetos secundarios en completarse.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Al establecer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> la línea de <xref:System.Windows.Duration.TimeSpan%2A> tiempo de un contenedor en un valor, puede forzar a reproducir más tiempo o más corto de lo que jugarían sus objetos secundarios. <xref:System.Windows.Media.Animation.Timeline> Si establece <xref:System.Windows.Media.Animation.Timeline.Duration%2A> el valor en un valor que es menor que <xref:System.Windows.Media.Animation.Timeline> la longitud <xref:System.Windows.Media.Animation.Timeline> de los objetos secundarios de la línea de tiempo del contenedor, los objetos secundarios dejan de reproducirse cuando lo hace la línea de tiempo del contenedor. En el ejemplo <xref:System.Windows.Media.Animation.Timeline.Duration%2A> siguiente <xref:System.Windows.Media.Animation.Storyboard> se establece el de los ejemplos anteriores en tres segundos. Como resultado, el <xref:System.Windows.Media.Animation.DoubleAnimation> primero deja de progresar después de tres segundos, cuando ha animado el ancho del rectángulo de destino a 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>Propiedad RepeatBehavior  
 La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad <xref:System.Windows.Media.Animation.Timeline> de un controla cuántas veces repite su duración simple. Con <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> la propiedad, puede especificar cuántas veces <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>se reproduce la línea de tiempo (una iteración) o el tiempo total que debe reproducir (una repetición). <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A> En cualquier caso, la animación pasa por tantas repeticiones de principio a fin como sean necesarias para completar el recuento o la duración solicitados. De forma predeterminada, las escalas de tiempo tienen un recuento de iteraciones de `1.0`, lo que significa que se reproducen una vez y no se repiten en absoluto.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza la propiedad para realizar una reproducción durante el doble de su duración simple especificando un recuento de iteraciones.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 En el ejemplo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza la propiedad para hacer la reproducción durante la mitad de su duración simple.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Si establece <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> la propiedad <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>de <xref:System.Windows.Media.Animation.Timeline> a a , las repeticiones hasta que se detengan interactivamente o por el sistema de temporización. En el ejemplo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza la propiedad para que la reproducción sea indefinida.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Para obtener un ejemplo adicional, consulte [Repetir una animación](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>Propiedad AutoReverse  
 La <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad especifica <xref:System.Windows.Media.Animation.Timeline> si a se reproducirá hacia atrás al final de cada iteración hacia delante. En el ejemplo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> `true`establece en la propiedad de a to ; como resultado, se anima de cero a 100, y luego de 100 a cero. Se reproduce durante un total de 10 segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Cuando se <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> utiliza un <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> valor <xref:System.Windows.Media.Animation.Timeline> para <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> especificar la <xref:System.Windows.Media.Animation.Timeline> `true`propiedad de a y la propiedad de es , una sola repetición consta de una iteración hacia delante seguida de una iteración hacia atrás.  En el ejemplo <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> siguiente <xref:System.Windows.Media.Animation.DoubleAnimation> se establece el <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> del ejemplo anterior en a de dos. Como resultado, <xref:System.Windows.Media.Animation.DoubleAnimation> las jugadas durante 20 segundos: hacia adelante durante cinco segundos, hacia atrás durante cinco segundos, hacia adelante durante 5 segundos de nuevo y luego hacia atrás durante cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Si una línea <xref:System.Windows.Media.Animation.Timeline> de tiempo de contenedor tiene objetos secundarios, se invierten cuando la línea de tiempo del contenedor lo hace. Para obtener ejemplos adicionales, consulte [Especificar si una línea de tiempo se invierte automáticamente.](how-to-specify-whether-a-timeline-automatically-reverses.md)  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>Propiedad BeginTime  
 La <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad le permite especificar cuándo se inicia una línea de tiempo.  El momento de inicio de un objeto Timeline es relativo a su objeto Timeline primario. Un tiempo de inicio de cero segundos significa que el objeto Timeline se inicia tan pronto lo hace su primario; cualquier otro valor crea un desfase entre el momento en que se empieza a reproducir el Timeline primario y el momento en que lo hace el secundario. Por ejemplo, un tiempo de inicio de dos segundos significa que el objeto Timeline empieza a reproducirse cuando su elemento primario ha alcanzado un tiempo de dos segundos. De forma predeterminada, todos los objetos Timeline tienen un tiempo de inicio de cero segundos. También puede establecer la hora de `null`inicio de una línea de tiempo en , lo que impide que se inicie la línea de tiempo. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se especifica null mediante la [extensión de marcado x:Null](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Tenga en cuenta que la hora de inicio no <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> se aplica cada vez que se repite una línea de tiempo debido a su configuración. Si creara una animación <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> con un de <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>10 segundos y un de , habría un retraso de 10 segundos antes de la animación reproducida por primera vez, pero no para cada repetición sucesiva. Sin embargo, si se reinicia o repite el objeto Timeline primario, se produciría el retraso de 10 segundos.  
  
 La <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad es útil para escalonar las escalas de tiempo. En el ejemplo <xref:System.Windows.Media.Animation.Storyboard> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> crea un que tiene dos objetos secundarios. La primera animación tiene un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco <xref:System.Windows.Media.Animation.Timeline.Duration%2A> segundos, y la segunda tiene un de 3 segundos. El ejemplo <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> establece el <xref:System.Windows.Media.Animation.DoubleAnimation> segundo en 5 segundos, de <xref:System.Windows.Media.Animation.DoubleAnimation> modo que comienza a jugar después de que finalice el primer.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>Propiedad FillBehavior  
 Cuando <xref:System.Windows.Media.Animation.Timeline> a alcanza el final de <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> su duración activa total, la propiedad especifica si se detiene o contiene su último valor. Una animación <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> con un de "mantiene" su valor de salida: la propiedad que se está animando conserva el último valor de la animación. Un valor <xref:System.Windows.Media.Animation.FillBehavior.Stop> de causa que la animación deje de afectar a su propiedad de destino una vez finalizada.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.Storyboard> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> crea un que tiene dos objetos secundarios. Ambos <xref:System.Windows.Media.Animation.DoubleAnimation> objetos <xref:System.Windows.FrameworkElement.Width%2A> animan el de un <xref:System.Windows.Shapes.Rectangle> de 0 a 100. Los <xref:System.Windows.Shapes.Rectangle> elementos tienen <xref:System.Windows.FrameworkElement.Width%2A> valores no animados de 500 [píxeles independientes del dispositivo].  
  
- La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad de <xref:System.Windows.Media.Animation.DoubleAnimation> la <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>primera se establece en , el valor predeterminado. Como resultado, el Ancho del Rectángulo permanece en <xref:System.Windows.Media.Animation.DoubleAnimation> 100 después de los extremos.  
  
- La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad del <xref:System.Windows.Media.Animation.DoubleAnimation> segundo <xref:System.Windows.Media.Animation.FillBehavior.Stop>se establece en . Como resultado, <xref:System.Windows.FrameworkElement.Width%2A> el segundo <xref:System.Windows.Shapes.Rectangle> se revierte a <xref:System.Windows.Media.Animation.DoubleAnimation> 500 después de los extremos.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Propiedades que controlan la velocidad de un objeto Timeline  
 La <xref:System.Windows.Media.Animation.Timeline> clase proporciona tres propiedades para especificar su velocidad:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>– Especifica esa tasa, en relación con su <xref:System.Windows.Media.Animation.Timeline>elemento primario, en la que avanza el momento de un archivo . Los valores mayores que uno <xref:System.Windows.Media.Animation.Timeline> aumentan <xref:System.Windows.Media.Animation.Timeline> la velocidad de los objetos secundarios y los suyos secundarios; valores entre cero y uno lo ralentizan. Un valor de uno <xref:System.Windows.Media.Animation.Timeline> indica que progresa a la misma velocidad que su elemento primario. La <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> configuración de una escala de <xref:System.Windows.Media.Animation.Timeline> tiempo de contenedor también afecta a todos sus objetos secundarios.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>: especifica el porcentaje <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una línea de tiempo gastada en aceleración. Para obtener un ejemplo, vea [Cómo: Acelerar o desacelerar una animación](how-to-accelerate-or-decelerate-an-animation.md).
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: especifica el porcentaje <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una línea de tiempo gastada en desaceleración. Para obtener un ejemplo, vea [Cómo: Acelerar o desacelerar una animación](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md)
- [Información general sobre eventos de control de tiempo](timing-events-overview.md)
- [Temas de información](animation-and-timing-how-to-topics.md)
- [Ejemplo del comportamiento del control de tiempo de la animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
