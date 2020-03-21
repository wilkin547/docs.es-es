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
ms.openlocfilehash: 0b4bf6d4963f32ad83f762fce73c805197ff9c9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181846"
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
|Animación de guión gráfico|Por instancia, <xref:System.Windows.Style> <xref:System.Windows.Controls.ControlTemplate>, ,<xref:System.Windows.DataTemplate>|Sí|Sí|  
|Animación local|Por instancia|Sin |Sin |  
|Animación de reloj|Por instancia|Sin |Sí|  
|Animación por fotograma|Por instancia|Sin |N/D|  
  
<a name="storyboard_animations"></a>
## <a name="storyboard-animations"></a>Animaciones de guión gráfico  
 Utilice <xref:System.Windows.Media.Animation.Storyboard> a cuando desee definir y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]aplicar las animaciones en , controle interactivamente las animaciones después <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.DataTemplate>de que se inicien, cree un árbol complejo de animaciones o anime en un <xref:System.Windows.Style>, o . Para que un objeto <xref:System.Windows.Media.Animation.Storyboard>sea animado por <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>un , debe ser a <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>o , o debe usarse para establecer un o . Para obtener más detalles, consulte [Información general sobre objetos Storyboard](storyboards-overview.md).  
  
 A <xref:System.Windows.Media.Animation.Storyboard> es un tipo <xref:System.Windows.Media.Animation.Timeline> especial de contenedor que proporciona información de segmentación para las animaciones que contiene. Para animar <xref:System.Windows.Media.Animation.Storyboard>con un , complete los tres pasos siguientes.  
  
1. Declare <xref:System.Windows.Media.Animation.Storyboard> una y una o más animaciones.  
  
2. Utilice <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> las <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedades adjuntas y para especificar el objeto de destino y la propiedad de cada animación.  
  
3. (Sólo código) Defina <xref:System.Windows.NameScope> a <xref:System.Windows.FrameworkElement> for <xref:System.Windows.FrameworkContentElement>a o . Registre los nombres de los <xref:System.Windows.FrameworkElement> objetos que se animará con ese o <xref:System.Windows.FrameworkContentElement>.  
  
4. Comience <xref:System.Windows.Media.Animation.Storyboard>el archivo .  
  
 Al <xref:System.Windows.Media.Animation.Storyboard> iniciar una aplicación de animaciones a las propiedades que animan y las inicia. Hay dos maneras <xref:System.Windows.Media.Animation.Storyboard>de comenzar un <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> : puede <xref:System.Windows.Media.Animation.Storyboard> utilizar el método <xref:System.Windows.Media.Animation.BeginStoryboard> proporcionado por la clase, o puede utilizar una acción. La única manera [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de animar <xref:System.Windows.Media.Animation.BeginStoryboard> es usar una acción. Una <xref:System.Windows.Media.Animation.BeginStoryboard> acción se puede <xref:System.Windows.EventTrigger>utilizar <xref:System.Windows.Trigger>en <xref:System.Windows.DataTrigger>una propiedad , o un archivo .  
  
 En la tabla siguiente se <xref:System.Windows.Media.Animation.Storyboard> muestran los diferentes lugares donde se admite cada técnica de inicio: por instancia, estilo, plantilla de control y plantilla de datos.  
  
|El guión gráfico se comienza utilizando...|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y una propiedad<xref:System.Windows.Trigger>|Sin |Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.DataTrigger>|Sin |Sí|Sí|Sí|[Cómo: Activar una animación cuando se cambian datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|Método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sí|Sin |Sin |Sin |[Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Para obtener <xref:System.Windows.Media.Animation.Storyboard> más información acerca de los objetos, vea Información general sobre [guiones gráficos](storyboards-overview.md).  
  
## <a name="local-animations"></a>Animaciones locales  
 Las animaciones locales proporcionan una manera <xref:System.Windows.Media.Animation.Animatable> cómoda de animar una propiedad de dependencia de cualquier objeto. Las animaciones locales se utilizan cuando se desea aplicar una sola animación a una propiedad y no se necesita controlar interactivamente la animación después de iniciarse. A <xref:System.Windows.Media.Animation.Storyboard> diferencia de una animación, una animación local <xref:System.Windows.FrameworkElement> puede <xref:System.Windows.FrameworkContentElement>animar un objeto que no está asociado a un archivo o a . Tampoco es que tenga <xref:System.Windows.NameScope> que definir a para este tipo de animación.  
  
 Las animaciones locales únicamente se pueden utilizar mediante código y no se pueden definir en estilos, plantillas de control ni plantillas de datos. Una animación local no se puede controlar interactivamente una vez iniciada.  
  
 Para animar mediante una animación local, complete los pasos siguientes.  
  
1. Cree un objeto <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2. Utilice <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> el método del objeto que desea <xref:System.Windows.Media.Animation.AnimationTimeline> animar para aplicar la propiedad que especifique.  
  
 En el ejemplo siguiente se muestra cómo <xref:System.Windows.Controls.Button>animar el ancho y el color de fondo de un archivo .  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Animaciones de reloj  
 Utilice <xref:System.Windows.Media.MediaPlayer.Clock%2A> objetos cuando desee <xref:System.Windows.Media.Animation.Storyboard> animar sin usar a y desee crear árboles de temporización complejos o controlar animaciones de forma interactiva después de que se inicien. Puede utilizar Clock objetos para animar <xref:System.Windows.Media.Animation.Animatable> una propiedad de dependencia de cualquier objeto.  
  
 No puede <xref:System.Windows.Media.Animation.Clock> utilizar objetos directamente para animar en estilos, plantillas de control o plantillas de datos. (El sistema de animación <xref:System.Windows.Media.Animation.Clock> y temporización realmente utiliza objetos para animar <xref:System.Windows.Media.Animation.Clock> en estilos, <xref:System.Windows.Media.Animation.Storyboard>plantillas de control y plantillas de datos, pero debe crear esos objetos para usted a partir de un archivo . Para obtener más información <xref:System.Windows.Media.Animation.Storyboard> acerca <xref:System.Windows.Media.Animation.Clock> de la relación entre objetos y objetos, vea Información general sobre el sistema de [animación y temporización](animation-and-timing-system-overview.md).)  
  
 Para aplicar <xref:System.Windows.Media.Animation.Clock> una sola a una propiedad, complete los pasos siguientes.  
  
1. Cree un objeto <xref:System.Windows.Media.Animation.AnimationTimeline>.  
  
2. Utilice <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> el método <xref:System.Windows.Media.Animation.AnimationTimeline> de <xref:System.Windows.Media.Animation.AnimationClock>la para crear un archivo .  
  
3. Utilice <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> el método del objeto que desea <xref:System.Windows.Media.Animation.AnimationClock> animar para aplicar lo a la propiedad que especifique.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Animation.AnimationClock> se muestra cómo crear un y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para crear un árbol de control de tiempo y utilizarlo para animar propiedades, complete los pasos siguientes.  
  
1. Utilice <xref:System.Windows.Media.Animation.ParallelTimeline> <xref:System.Windows.Media.Animation.AnimationTimeline> y objetos para crear el árbol de tiempo.  
  
2. Utilice <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> la raíz <xref:System.Windows.Media.Animation.ParallelTimeline> para <xref:System.Windows.Media.Animation.ClockGroup>crear un archivo .  
  
3. Repasar en <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> iteración el de y <xref:System.Windows.Media.Animation.ClockGroup> aplicar sus objetos secundarios. <xref:System.Windows.Media.Animation.Clock> Para <xref:System.Windows.Media.Animation.AnimationClock> cada elemento <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> secundario, utilice el método del objeto <xref:System.Windows.Media.Animation.AnimationClock> que desea animar para aplicar la propiedad especificada  
  
 Para más información acerca de los objetos de reloj, consulte [Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Animación por fotograma: omitir el sistema de animación y control de tiempo  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Un escenario para este enfoque lo constituyen las animaciones físicas, donde a cada paso de la animación es preciso volver a calcular los objetos basándose en el último conjunto de interacciones de objeto.  
  
 Las animaciones por fotograma no se pueden definir dentro de estilos, plantillas de control ni plantillas de datos.  
  
 Para animar fotograma a fotograma, registre <xref:System.Windows.Media.CompositionTarget.Rendering> el evento del objeto que contiene los objetos que desea animar. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación <xref:System.EventArgs> para el fotograma actual, el asociado a este evento se puede convertir como <xref:System.Windows.Media.RenderingEventArgs>, que proporcionan una <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> propiedad que puede usar para obtener el tiempo de representación del fotograma actual.  
  
 Para obtener más <xref:System.Windows.Media.CompositionTarget.Rendering> información, consulte la página.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
- [Información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md)
- [Descripción general de las propiedades de dependencia](../advanced/dependency-properties-overview.md)
