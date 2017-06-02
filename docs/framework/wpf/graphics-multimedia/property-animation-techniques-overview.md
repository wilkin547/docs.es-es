---
title: "Informaci&#243;n general sobre t&#233;cnicas de animaci&#243;n de propiedades | Microsoft Docs"
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
  - "animación, propiedades, métodos para"
  - "propiedades, métodos para animar"
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre t&#233;cnicas de animaci&#243;n de propiedades
En este tema se describen los enfoques diferentes para animar propiedades: guiones gráficos, animaciones locales, relojes y animaciones por fotograma.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas descritas en [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="summary"></a>   
## Distintas maneras de animar  
 Dado que hay muchos escenarios diferentes para animar propiedades, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varios enfoques para ello.  
  
 Para cada enfoque, en la tabla siguiente se indica si se puede utilizar por instancia, en estilos, en plantillas de control o en plantillas de datos; si se puede utilizar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; y si el enfoque permite controlar interactivamente la animación.  "Por instancia" se refiere a la técnica de aplicar directamente una animación o guión gráfico a las instancias de un objeto, en lugar de en un estilo, una plantilla de control o una plantilla de datos.  
  
|Técnica de animación|Escenarios|Admite XAML|Control interactivo|  
|--------------------------|----------------|-----------------|-------------------------|  
|Animación de guión gráfico|Por instancia, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Sí|Sí|  
|Animación local|Por instancia|No|No|  
|Animación de reloj|Por instancia|No|Sí|  
|Animación por fotograma|Por instancia|No|N\/D|  
  
<a name="storyboard_animations"></a>   
## Animaciones de guión gráfico  
 Un <xref:System.Windows.Media.Animation.Storyboard> se utiliza cuando se desea definir y aplicar animaciones en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], controlarlas interactivamente después de comenzar, crear un árbol complejo de animaciones o animar en un <xref:System.Windows.Style>, una <xref:System.Windows.Controls.ControlTemplate> o una <xref:System.Windows.DataTemplate>.  Para animar un objeto mediante <xref:System.Windows.Media.Animation.Storyboard>, debe ser un elemento <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o bien utilizarse para establecer un elemento <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  Para obtener más detalles, consulte [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Un guión gráfico, o <xref:System.Windows.Media.Animation.Storyboard>, es un tipo de escala de tiempo \(<xref:System.Windows.Media.Animation.Timeline>\) contenedora que proporciona información de destino para las animaciones que contiene.  Para animar con <xref:System.Windows.Media.Animation.Storyboard>, debe completar los tres pasos siguientes.  
  
1.  Declare un <xref:System.Windows.Media.Animation.Storyboard> y una o más animaciones.  
  
2.  Utilice las [propiedades adjuntas](GTMT) <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> para especificar el objeto y la propiedad de destino de cada animación.  
  
3.  \(Sólo mediante código\) Defina un objeto <xref:System.Windows.NameScope> para un elemento <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  Registre los nombres de los objetos que va a animar con ese elemento <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
4.  Comience el <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Al comenzar un <xref:System.Windows.Media.Animation.Storyboard>, se aplican animaciones a las propiedades que se animan, y se inician.  Hay dos maneras de comenzar un <xref:System.Windows.Media.Animation.Storyboard>: puede utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> proporcionado por la clase <xref:System.Windows.Media.Animation.Storyboard>, o bien puede utilizar una acción <xref:System.Windows.Media.Animation.BeginStoryboard>.  La única forma de animar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es utilizar una acción <xref:System.Windows.Media.Animation.BeginStoryboard>. Una acción <xref:System.Windows.Media.Animation.BeginStoryboard> se puede utilizar en un <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger> de propiedad o <xref:System.Windows.DataTrigger>.  
  
 En la tabla siguiente se muestran los distintos espacios en que se admite cada técnica de comienzo de <xref:System.Windows.Media.Animation.Storyboard>: por instancia, estilo, plantilla de control y plantilla de datos.  
  
|El guión gráfico se comienza utilizando…|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|  
|----------------------------------------------|-------------------|------------|--------------------------|------------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y <xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y un <xref:System.Windows.Trigger> de propiedad|No|Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y <xref:System.Windows.DataTrigger>|No|Sí|Sí|Sí|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/es-es/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sí|No|No|No|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Para obtener más información acerca de los objetos <xref:System.Windows.Media.Animation.Storyboard>, vea [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## Animaciones locales  
 Las animaciones locales proporcionan una manera cómoda de animar una [propiedad de dependencia](GTMT) de cualquier objeto <xref:System.Windows.Media.Animation.Animatable>.  Las animaciones locales se utilizan cuando se desea aplicar una sola animación a una propiedad y no se necesita controlar interactivamente la animación después de iniciarse.  A diferencia de una animación de <xref:System.Windows.Media.Animation.Storyboard>, una animación local puede animar un objeto que no está asociado a un elemento <xref:System.Windows.FrameworkElement> ni un elemento <xref:System.Windows.FrameworkContentElement>.  Tampoco es preciso definir <xref:System.Windows.NameScope> para este tipo de animación.  
  
 Las animaciones locales únicamente se pueden utilizar mediante código y no se pueden definir en estilos, plantillas de control ni plantillas de datos.  Una animación local no se puede controlar interactivamente una vez iniciada.  
  
 Para animar mediante una animación local, complete los pasos siguientes.  
  
1.  Cree un objeto <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2.  Utilice el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> del objeto que desea animar para aplicar <xref:System.Windows.Media.Animation.AnimationTimeline> a la propiedad que especifica.  
  
 En el ejemplo siguiente se muestra cómo animar el ancho y el color de fondo de un objeto <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## Animaciones de reloj  
 Los objetos <xref:System.Windows.Media.MediaPlayer.Clock%2A> se utilizan cuando se desea animar sin utilizar <xref:System.Windows.Media.Animation.Storyboard> y se desea crear árboles de control de tiempo complejos o controlar interactivamente las animaciones después de iniciarse.  Puede utilizar objetos de reloj para animar una [propiedad de dependencia](GTMT) de cualquier objeto <xref:System.Windows.Media.Animation.Animatable>.  
  
 Los objetos <xref:System.Windows.Media.Animation.Clock> no se pueden utilizar directamente para animar en estilos, plantillas de control ni plantillas de datos.  \(En realidad, el sistema de animación y control de tiempo sí utiliza objetos <xref:System.Windows.Media.Animation.Clock> para animar en estilos, plantillas de control y plantillas de datos, pero debe crear esos objetos <xref:System.Windows.Media.Animation.Clock> a partir de un objeto <xref:System.Windows.Media.Animation.Storyboard>.  Para obtener más información sobre la relación entre los objetos <xref:System.Windows.Media.Animation.Storyboard> y los objetos <xref:System.Windows.Media.Animation.Clock>, consulte [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).\)  
  
 Para aplicar un objeto <xref:System.Windows.Media.Animation.Clock> único a una propiedad, complete los pasos siguientes.  
  
1.  Cree un objeto <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2.  Utilice el método <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> de <xref:System.Windows.Media.Animation.AnimationTimeline> para crear un objeto <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Utilice el método <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> del objeto que desea animar para aplicar <xref:System.Windows.Media.Animation.AnimationClock> a la propiedad que especifica.  
  
 En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para crear un árbol de control de tiempo y utilizarlo para animar propiedades, complete los pasos siguientes.  
  
1.  Utilice los objetos <xref:System.Windows.Media.Animation.ParallelTimeline> y <xref:System.Windows.Media.Animation.AnimationTimeline> para crear el árbol de control de tiempo.  
  
2.  Utilice el método <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> del objeto  <xref:System.Windows.Media.Animation.ParallelTimeline> raíz para crear <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Recorra en iteración las propiedades <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> de <xref:System.Windows.Media.Animation.ClockGroup> y aplique sus objetos <xref:System.Windows.Media.Animation.Clock> secundarios.  Para cada elemento secundario <xref:System.Windows.Media.Animation.AnimationClock>, utilice el método <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> del objeto que desea animar a fin de aplicar <xref:System.Windows.Media.Animation.AnimationClock> a la propiedad que especifique.  
  
 Para obtener más información acerca de los objetos de reloj, consulte [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## Animación por fotograma: omitir el sistema de animación y control de tiempo  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Un escenario para este enfoque lo constituyen las animaciones físicas, donde a cada paso de la animación es preciso volver a calcular los objetos basándose en el último conjunto de interacciones de objeto.  
  
 Las animaciones por fotograma no se pueden definir dentro de estilos, plantillas de control ni plantillas de datos.  
  
 Para animar fotograma a fotograma, se efectúa el registro para el evento <xref:System.Windows.Media.CompositionTarget.Rendering> del objeto que contiene los objetos que se desea animar.  Se llama a este método de control de eventos una vez por cada fotograma.  Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] calcula las referencias de los datos de representación conservados en el [árbol visual](GTMT) hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación del fotograma actual, puede convertir el <xref:System.EventArgs> asociado a este evento como <xref:System.Windows.Media.RenderingEventArgs>, que proporciona una propiedad <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> que puede utilizar para obtener el tiempo de representación del fotograma actual.  
  
 Para obtener más información, vea la página <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)