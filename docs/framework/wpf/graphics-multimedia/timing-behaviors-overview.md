---
title: "Informaci&#243;n general sobre comportamientos de control de tiempo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "comportamientos, control de tiempo"
  - "comportamientos de temporización"
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general sobre comportamientos de control de tiempo
En este tema se describen los comportamientos de control de tiempo de las animaciones y otros objetos <xref:System.Windows.Media.Animation.Timeline>.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas.  Para obtener más información, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="timelinetypes"></a>   
## Tipos de escalas de tiempo  
 Una <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo.  Proporciona propiedades que permiten especificar la longitud de ese segmento, cuándo debe iniciarse, cuántas veces se repetirá, con qué velocidad progresará el tiempo en ese segmento, etc.  
  
 Las clases que heredan de la clase de escala de tiempo proporcionan funcionalidades adicionales, como reproducción de animaciones y multimedia.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona los tipos <xref:System.Windows.Media.Animation.Timeline> siguientes.  
  
|Tipo de escala de tiempo|Descripción|  
|------------------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|Clase base abstracta para los objetos <xref:System.Windows.Media.Animation.Timeline> que generan los valores de salida para animar propiedades.|  
|<xref:System.Windows.Media.MediaTimeline>|Genera la salida de un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|Un tipo de <xref:System.Windows.Media.Animation.TimelineGroup> que agrupa y controla objetos <xref:System.Windows.Media.Animation.Timeline> secundarios.|  
|<xref:System.Windows.Media.Animation.Storyboard>|Un tipo de <xref:System.Windows.Media.Animation.ParallelTimeline> que proporciona información de destino para los objetos de escala de tiempo que contiene.|  
|<xref:System.Windows.Media.Animation.Timeline>|Clase base abstracta que define los comportamientos de control de tiempo.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|Clase abstracta para objetos <xref:System.Windows.Media.Animation.Timeline> que pueden contener otros objetos <xref:System.Windows.Media.Animation.Timeline>.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## Propiedades que controlan la longitud de una escala de tiempo  
 <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo. La longitud de una escala de tiempo se puede describir de maneras diferentes.  En la tabla siguiente se definen varios términos que describen la longitud de una escala de tiempo.  
  
|Término|Descripción|Propiedades||||  
|-------------|-----------------|-----------------|-|-|-|  
|Duración simple|El intervalo de tiempo que tarda una escala de tiempo en realizar una sola iteración de avance.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|Una repetición|El intervalo de tiempo que tarda una escala de tiempo en reproducirse hacia delante una vez y, si la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> es true, en reproducirse una vez hacia atrás.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|Período activo|Intervalo de tiempo que tarda una escala de tiempo en completar todas las repeticiones especificadas por su propiedad <xref:System.Windows.Media.Animation.RepeatBehavior>.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### Propiedad Duration  
 Como se ha mencionado previamente, una escala de tiempo representa un segmento de tiempo.  La longitud de ese segmento la determina la propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la escala de tiempo.  Cuando una escala de tiempo llega al fin de su duración, su reproducción se detiene.  Si la escala de tiempo tiene escalas de tiempo secundarias, también se detiene su reproducción.  En el caso de una animación, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> especifica cuánto tiempo tarda la animación en efectuar la transición desde su valor inicial hasta su valor final.  La duración de una escala de tiempo se denomina, en ocasiones, su *duración simple*, para distinguir entre la duración de una iteración única y el intervalo de tiempo total durante el que se reproduce una animación, incluidas las repeticiones.  Puede especificar una duración mediante un valor de tiempo finito, o con los valores especiales <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>.  La duración de una animación se debe resolver en un valor <xref:System.Windows.Duration.TimeSpan%2A>, para que pueda efectuar la transición entre valores.  
  
 En el ejemplo siguiente se muestra una <xref:System.Windows.Media.Animation.DoubleAnimation> con una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos.  
  
  
  
 Las escalas de tiempo contenedoras, como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que quiere decir que finalizan automáticamente cuando se detiene la reproducción de la última escala de tiempo secundaria.  En el ejemplo siguiente se muestra un <xref:System.Windows.Media.Animation.Storyboard> cuya <xref:System.Windows.Media.Animation.Timeline.Duration%2A> se resuelve en cinco segundos, el intervalo de tiempo que tardan en completarse todos sus objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios.  
  
  
  
 Estableciendo la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo contenedora en un valor de <xref:System.Windows.Duration.TimeSpan%2A>, puede forzar una reproducción durante más o menos tiempo que el que tardarían en reproducirse sus objetos <xref:System.Windows.Media.Animation.Timeline> secundarios.  Si establece <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en un valor que es menor que la longitud de los objetos <xref:System.Windows.Media.Animation.Timeline> secundarios de la escala de tiempo contenedora, la reproducción de los objetos <xref:System.Windows.Media.Animation.Timeline> secundarios se detendrá cuando lo haga la escala de tiempo contenedora.  En el ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> del <xref:System.Windows.Media.Animation.Storyboard> de los ejemplos anteriores en tres segundos.  Como resultado, la reproducción de la primera <xref:System.Windows.Media.Animation.DoubleAnimation> se detiene transcurridos tres segundos, cuando ha animado el ancho del rectángulo de destino hasta 60.  
  
  
  
<a name="repeatinganimations"></a>   
### Propiedad RepeatBehavior  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un objeto <xref:System.Windows.Media.Animation.Timeline> controla cuántas veces repite su duración simple.  Con la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar cuántas veces se reproduce la escala de tiempo \(<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> de iteración\) o el intervalo de tiempo total durante el que se debe reproducir \(<xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A> de repetición\).  En cualquier caso, la animación pasa por tantas repeticiones de principio a fin como sea necesario para rellenar el recuento o la duración solicitados.  De manera predeterminada, las escalas de tiempo tienen una iteración de `1.0`, lo que significa que se reproducen una vez y no se repiten en absoluto.  
  
 En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para reproducir <xref:System.Windows.Media.Animation.DoubleAnimation> durante dos veces su duración simple especificando un recuento de iteraciones.  
  
  
  
 En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para reproducir <xref:System.Windows.Media.Animation.DoubleAnimation> durante la mitad de su duración simple.  
  
  
  
 Si establece la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de <xref:System.Windows.Media.Animation.Timeline> en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, <xref:System.Windows.Media.Animation.Timeline> se repite hasta que se detenga interactivamente o por el sistema de control de tiempo.  En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para que <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduzca indefinidamente.  
  
  
  
 Para obtener otro ejemplo, vea [Repetir una animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md).  
  
<a name="autoreverseproperty"></a>   
### Propiedad AutoReverse  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> especifica si una <xref:System.Windows.Media.Animation.Timeline> se reproducirá hacia atrás al final de cada iteración de avance.  En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> de <xref:System.Windows.Media.Animation.DoubleAnimation> en `true`. Como resultado, se anima de cero a 100 y, a continuación, de 100 a cero.  Se reproduce durante un total de 10 segundos.  
  
  
  
 Cuando se utiliza un valor de <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> para especificar el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de <xref:System.Windows.Media.Animation.Timeline> y la propiedad <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> de esa <xref:System.Windows.Media.Animation.Timeline> es `true`, una repetición única está compuesta de una iteración de avance seguida por una iteración de retroceso.  En el ejemplo siguiente se establece el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de la <xref:System.Windows.Media.Animation.DoubleAnimation> de los ejemplos anteriores en un <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> de dos.  Como resultado, <xref:System.Windows.Media.Animation.DoubleAnimation> se reproduce durante 20 segundos: hacia delante durante cinco segundos, hacia atrás durante cinco segundos, de nuevo hacia delante durante 5 segundos y, por último, hacia atrás durante cinco segundos.  
  
  
  
 Si una escala de tiempo contenedora contenedor tiene objetos <xref:System.Windows.Media.Animation.Timeline> secundarios, su reproducción se invierte cuando lo hace la escala de tiempo contenedora.  Para obtener otros ejemplos, vea [Especificar si una escala de tiempo se invierte automáticamente](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md).  
  
<a name="timelinebegin"></a>   
## Propiedad BeginTime  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> permite especificar cuándo se inicia una escala de tiempo.  El momento de inicio de una escala de tiempo es relativa a su escala de tiempo primaria.  Un tiempo inicial de cero segundos significa que la escala de tiempo se inicia a la vez que su primaria; cualquier otro valor crea un desfase desde que se empieza a reproducir la escala de tiempo primaria hasta que se reproduce la escala de tiempo secundaria.  Por ejemplo, un tiempo de inicio de dos segundo significa que la reproducción de la escala de tiempo se inicia cuando su elemento primario lleva dos segundos reproduciéndose.  De manera predeterminada, todas las escalas de tiempo tienen un tiempo de inicio de cero segundos.  También puede establecer el tiempo inicial de una escala de tiempo en `null`, lo que evita que la escala de tiempo se inicie.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se especifica null mediante la [x:Null \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
 Observe que el tiempo de inicio no se aplica cada vez que una escala de tiempo se repite a causa de su valor de <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  Si crea una animación con un <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> de 10 segundos y un <xref:System.Windows.Media.Animation.RepeatBehavior> de <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, se producirá un retraso de 10 segundos antes de que la animación se reproduzca por primera vez, pero no para cada repetición sucesiva.  Sin embargo, si se inicia o repite la escala de tiempo primaria de la animación, se producirá el retraso de 10 segundos.  
  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> resulta útil para escalonar escalas de tiempo.  En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios.  La primera animación tiene una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos y, la segunda, una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de 3 segundos.  En el ejemplo se establece el <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> de la segunda <xref:System.Windows.Media.Animation.DoubleAnimation> en 5 segundos, para que empiece a reproducirse después de que finalice la primera <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
  
  
<a name="fillbehaviorproperty"></a>   
## Propiedad FillBehavior  
 Cuando una <xref:System.Windows.Media.Animation.Timeline> llega al final de su duración activa total, la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> especifica si se detiene o mantiene su último valor.  Una animación cuyo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> sea <xref:System.Windows.Media.Animation.FillBehavior> "mantendrá" su valor de salida: la propiedad animada conservará el último valor de la animación.  Un valor de <xref:System.Windows.Media.Animation.FillBehavior> hace que la animación deje de afectar a su propiedad de destino después de finalizar.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.Animation.Storyboard> que tiene dos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> secundarios.  Ambos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> animan la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de un objeto <xref:System.Windows.Shapes.Rectangle> de 0 a 100.  Los elementos <xref:System.Windows.Shapes.Rectangle> tienen valores <xref:System.Windows.FrameworkElement.Width%2A> no animados de 500 [píxeles independientes del dispositivo](GTMT).  
  
-   La propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de la primera <xref:System.Windows.Media.Animation.DoubleAnimation> se establece en <xref:System.Windows.Media.Animation.FillBehavior>, el valor predeterminado.  Como resultado, el ancho del rectángulo se mantiene en 100 después de que <xref:System.Windows.Media.Animation.DoubleAnimation> finalice.  
  
-   La propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de la segunda <xref:System.Windows.Media.Animation.DoubleAnimation> se establece en <xref:System.Windows.Media.Animation.FillBehavior>.  Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del segundo <xref:System.Windows.Shapes.Rectangle> revierte a 500 después de que <xref:System.Windows.Media.Animation.DoubleAnimation> finalice.  
  
  
  
<a name="speedproperties"></a>   
## Propiedades que controlan la velocidad de una escala de tiempo  
 La clase <xref:System.Windows.Media.Animation.Timeline> proporciona tres propiedades para especificar su velocidad:  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>: especifica la velocidad, relativa a su elemento primario, a la que progresa el tiempo para una <xref:System.Windows.Media.Animation.Timeline>.  Los valores mayores que uno aumentan la velocidad de <xref:System.Windows.Media.Animation.Timeline> y de sus objetos <xref:System.Windows.Media.Animation.Timeline> secundarios; los valores comprendidos entre cero y uno la reducen.  Un valor de uno indica que <xref:System.Windows.Media.Animation.Timeline> progresa a la misma velocidad que su elemento primario.  El valor <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> de una escala de tiempo contenedora también afecta a todos sus objetos <xref:System.Windows.Media.Animation.Timeline> secundarios.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>: especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo que se dedica a acelerar.  Para obtener un ejemplo, vea [Aumentar o reducir la velocidad de una animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>: especifica el porcentaje de la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una escala de tiempo que se dedica a decelerar.  Para obtener un ejemplo, vea [Aumentar o reducir la velocidad de una animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md).  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Información general sobre eventos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Ejemplo Animation Timing Behavior](http://go.microsoft.com/fwlink/?LinkID=159970)