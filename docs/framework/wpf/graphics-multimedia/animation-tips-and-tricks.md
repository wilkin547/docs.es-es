---
title: "Sugerencias y trucos para animaciones | Microsoft Docs"
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
  - "animar objetos [WPF], solucionar problemas"
  - "sugerencias y trucos para animaciones [WPF]"
  - "animaciones [WPF], FillBehavior (propiedad)"
  - "animaciones [WPF], uso de recursos del sistema"
  - "solucionar problemas de rendimiento [WPF], animación"
  - "consejos y sugerencias [WPF], animación"
  - "solucionar problemas [WPF], animación"
  - "solucionar problemas de animación [WPF]"
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Sugerencias y trucos para animaciones
Cuando se trabaja con animaciones en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], hay varias sugerencias y trucos que pueden mejorar el rendimiento de las animaciones y evitar muchas frustraciones.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="generalissuessection"></a>   
## Problemas generales  
  
### Al animar la posición de una barra de desplazamiento o de un control deslizante, se inmoviliza  
 Si anima la posición de una barra de desplazamiento o de un control deslizante utilizando una animación cuyo <xref:System.Windows.Media.Animation.FillBehavior> es <xref:System.Windows.Media.Animation.FillBehavior> \(el valor predeterminado\), el usuario ya no podrá mover la barra de desplazamiento o el control deslizante.  Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad de destino.  Para que la animación deje de invalidar el valor actual de la propiedad, quítelo o asigne a <xref:System.Windows.Media.Animation.FillBehavior> el valor <xref:System.Windows.Media.Animation.FillBehavior>.  Para obtener más información y un ejemplo, consulte [Establecer una propiedad después de animarla con un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Animar el resultado de una animación no surte ningún efecto  
 No se puede animar ningún objeto que sea el resultado de otra animación.  Por ejemplo, si utiliza un objeto <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle> desde <xref:System.Windows.Media.RadialGradientBrush> hasta <xref:System.Windows.Media.SolidColorBrush>, no podrá animar propiedad del objeto <xref:System.Windows.Media.RadialGradientBrush> ni de <xref:System.Windows.Media.SolidColorBrush>.  
  
### No se puede cambiar el valor de una propiedad después de animarla  
 En algunos casos, puede parecer que no es posible cambiar el valor de una propiedad después de animarla, incluso después de que la animación haya finalizado.  Esto se debe a que, aunque la animación finaliza, continúa invalidando el valor base de la propiedad.  Para que la animación deje de invalidar el valor actual de la propiedad, quítelo o asigne a <xref:System.Windows.Media.Animation.FillBehavior> el valor <xref:System.Windows.Media.Animation.FillBehavior>.  Para obtener más información y un ejemplo, consulte [Establecer una propiedad después de animarla con un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Cambiar una escala de tiempo no surte ningún efecto  
 Aunque la mayoría de las propiedades <xref:System.Windows.Media.Animation.Timeline> se pueden animar y enlazar a datos, cambiar los valores de propiedad de un objeto <xref:System.Windows.Media.Animation.Timeline> activo parece no surtir ningún efecto.  Esto se debe a que, cuando la <xref:System.Windows.Media.Animation.Timeline> se inicia, el sistema de control de tiempo realiza una copia de <xref:System.Windows.Media.Animation.Timeline> y la utiliza para crear un objeto <xref:System.Windows.Media.Animation.Clock>.  Modificar el original no surte ningún efecto en la copia del sistema.  
  
 Para que una <xref:System.Windows.Media.Animation.Timeline> refleje los cambios, deberá volver a generarse su reloj y utilizarlo para reemplazar el reloj previamente creado.  Los relojes no se regeneran automáticamente.  A continuación, se muestran distintas maneras de aplicar cambios a las escalas de tiempo:  
  
-   Si la escala de tiempo es un objeto <xref:System.Windows.Media.Animation.Storyboard> o pertenece a esta clase, para reflejar los cambios puede volver a aplicar su guión gráfico a través del método <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  El efecto secundario de esta acción es que también se reinicia la animación.  En el código, puede utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> para que el guión gráfico vuelva a su posición anterior.  
  
-   Si aplicó una animación directamente a una propiedad utilizando el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>, llame de nuevo el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> y pásele la animación que se ha modificado.  
  
-   Si está trabajando directamente en el nivel de relojes, cree y aplique un nuevo conjunto de relojes y utilícelos para reemplazar el conjunto anterior de relojes generados.  
  
 Para obtener más información sobre escalas de tiempo y relojes, consulte [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### FillBehavior.Stop no funciona como se espera  
 En ocasiones, parece que establecer la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> en <xref:System.Windows.Media.Animation.FillBehavior> no surte ningún efecto, como cuando una animación "se entrega" a otra porque el valor de su propiedad <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> es <xref:System.Windows.Media.Animation.HandoffBehavior>.  
  
 En el siguiente ejemplo, se crean una conexión <xref:System.Windows.Controls.Canvas>, un objeto <xref:System.Windows.Shapes.Rectangle> y un <xref:System.Windows.Media.TranslateTransform>.  <xref:System.Windows.Media.TranslateTransform> se animará para mover <xref:System.Windows.Shapes.Rectangle> alrededor de <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 En los ejemplos de esta sección se utilizan los objetos anteriores para mostrar varios casos en que la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> no se comporta como cabría esperar.  
  
#### FillBehavior\="Stop" y HandoffBehavior con varias animaciones  
 A veces, parece como si una animación omitiese su propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> cuando la reemplaza una segunda animación.  Tomemos el ejemplo siguiente, en el que se crean dos objetos <xref:System.Windows.Media.Animation.Storyboard> y se utilizan para animar la misma transformación <xref:System.Windows.Media.TranslateTransform> mostrada en el ejemplo anterior.  
  
 El primer <xref:System.Windows.Media.Animation.Storyboard>, `B1`, anima la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de <xref:System.Windows.Media.TranslateTransform> desde 0 hasta 350, lo que mueve el rectángulo 350 píxeles a la derecha.  Cuando la animación alcanza el fin de su duración y su reproducción se detiene, la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> revierte a su valor original, 0.  Como resultado, el rectángulo se mueve 350 píxeles a la derecha y, a continuación, salta para situarse en su posición original.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 El segundo <xref:System.Windows.Media.Animation.Storyboard>, `B2`, también anima la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la misma <xref:System.Windows.Media.TranslateTransform>.  Dado que se establece únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> de la animación en este <xref:System.Windows.Media.Animation.Storyboard>, la animación utiliza el valor actual de la propiedad que anima como su valor inicial.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Si hace clic en el segundo botón mientras el primer <xref:System.Windows.Media.Animation.Storyboard> se está reproduciendo, cabría esperar el comportamiento siguiente:  
  
1.  El primer guión gráfico finaliza y envía el rectángulo a su posición original, porque el valor de la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de la animación es <xref:System.Windows.Media.Animation.FillBehavior>.  
  
2.  El segundo guión gráfico se lleva a efecto y anima el objeto a partir de la posición actual, que ahora es 0, hasta 500.  
  
 **Pero esto no es lo que sucede.** En lugar de ello, el rectángulo no salta a su posición original, sino que continúa moviéndose a la derecha.  Esto se debe a que la segunda animación utiliza el valor actual de la primera animación como su valor inicial y anima desde ese valor hasta 500.  Cuando la segunda animación reemplaza a la primera porque se utiliza el valor <xref:System.Windows.Media.Animation.HandoffBehavior> de <xref:System.Windows.Media.Animation.HandoffBehavior>, el valor de <xref:System.Windows.Media.Animation.FillBehavior> de la primera animación no se tiene en cuenta.  
  
#### FillBehavior y el evento Completed  
 En los ejemplos siguientes se muestra otro escenario en el que el valor <xref:System.Windows.Media.Animation.FillBehavior> de la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> parece no surtir ningún efecto.  De nuevo, en el ejemplo se utiliza un guión gráfico para animar la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de la transformación <xref:System.Windows.Media.TranslateTransform> desde 0 hasta 350.  Sin embargo, esta vez en el ejemplo se efectúa el registro para el evento <xref:System.Windows.Media.Animation.Timeline.Completed>.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 El controlador de eventos <xref:System.Windows.Media.Animation.Timeline.Completed> inicia otro <xref:System.Windows.Media.Animation.Storyboard> que anima la misma propiedad desde su valor actual hasta 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 A continuación, se muestra el marcado que define el segundo <xref:System.Windows.Media.Animation.Storyboard> como recurso.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Al ejecutar el objeto <xref:System.Windows.Media.Animation.Storyboard>, cabría esperar que la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de <xref:System.Windows.Media.TranslateTransform> se anime de 0 a 350, y luego revierta a 0 después de completarse \(dado que su valor de <xref:System.Windows.Media.Animation.FillBehavior> es <xref:System.Windows.Media.Animation.FillBehavior>\), para, por último, animarse desde 0 hasta 500.  En cambio, <xref:System.Windows.Media.TranslateTransform> se anima de 0 a 350 y, a continuación, hasta 500.  
  
 Esto se debe al orden en el que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genera los eventos y al hecho de que los valores de propiedad se almacenan en la memoria caché y no se actualizan a menos que se invalide la propiedad.  El evento <xref:System.Windows.Media.Animation.Timeline.Completed> se procesa en primer lugar porque lo activa la escala de tiempo raíz \(el primer <xref:System.Windows.Media.Animation.Storyboard>\).  En este momento, la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> sigue devolviendo el valor animado, porque todavía no se ha invalidado.  El segundo <xref:System.Windows.Media.Animation.Storyboard> utiliza el valor almacenado en memoria caché como su valor inicial y comienza la animación.  
  
<a name="performancesection"></a>   
## Rendimiento  
  
### Las animaciones siguen ejecutándose después de salir de una página  
 Cuando se navega para salir de un control <xref:System.Windows.Controls.Page> que contiene animaciones en ejecución, éstas continuarán reproduciéndose hasta que se efectúe la recolección de elementos no utilizados de <xref:System.Windows.Controls.Page>.  Según el sistema de navegación que se utilice, la página de la que ha salido al navegar podría permanecer en memoria por tiempo indefinido, durante el cual seguiría consumiendo recursos con sus animaciones.  Esto resulta especialmente patente cuando una página contiene animaciones de ejecución continua \("ambiente"\).  
  
 Por esta razón, es conveniente utilizar el evento <xref:System.Windows.FrameworkElement.Unloaded> para quitar las animaciones cuando se sale de una página al navegar.  
  
 Hay diferentes maneras de quitar una animación.  Las técnicas siguientes se pueden utilizar para quitar animaciones que pertenecen a un objeto <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Para quitar un <xref:System.Windows.Media.Animation.Storyboard> iniciado con un desencadenador de eventos, consulte [How to: Remove a Storyboard](http://msdn.microsoft.com/es-es/7fe39531-de2f-46a0-a69f-b783d04235ee).  
  
-   Para quitar un <xref:System.Windows.Media.Animation.Storyboard> mediante código, consulte el método <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>.  
  
 La técnica siguiente se puede utilizar sin tener en cuenta cómo se inició la animación.  
  
-   Para quitar animaciones de una propiedad concreta, utilice el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>.  Especifique la propiedad que se va a animar como primer parámetro y `null` como segundo parámetro.  De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
 Para obtener más información sobre los distintos modos de animar propiedades, consulte [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### Utilizar el valor Compose de HandoffBehavior consume recursos del sistema  
 Cuando se aplica un objeto <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline> o <xref:System.Windows.Media.Animation.AnimationClock> a una propiedad utilizando el valor <xref:System.Windows.Media.Animation.HandoffBehavior> de <xref:System.Windows.Media.Animation.HandoffBehavior>, los objetos <xref:System.Windows.Media.Animation.Clock> asociados con anterioridad a esa propiedad siguen utilizando recursos del sistema; el sistema de control de tiempo no quitará estos relojes automáticamente.  
  
 Para evitar problemas de rendimiento cuando aplique muchos relojes mediante <xref:System.Windows.Media.Animation.HandoffBehavior>, debe quitar los relojes de composición de la propiedad animada cuando se hayan completado.  Hay varias formas de quitar un reloj.  
  
-   Para quitar todos los relojes de una propiedad, utilice el método <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> o <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> del objeto animado.  Especifique la propiedad que se va a animar como primer parámetro y `null` como segundo parámetro.  De este modo, se quitarán todos los relojes de animación de la propiedad.  
  
-   Para quitar un objeto <xref:System.Windows.Media.Animation.AnimationClock> específico de una lista de relojes, utilice la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de <xref:System.Windows.Media.Animation.AnimationClock> para recuperar un objeto <xref:System.Windows.Media.Animation.ClockController> y, a continuación, llame al método <xref:System.Windows.Media.Animation.ClockController.Remove%2A> de <xref:System.Windows.Media.Animation.ClockController>.  Normalmente esta operación se realiza en el controlador del evento <xref:System.Windows.Media.Animation.Clock.Completed> de un reloj.  Observe que <xref:System.Windows.Media.Animation.ClockController> sólo puede controlar los relojes de raíz; la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de un reloj secundario devolverá `null`.  Tenga en cuenta también que no se provocará el evento <xref:System.Windows.Media.Animation.Clock.Completed> si la duración real del reloj es para siempre.  En ese caso, el usuario deberá determinar cuándo llamar a <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Este problema se produce principalmente en las animaciones de objetos que tienen un período de duración prolongado.  Cuando un objeto se recolecta como elemento no utilizado, sus relojes también se desconectan y se recolectan como elementos no utilizados.  
  
 Para obtener más información acerca de los objetos de reloj, consulte [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)