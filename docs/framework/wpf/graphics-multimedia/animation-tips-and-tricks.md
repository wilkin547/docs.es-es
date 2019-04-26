---
title: Sugerencias y trucos para animaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: 3a22c83eb739a735d42fa0f670716a0e75bbd54c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020275"
---
# <a name="animation-tips-and-tricks"></a>Sugerencias y trucos para animaciones
Cuando se trabaja con animaciones en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], hay una serie de sugerencias y trucos que pueden mejorar las animaciones un mejor rendimiento y evitar muchas frustraciones.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Problemas generales  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Al animar la posición de una barra de desplazamiento o de un control deslizante, se inmoviliza  
 Si anima la posición de una barra de desplazamiento o control deslizante utilizando una animación que tiene un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (el valor predeterminado), el usuario ya no será capaz de mover la barra de desplazamiento o el control deslizante. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad de destino. Para detener la animación de invalidar el valor actual de la propiedad, quítelo o asigne un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guión gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animar la salida de una animación no surte ningún efecto  
 No se puede animar ningún objeto que sea la salida de otra animación. Por ejemplo, si usa un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> para animar la <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> desde un <xref:System.Windows.Media.RadialGradientBrush> a un <xref:System.Windows.Media.SolidColorBrush>, no se puede animar cualquier propiedad de la <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>No se puede cambiar el valor de una propiedad después de animarla  
 En algunos casos, puede parecer que no es posible cambiar el valor de una propiedad después de animarla, incluso después de que la animación haya finalizado. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad. Para detener la animación de invalidar el valor actual de la propiedad, quítelo o asigne un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guión gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Cambiar una escala de tiempo no surte ningún efecto  
 Aunque la mayoría <xref:System.Windows.Media.Animation.Timeline> son que se pueden animar las propiedades y pueden ser datos enlazados, cambiando los valores de propiedad de un activo <xref:System.Windows.Media.Animation.Timeline> parece no surtir ningún efecto. Eso es porque, cuando un <xref:System.Windows.Media.Animation.Timeline> es comenzado, el sistema de control de tiempo realiza una copia de la <xref:System.Windows.Media.Animation.Timeline> y lo usa para crear un <xref:System.Windows.Media.Animation.Clock> objeto. Modificar el original no surte ningún efecto en la copia del sistema.  
  
 Para un <xref:System.Windows.Media.Animation.Timeline> para reflejar los cambios, debe volver a generar su reloj y utilizar para reemplazar el reloj previamente creado. Los relojes no se regeneran automáticamente. A continuación se muestran distintas maneras de aplicar cambios a las escalas de tiempo:  
  
-   Si la escala de tiempo es o pertenece a un <xref:System.Windows.Media.Animation.Storyboard>, puede hacer que reflejan los cambios puede volver a aplicar su guion gráfico utilizando un <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método. El efecto secundario de esta acción es que también se reinicia la animación. En el código, puede usar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> hacer una copia de método para avanzar el guión gráfico a su posición anterior.  
  
-   Si aplica una animación directamente a una propiedad mediante el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método, llame a la <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nuevo al método y pásele la animación que se ha modificado.  
  
-   Si está trabajando directamente en el nivel de relojes, cree y aplique un nuevo conjunto de relojes y utilícelos para reemplazar el conjunto anterior de relojes generados.  
  
 Para obtener más información acerca de las escalas de tiempo y relojes, consulte [Animation and Timing System Overview](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop no funciona como se espera  
 Hay ocasiones al establecer el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad a <xref:System.Windows.Media.Animation.FillBehavior.Stop> parece no surtir ningún efecto, como cuando una animación "se entrega" a otra porque tiene un <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Canvas>, un <xref:System.Windows.Shapes.Rectangle> y un <xref:System.Windows.Media.TranslateTransform>. El <xref:System.Windows.Media.TranslateTransform> se animará para mover el <xref:System.Windows.Shapes.Rectangle> en torno a la <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Los ejemplos de esta sección usan los objetos anteriores para mostrar varios casos donde el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad no se comporta como cabría esperar que.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" y HandoffBehavior con varias animaciones  
 A veces, parece como si una animación omitiese su <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad cuando se reemplaza por una segunda animación. Tomemos el ejemplo siguiente, que se crea dos <xref:System.Windows.Media.Animation.Storyboard> objetos y las usa para animar la misma <xref:System.Windows.Media.TranslateTransform> se muestra en el ejemplo anterior.  
  
 La primera <xref:System.Windows.Media.Animation.Storyboard>, `B1`, anima la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> desde 0 hasta 350, que mueve el rectángulo 350 píxeles a la derecha. Cuando la animación alcanza el final de su duración y detiene la reproducción, el <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad revierte a su valor original, 0. Como resultado, el rectángulo se mueve 350 píxeles a la derecha y luego salta para situarse en su posición original.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 El segundo <xref:System.Windows.Media.Animation.Storyboard>, `B2`, también anima la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad del mismo <xref:System.Windows.Media.TranslateTransform>. Dado que sólo el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad de la animación en este <xref:System.Windows.Media.Animation.Storyboard> está establecido, la animación utiliza el valor actual de la propiedad que anima como su valor inicial.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Si hace clic en el segundo botón mientras la primera <xref:System.Windows.Media.Animation.Storyboard> está reproduciendo, cabría esperar el comportamiento siguiente:  
  
1. El primer guion gráfico finaliza y envía el rectángulo a su posición original, ya que la animación un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2. El segundo guion gráfico se lleva a efecto y anima el objeto a partir de la posición actual, que ahora es 0, hasta 500.  
  
 **Pero esto no es lo que sucede.** En lugar de ello, el rectángulo no salta a su posición original, sino que continúa moviéndose a la derecha. Esto se debe a que la segunda animación utiliza el valor actual de la primera animación como su valor inicial y anima desde ese valor hasta 500. Cuando la segunda animación reemplaza a la primera porque el <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> se usa, la <xref:System.Windows.Media.Animation.FillBehavior> de la primera animación no importa.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior y el evento Completed  
 Los ejemplos siguientes muestran otro escenario en el que el <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> parece no surtir ningún efecto. De nuevo, en el ejemplo se utiliza un guión gráfico para animar la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> desde 0 hasta 350. Sin embargo, esta vez el ejemplo se registra el <xref:System.Windows.Media.Animation.Timeline.Completed> eventos.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 El <xref:System.Windows.Media.Animation.Timeline.Completed> controlador de eventos inicia otro <xref:System.Windows.Media.Animation.Storyboard> que anima la misma propiedad desde su valor actual hasta 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 El siguiente es el marcado que define el segundo <xref:System.Windows.Media.Animation.Storyboard> como un recurso.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Al ejecutar el <xref:System.Windows.Media.Animation.Storyboard>, cabría esperar el <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> para animar desde 0 hasta 350, a continuación, volver a 0 después de completar (porque no tiene un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>) y, a continuación, animar desde 0 a 500. En su lugar, el <xref:System.Windows.Media.TranslateTransform> se anima de 0 a 350 y, a continuación, en 500.  
  
 Eso es debido a la forma en que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genera eventos y porque los valores de propiedad se almacenan en caché y no se vuelven a calcular a menos que se invalide la propiedad. El <xref:System.Windows.Media.Animation.Timeline.Completed> evento se procesa en primer lugar porque lo activa por la escala de tiempo raíz (la primera <xref:System.Windows.Media.Animation.Storyboard>). En este momento, el <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad sigue devolviendo el valor animado porque aún no se ha invalidado todavía. El segundo <xref:System.Windows.Media.Animation.Storyboard> utiliza el valor almacenado en caché como su valor inicial y comienza la animación.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Rendimiento  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Las animaciones siguen ejecutándose después de salir de una página  
 Cuando se desplaza fuera de un <xref:System.Windows.Controls.Page> que contiene animaciones en ejecución, las animaciones continuarán reproduciéndose hasta que el <xref:System.Windows.Controls.Page> recolección. Según el sistema de navegación que se utilice, la página de la que ha salido al navegar podría permanecer en memoria por tiempo indefinido, durante el cual seguiría consumiendo recursos con sus animaciones. Esto resulta especialmente patente cuando una página contiene animaciones de ejecución continua ("ambiente").  
  
 Por este motivo, es una buena idea usar el <xref:System.Windows.FrameworkElement.Unloaded> eventos para quitar animaciones al salir de una página.  
  
 Hay diferentes maneras de quitar una animación. Las técnicas siguientes pueden usarse para quitar animaciones que pertenecen a un <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Para quitar un <xref:System.Windows.Media.Animation.Storyboard> empezó con un desencadenador de eventos, vea [Cómo: Quitar un guión gráfico](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
-   Usar código para quitar un <xref:System.Windows.Media.Animation.Storyboard>, consulte el <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> método.  
  
 La técnica siguiente se puede utilizar sin tener en cuenta cómo se inició la animación.  
  
-   Para quitar animaciones de una propiedad específica, use el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> método. Especifique la propiedad animada como primer parámetro, y `null` como el segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
 Para obtener más información sobre las diferentes maneras de animar propiedades, vea [técnicas de animación de información general sobre propiedades](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Utilizar el valor Compose de HandoffBehavior consume recursos del sistema  
 Al aplicar un <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, o <xref:System.Windows.Media.Animation.AnimationClock> a una propiedad mediante el <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, cualquier <xref:System.Windows.Media.Animation.Clock> objetos asociados anteriormente a esa propiedad siguen consumiendo recursos del sistema; no lo hará el sistema de temporización Quite estos relojes automáticamente.  
  
 Para evitar problemas de rendimiento cuando aplique muchos relojes mediante <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, debe quitar los relojes de composición de la propiedad animada cuando se hayan completado. Hay varias formas de quitar un reloj.  
  
-   Para quitar todos los relojes de una propiedad, utilice el <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> método del objeto animado. Especifique la propiedad animada como primer parámetro, y `null` como el segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
-   Para quitar un determinado <xref:System.Windows.Media.Animation.AnimationClock> desde una lista de relojes, utilice la <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de la <xref:System.Windows.Media.Animation.AnimationClock> para recuperar un <xref:System.Windows.Media.Animation.ClockController>, a continuación, llame a la <xref:System.Windows.Media.Animation.ClockController.Remove%2A> método de la <xref:System.Windows.Media.Animation.ClockController>. Esto se hace normalmente el <xref:System.Windows.Media.Animation.Clock.Completed> controlador de eventos de un reloj. Tenga en cuenta que los relojes de raíz única pueden controlarse mediante una <xref:System.Windows.Media.Animation.ClockController>; el <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de un reloj secundario devolverá `null`. Tenga en cuenta también que el <xref:System.Windows.Media.Animation.Clock.Completed> eventos no se llamará si la duración efectiva del reloj es para siempre.  En ese caso, el usuario deberá determinar cuándo llamar a <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Este problema se produce principalmente en las animaciones de objetos que tienen un período de duración prolongado.  Cuando un objeto se recolecta como elemento no utilizado, sus relojes también se desconectan y se recolectan como elementos no utilizados.  
  
 Para obtener más información acerca de los objetos de reloj, consulte [Animation and Timing System Overview](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
