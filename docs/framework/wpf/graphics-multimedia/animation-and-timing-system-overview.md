---
title: Información general sobre sistemas de temporización y animación
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: bfb9a337a604fe8d86d208344d4371748e28f285
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="animation-and-timing-system-overview"></a>Información general sobre sistemas de temporización y animación
Este tema describe cómo el sistema de temporización usa la animación, <xref:System.Windows.Media.Animation.Timeline>, y <xref:System.Windows.Media.Animation.Clock> clases para animar propiedades.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe poder utilizar animaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para animar propiedades, como se describe en [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). También ayuda conocer las propiedades de dependencia; para más información, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>Escalas de tiempo y relojes  
 El [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) se describe cómo un <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo y una animación es un tipo de <xref:System.Windows.Media.Animation.Timeline> que genera valores de salida. Por sí mismo, un <xref:System.Windows.Media.Animation.Timeline>, no hace nada más que describir un segmento de tiempo. Es la escala de tiempo <xref:System.Windows.Media.Animation.Clock> objeto que realiza el trabajo real. Del mismo modo, animación realmente no animar propiedades: una clase de animación describe cómo se deben calcular los valores de salida, pero es el <xref:System.Windows.Media.Animation.Clock> que se creó para la animación que controla la salida de la animación y se aplica a las propiedades.  
  
 A <xref:System.Windows.Media.Animation.Clock> es un tipo especial de objeto que mantiene el estado de tiempo de ejecución relacionados con el control de tiempo para el <xref:System.Windows.Media.Animation.Timeline>. Proporciona tres bits de información que son esenciales para la animación y el sistema de control de tiempo: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, y <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>. A <xref:System.Windows.Media.Animation.Clock> determina su hora actual, el progreso y el estado mediante los comportamientos de control de tiempo descritos por su <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, y así sucesivamente.  
  
 En la mayoría de los casos, un <xref:System.Windows.Media.Animation.Clock> se crea automáticamente la escala de tiempo. Cuando se anima mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método, relojes automáticamente se crean para su escalas de tiempo y las animaciones y se aplican a sus propiedades de destino. También puede crear un <xref:System.Windows.Media.Animation.Clock> explícitamente mediante la <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> método de su <xref:System.Windows.Media.Animation.Timeline>. El <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> método crea un reloj del tipo adecuado para el <xref:System.Windows.Media.Animation.Timeline> en el que se llama. Si el <xref:System.Windows.Media.Animation.Timeline> contiene escalas de tiempo secundarias, crea <xref:System.Windows.Media.Animation.Clock> objetos también para ellos. Resultante <xref:System.Windows.Media.Animation.Clock> objetos estén organizados en árboles que coinciden con la estructura de la <xref:System.Windows.Media.Animation.Timeline> árbol de los objetos desde que se han creado.  
  
 Hay diferentes tipos de relojes para diferentes tipos de escalas de tiempo. La tabla siguiente muestra la <xref:System.Windows.Media.Animation.Clock> tipos que corresponden a algunos de los diferentes <xref:System.Windows.Media.Animation.Timeline> tipos.  
  
|Tipos de objetos Timeline|Tipo de reloj|Propósito del reloj|  
|-------------------|----------------|-------------------|  
|Animación (hereda de <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|Genera valores de salida para una propiedad de dependencia.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|Procesa un archivo multimedia.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|Agrupa y controla su elemento secundario <xref:System.Windows.Media.Animation.Clock> objetos|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|Agrupa y controla su elemento secundario <xref:System.Windows.Media.Animation.Clock> objetos|  
  
 Puede aplicar cualquiera <xref:System.Windows.Media.Animation.AnimationClock> objetos crear para propiedades de dependencia compatibles con el <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> método.  
  
 En escenarios de rendimiento intensivo, tales como la animación de grandes números de objetos similares, administrar su propio <xref:System.Windows.Media.Animation.Clock> uso puede proporcionar ventajas de rendimiento.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>Los relojes y el administrador de tiempo  
 Al animar objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es el Administrador de tiempo que administra el <xref:System.Windows.Media.MediaPlayer.Clock%2A> objetos creados para las escalas de tiempo. El administrador de tiempo es la raíz de un árbol de objetos <xref:System.Windows.Media.MediaPlayer.Clock%2A> y controla el flujo de tiempo en ese árbol.  El administrador de tiempo se crea automáticamente para cada aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y no es visible para el desarrollador de aplicaciones. El administrador de tiempo "marca pasos" muchas veces por segundo; el número real de pasos que se producen cada segundo varía, en función de los recursos disponibles en el sistema. Durante cada uno de estos pasos, el Administrador de tiempo calcula el estado de todos los <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> objetos en el árbol de control de tiempo.  
  
 En la siguiente ilustración muestra la relación entre el Administrador de tiempo, y <xref:System.Windows.Media.Animation.AnimationClock>y una propiedad de dependencia animada.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
Animación de una propiedad  
  
 Cuando el Administrador de tiempo tics, actualiza el tiempo de cada <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> en la aplicación. Si el <xref:System.Windows.Media.Animation.Clock> es un <xref:System.Windows.Media.Animation.AnimationClock>, usa el <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> método de la <xref:System.Windows.Media.Animation.AnimationTimeline> desde que se creó calcular su actual valor de salida. El <xref:System.Windows.Media.Animation.AnimationClock> proporciona la <xref:System.Windows.Media.Animation.AnimationTimeline> con la hora local actual, un valor de entrada, que normalmente es el valor base de la propiedad y un valor de destino predeterminado. Cuando se recupera el valor de un elemento animado por propiedad mediante la <xref:System.Windows.DependencyObject.GetValue%2A> método o su descriptor de acceso CLR, obtendrá el resultado de su <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="clock-groups"></a>Grupos de relojes  
 La sección anterior describe cómo hay diferentes tipos de <xref:System.Windows.Media.Animation.Clock> objetos de diferentes tipos de escalas de tiempo. En la siguiente ilustración muestra la relación entre el Administrador de tiempo, un <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock>y una propiedad de dependencia animada. A <xref:System.Windows.Media.Animation.ClockGroup> se crea para las escalas de tiempo que agrupan otras escalas de tiempo, como la <xref:System.Windows.Media.Animation.Storyboard> (clase), que agrupa animaciones y otras escalas de tiempo.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
Un objeto ClockGroup  
  
#### <a name="composition"></a>Composición  
 Es posible asociar varios relojes a una única propiedad, en cuyo caso cada reloj utiliza el valor de salida del reloj anterior como su valor base. En la siguiente ilustración se muestra tres <xref:System.Windows.Media.Animation.AnimationClock> objetos que se aplican a la misma propiedad. El reloj1 utiliza el valor base de la propiedad animada como entrada y lo utiliza para generar la salida. El reloj2 toma la salida del reloj1 como entrada y lo utiliza para generar la salida. El reloj3 toma la salida del reloj2 como entrada y lo utiliza para generar la salida. Cuando varios relojes afectan simultáneamente a la misma propiedad, se dice que están en una cadena de composición.  
  
 ![Componentes del sistema de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
Una cadena de composición  
  
 Tenga en cuenta que, aunque se crea una relación entre la entrada y salida de la <xref:System.Windows.Media.Animation.AnimationClock> objetos de la cadena de composición, sus comportamientos de control de tiempo no se ven afectados; <xref:System.Windows.Media.Animation.Clock> objetos (incluidos los <xref:System.Windows.Media.Animation.AnimationClock> objetos) tienen una dependencia jerárquica en su elemento primario <xref:System.Windows.Media.Animation.Clock> objetos.  
  
 Para aplicar varios relojes a la misma propiedad, utilice la <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> al aplicar un <xref:System.Windows.Media.Animation.Storyboard>, animación, o <xref:System.Windows.Media.Animation.AnimationClock>.  
  
#### <a name="ticks-and-event-consolidation"></a>Pasos y consolidación de eventos  
 Además de calcular valores de salida, el administrador de tiempo hace otras cosas a cada paso que marca: determina el estado de cada reloj y genera los eventos adecuados.  
  
 Aunque los ciclos se producen con frecuencia, pueden ocurrir muchas cosas entre ellos. Por ejemplo, un <xref:System.Windows.Media.Animation.Clock> podría detener, iniciarse y detenerse de nuevo, en cuyo caso su <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> valor habrá cambiado tres veces. En teoría, el <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento se podría provocar varias veces en un único paso; sin embargo, el motor de tiempo consolida los eventos, para que la <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento se puede generar como máximo una vez por TIC. Esto es cierto para todos los eventos de sincronización: a lo sumo un evento de cada tipo se genera para un determinado <xref:System.Windows.Media.Animation.Clock> objeto.  
  
 Cuando un <xref:System.Windows.Media.Animation.Clock> cambia de estado y devuelve a su estado original entre los ciclos de (por ejemplo, cambiar de <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Stopped> y de vuelta a <xref:System.Windows.Media.Animation.ClockState.Active>), sigue produciendo el evento asociado.  
  
 Para más información acerca de los eventos de control de tiempo, vea [Información general sobre eventos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md).  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>Valores actuales y valores base de propiedades  
 Una propiedad que se pueda animar puede tener dos valores: un valor base y un valor actual. Al establecer la propiedad mediante su descriptor de acceso CLR o <xref:System.Windows.DependencyObject.SetValue%2A> método, establezca su valor base. Cuando no se anima una propiedad, su valor base y su valor actual son el mismo.  
  
 Al animar una propiedad, el <xref:System.Windows.Media.Animation.AnimationClock> establece la propiedad *actual* valor. Recuperar el valor de la propiedad a través de su descriptor de acceso CLR o <xref:System.Windows.DependencyObject.GetValue%2A> método devuelve el resultado de la <xref:System.Windows.Media.Animation.AnimationClock> cuando el <xref:System.Windows.Media.Animation.AnimationClock> es <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling>. Puede recuperar el valor de la propiedad base mediante el <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> método.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre eventos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
