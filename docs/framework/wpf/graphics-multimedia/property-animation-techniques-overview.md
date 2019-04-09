---
title: Información general sobre técnicas de animación de propiedades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 5ec401aea139a868b3633afce4c74558aafcaa1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165443"
---
# <a name="property-animation-techniques-overview"></a>Información general sobre técnicas de animación de propiedades
En este tema se describen los enfoques diferentes para animar propiedades: guiones gráficos, animaciones locales, relojes y animaciones por fotograma.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación básicas descritas en [Información general sobre animaciones](animation-overview.md).  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>Diferentes maneras de animar  
 Dado que hay muchos escenarios diferentes para animar propiedades, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varios enfoques para ello.  
  
 Para cada enfoque, en la tabla siguiente se indica si se puede utilizar por instancia, en estilos, en plantillas de control o en plantillas de datos; si se puede utilizar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; y si el enfoque permite controlar interactivamente la animación.  "Por instancia" se refiere a la técnica de aplicar directamente una animación o guión gráfico a las instancias de un objeto, en lugar de en un estilo, una plantilla de control o una plantilla de datos.  
  
|Técnica de animación|Escenarios|Admite XAML|Control interactivo|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Animación de guión gráfico|Por instancia, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Sí|Sí|  
|Animación local|Por instancia|No|No|  
|Animación de reloj|Por instancia|No|Sí|  
|Animación por fotograma|Por instancia|No|N/D|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>Animaciones de guión gráfico  
 Use un <xref:System.Windows.Media.Animation.Storyboard> cuando desee definir y aplicar animaciones en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]de forma interactiva controlar las animaciones después de iniciar, crear un árbol complejo de animaciones o animar en un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>. Animar un objeto un <xref:System.Windows.Media.Animation.Storyboard>, debe ser un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o se debe utilizar para establecer un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Para obtener más detalles, consulte [Información general sobre objetos Storyboard](storyboards-overview.md).  
  
 Un <xref:System.Windows.Media.Animation.Storyboard> es un tipo especial de contenedor <xref:System.Windows.Media.Animation.Timeline> que proporciona información de destino para las animaciones que contiene. Para animar con un <xref:System.Windows.Media.Animation.Storyboard>, complete los tres pasos siguientes.  
  
1.  Declarar un <xref:System.Windows.Media.Animation.Storyboard> y animaciones de uno o más.  
  
2.  Use la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> adjunta propiedades para especificar el objeto de destino y propiedad de cada animación.  
  
3.  (Solo código) Definir un <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Registrar los nombres de los objetos que se va a animar con ese <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
4.  Comenzar la <xref:System.Windows.Media.Animation.Storyboard>.  
  
 A partir de un <xref:System.Windows.Media.Animation.Storyboard> se aplican animaciones a las propiedades que animan y las inicia. Hay dos maneras de comenzar un <xref:System.Windows.Media.Animation.Storyboard>: puede usar el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método proporcionado por el <xref:System.Windows.Media.Animation.Storyboard> clase, o bien puede usar un <xref:System.Windows.Media.Animation.BeginStoryboard> acción. La única forma de animar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste en usar un <xref:System.Windows.Media.Animation.BeginStoryboard> acción. Un <xref:System.Windows.Media.Animation.BeginStoryboard> acción se puede usar en un <xref:System.Windows.EventTrigger>, propiedad <xref:System.Windows.Trigger>, o un <xref:System.Windows.DataTrigger>.  
  
 La siguiente tabla muestra los diferentes lugares donde cada <xref:System.Windows.Media.Animation.Storyboard> comenzar es compatible con la técnica: por instancia, estilo, plantilla de control y plantilla de datos.  
  
|El guión gráfico se comienza utilizando...|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y una <xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y una propiedad <xref:System.Windows.Trigger>|No|Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y un <xref:System.Windows.DataTrigger>|No|Sí|Sí|Sí|[Filtrar Activar una animación cuando cambian los datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método|Sí|No|No|No|[Animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Animation.Storyboard> objetos, vea el [Storyboards Overview](storyboards-overview.md).  
  
## <a name="local-animations"></a>Animaciones locales  
 Las animaciones locales proporcionan una manera cómoda de animar una propiedad de dependencia de cualquier <xref:System.Windows.Media.Animation.Animatable> objeto. Las animaciones locales se utilizan cuando se desea aplicar una sola animación a una propiedad y no se necesita controlar interactivamente la animación después de iniciarse. A diferencia de un <xref:System.Windows.Media.Animation.Storyboard> animación, una animación local puede animar un objeto que no está asociado con un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. También no tiene que definir un <xref:System.Windows.NameScope> para este tipo de animación.  
  
 Las animaciones locales únicamente se pueden utilizar mediante código y no se pueden definir en estilos, plantillas de control ni plantillas de datos. Una animación local no se puede controlar interactivamente una vez iniciada.  
  
 Para animar mediante una animación local, complete los pasos siguientes.  
  
1.  Crear un <xref:System.Windows.Media.Animation.AnimationTimeline> objeto.  
  
2.  Use la <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método del objeto que desea animar para aplicar el <xref:System.Windows.Media.Animation.AnimationTimeline> a la propiedad que especifique.  
  
 El ejemplo siguiente muestra cómo animar el color de fondo y de ancho de un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Animaciones de reloj  
 Use <xref:System.Windows.Media.MediaPlayer.Clock%2A> objetos cuando desea animar sin utilizar un <xref:System.Windows.Media.Animation.Storyboard> y desea crear árboles de control de tiempo complejos o controlar interactivamente las animaciones después de iniciarse. Puede usar los objetos de reloj para animar una propiedad de dependencia de cualquier <xref:System.Windows.Media.Animation.Animatable> objeto.  
  
 No puede usar <xref:System.Windows.Media.Animation.Clock> objetos controlan directamente a animar en estilos, plantillas o plantillas de datos. (Use el sistema de animación y temporización realmente <xref:System.Windows.Media.Animation.Clock> objetos que se va a animar en estilos, plantillas de control y plantillas de datos, pero deben crearlos <xref:System.Windows.Media.Animation.Clock> objetos para usted desde un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener más información sobre la relación entre <xref:System.Windows.Media.Animation.Storyboard> objetos y <xref:System.Windows.Media.Animation.Clock> objetos, vea el [Animation and Timing System Overview](animation-and-timing-system-overview.md).)  
  
 Para aplicar una sola <xref:System.Windows.Media.Animation.Clock> a una propiedad, complete los pasos siguientes.  
  
1.  Crear un <xref:System.Windows.Media.Animation.AnimationTimeline> objeto.  
  
2.  Use la <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> método de la <xref:System.Windows.Media.Animation.AnimationTimeline> para crear un <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Use la <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> método del objeto que desea animar para aplicar el <xref:System.Windows.Media.Animation.AnimationClock> a la propiedad especificada.  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para crear un árbol de control de tiempo y utilizarlo para animar propiedades, complete los pasos siguientes.  
  
1.  Use <xref:System.Windows.Media.Animation.ParallelTimeline> y <xref:System.Windows.Media.Animation.AnimationTimeline> objetos para crear el árbol de control de tiempo.  
  
2.  Use la <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> de la raíz <xref:System.Windows.Media.Animation.ParallelTimeline> para crear un <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Recorrer en iteración el <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> de la <xref:System.Windows.Media.Animation.ClockGroup> y se aplican a su elemento secundario <xref:System.Windows.Media.Animation.Clock> objetos. Para cada <xref:System.Windows.Media.Animation.AnimationClock> secundario, use la <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> método del objeto que desea animar para aplicar el <xref:System.Windows.Media.Animation.AnimationClock> a la propiedad especificada  
  
 Para más información acerca de los objetos de reloj, consulte [Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Animación por fotograma: Omitir el sistema de temporización y animación  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Un escenario para este enfoque lo constituyen las animaciones físicas, donde a cada paso de la animación es preciso volver a calcular los objetos basándose en el último conjunto de interacciones de objeto.  
  
 Las animaciones por fotograma no se pueden definir dentro de estilos, plantillas de control ni plantillas de datos.  
  
 Para animar fotograma a fotograma, se registra para el <xref:System.Windows.Media.CompositionTarget.Rendering> eventos del objeto que contiene los objetos que desee animar. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación del fotograma actual, el <xref:System.EventArgs> asociado a este evento se puede convertir <xref:System.Windows.Media.RenderingEventArgs>, que proporcionan un <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> el tiempo de representación de propiedad que se puede utilizar para obtener el marco actual.  
  
 Para obtener más información, consulte la <xref:System.Windows.Media.CompositionTarget.Rendering> página.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
- [Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md)
- [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md)
