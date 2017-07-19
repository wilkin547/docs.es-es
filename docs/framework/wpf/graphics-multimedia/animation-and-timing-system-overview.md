---
title: "Informaci&#243;n general sobre sistemas de temporizaci&#243;n y animaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación [WPF]"
  - "sistema de temporización [WPF]"
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre sistemas de temporizaci&#243;n y animaci&#243;n
En este tema se describe cómo el sistema del control de tiempo utiliza las clases de animación, <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> para animar propiedades.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe poder utilizar animaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para animar propiedades, como se describe en [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  También ayuda conocer las [propiedades de dependencia](GTMT); para obtener más información, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## Escalas de tiempo y relojes  
 En [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) se describía cómo un objeto <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo, y cómo una animación es un tipo de objeto <xref:System.Windows.Media.Animation.Timeline> que produce valores de salida.  Por sí mismo, un objeto <xref:System.Windows.Media.Animation.Timeline>, no hace nada más que describir un segmento de tiempo.  Es el objeto <xref:System.Windows.Media.Animation.Clock> de la escala de tiempo el que hace el trabajo real.  Igualmente, la animación realmente no anima las propiedades: una clase de animación describe cómo se deben calcular los valores de salida, pero es el objeto <xref:System.Windows.Media.Animation.Clock> creado para la animación el que controla el resultado de la animación y lo aplica a las propiedades.  
  
 Un objeto <xref:System.Windows.Media.Animation.Clock> es un tipo especial de objeto que mantiene el estado de tiempo de ejecución relacionado con el control de tiempo para el objeto <xref:System.Windows.Media.Animation.Timeline>.  Proporciona tres bits de información que son esenciales a la animación y el sistema de control de tiempo: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A> y <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>.  Un objeto <xref:System.Windows.Media.Animation.Clock> determina la hora actual, el progreso y el estado utilizando los comportamientos de control de tiempo descritos por <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, etc.  
  
 En la mayoría de los casos, se crea automáticamente un objeto <xref:System.Windows.Media.Animation.Clock> para la escala de tiempo.  Al animar utilizando un objeto <xref:System.Windows.Media.Animation.Storyboard> o el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>, se crean automáticamente relojes para las escalas de tiempo y las animaciones, y se aplican a sus propiedades concretas.  También se puede crear un objeto <xref:System.Windows.Media.Animation.Clock> explícitamente usando el método <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> del objeto <xref:System.Windows.Media.Animation.Timeline>.  El método <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=fullName> crea un reloj del tipo adecuado para el objeto <xref:System.Windows.Media.Animation.Timeline> en el que se llama.  Si el objeto <xref:System.Windows.Media.Animation.Timeline> contiene escalas de tiempo secundarias, también crea objetos <xref:System.Windows.Media.Animation.Clock> para ellas.  Los objetos <xref:System.Windows.Media.Animation.Clock> resultantes se organizan en árboles que coinciden con la estructura del árbol de objetos <xref:System.Windows.Media.Animation.Timeline> a partir del cual se crean.  
  
 Hay diferentes tipos de relojes para diferentes tipos de escalas de tiempo.  La tabla siguiente muestra los tipos de <xref:System.Windows.Media.Animation.Clock> que corresponden a algunos de los diferentes tipos de <xref:System.Windows.Media.Animation.Timeline>.  
  
|Tipo de escala de tiempo|Tipo de reloj|Propósito del reloj|  
|------------------------------|-------------------|-------------------------|  
|Animación \(hereda de <xref:System.Windows.Media.Animation.AnimationTimeline>\)|<xref:System.Windows.Media.Animation.AnimationClock>|Genera valores de salida para una propiedad de dependencia.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Procesa un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Agrupa y controla sus objetos <xref:System.Windows.Media.Animation.Clock> secundarios|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Agrupa y controla sus objetos <xref:System.Windows.Media.Animation.Clock> secundarios|  
  
 Puede aplicar cualquier objeto <xref:System.Windows.Media.Animation.AnimationClock> que cree a las propiedades de dependencia compatibles utilizando el método <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A>.  
  
 En los escenarios de rendimiento intensivo, tales como la animación de grandes números de objetos similares, la administración del uso del propio objeto <xref:System.Windows.Media.Animation.Clock> puede proporcionar ventajas de rendimiento.  
  
<a name="timemanager"></a>   
## Los relojes y el administrador de tiempo  
 Al animar los objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es el administrador de tiempo el que administra los objetos <xref:System.Windows.Media.MediaPlayer.Clock%2A> creados para las escalas de tiempo.  El administrador de tiempo es la raíz de un árbol de objetos <xref:System.Windows.Media.MediaPlayer.Clock%2A> y controla el flujo de tiempo en ese árbol.  El administrador de tiempo se crea automáticamente para cada aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y no es visible para el desarrollador de aplicaciones. El administrador de tiempo "marca pasos" muchas veces por segundo; el número real de pasos que se producen cada segundo varía, en función de los recursos disponibles en el sistema.  Durante cada uno de estos pasos, el administrador de tiempo calcula el estado de todos los objetos <xref:System.Windows.Media.Animation.ClockState><xref:System.Windows.Media.Animation.Clock>del árbol de control de tiempo.  
  
 En la ilustración siguiente se muestra la relación entre el administrador de tiempo, <xref:System.Windows.Media.Animation.AnimationClock> y una propiedad de dependencia animada.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm\_clocks\_1clock1prop")  
Animar una propiedad  
  
 Cuando el administrador horario marca un paso, actualiza el tiempo de cada objeto <xref:System.Windows.Media.Animation.Clock> <xref:System.Windows.Media.Animation.ClockState> de la aplicación.  Si el objeto <xref:System.Windows.Media.Animation.Clock> es un objeto <xref:System.Windows.Media.Animation.AnimationClock>, utiliza el método <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> del objeto <xref:System.Windows.Media.Animation.AnimationTimeline> a partir del que fue creado para calcular su valor de salida actual.  El objeto <xref:System.Windows.Media.Animation.AnimationClock> proporciona al objeto <xref:System.Windows.Media.Animation.AnimationTimeline> la hora local actual, un valor de entrada, que es normalmente el valor base de la propiedad, y un valor de destino predeterminado.  Al recuperar el valor de un elemento animado por propiedad utilizando el método <xref:System.Windows.DependencyObject.GetValue%2A> o su descriptor de acceso CLR, se obtiene el resultado de su objeto <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### Grupos de relojes  
 En la sección anterior se describió cómo hay diferentes tipos de objetos <xref:System.Windows.Media.Animation.Clock> para los diferentes tipos de escala de tiempo.  En la ilustración siguiente se muestra la relación entre el administrador de tiempo, un objeto <xref:System.Windows.Media.Animation.ClockGroup>, un objeto <xref:System.Windows.Media.Animation.AnimationClock> y una propiedad de dependencia animada.  Un objeto <xref:System.Windows.Media.Animation.ClockGroup> se crea para las escalas de tiempo que agrupan otras escalas de tiempo, tales como la clase <xref:System.Windows.Media.Animation.Storyboard>, que agrupa animaciones y otras escalas de tiempo.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm\_clocks\_2clock1clockgroup2prop")  
Un objeto ClockGroup  
  
#### Composición  
 Es posible asociar varios relojes a una única propiedad, en cuyo caso cada reloj utiliza el valor de salida del reloj anterior como su valor base.  En la ilustración siguiente se muestran tres objetos <xref:System.Windows.Media.Animation.AnimationClock> aplicados a la misma propiedad.  El reloj1 utiliza el valor base de la propiedad animada como entrada y lo utiliza para generar el resultado.  El reloj2 toma el resultado del reloj1 como entrada y lo utiliza para generar el resultado.  El reloj3 toma el resultado del reloj2 como entrada y lo utiliza para generar el resultado.  Cuando varios relojes afectan simultáneamente a la misma propiedad, se dice que están en una cadena de composición.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm\_clocks\_2clock1prop")  
Una cadena de composición  
  
 Tenga en cuenta que, aunque se crea una relación entre la entrada y la salida de los objetos <xref:System.Windows.Media.Animation.AnimationClock> de la cadena de composición, sus comportamientos de control de tiempo no se ven afectados; los objetos <xref:System.Windows.Media.Animation.Clock> \(incluidos los objetos <xref:System.Windows.Media.Animation.AnimationClock>\) tienen una dependencia jerárquica de sus objetos <xref:System.Windows.Media.Animation.Clock> primarios.  
  
 Para aplicar varios relojes a la misma propiedad, utilice el miembro <xref:System.Windows.Media.Animation.HandoffBehavior> de <xref:System.Windows.Media.Animation.HandoffBehavior> cuando aplique una animación de <xref:System.Windows.Media.Animation.Storyboard>, o un objeto <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### Pasos y consolidación de eventos  
 Además de calcular valores de salida, el administrador de tiempo hace otras cosas a cada paso que marca: determina el estado de cada reloj y genera los eventos adecuados.  
  
 Aunque los pasos se producen con frecuencia, pueden ocurrir muchas cosas entre ellos.  Por ejemplo, un objeto <xref:System.Windows.Media.Animation.Clock> se puede detener, iniciarse y detenerse de nuevo, en cuyo caso sus valores <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> habrán cambiado tres veces.  En teoría, el evento <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> se podría provocarse varias veces en un único paso; sin embargo, el motor de control de tiempo consolida los eventos, para que el evento <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> pueda provocarse como máximo una vez por paso.  Esto es verdadero para todos los eventos de control de tiempo: como máximo se provoca un evento de cada tipo para un objeto <xref:System.Windows.Media.Animation.Clock> determinado.  
  
 Cuando un objeto <xref:System.Windows.Media.Animation.Clock> cambia de estado y vuelve a su estado original entre pasos \(por ejemplo al cambiar de <xref:System.Windows.Media.Animation.ClockState> a <xref:System.Windows.Media.Animation.ClockState> y de nuevo a <xref:System.Windows.Media.Animation.ClockState>\), el evento asociado continúa produciéndose.  
  
 \(Para obtener más información acerca de los eventos de control de tiempo, vea [Información general sobre eventos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).\)  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## Valores actuales y valores base de propiedades  
 Una propiedad que se pueda animar puede tener dos valores: un valor base y un valor actual.  Al establecer propiedades mediante su descriptor de acceso CLR o el método <xref:System.Windows.DependencyObject.SetValue%2A>, se establece su valor base.  Cuando no se anima una propiedad, su valor base y su valor actual son el mismo.  
  
 Cuando se anima una propiedad, el objeto <xref:System.Windows.Media.Animation.AnimationClock> establece el valor *actual* de la propiedad.  Al recuperar el valor de la propiedad a través de su descriptor de acceso CLR o del método <xref:System.Windows.DependencyObject.GetValue%2A> se devuelve el resultado del objeto <xref:System.Windows.Media.Animation.AnimationClock> cuando el objeto <xref:System.Windows.Media.Animation.AnimationClock> es <xref:System.Windows.Media.Animation.ClockState> o <xref:System.Windows.Media.Animation.ClockState>.  Puede recuperar el valor base de la propiedad utilizando el método <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A>.  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre eventos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)