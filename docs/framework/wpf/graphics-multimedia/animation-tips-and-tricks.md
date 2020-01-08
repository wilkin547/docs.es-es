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
ms.openlocfilehash: ef59631663e6cf1c98adfed77a2dbdb6ca124fa1
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636034"
---
# <a name="animation-tips-and-tricks"></a>Sugerencias y trucos para animaciones
Al trabajar con animaciones en WPF, hay una serie de sugerencias y trucos que pueden hacer que las animaciones funcionen mejor y ahorren frustraciones.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Problemas generales  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Al animar la posición de una barra de desplazamiento o de un control deslizante, se inmoviliza  
 Si anima la posición de una barra de desplazamiento o un control deslizante mediante una animación que tiene una <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (el valor predeterminado), el usuario ya no podrá mover la barra de desplazamiento o el control deslizante. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad de destino. Para que la animación deje de invalidar el valor actual de la propiedad, quítelo o asígnele un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guion gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animar la salida de una animación no surte ningún efecto  
 No se puede animar ningún objeto que sea la salida de otra animación. Por ejemplo, si usa un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> para animar el <xref:System.Windows.Shapes.Shape.Fill%2A> de una <xref:System.Windows.Shapes.Rectangle> de una <xref:System.Windows.Media.RadialGradientBrush> a una <xref:System.Windows.Media.SolidColorBrush>, no puede animar las propiedades de la <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>No se puede cambiar el valor de una propiedad después de animarla  
 En algunos casos, puede parecer que no es posible cambiar el valor de una propiedad después de animarla, incluso después de que la animación haya finalizado. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad. Para que la animación deje de invalidar el valor actual de la propiedad, quítelo o asígnele un <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guion gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Cambiar una escala de tiempo no surte ningún efecto  
 Aunque la mayoría de las propiedades de <xref:System.Windows.Media.Animation.Timeline> se pueden animar y enlazar a datos, el cambio de los valores de propiedad de una <xref:System.Windows.Media.Animation.Timeline> activa parece no tener ningún efecto. Esto se debe a que, cuando se inicia un <xref:System.Windows.Media.Animation.Timeline>, el sistema de control de tiempo realiza una copia del <xref:System.Windows.Media.Animation.Timeline> y lo usa para crear un objeto <xref:System.Windows.Media.Animation.Clock>. Modificar el original no surte ningún efecto en la copia del sistema.  
  
 Para que un <xref:System.Windows.Media.Animation.Timeline> refleje los cambios, su reloj se debe volver a generar y usar para reemplazar el reloj creado previamente. Los relojes no se regeneran automáticamente. A continuación se muestran distintas maneras de aplicar cambios a las escalas de tiempo:  
  
- Si la escala de tiempo es o pertenece a un <xref:System.Windows.Media.Animation.Storyboard>, puede hacer que refleje los cambios reaplicando su guion gráfico mediante un <xref:System.Windows.Media.Animation.BeginStoryboard> o el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>. El efecto secundario de esta acción es que también se reinicia la animación. En el código, puede utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> para hacer avanzar el guión gráfico hasta su posición anterior.  
  
- Si aplicó una animación directamente a una propiedad mediante el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>, llame de nuevo al método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> y pásele la animación que se ha modificado.  
  
- Si está trabajando directamente en el nivel de relojes, cree y aplique un nuevo conjunto de relojes y utilícelos para reemplazar el conjunto anterior de relojes generados.  
  
 Para obtener más información acerca de las escalas de tiempo y los relojes, consulte [información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop no funciona como se espera  
 Hay ocasiones en las que el establecimiento de la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> en <xref:System.Windows.Media.Animation.FillBehavior.Stop> parece no tener ningún efecto, como cuando una animación "se entrega" a otra porque tiene un valor <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> de <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Canvas>, un <xref:System.Windows.Shapes.Rectangle> y un <xref:System.Windows.Media.TranslateTransform>. El <xref:System.Windows.Media.TranslateTransform> se animará para mover el <xref:System.Windows.Shapes.Rectangle> alrededor de la <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 En los ejemplos de esta sección se usan los objetos anteriores para mostrar varios casos en los que la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> no se comporte como cabría esperar.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" y HandoffBehavior con varias animaciones  
 A veces parece que una animación omite su <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad cuando se reemplaza por una segunda animación. Tome el ejemplo siguiente, que crea dos objetos <xref:System.Windows.Media.Animation.Storyboard> y los usa para animar la misma <xref:System.Windows.Media.TranslateTransform> que se muestra en el ejemplo anterior.  
  
 La primera <xref:System.Windows.Media.Animation.Storyboard>, `B1`, anima la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> de 0 a 350, que mueve el rectángulo 350 píxeles a la derecha. Cuando la animación alcanza el final de su duración y deja de reproducirse, la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> vuelve a su valor original, 0. Como resultado, el rectángulo se mueve 350 píxeles a la derecha y luego salta para situarse en su posición original.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 La segunda <xref:System.Windows.Media.Animation.Storyboard>, `B2`, también anima la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la misma <xref:System.Windows.Media.TranslateTransform>. Dado que solo se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> de la animación de este <xref:System.Windows.Media.Animation.Storyboard>, la animación utiliza el valor actual de la propiedad que anima como su valor de inicio.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Si hace clic en el segundo botón mientras se reproduce el primer <xref:System.Windows.Media.Animation.Storyboard>, es posible que espere el siguiente comportamiento:  
  
1. El primer guion gráfico finaliza y devuelve el rectángulo a su posición original, porque la animación tiene una <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2. El segundo guion gráfico se lleva a efecto y anima el objeto a partir de la posición actual, que ahora es 0, hasta 500.  
  
 **Pero esto no es lo que sucede.** En lugar de ello, el rectángulo no salta a su posición original, sino que continúa moviéndose a la derecha. Esto se debe a que la segunda animación utiliza el valor actual de la primera animación como su valor inicial y anima desde ese valor hasta 500. Cuando la segunda animación reemplaza la primera porque se usa el <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>, el <xref:System.Windows.Media.Animation.FillBehavior> de la primera animación no importa.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior y el evento Completed  
 En los siguientes ejemplos se muestra otro escenario en el que parece que el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>no tiene ningún efecto. De nuevo, en el ejemplo se usa un guion gráfico para animar la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> de 0 a 350. Sin embargo, esta vez el ejemplo se registra para el evento <xref:System.Windows.Media.Animation.Timeline.Completed>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 El controlador de eventos <xref:System.Windows.Media.Animation.Timeline.Completed> inicia otro <xref:System.Windows.Media.Animation.Storyboard> que anima la misma propiedad desde su valor actual hasta 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 A continuación se indica el marcado que define el segundo <xref:System.Windows.Media.Animation.Storyboard> como un recurso.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Al ejecutar el <xref:System.Windows.Media.Animation.Storyboard>, puede esperar que la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> se anime de 0 a 350 y, a continuación, vuelva a 0 después de completarse (porque tiene un valor <xref:System.Windows.Media.Animation.FillBehavior> de <xref:System.Windows.Media.Animation.FillBehavior.Stop>) y, a continuación, se anima desde 0 hasta 500. En su lugar, el <xref:System.Windows.Media.TranslateTransform> anima de 0 a 350 y, a continuación, a 500.  
  
 Esto se debe a que el orden en que WPF genera eventos y porque los valores de propiedad se almacenan en caché y no se recalculan a menos que se invalide la propiedad. El evento <xref:System.Windows.Media.Animation.Timeline.Completed> se procesa en primer lugar porque lo desencadenó la escala de tiempo raíz (la primera <xref:System.Windows.Media.Animation.Storyboard>). En este momento, la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> todavía devuelve su valor animado porque todavía no se ha invalidado. En el segundo <xref:System.Windows.Media.Animation.Storyboard> se utiliza el valor almacenado en caché como su valor inicial y comienza la animación.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Rendimiento  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Las animaciones siguen ejecutándose después de salir de una página  
 Cuando sale de una <xref:System.Windows.Controls.Page> que contiene animaciones en ejecución, esas animaciones seguirán reproduciéndose hasta que el <xref:System.Windows.Controls.Page> se recopile como elemento no utilizado. Según el sistema de navegación que se utilice, la página de la que ha salido al navegar podría permanecer en memoria por tiempo indefinido, durante el cual seguiría consumiendo recursos con sus animaciones. Esto resulta especialmente patente cuando una página contiene animaciones de ejecución continua ("ambiente").  
  
 Por esta razón, se recomienda usar el evento <xref:System.Windows.FrameworkElement.Unloaded> para quitar animaciones cuando se sale de una página.  
  
 Hay diferentes maneras de quitar una animación. Las técnicas siguientes se pueden usar para quitar animaciones que pertenecen a un <xref:System.Windows.Media.Animation.Storyboard>.  
  
- Para quitar una <xref:System.Windows.Media.Animation.Storyboard> inicia con un desencadenador de eventos, vea [Cómo: quitar un guion gráfico](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Para usar código con el fin de quitar un <xref:System.Windows.Media.Animation.Storyboard>, vea el método <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>.  
  
 La técnica siguiente se puede utilizar sin tener en cuenta cómo se inició la animación.  
  
- Para quitar animaciones de una propiedad concreta, use el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>. Especifique la propiedad que se anima como primer parámetro y `null` como segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
 Para obtener más información sobre las distintas formas de animar propiedades, vea [información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Utilizar el valor Compose de HandoffBehavior consume recursos del sistema  
 Cuando se aplica un <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>o <xref:System.Windows.Media.Animation.AnimationClock> a una propiedad mediante el <xref:System.Windows.Media.Animation.HandoffBehavior><xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, los objetos <xref:System.Windows.Media.Animation.Clock> asociados previamente a esa propiedad continúan consumiendo recursos del sistema; el sistema de control de tiempo no quitará estos relojes automáticamente.  
  
 Para evitar problemas de rendimiento al aplicar un gran número de relojes mediante <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, debe quitar los relojes de composición de la propiedad animada una vez completados. Hay varias formas de quitar un reloj.  
  
- Para quitar todos los relojes de una propiedad, use el método <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> del objeto animado. Especifique la propiedad que se anima como primer parámetro y `null` como segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
- Para quitar una <xref:System.Windows.Media.Animation.AnimationClock> específica de una lista de relojes, utilice la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de la <xref:System.Windows.Media.Animation.AnimationClock> para recuperar una <xref:System.Windows.Media.Animation.ClockController>y, a continuación, llame al método <xref:System.Windows.Media.Animation.ClockController.Remove%2A> de la <xref:System.Windows.Media.Animation.ClockController>. Esto se hace normalmente en el controlador de eventos <xref:System.Windows.Media.Animation.Clock.Completed> para un reloj. Tenga en cuenta que solo los relojes de raíz pueden controlarse mediante un <xref:System.Windows.Media.Animation.ClockController>; la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de un reloj secundario devolverá `null`. Tenga en cuenta también que no se llamará al evento <xref:System.Windows.Media.Animation.Clock.Completed> si la duración efectiva del reloj es indefinidamente.  En ese caso, el usuario deberá determinar cuándo llamar a <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Este problema se produce principalmente en las animaciones de objetos que tienen un período de duración prolongado.  Cuando un objeto se recolecta como elemento no utilizado, sus relojes también se desconectan y se recolectan como elementos no utilizados.  
  
 Para obtener más información sobre los objetos de reloj, consulte [información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
