---
title: Información general sobre comportamientos de control de tiempo
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: f7c1aa81a5d3c283fdea06dd812f879f096c2ee2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355524"
---
# <a name="timing-behaviors-overview"></a>Información general sobre comportamientos de control de tiempo
En este tema se describe los comportamientos de temporización de animaciones y otros <xref:System.Windows.Media.Animation.Timeline> objetos.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas. Para obtener más información, consulte el [información general sobre animaciones](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Tipos de objetos Timeline  
 Un <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo. Proporciona propiedades que permiten especificar la longitud de ese segmento, cuándo debe iniciarse, cuántas veces se repetirá o la velocidad a la que progresará el tiempo en ese segmento, entre otras.  
  
 Las clases que heredan de la clase Timeline proporcionan funcionalidades adicionales, como reproducción de animaciones y multimedia. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona la siguiente <xref:System.Windows.Media.Animation.Timeline> tipos.  
  
|Tipos de objetos Timeline|Descripción|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Clase base abstracta para <xref:System.Windows.Media.Animation.Timeline> objetos que generan valores de salida para animar propiedades.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera la salida de un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Un tipo de <xref:System.Windows.Media.Animation.TimelineGroup> que los grupos y controles secundarios <xref:System.Windows.Media.Animation.Timeline> objetos.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Un tipo de <xref:System.Windows.Media.Animation.ParallelTimeline> que proporciona información de destino para los objetos de la escala de tiempo que contiene.|  
|<xref:System.Windows.Media.Animation.Timeline>|Clase base abstracta que define los comportamientos de control de tiempo.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Clase abstracta para <xref:System.Windows.Media.Animation.Timeline> objetos que pueden contener otros <xref:System.Windows.Media.Animation.Timeline> objetos.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Propiedades que controlan la longitud de un objeto Timeline  
 Un <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y la longitud de una escala de tiempo se pueden describir de maneras diferentes. La siguiente tabla define varios términos para describir la longitud de un objeto Timeline.  
  
|Término|Descripción|Propiedades||||  
|----------|-----------------|----------------|-|-|-|  
|Duración simple|El intervalo de tiempo que un objeto Timeline tarda en realizar una iteración de avance.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una repetición|El período de tiempo que tarda una escala de tiempo jugar al día una vez y, si la <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad es true, reproducir una vez hacia atrás.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Período activo|El período de tiempo que tarda una escala de tiempo completar todas las repeticiones especificadas por su <xref:System.Windows.Media.Animation.RepeatBehavior> propiedad.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Propiedad Duration  
 Como se ha mencionado previamente, un objeto Timeline representa un segmento de tiempo. La longitud de ese segmento viene determinada por la escala de tiempo <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Cuando un objeto Timeline llega al final de su duración, detiene la reproducción. Si el objeto Timeline tiene objetos Timeline secundarios, su reproducción también se detiene. En el caso de una animación, la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> especifica cuánto tiempo tarda la animación en la transición desde su valor inicial hasta su valor final. Duración de una escala de tiempo a veces se denomina su *duración simple*, para distinguir entre la duración de una sola iteración y la longitud total de tiempo reproduce la animación, incluidas las repeticiones. Puede especificar una duración mediante un valor de tiempo finito o los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. Duración de la animación se debe resolver en un <xref:System.Windows.Duration.TimeSpan%2A> valor, por lo que puede realizar la transición entre valores.  
  
 El ejemplo siguiente se muestra un <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Escalas de tiempo contenedoras, tales como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que significa que finalizan automáticamente cuando detiene la reproducción de su último miembro secundario. El ejemplo siguiente se muestra un <xref:System.Windows.Media.Animation.Storyboard> cuyo <xref:System.Windows.Media.Animation.Timeline.Duration%2A> se resuelve en cinco segundos, la longitud de tiempo que tarda en todos sus secundarios <xref:System.Windows.Media.Animation.DoubleAnimation> objetos que se va a completar.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Estableciendo el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de escala de tiempo contenedora para un <xref:System.Windows.Duration.TimeSpan%2A> valor, se puede forzar una reproducción mayores o menores que su elemento secundario <xref:System.Windows.Media.Animation.Timeline> objetos tardarían en reproducirse. Si establece la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en un valor que es menor que la longitud de los secundarios del contenedor <xref:System.Windows.Media.Animation.Timeline> objetos, el elemento secundario <xref:System.Windows.Media.Animation.Timeline> objetos detendrán la reproducción cuando lo hace su contenedor. El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la <xref:System.Windows.Media.Animation.Storyboard> de los ejemplos anteriores en tres segundos. Como resultado, la primera <xref:System.Windows.Media.Animation.DoubleAnimation> se detiene transcurridos tres segundos, cuando ha animado ancho del rectángulo de destino a 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>Propiedad RepeatBehavior  
 El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> controla cuántas veces repite su duración simple. Mediante el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad, puede especificar cuántas veces se reproduce la escala de tiempo (una iteración <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) o la longitud total de tiempo de reproducción (repetición <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). En cualquier caso, la animación pasa por tantas repeticiones de principio a fin como sean necesarias para completar el recuento o la duración solicitados. De forma predeterminada, las escalas de tiempo tienen una iteración de `1.0`, lo que significa que se reproducen una vez y no se repiten en absoluto.  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para hacer un <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca por dos veces su duración simple mediante la especificación de un número de iteraciones.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 El ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para hacer el <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca por la mitad de su duración simple.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Si establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad de un <xref:System.Windows.Media.Animation.Timeline> a <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, el <xref:System.Windows.Media.Animation.Timeline> se repite hasta que se detenga interactivamente o por el sistema de temporización. En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad para realizar la <xref:System.Windows.Media.Animation.DoubleAnimation> reproducir indefinidamente.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Para obtener un ejemplo adicional, consulte [repetir una animación](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>Propiedad AutoReverse  
 El <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad especifica si un <xref:System.Windows.Media.Animation.Timeline> se reproducirá hacia atrás al final de cada iteración de avance. El ejemplo siguiente se establece en el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad de un <xref:System.Windows.Media.Animation.DoubleAnimation> a `true`; como resultado, anima de cero a 100 y, a continuación, de 100 a cero. Se reproduce durante un total de 10 segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Cuando se usa un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> valor para especificar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un <xref:System.Windows.Media.Animation.Timeline> y el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad de ese <xref:System.Windows.Media.Animation.Timeline> es `true`, una repetición consta de una iteración de avance seguida de uno hacia atrás iteración.  El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de la <xref:System.Windows.Media.Animation.DoubleAnimation> del ejemplo anterior para un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> de dos. Como resultado, el <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduce durante 20 segundos: avanza cinco segundos, retrocede cinco segundos, avanza 5 segundos de nuevo y, finalmente, retrocede cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Si un contenedor tiene secundarios <xref:System.Windows.Media.Animation.Timeline> objetos, la reproducción se invierte cuando lo hace su contenedor. Para obtener ejemplos adicionales, consulte [especificar si una escala de tiempo se invierte automáticamente](how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>Propiedad BeginTime  
 El <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad le permite especificar cuándo se inicia una escala de tiempo.  El momento de inicio de un objeto Timeline es relativo a su objeto Timeline primario. Un tiempo de inicio de cero segundos significa que el objeto Timeline se inicia tan pronto lo hace su primario; cualquier otro valor crea un desfase entre el momento en que se empieza a reproducir el Timeline primario y el momento en que lo hace el secundario. Por ejemplo, un tiempo de inicio de dos segundos significa que el objeto Timeline empieza a reproducirse cuando su elemento primario ha alcanzado un tiempo de dos segundos. De forma predeterminada, todos los objetos Timeline tienen un tiempo de inicio de cero segundos. También puede establecer una escala de tiempo empezar a tiempo para `null`, lo que impide que se inicie la escala de tiempo. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especifique null mediante el [x: Null Markup Extension](../../xaml-services/x-null-markup-extension.md).  
  
 Observe que la hora de inicio no aplica cada vez que se repite una escala de tiempo de su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> configuración. Si desea crear una animación con una <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> de 10 segundos y un <xref:System.Windows.Media.Animation.RepeatBehavior> de <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, podría haber un retraso de 10 segundos antes de que se reproduce la animación por primera vez, pero no en sucesivas repeticiones. Sin embargo, si se reinicia o repite el objeto Timeline primario, se produciría el retraso de 10 segundos.  
  
 El <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad resulta útil para escalonar objetos Timeline. En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos secundarios <xref:System.Windows.Media.Animation.DoubleAnimation> objetos. La primera animación tiene un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos, y el segundo tiene un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de 3 segundos. El ejemplo se establece la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> del segundo <xref:System.Windows.Media.Animation.DoubleAnimation> en 5 segundos, lo que TI empieza a reproducirse después del primer <xref:System.Windows.Media.Animation.DoubleAnimation> finaliza.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>Propiedad FillBehavior  
 Cuando un <xref:System.Windows.Media.Animation.Timeline> llega al final de su duración activa total, el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad especifica si se detiene o mantiene su último valor. Una animación con una <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> ", mantiene su valor de salida: la propiedad animada conservará el último valor de la animación. Un valor de <xref:System.Windows.Media.Animation.FillBehavior.Stop> hace que la animación deje de afectar a su propiedad de destino después de finalizar.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos secundarios <xref:System.Windows.Media.Animation.DoubleAnimation> objetos. Ambos <xref:System.Windows.Media.Animation.DoubleAnimation> objetos animan la <xref:System.Windows.FrameworkElement.Width%2A> de un <xref:System.Windows.Shapes.Rectangle> de 0 a 100. El <xref:System.Windows.Shapes.Rectangle> elementos tienen no animado <xref:System.Windows.FrameworkElement.Width%2A> valores de 500 [píxeles independientes del dispositivo].  
  
-   El <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad de la primera <xref:System.Windows.Media.Animation.DoubleAnimation> está establecido en <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, el valor predeterminado. Como resultado, el ancho del rectángulo se mantiene en 100 después de la <xref:System.Windows.Media.Animation.DoubleAnimation> finaliza.  
  
-   El <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad del segundo <xref:System.Windows.Media.Animation.DoubleAnimation> está establecido en <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del segundo <xref:System.Windows.Shapes.Rectangle> vuelve a 500 después el <xref:System.Windows.Media.Animation.DoubleAnimation> finaliza.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Propiedades que controlan la velocidad de un objeto Timeline  
 La <xref:System.Windows.Media.Animation.Timeline> clase proporciona tres propiedades para especificar su velocidad:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> : Especifica la velocidad, en relación con su elemento primario, en el que pasa el tiempo para un <xref:System.Windows.Media.Animation.Timeline>. Los valores mayores que uno aumentan la velocidad de la <xref:System.Windows.Media.Animation.Timeline> y su elemento secundario <xref:System.Windows.Media.Animation.Timeline> objetos; los valores entre cero y uno la reducen. Un valor de uno indica que <xref:System.Windows.Media.Animation.Timeline> que avanza a la misma velocidad que su elemento primario. El <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> configuración de un objeto contenedor afecta a todos los de su elemento secundario <xref:System.Windows.Media.Animation.Timeline> también objetos.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> : Especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo transcurrido acelerando. Como ejemplo, vea [Cómo: Aumentar o reducir la velocidad de una animación](how-to-accelerate-or-decelerate-an-animation.md). 
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> : Especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de un objeto Timeline empleado en decelerar. Como ejemplo, vea [Cómo: Aumentar o reducir la velocidad de una animación](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre sistemas de control de tiempo y animación ](animation-and-timing-system-overview.md)
- [Información general sobre eventos de control de tiempo](timing-events-overview.md)
- [Temas "Cómo..."](animation-and-timing-how-to-topics.md)
- [Ejemplo del comportamiento del control de tiempo de la animación](https://go.microsoft.com/fwlink/?LinkID=159970)
