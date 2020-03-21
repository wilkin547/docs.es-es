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
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187650"
---
# <a name="animation-tips-and-tricks"></a>Sugerencias y trucos para animaciones
Cuando se trabaja con animaciones en WPFWPF, hay una serie de consejos y trucos que pueden hacer que las animaciones funcionen mejor y ahorrar frustración.  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>Problemas generales  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Al animar la posición de una barra de desplazamiento o de un control deslizante, se inmoviliza  
 Si anima la posición de una barra de desplazamiento <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> o un control deslizante mediante una animación que tiene un de (el valor predeterminado), el usuario ya no podrá mover la barra de desplazamiento o el control deslizante. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad de destino. Para evitar que la animación reemplace el valor actual de <xref:System.Windows.Media.Animation.FillBehavior> la <xref:System.Windows.Media.Animation.FillBehavior.Stop>propiedad, elimínela o asípiese de . Para obtener más información y un ejemplo, vea Establecer una propiedad después de [animarla con un guión gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animar la salida de una animación no surte ningún efecto  
 No se puede animar ningún objeto que sea la salida de otra animación. Por ejemplo, si <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> utiliza un <xref:System.Windows.Shapes.Shape.Fill%2A> para <xref:System.Windows.Shapes.Rectangle> animar <xref:System.Windows.Media.RadialGradientBrush> la <xref:System.Windows.Media.SolidColorBrush>de a a a , <xref:System.Windows.Media.RadialGradientBrush> <xref:System.Windows.Media.SolidColorBrush>no puede animar ninguna propiedad de la o .  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>No se puede cambiar el valor de una propiedad después de animarla  
 En algunos casos, puede parecer que no es posible cambiar el valor de una propiedad después de animarla, incluso después de que la animación haya finalizado. Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad. Para evitar que la animación reemplace el valor actual de <xref:System.Windows.Media.Animation.FillBehavior> la <xref:System.Windows.Media.Animation.FillBehavior.Stop>propiedad, elimínela o asípiese de . Para obtener más información y un ejemplo, vea Establecer una propiedad después de [animarla con un guión gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Cambiar una escala de tiempo no surte ningún efecto  
 Aunque <xref:System.Windows.Media.Animation.Timeline> la mayoría de las propiedades son animables y <xref:System.Windows.Media.Animation.Timeline> pueden estar enlazadas a datos, cambiar los valores de propiedad de un activo parece no tener ningún efecto. Esto se debe a <xref:System.Windows.Media.Animation.Timeline> que, cuando se inicia a, el sistema de sincronización hace una copia de la <xref:System.Windows.Media.Animation.Timeline> y la utiliza para crear un <xref:System.Windows.Media.Animation.Clock> objeto. Modificar el original no surte ningún efecto en la copia del sistema.  
  
 Para <xref:System.Windows.Media.Animation.Timeline> que refleje los cambios, su reloj debe ser regenerado y usado para reemplazar el reloj creado previamente. Los relojes no se regeneran automáticamente. A continuación se muestran distintas maneras de aplicar cambios a las escalas de tiempo:  
  
- Si la línea de <xref:System.Windows.Media.Animation.Storyboard>tiempo es o pertenece a un , puede <xref:System.Windows.Media.Animation.BeginStoryboard> hacer <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> que refleje los cambios volviendo a aplicar su guión gráfico mediante un método o un método. El efecto secundario de esta acción es que también se reinicia la animación. En el código, <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> puede usar el método para avanzar el guión gráfico a su posición anterior.  
  
- Si aplicó una animación directamente a una propiedad mediante el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método, llame al <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método de nuevo y pásele la animación que se ha modificado.  
  
- Si está trabajando directamente en el nivel de relojes, cree y aplique un nuevo conjunto de relojes y utilícelos para reemplazar el conjunto anterior de relojes generados.  
  
 Para obtener más información acerca de las escalas de tiempo y los relojes, consulte Información general del sistema de [animación y temporización](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop no funciona como se espera  
 Hay ocasiones al <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> establecer <xref:System.Windows.Media.Animation.FillBehavior.Stop> la propiedad en parece no tener ningún efecto, como cuando <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> una <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>animación "manos fuera" a otra porque tiene un ajuste de .  
  
 En el ejemplo <xref:System.Windows.Controls.Canvas>siguiente <xref:System.Windows.Shapes.Rectangle> se <xref:System.Windows.Media.TranslateTransform>crea un archivo , a y un archivo . El <xref:System.Windows.Media.TranslateTransform> se animará <xref:System.Windows.Shapes.Rectangle> para <xref:System.Windows.Controls.Canvas>mover el archivo .  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Los ejemplos de esta sección usan los objetos <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> anteriores para mostrar varios casos en los que la propiedad no se comporta como cabría esperar.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" y HandoffBehavior con varias animaciones  
 A veces parece que una <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> animación omite su propiedad cuando se reemplaza por una segunda animación. Tome mostrase el <xref:System.Windows.Media.Animation.Storyboard> ejemplo siguiente, que <xref:System.Windows.Media.TranslateTransform> crea dos objetos y los utiliza para animar el mismo que se muestra en el ejemplo anterior.  
  
 El <xref:System.Windows.Media.Animation.Storyboard>primero `B1`, , <xref:System.Windows.Media.TranslateTransform.X%2A> anima <xref:System.Windows.Media.TranslateTransform> la propiedad de 0 a 350, que mueve el rectángulo 350 píxeles a la derecha. Cuando la animación llega al final de <xref:System.Windows.Media.TranslateTransform.X%2A> su duración y deja de reproducirse, la propiedad vuelve a su valor original, 0. Como resultado, el rectángulo se mueve 350 píxeles a la derecha y luego salta para situarse en su posición original.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 El <xref:System.Windows.Media.Animation.Storyboard>segundo `B2`, , <xref:System.Windows.Media.TranslateTransform.X%2A> también anima <xref:System.Windows.Media.TranslateTransform>la propiedad de la misma . Dado que <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> solo se establece <xref:System.Windows.Media.Animation.Storyboard> la propiedad de la animación en esto, la animación utiliza el valor actual de la propiedad que anima como su valor inicial.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Si hace clic en el <xref:System.Windows.Media.Animation.Storyboard> segundo botón mientras se reproduce el primero, es posible que espere el siguiente comportamiento:  
  
1. El primer guión gráfico finaliza y envía el rectángulo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> a <xref:System.Windows.Media.Animation.FillBehavior.Stop>su posición original, porque la animación tiene un de .  
  
2. El segundo guion gráfico se lleva a efecto y anima el objeto a partir de la posición actual, que ahora es 0, hasta 500.  
  
 **Pero esto no es lo que sucede.** En lugar de ello, el rectángulo no salta a su posición original, sino que continúa moviéndose a la derecha. Esto se debe a que la segunda animación utiliza el valor actual de la primera animación como su valor inicial y anima desde ese valor hasta 500. Cuando la segunda animación reemplaza <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> la primera <xref:System.Windows.Media.Animation.FillBehavior> porque se utiliza, la de la primera animación no importa.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior y el evento Completed  
 Los siguientes ejemplos muestran <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> otro escenario en el que parece no tener ningún efecto. De nuevo, en el ejemplo <xref:System.Windows.Media.TranslateTransform.X%2A> se <xref:System.Windows.Media.TranslateTransform> usa un guión gráfico para animar la propiedad de 0 a 350. Sin embargo, esta vez <xref:System.Windows.Media.Animation.Timeline.Completed> el ejemplo se registra para el evento.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 El <xref:System.Windows.Media.Animation.Timeline.Completed> controlador de <xref:System.Windows.Media.Animation.Storyboard> eventos inicia otro que anima la misma propiedad desde su valor actual a 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 A continuación se muestra el <xref:System.Windows.Media.Animation.Storyboard> marcado que define el segundo como un recurso.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Al ejecutar <xref:System.Windows.Media.Animation.Storyboard>el , puede <xref:System.Windows.Media.TranslateTransform.X%2A> esperar <xref:System.Windows.Media.TranslateTransform> que la propiedad de la para animar de 0 a 350, a continuación, volver a 0 después de que se completa (porque tiene un <xref:System.Windows.Media.Animation.FillBehavior> valor de <xref:System.Windows.Media.Animation.FillBehavior.Stop>), y, a continuación, animar de 0 a 500. En su <xref:System.Windows.Media.TranslateTransform> lugar, los anima de 0 a 350 y luego a 500.  
  
 Esto se debe al orden en que WPFWPF genera eventos y porque los valores de propiedad se almacenan en caché y no se vuelven a calcular a menos que se invalide la propiedad. El <xref:System.Windows.Media.Animation.Timeline.Completed> evento se procesa primero porque se desencadenó <xref:System.Windows.Media.Animation.Storyboard>mediante la línea de tiempo raíz (la primera ). En este momento, la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad todavía devuelve su valor animado porque aún no se ha invalidado. El <xref:System.Windows.Media.Animation.Storyboard> segundo utiliza el valor almacenado en caché como su valor inicial y comienza a animar.  
  
<a name="performancesection"></a>
## <a name="performance"></a>Rendimiento  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Las animaciones siguen ejecutándose después de salir de una página  
 Cuando se navega <xref:System.Windows.Controls.Page> lejos de un que contiene animaciones en <xref:System.Windows.Controls.Page> ejecución, esas animaciones continuarán reproduciéndose hasta que se recopile la basura. Según el sistema de navegación que se utilice, la página de la que ha salido al navegar podría permanecer en memoria por tiempo indefinido, durante el cual seguiría consumiendo recursos con sus animaciones. Esto resulta especialmente patente cuando una página contiene animaciones de ejecución continua ("ambiente").  
  
 Por este motivo, es una buena <xref:System.Windows.FrameworkElement.Unloaded> idea usar el evento para quitar animaciones cuando se navega fuera de una página.  
  
 Hay diferentes maneras de quitar una animación. Las siguientes técnicas se pueden utilizar para <xref:System.Windows.Media.Animation.Storyboard>quitar animaciones que pertenecen a un archivo .  
  
- Para quitar <xref:System.Windows.Media.Animation.Storyboard> un iniciado con un desencadenador de eventos, vea [Cómo: Quitar un guión gráfico](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Para usar código <xref:System.Windows.Media.Animation.Storyboard>para quitar <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> un , consulte el método.  
  
 La técnica siguiente se puede utilizar sin tener en cuenta cómo se inició la animación.  
  
- Para quitar animaciones de una <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> propiedad específica, utilice el método. Especifique la propiedad que se está `null` animando como el primer parámetro y como el segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
 Para obtener más información sobre las diferentes formas de animar propiedades, vea [Información general sobre técnicas](property-animation-techniques-overview.md)de animación de propiedades .  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Utilizar el valor Compose de HandoffBehavior consume recursos del sistema  
 Al aplicar <xref:System.Windows.Media.Animation.Storyboard>un <xref:System.Windows.Media.Animation.AnimationTimeline>, <xref:System.Windows.Media.Animation.AnimationClock> , o <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>a <xref:System.Windows.Media.Animation.Clock> una propiedad mediante el , cualquier objeto asociado previamente a esa propiedad continúan consumiendo recursos del sistema; el sistema de sincronización no eliminará estos relojes automáticamente.  
  
 Para evitar problemas de rendimiento al aplicar <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>un gran número de relojes con , debe quitar los relojes de composición de la propiedad animada después de que se completen. Hay varias formas de quitar un reloj.  
  
- Para quitar todos los relojes de <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> una propiedad, utilice el método o del objeto animado. Especifique la propiedad que se está `null` animando como el primer parámetro y como el segundo. De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
- Para quitar <xref:System.Windows.Media.Animation.AnimationClock> un específico de una lista <xref:System.Windows.Media.Animation.Clock.Controller%2A> de <xref:System.Windows.Media.Animation.AnimationClock> relojes, <xref:System.Windows.Media.Animation.ClockController>utilice la <xref:System.Windows.Media.Animation.ClockController.Remove%2A> propiedad de <xref:System.Windows.Media.Animation.ClockController>la para recuperar un , a continuación, llame al método de la . Esto se hace normalmente en el <xref:System.Windows.Media.Animation.Clock.Completed> controlador de eventos para un reloj. Tenga en cuenta que sólo los <xref:System.Windows.Media.Animation.ClockController>relojes raíz pueden ser controlados por un ; la <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de un `null`reloj secundario volverá . Tenga en <xref:System.Windows.Media.Animation.Clock.Completed> cuenta también que el evento no se llamará si la duración efectiva del reloj es para siempre.  En ese caso, el usuario tendrá <xref:System.Windows.Media.Animation.ClockController.Remove%2A>que determinar cuándo llamar a .  
  
 Este problema se produce principalmente en las animaciones de objetos que tienen un período de duración prolongado.  Cuando un objeto se recolecta como elemento no utilizado, sus relojes también se desconectan y se recolectan como elementos no utilizados.  
  
 Para obtener más información acerca de los objetos de reloj, vea Información general sobre el sistema de [animación y temporización](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
