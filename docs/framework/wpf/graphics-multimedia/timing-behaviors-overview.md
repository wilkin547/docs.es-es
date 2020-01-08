---
title: Información general sobre comportamientos de control de tiempo
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559955"
---
# <a name="timing-behaviors-overview"></a>Información general sobre comportamientos de control de tiempo
En este tema se describen los comportamientos de control de tiempo de las animaciones y otros objetos de <xref:System.Windows.Media.Animation.Timeline>.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas. Para obtener más información, vea [información general sobre animaciones](animation-overview.md).  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>Tipos de objetos Timeline  
 <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo. Proporciona propiedades que permiten especificar la longitud de ese segmento, cuándo debe iniciarse, cuántas veces se repetirá o la velocidad a la que progresará el tiempo en ese segmento, entre otras.  
  
 Las clases que heredan de la clase Timeline proporcionan funcionalidades adicionales, como reproducción de animaciones y multimedia. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona los siguientes tipos de <xref:System.Windows.Media.Animation.Timeline>.  
  
|Tipos de objetos Timeline|Descripción|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Clase base abstracta para los objetos <xref:System.Windows.Media.Animation.Timeline> que generan valores de salida para animar propiedades.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera la salida de un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Tipo de <xref:System.Windows.Media.Animation.TimelineGroup> que agrupa y controla los objetos <xref:System.Windows.Media.Animation.Timeline> secundarios.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Tipo de <xref:System.Windows.Media.Animation.ParallelTimeline> que proporciona información de destino para los objetos de la escala de tiempo que contiene.|  
|<xref:System.Windows.Media.Animation.Timeline>|Clase base abstracta que define los comportamientos de control de tiempo.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Clase abstracta para los objetos <xref:System.Windows.Media.Animation.Timeline> que pueden contener otros objetos <xref:System.Windows.Media.Animation.Timeline>.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>Propiedades que controlan la longitud de un objeto Timeline  
 Una <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo, y la longitud de una escala de tiempo se puede describir de maneras diferentes. La siguiente tabla define varios términos para describir la longitud de un objeto Timeline.  
  
|Término|Descripción|Propiedades||||  
|----------|-----------------|----------------|-|-|-|  
|Duración simple|El intervalo de tiempo que un objeto Timeline tarda en realizar una iteración de avance.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una repetición|La cantidad de tiempo que tarda una escala de tiempo en reproducirse una vez y, si la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> es true, se reproduce una vez hacia atrás.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Período activo|Período de tiempo que tarda una escala de tiempo en completar todas las repeticiones especificadas por su propiedad <xref:System.Windows.Media.Animation.RepeatBehavior>.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Propiedad Duration  
 Como se ha mencionado previamente, un objeto Timeline representa un segmento de tiempo. La longitud de ese segmento viene determinada por la <xref:System.Windows.Media.Animation.Timeline.Duration%2A>de la escala de tiempo. Cuando un objeto Timeline llega al final de su duración, detiene la reproducción. Si el objeto Timeline tiene objetos Timeline secundarios, su reproducción también se detiene. En el caso de una animación, el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> especifica cuánto tiempo tarda la animación en pasar de su valor inicial a su valor final. La duración de una escala de tiempo se denomina a veces su *duración simple*, para distinguir entre la duración de una iteración única y la duración total de tiempo que se reproduce la animación, incluidas las repeticiones. Puede especificar una duración mediante un valor de hora finito o los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>. La duración de una animación debe resolverse en un valor <xref:System.Windows.Duration.TimeSpan%2A>, por lo que puede realizar la transición entre valores.  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 Las escalas de tiempo de contenedor, como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que significa que finalizan automáticamente cuando su último elemento secundario deja de reproducirse. En el ejemplo siguiente se muestra un <xref:System.Windows.Media.Animation.Storyboard> cuyo <xref:System.Windows.Media.Animation.Timeline.Duration%2A> se resuelve en cinco segundos, el tiempo que se tardan todos sus objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios en completarse.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 Al establecer el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo de contenedor en un valor de <xref:System.Windows.Duration.TimeSpan%2A>, puede forzar que se reproduzca más o menos que sus objetos <xref:System.Windows.Media.Animation.Timeline> secundarios se reproduzcan. Si establece el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en un valor menor que la longitud de los objetos <xref:System.Windows.Media.Animation.Timeline> secundarios de la escala de tiempo del contenedor, los objetos secundarios <xref:System.Windows.Media.Animation.Timeline> dejarán de reproducirse cuando lo hace la escala de tiempo del contenedor. En el ejemplo siguiente se establece el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la <xref:System.Windows.Media.Animation.Storyboard> de los ejemplos anteriores en tres segundos. Como resultado, la primera <xref:System.Windows.Media.Animation.DoubleAnimation> detiene el progreso transcurridos tres segundos, cuando ha animado el ancho del rectángulo de destino hasta 60.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>Propiedad RepeatBehavior  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de una <xref:System.Windows.Media.Animation.Timeline> controla el número de veces que se repite su duración simple. Con la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar el número de veces que se reproduce la escala de tiempo (una iteración <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) o la duración total de tiempo que debe reproducirse (un <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>de repetición). En cualquier caso, la animación pasa por tantas repeticiones de principio a fin como sean necesarias para completar el recuento o la duración solicitados. De forma predeterminada, las escalas de tiempo tienen un recuento de iteraciones de `1.0`, lo que significa que se reproducen una vez y no se repiten.  
  
 En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para hacer que un <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca durante el doble de su duración simple mediante la especificación de un recuento de iteraciones.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para hacer que el <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca durante la mitad de su duración simple.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 Si establece la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de una <xref:System.Windows.Media.Animation.Timeline> en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la <xref:System.Windows.Media.Animation.Timeline> se repite hasta que se detiene interactivamente o por el sistema de control de tiempo. En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para hacer que el <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca indefinidamente.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 Para ver un ejemplo adicional, consulte [repetir una animación](how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>Propiedad AutoReverse  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> especifica si un <xref:System.Windows.Media.Animation.Timeline> se reproducirá hacia atrás al final de cada iteración de avance. En el ejemplo siguiente se establece en la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> de una <xref:System.Windows.Media.Animation.DoubleAnimation> en `true`; como resultado, anima desde cero hasta 100 y, a continuación, de 100 a cero. Se reproduce durante un total de 10 segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 Cuando se usa un valor <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> para especificar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un <xref:System.Windows.Media.Animation.Timeline> y la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> de ese <xref:System.Windows.Media.Animation.Timeline> es `true`, una repetición única consta de una iteración de avance seguida de una iteración hacia atrás.  En el ejemplo siguiente se establece el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> del ejemplo anterior en una <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> de dos. Como resultado, el <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduce durante 20 segundos: avance durante cinco segundos, hacia atrás durante cinco segundos, hacia adelante durante cinco segundos y, a continuación, hacia atrás durante cinco segundos.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 Si una escala de tiempo de contenedor tiene objetos secundarios <xref:System.Windows.Media.Animation.Timeline>, se revierten cuando la escala de tiempo del contenedor. Para obtener más ejemplos, vea [especificar si una escala de tiempo se invierte automáticamente](how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>Propiedad BeginTime  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> permite especificar Cuándo se inicia una escala de tiempo.  El momento de inicio de un objeto Timeline es relativo a su objeto Timeline primario. Un tiempo de inicio de cero segundos significa que el objeto Timeline se inicia tan pronto lo hace su primario; cualquier otro valor crea un desfase entre el momento en que se empieza a reproducir el Timeline primario y el momento en que lo hace el secundario. Por ejemplo, un tiempo de inicio de dos segundos significa que el objeto Timeline empieza a reproducirse cuando su elemento primario ha alcanzado un tiempo de dos segundos. De forma predeterminada, todos los objetos Timeline tienen un tiempo de inicio de cero segundos. También puede establecer la hora de inicio de una escala de tiempo en `null`, lo que impide que se inicie la escala de tiempo. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especifique NULL mediante la [extensión de marcado x:null](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
 Tenga en cuenta que la hora de inicio no se aplica cada vez que una escala de tiempo se repite debido a su configuración <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>. Si fuera a crear una animación con una <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> de 10 segundos y un <xref:System.Windows.Media.Animation.RepeatBehavior> de <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, se produciría un retraso de 10 segundos antes de que se reproduzca la animación por primera vez, pero no para cada repetición sucesiva. Sin embargo, si se reinicia o repite el objeto Timeline primario, se produciría el retraso de 10 segundos.  
  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> es útil para escalonar las escalas de tiempo. En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios. La primera animación tiene una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos y la segunda tiene una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de 3 segundos. En el ejemplo se establece el <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> del segundo <xref:System.Windows.Media.Animation.DoubleAnimation> en 5 segundos, de modo que comience a reproducirse después de que finalice la primera <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>Propiedad FillBehavior  
 Cuando un <xref:System.Windows.Media.Animation.Timeline> alcanza el final de su duración total activa, la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> especifica si se detiene o contiene su último valor. Una animación con una <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "contiene" su valor de salida: la propiedad que se anima conserva el último valor de la animación. Un valor de <xref:System.Windows.Media.Animation.FillBehavior.Stop> hace que la animación deje de afectar a su propiedad de destino una vez finalizada.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios. Ambos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> animan el <xref:System.Windows.FrameworkElement.Width%2A> de una <xref:System.Windows.Shapes.Rectangle> de 0 a 100. Los elementos <xref:System.Windows.Shapes.Rectangle> tienen valores de <xref:System.Windows.FrameworkElement.Width%2A> no animados de 500 [píxeles independientes del dispositivo].  
  
- La propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> del primer <xref:System.Windows.Media.Animation.DoubleAnimation> está establecida en <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, el valor predeterminado. Como resultado, el ancho del rectángulo permanece en 100 una vez finalizada la <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
- La propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> del segundo <xref:System.Windows.Media.Animation.DoubleAnimation> está establecida en <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del segundo <xref:System.Windows.Shapes.Rectangle> vuelve a 500 después de que finalice la <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>Propiedades que controlan la velocidad de un objeto Timeline  
 La clase <xref:System.Windows.Media.Animation.Timeline> proporciona tres propiedades para especificar su velocidad:  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>: especifica la velocidad, en relación con su elemento primario, a la que progresa el tiempo para un <xref:System.Windows.Media.Animation.Timeline>. Los valores mayores que uno aumentan la velocidad del <xref:System.Windows.Media.Animation.Timeline> y sus objetos <xref:System.Windows.Media.Animation.Timeline> secundarios; los valores entre cero y uno lo ralentizan. Un valor de uno indica que <xref:System.Windows.Media.Animation.Timeline> progresa a la misma velocidad que su elemento primario. La <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> configuración de una escala de tiempo de contenedor afecta también a todos los objetos <xref:System.Windows.Media.Animation.Timeline> secundarios.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>: especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo que se dedica a acelerar. Para obtener un ejemplo, consulte [Cómo: acelerar o reducir la velocidad de una animación](how-to-accelerate-or-decelerate-an-animation.md). 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo empleada en deceleración. Para obtener un ejemplo, consulte [Cómo: acelerar o reducir la velocidad de una animación](how-to-accelerate-or-decelerate-an-animation.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre sistemas de control de tiempo y animación ](animation-and-timing-system-overview.md)
- [Información general sobre eventos de control de tiempo](timing-events-overview.md)
- [Temas "Cómo..."](animation-and-timing-how-to-topics.md)
- [Ejemplo del comportamiento del control de tiempo de la animación](https://go.microsoft.com/fwlink/?LinkID=159970)
