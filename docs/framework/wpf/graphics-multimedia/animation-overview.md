---
title: "Informaci&#243;n general sobre animaciones | Microsoft Docs"
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
  - "Guiones gráficos [WPF], animaciones"
  - "animaciones [WPF], información general"
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
caps.latest.revision: 73
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 73
---
# Informaci&#243;n general sobre animaciones
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un conjunto eficaz de características de gráficos y diseño que le permiten crear interfaces de usuario y documentos atractivos. Animación puede hacer que una interfaz de usuario aún más espectacular y utilizable. Simplemente animar un color de fondo o aplicando un animado <xref:System.Windows.Media.Transform>, puede crear transiciones de pantalla espectaculares o proporcionar indicaciones visuales útiles.  
  
 Esta información general proporciona una introducción a los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de animación y temporización. Se centra en la animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos mediante guiones gráficos.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Introducción a las animaciones  
 La animación es una ilusión que se crea mediante el cambio rápido a través de una serie de imágenes, cada forma ligeramente diferentes a la última. El cerebro percibe el grupo de imágenes como una sola escena cambiante. En una película, se crea esta ilusión mediante cámaras que graban muchas fotografías, o fotogramas, cada segundo. Cuando un proyector reproduce estos fotogramas, los espectadores ven una imagen en movimiento.  
  
 Animación en un equipo es similar. Por ejemplo, un programa que realiza un dibujo de atenuación rectángulo fuera de la vista funcionen como sigue.  
  
-   El programa crea un temporizador.  
  
-   El programa comprueba el temporizador a intervalos establecidos para ver cuánto tiempo ha transcurrido.  
  
-   Cada vez que el programa comprueba el temporizador, calcula el valor de opacidad actual del rectángulo en función de cuánto tiempo ha transcurrido.  
  
-   A continuación, el programa actualiza el rectángulo con el nuevo valor y dibuja de nuevo.  
  
 Anteriores a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] los programadores tenían que crear y administrar sus propios sistemas de temporización o utilizar bibliotecas personalizadas especiales.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]incluye un sistema eficaz de control de tiempo que se expone a través de código administrado y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y que está muy integrado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]animación facilita animar los controles y otros objetos gráficos.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]administra todo el trabajo entre bastidores de administrar un sistema de temporización y volver a dibujar la pantalla de manera eficiente. Proporciona clases de tiempo que le permiten centrarse en los efectos que desee crear, en lugar de la mecánica de conseguir dichos efectos.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]También facilita la tarea para crear sus propias animaciones exponiendo clases base de animación desde el que se pueden heredar sus clases, para generar animaciones personalizadas. Estas animaciones personalizadas benefician muchas de las ventajas de rendimiento de las clases de animación estándar.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Sistema de animación de propiedades WPF  
 Si comprende algunos conceptos importantes sobre el sistema de temporización [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animaciones pueden ser más fáciles de usar. Más importante es que, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], objetos se animan al aplicar animaciones a sus propiedades individuales. Por ejemplo, para hacer que un elemento de marco crezca, se animan sus <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades. Para hacer que un objeto se desvanece de la vista, se anima su <xref:System.Windows.UIElement.Opacity%2A> propiedad.  
  
 Para que una propiedad que tienen capacidades de animación, debe cumplir los tres requisitos siguientes:  
  
-   Debe ser una propiedad de dependencia.  
  
-   Debe pertenecer a una clase que hereda de <xref:System.Windows.DependencyObject> e implementa la <xref:System.Windows.Media.Animation.IAnimatable> interfaz.  
  
-   Debe haber un tipo de animación compatible disponible. (Si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ninguno, puede crear los suyos propios. Consulte la [información general sobre animaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]contiene muchos objetos que tienen <xref:System.Windows.Media.Animation.IAnimatable> propiedades. Controles como <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.TabControl>y también <xref:System.Windows.Controls.Panel> y <xref:System.Windows.Shapes.Shape> objetos heredan de <xref:System.Windows.DependencyObject>. La mayoría de sus propiedades son propiedades de dependencia.  
  
 Puede usar animaciones casi en cualquier lugar, que incluye estilos y plantillas de control. Animaciones no tienen que ser visuales; Puede animar objetos que no forman parte de la interfaz de usuario si cumplen los criterios que se describen en esta sección.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Ejemplo: Hacer una transición del elemento dentro y fuera de la vista  
 Este ejemplo muestra cómo utilizar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animación para animar el valor de una propiedad de dependencia. Utiliza un <xref:System.Windows.Media.Animation.DoubleAnimation>, que es un tipo de animación que genera <xref:System.Double> valores para animar el <xref:System.Windows.UIElement.Opacity%2A> propiedad de un <xref:System.Windows.Shapes.Rectangle>. Como resultado, el <xref:System.Windows.Shapes.Rectangle> desaparece.  
  
 La primera parte del ejemplo se crea un <xref:System.Windows.Shapes.Rectangle> elemento. Los pasos siguientes muestran cómo crear una animación y aplicarla al rectángulo <xref:System.Windows.UIElement.Opacity%2A> propiedad.  
  
 El siguiente código muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en XAML.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 El siguiente código muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en el código.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Parte 1: Crear una animación DoubleAnimation  
 Una manera de hacer que un elemento fundido es animar su <xref:System.Windows.UIElement.Opacity%2A> propiedad. Dado que la <xref:System.Windows.UIElement.Opacity%2A> propiedad es de tipo <xref:System.Double>, necesita una animación que genera valores double. Un <xref:System.Windows.Media.Animation.DoubleAnimation> es una animación de este tipo. Un <xref:System.Windows.Media.Animation.DoubleAnimation> crea una transición entre dos valores double. Para especificar su valor inicial, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad. Para especificar su valor final, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.  
  
1.  Un valor de opacidad de `1.0` hace que el objeto completamente opaco y un valor de opacidad de `0.0` oculta completamente. To make the animation transition from                                  `1.0` to                                  `0.0` you set its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to                                  `1.0` and its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property to                                  `0.0`. El siguiente código muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     El siguiente código muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  A continuación, debe especificar un <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. El <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una animación especifica cuánto tiempo tarda vaya desde su valor inicial al valor de destino. El siguiente código muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> a cinco segundos en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     El siguiente código muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en cinco segundos en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  El código anterior mostraba una animación que realiza la transición de `1.0` a `0.0`, lo que hace que el elemento de destino para la atenuación de completamente opaco a ser completamente invisible. Para que el elemento aparezca progresivamente en la vista antes de desaparecer, establezca la <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad de la animación `true`. Para que la animación se repita indefinidamente, establezca su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. El siguiente código muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     El siguiente código muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Parte 2: Crear un guión gráfico  
 Para aplicar una animación a un objeto, se crea un <xref:System.Windows.Media.Animation.Storyboard> y use la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> adjunta propiedades para especificar el objeto y propiedad que desea animar.  
  
1.  Crear la <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario. El siguiente código muestra cómo crear el <xref:System.Windows.Media.Animation.Storyboard> en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]  
  
     Para crear el <xref:System.Windows.Media.Animation.Storyboard> en el código, declare un <xref:System.Windows.Media.Animation.Storyboard> variable en el nivel de clase.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     A continuación, inicialice la <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  El <xref:System.Windows.Media.Animation.Storyboard> debe saber dónde aplicar la animación. Utilice la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> propiedad adjunta para especificar el objeto que desea animar. La siguiente muestra cómo establecer el nombre de destino de la <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     La siguiente muestra cómo establecer el nombre de destino de la <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Utilice la <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> propiedad adjunta para especificar la propiedad que se va a animar. La siguiente muestra cómo se configura la animación al destino el <xref:System.Windows.UIElement.Opacity%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> en XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     La siguiente muestra cómo se configura la animación al destino el <xref:System.Windows.UIElement.Opacity%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> sintaxis y ejemplos adicionales, vea la [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML): Asociar el guión gráfico con un desencadenador  
 La manera más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es usar un desencadenador de eventos.                          Esta sección muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un desencadenador en XAML.  
  
1.  Crear un <xref:System.Windows.Media.Animation.BeginStoryboard> de objetos y asociar el guión gráfico. Un <xref:System.Windows.Media.Animation.BeginStoryboard> es un tipo de <xref:System.Windows.TriggerAction> que aplica e inicia un <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Crear un <xref:System.Windows.EventTrigger> y agregue la <xref:System.Windows.Media.Animation.BeginStoryboard> a su <xref:System.Windows.EventTrigger.Actions%2A> colección. Establecer el <xref:System.Windows.EventTrigger.RoutedEvent%2A> propiedad de la <xref:System.Windows.EventTrigger> para el evento enrutado que desea iniciar la <xref:System.Windows.Media.Animation.Storyboard>. (Para obtener más información sobre eventos enrutados, vea la [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Agregue el <xref:System.Windows.EventTrigger> a la <xref:System.Windows.FrameworkElement.Triggers%2A> colección del rectángulo.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (código): Asociar el guión gráfico con un controlador de eventos  
 La manera más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en código es usar un controlador de eventos. Esta sección muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un controlador de eventos en el código.  
  
1.  Registrarse para la <xref:System.Windows.FrameworkElement.Loaded> eventos del rectángulo.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Declare el controlador de eventos. En el controlador de eventos, use la <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método para aplicar el guión gráfico.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Ejemplo completo  
 A continuación muestra cómo crear un rectángulo que desaparece en XAML.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 A continuación muestra cómo crear un rectángulo que desaparece en el código.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Tipos de animación  
 Porque animaciones generan valores de propiedad, existen distintos tipos de animaciones para distintos tipos de propiedades. Para animar una propiedad que acepta un <xref:System.Double>, como el <xref:System.Windows.FrameworkElement.Width%2A> propiedad de un elemento, se usa una animación que genera <xref:System.Double> valores. Para animar una propiedad que acepta un <xref:System.Windows.Point>, usa una animación que genera <xref:System.Windows.Point> valores y así sucesivamente. Debido al número de distintos tipos de propiedades, hay varias clases de animación en el <xref:System.Windows.Media.Animation> espacio de nombres. Afortunadamente, siguen una convención de nomenclatura estricta que hace fácil diferenciar entre ellos:  
  
-   \<                         *Tipo*> animación  
  
     Estos se conoce como "From/To/By" o "básica" animación, animación entre un valor de inicio y de destino, o mediante la adición de un valor de desplazamiento y su valor inicial.  
  
    -   Para especificar un valor inicial, establezca la propiedad From de la animación.  
  
    -   Para especificar un valor final, establezca la propiedad To de la animación.  
  
    -   Para especificar un valor de desplazamiento, establezca la propiedad By de la animación.  
  
     Los ejemplos en esta introducción usan estas animaciones porque son las más fáciles de usar. Animaciones From/To/By se describen en detalle en la información general sobre animaciones de From/To/By.  
  
-   \<                         *Tipo*> AnimationUsingKeyFrames  
  
     Animaciones de fotogramas clave son más eficaces que las animaciones From/To/By porque se puede especificar cualquier número de valores de destino e incluso controlar su método de interpolación. Algunos tipos solo se pueden animar con animaciones de fotogramas clave. Animaciones de fotogramas clave se describen en detalle en el [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   \<                         *Tipo*> AnimationUsingPath  
  
     Las animaciones de trazado permiten usar un trazado geométrico para generar valores animados.  
  
-   \<                         *Tipo*> AnimationBase  
  
     Clase abstracta que, cuando se implementa, anima un <> \</> *tipo*> valor. Esta clase actúa como clase base para <> \</> *tipo*> animación y <> \</> *tipo*> AnimationUsingKeyFrames clases. Tiene que tratar directamente con estas clases solo si desea crear sus propias animaciones personalizadas. De lo contrario, utilice un <> \</> *tipo*> animación o fotograma clave<>*tipo*> animación.  
  
 En la mayoría de los casos, deseará utilizar los <> \</> *tipo*> clases de animación, como <xref:System.Windows.Media.Animation.DoubleAnimation> y <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 La tabla siguiente muestran varios tipos de animación comunes y algunas propiedades con las que se utilizan.  
  
|Tipo de propiedad|Animación correspondiente de basic (From/To/By)|Animación de fotogramas clave correspondiente|Animación de trazado correspondiente|Ejemplo de uso|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Ninguna|Animate the                                  <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a                                  <xref:System.Windows.Media.SolidColorBrush> or a                                  <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animate the                                  <xref:System.Windows.FrameworkElement.Width%2A> of a                                  <xref:System.Windows.Controls.DockPanel> or the                                  <xref:System.Windows.FrameworkElement.Height%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animar el <xref:System.Windows.Media.EllipseGeometry.Center%2A> posición de un <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Ninguna|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Ninguna|Animate the                                  <xref:System.Windows.Controls.TextBlock.Text%2A> of a                                  <xref:System.Windows.Controls.TextBlock> or the                                  <xref:System.Windows.Controls.ContentControl.Content%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Las animaciones son escalas de tiempo  
 Todos los tipos de animación que se heredan de la <xref:System.Windows.Media.Animation.Timeline> clase; por lo tanto, todas las animaciones son tipos especializados de escalas de tiempo. Un <xref:System.Windows.Media.Animation.Timeline> define un segmento de tiempo. Puede especificar el *comportamientos de temporización* de escala de tiempo: su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, cuántas veces es repetido e incluso cómo rapidez pasa el tiempo para ella.  
  
 Dado que una animación es un <xref:System.Windows.Media.Animation.Timeline>, también representa un segmento de tiempo. Una animación también calcula valores de salida de medida que avanza por su segmento de tiempo especificado (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Como la animación avanza, o "reproduce", actualiza la propiedad que está asociado.  
  
 Tres propiedades de temporización que se usan con frecuencia son <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>La propiedad Duration  
 Como se mencionó anteriormente, una escala de tiempo representa un segmento de tiempo. La longitud de ese segmento se determina por la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la escala de tiempo, que normalmente se especifica mediante una <xref:System.Windows.Duration.TimeSpan%2A> valor. Cuando una escala de tiempo llega al final de su duración, se ha completado una iteración.  
  
 Una animación usa su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para determinar su valor actual. Si no especifica un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valor para una animación, se usa 1 segundo, que es el valor predeterminado.  
  
 La sintaxis siguiente muestra una versión simplificada de la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis para la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad.  
  
||  
|-|  
|*hours* `:` *minutes* `:` *seconds*|  
  
 En la tabla siguiente se muestra varios <xref:System.Windows.Duration> configuración y sus valores resultantes.  
  
|Configuración|Valor resultante|  
|-------------|---------------------|  
|0:0:5.5|5,5 segundos.|  
|0:30:5.5|30 minutos y 5,5 segundos.|  
|1:30:5.5|1 hora, 30 minutos y 5,5 segundos.|  
  
 Una manera de especificar un <xref:System.Windows.Duration> en código es usar el <xref:System.TimeSpan.FromSeconds%2A> método para crear un <xref:System.TimeSpan>, a continuación, declare un nuevo <xref:System.Windows.Duration> estructura utilizando <xref:System.TimeSpan>.  
  
 Para obtener más información acerca de <xref:System.Windows.Duration> valores y la completa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintaxis, consulte el <xref:System.Windows.Duration> estructura.  
  
#### <a name="autoreverse"></a>AutoReverse  
 El <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad especifica si una escala de tiempo se reproduce hacia atrás cuando se llegue al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Si establece esta propiedad de animación en `true`, la animación se invierte después de llegar al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, reproduce desde su valor final a su valor inicial. De forma predeterminada, esta propiedad es `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad especifica cuántas veces se reproduce una escala de tiempo. De forma predeterminada, las escalas de tiempo tienen una iteración de `1.0`, lo que significa que desempeñan una vez y no se repita.  
  
 Para obtener más información acerca de estas propiedades y otras, vea la [Timing Behaviors Overview](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Aplicar una animación a una propiedad  
 Las secciones anteriores describen los distintos tipos de animaciones y sus propiedades de temporización. En esta sección se muestra cómo aplicar la animación a la propiedad que desea animar.                  <xref:System.Windows.Media.Animation.Storyboard> objetos proporcionan una manera de aplicar animaciones a propiedades. Un <xref:System.Windows.Media.Animation.Storyboard> es una *escala de tiempo contenedora* que proporciona información de destino para las animaciones que contiene.  
  
### <a name="targeting-objects-and-properties"></a>Objetos y propiedades de destino  
 El <xref:System.Windows.Media.Animation.Storyboard> clase proporciona el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> propiedades adjuntas. Al establecer estas propiedades en una animación, se indica a la animación qué debe animar. Sin embargo, antes de que una animación puede tener como destino un objeto, el objeto debe suelen asignarse un nombre.  
  
 Asignar un nombre a un <xref:System.Windows.FrameworkElement> difiere de asignar un nombre a un <xref:System.Windows.Freezable> objeto. La mayoría de los controles y paneles son elementos de marco; Sin embargo, la mayoría de los objetos puramente gráfica, como pinceles, transformaciones y geometrías, es objetos freezable. Si no está seguro de si un tipo es un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.Freezable>, consulte el **jerarquía de herencia** sección de la documentación de referencia.  
  
-   Para realizar una <xref:System.Windows.FrameworkElement> un destino de animación, darle un nombre estableciendo su <xref:System.Windows.FrameworkElement.Name%2A> propiedad. En el código, debe usar también el <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el nombre del elemento con la página a la que pertenece.  
  
-   Para realizar una <xref:System.Windows.Freezable> objeto un destino de animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utiliza el [x: Name (directiva)](../../../../docs/framework/xaml-services/x-name-directive.md) para asignar un nombre. En código, utilice sólo la <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el objeto con la página a la que pertenece.  
  
 Las secciones siguientes proporcionan un ejemplo de asignación de nombres de un elemento en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el código. Para obtener información más detallada sobre la nomenclatura y de destino, consulte el [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Aplicar e iniciar guiones gráficos  
 Para iniciar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], debe asociarla a un <xref:System.Windows.EventTrigger>. Un <xref:System.Windows.EventTrigger> es un objeto que describe qué acciones debe realizar cuando se produce un evento especificado. Una de esas acciones puede ser un <xref:System.Windows.Media.Animation.BeginStoryboard> acción, que se utiliza para iniciar el guión gráfico. Desencadenadores de eventos son similares en concepto a los controladores de eventos porque permiten especificar cómo responde la aplicación a un evento determinado. A diferencia de los controladores de eventos, se pueden describir totalmente en desencadenadores de eventos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; se requiere ningún otro código.  
  
 Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> en código, puede usar un <xref:System.Windows.EventTrigger> o use la <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método de la <xref:System.Windows.Media.Animation.Storyboard> clase.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Controlar interactivamente un guión gráfico  
 En el ejemplo anterior se mostró cómo iniciar una <xref:System.Windows.Media.Animation.Storyboard> cuando se produce un evento. Puede controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse: se puede pausar, reanudar, detener, avanzar a su período de relleno, buscar y quitar el <xref:System.Windows.Media.Animation.Storyboard>. Para obtener más información y un ejemplo que muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard>, consulte el [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>¿Qué ocurre cuando una animación finaliza?  
 El <xref:System.Windows.Media.Animation.FillBehavior> propiedad especifica cómo se comporta una escala de tiempo cuando finaliza. De forma predeterminada, se inicia una escala de tiempo <xref:System.Windows.Media.Animation.ClockState> cuando termina. Una animación que es <xref:System.Windows.Media.Animation.ClockState> mantiene su valor de salida final.  
  
 El <xref:System.Windows.Media.Animation.DoubleAnimation> en el ejemplo anterior no finaliza porque su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad está establecida en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. En el ejemplo siguiente se anima un rectángulo usando una animación similar. A diferencia del ejemplo anterior, el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> y <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> se mantienen las propiedades de esta animación en sus valores predeterminados. Por lo tanto, la animación progresa de 1 a 0 en cinco segundos y, a continuación, se detiene.  
  
 [!code-xml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Dado que su <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> no se ha cambiado el valor predeterminado, que es <xref:System.Windows.Media.Animation.FillBehavior>, la animación retiene el valor final, 0, cuando finaliza. Por lo tanto, la <xref:System.Windows.UIElement.Opacity%2A> de rectángulo permanece en 0 después de la animación finaliza. Si establece la <xref:System.Windows.UIElement.Opacity%2A> del rectángulo en otro valor, el código parece que no tienen ningún efecto, porque la animación todavía influye en el <xref:System.Windows.UIElement.Opacity%2A> propiedad.  
  
 Una manera de recuperar el control de una propiedad animada en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método y especificar null para la <xref:System.Windows.Media.Animation.AnimationTimeline> parámetro. Para obtener más información y un ejemplo, vea [establece una propiedad después de la animación con un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Tenga en cuenta que, aunque se establece un valor de propiedad que tiene un <xref:System.Windows.Media.Animation.ClockState> o <xref:System.Windows.Media.Animation.ClockState> animación parece no tener ningún efecto, cambie el valor de propiedad. Para obtener más información, consulte el [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Enlace de datos y animaciones animadas  
 La mayoría de las propiedades de animación puede ser enlazadas a datos o animadas; Por ejemplo, puede animar el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad de un <xref:System.Windows.Media.Animation.DoubleAnimation>. Sin embargo, debido a la manera en que funciona el sistema de temporización, enlaza datos enlazadas o animadas animaciones se comportan como otros datos o animar objetos. Para entender su comportamiento, ayuda a comprender el significado de aplicar una animación a una propiedad.  
  
 Consulte el ejemplo en la sección anterior que mostraba cómo animar el <xref:System.Windows.UIElement.Opacity%2A> de un rectángulo. Cuando se carga el rectángulo en el ejemplo anterior, el desencadenador de eventos se aplica el <xref:System.Windows.Media.Animation.Storyboard>. El sistema de temporización crea una copia de la <xref:System.Windows.Media.Animation.Storyboard> y su animación. Estas copias se inmovilizan (hacen de solo lectura) y <xref:System.Windows.Media.Animation.Clock> se crean objetos de ellos. Estos relojes hacen el trabajo real de la animación de las propiedades de destino.  
  
 El sistema de temporización crea un reloj para la <xref:System.Windows.Media.Animation.DoubleAnimation> y lo aplica al objeto y la propiedad especificada por el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> de la <xref:System.Windows.Media.Animation.DoubleAnimation>. En este caso, el sistema de control de tiempo aplica el reloj para la <xref:System.Windows.UIElement.Opacity%2A> propiedad del objeto que se denomina "MyRectangle."  
  
 Aunque también se crea un reloj para la <xref:System.Windows.Media.Animation.Storyboard>, el reloj no se aplica a todas las propiedades. Su propósito es controlar su reloj secundario, el reloj que se crea para la <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Para que una animación reflejar los cambios de animación o el enlace de datos, debe regenerarse su reloj. Los relojes no se regeneran automáticamente. Para que una animación refleje los cambios, volver a aplicar su guión gráfico mediante una <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método. Al usar cualquiera de estos métodos, se reinicia la animación. En el código, puede utilizar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> volver a su posición anterior método para desplazar el guión gráfico.  
  
 Para un ejemplo de los datos enlazados de animación, vea [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011).                  Para obtener más información acerca de cómo funciona el sistema de animación y temporización, vea [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Otras maneras de animar  
 Los ejemplos de este tema muestran cómo animar mediante guiones gráficos. Cuando se utiliza código, puede animar de otras maneras. Para obtener más información, consulte el [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Ejemplos de animación  
 Los ejemplos siguientes pueden ayudarle a empezar a agregar animación a sus aplicaciones.  
  
-   [Desde, para y ejemplo de valores de destino de animación](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Muestra valores diferentes From/To/By.  
  
-   [Ejemplo de comportamiento de tiempo de animación](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Muestra las distintas maneras en que puede controlar el comportamiento de tiempo de una animación. Este ejemplo también muestra cómo enlaza a datos el valor de destino de una animación.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Información general del sistema de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Describe cómo se utiliza el sistema de temporización la <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> clases que le permiten crear animaciones.|  
|[Animación sugerencias y trucos](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Muestra sugerencias útiles para solucionar los problemas de animaciones, tales como el rendimiento.|  
|[Información general sobre animaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Describe cómo extender el sistema de animación con fotogramas clave, las clases de animación o las devoluciones de llamada por fotograma.|  
|Información general sobre animaciones From/To/By|Describe cómo crear una animación que realiza la transición entre dos valores.|  
|[Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Describe cómo crear una animación con varios valores de destino, incluida la capacidad para controlar el método de interpolación.|  
|[Funciones de aceleración](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Explica cómo aplicar fórmulas matemáticas a las animaciones para obtener un comportamiento realista, como rebote.|  
|[Información general sobre animaciones de ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Describe cómo mover o girar un objeto a lo largo de una trayectoria compleja.|  
|[Información general de las técnicas de animación de propiedad](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Describe las animaciones de propiedad con guiones gráficos, animaciones locales, relojes y animaciones por fotograma.|  
|[Información general de guiones gráficos](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Describe cómo usar guiones gráficos con varias escalas de tiempo para crear animaciones complejas.|  
|[Información general sobre comportamientos de temporización](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Describe el <xref:System.Windows.Media.Animation.Timeline> tipos y propiedades utilizadas en las animaciones.|  
|[Información general sobre eventos de temporización](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Describe los eventos disponibles en la <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> objetos para ejecutar código en los puntos de la escala de tiempo, como iniciar, pausar, reanudar, omitir o detener.|  
|[Temas de procedimientos](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Contiene ejemplos de código para usar animaciones y escalas de tiempo en la aplicación.|  
|[Temas de procedimientos de relojes](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Contiene ejemplos de código para usar el <xref:System.Windows.Media.Animation.Clock> objeto de la aplicación.|  
|[Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de fotogramas clave en la aplicación.|  
|[Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de trayectoria en la aplicación.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>