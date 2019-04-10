---
title: Información general sobre animaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: 530f6cb8fbe80df3ad374f8ad0e4836be82830a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337739"
---
# <a name="animation-overview"></a>Información general sobre animaciones
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Proporciona un conjunto eficaz de gráficos y diseño de características que le permiten crear interfaces de usuario y documentos atractivos. Las animaciones pueden hacer que una interfaz de usuario sea más vistosa y práctica. Simplemente animar un color de fondo o aplicando un elemento animado <xref:System.Windows.Media.Transform>, puede crear transiciones de pantalla espectaculares o proporcionar indicaciones visuales útiles.  
  
 Esta información general proporciona una introducción a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de temporización y animación. Se centra en la animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos mediante el uso de guiones gráficos.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Introducción a las animaciones  
 Una animación es una ilusión que se crea mediante el cambio rápido entre una serie de imágenes, cada una de las cuales es ligeramente diferente de la anterior. El cerebro percibe el grupo de imágenes como una sola escena cambiante. En las películas, este efecto se obtiene mediante el uso de cámaras que graban muchas fotografías, o fotogramas, cada segundo. Cuando un proyector reproduce estos fotogramas, los espectadores ven una imagen en movimiento.  
  
 La animación en un equipo es similar. Por ejemplo, un programa que hace que un dibujo de un rectángulo se desvanezca hasta desaparecer de la vista podría funcionar de la siguiente manera.  
  
-   El programa crea un temporizador.  
  
-   El programa comprueba el temporizador en los intervalos establecidos para ver cuánto tiempo ha transcurrido.  
  
-   Cada vez que el programa comprueba el temporizador, calcula el valor de opacidad actual del rectángulo en función del tiempo que ha transcurrido.  
  
-   Después, el programa actualiza el rectángulo con el nuevo valor y lo redibuja.  
  
 Anteriores a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] los desarrolladores tenían que crear y administrar sus propios sistemas de temporización o utilizar bibliotecas personalizadas especiales. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un sistema de control de tiempo eficaz que se expone a través de código administrado y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y que está muy integrado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animación facilita la animación de controles y otros objetos gráficos.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controla todo el trabajo en segundo plano de administración de un sistema de control de tiempo y volver a dibujar la pantalla de forma eficaz. Proporciona clases de control de tiempo que permiten centrarse en los efectos que se desea crear, en lugar de la mecánica para lograr esos efectos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También resulta fácil crear sus propias animaciones exponiendo clases base de animación desde el que se pueden heredar sus clases, para generar animaciones personalizadas. Estas animaciones personalizadas se benefician de la mayoría de las ventajas de rendimiento de las clases de animación estándar.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Sistema de animación de propiedades de WPF  
 Si comprende algunos conceptos importantes sobre el sistema de temporización [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animaciones pueden ser más fáciles de usar. Más importante es que, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], objetos se animan al aplicar animaciones a sus propiedades individuales. Por ejemplo, para hacer un elemento de marco crezca, se animan sus <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades. Para hacer que un objeto se desvanezca hasta desaparecer de la vista, se anima su <xref:System.Windows.UIElement.Opacity%2A> propiedad.  
  
 Para tener funcionalidad de animación, una propiedad debe cumplir los tres requisitos siguientes:  
  
-   Debe ser una propiedad de dependencia.  
  
-   Debe pertenecer a una clase que hereda de <xref:System.Windows.DependencyObject> e implementa el <xref:System.Windows.Media.Animation.IAnimatable> interfaz.  
  
-   Debe haber un tipo de animación compatible disponible. (Si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ninguno, puede crear los suyos propios. Consulte la [información general sobre animaciones personalizadas](custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene muchos objetos que tienen <xref:System.Windows.Media.Animation.IAnimatable> propiedades. Los controles como <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.TabControl>y también <xref:System.Windows.Controls.Panel> y <xref:System.Windows.Shapes.Shape> objetos heredan de <xref:System.Windows.DependencyObject>. La mayoría de sus propiedades son propiedades de dependencia.  
  
 Las animaciones pueden usarse casi en cualquier parte, lo que incluye estilos y plantillas de control. Las animaciones no tienen que ser visuales; puede animar objetos que no formen parte de la interfaz de usuario siempre y cuando cumplan los criterios que se describen en esta sección.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Ejemplo: Realizar una transición del elemento dentro y fuera de la vista  
 En este ejemplo se muestra cómo usar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animaciones para animar el valor de una propiedad de dependencia. Usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, que es un tipo de animación que genera <xref:System.Double> valores, se va a animar el <xref:System.Windows.UIElement.Opacity%2A> propiedad de un <xref:System.Windows.Shapes.Rectangle>. Como resultado, el <xref:System.Windows.Shapes.Rectangle> desaparece.  
  
 La primera parte del ejemplo se crea un <xref:System.Windows.Shapes.Rectangle> elemento. Los pasos siguientes muestran cómo crear una animación y aplicarla al rectángulo <xref:System.Windows.UIElement.Opacity%2A> propiedad.
  
 La siguiente muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 La siguiente muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en el código.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Parte 1: Crear una DoubleAnimation  
 Una manera de hacer que un elemento fundido es animar su <xref:System.Windows.UIElement.Opacity%2A> propiedad. Dado que el <xref:System.Windows.UIElement.Opacity%2A> propiedad es de tipo <xref:System.Double>, necesita una animación que genera valores double. Un <xref:System.Windows.Media.Animation.DoubleAnimation> es una animación de este tipo. Un <xref:System.Windows.Media.Animation.DoubleAnimation> crea una transición entre dos valores double. Para especificar su valor inicial, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad. Para especificar su valor final, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.  
  
1. Un valor de opacidad de `1.0` hace que el objeto completamente opaco y un valor de opacidad de `0.0` hace que sea completamente invisible. Para realizar la transición de animación de `1.0` a `0.0` establece su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad `1.0` y su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad `0.0`. La siguiente muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     La siguiente muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2. A continuación, debe especificar un <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. El <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una animación especifica cuánto tarda en ir desde su valor inicial al valor de destino. La siguiente muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en cinco segundos en XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     La siguiente muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en cinco segundos en código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3. El código anterior mostraba una animación que realiza la transición desde `1.0` a `0.0`, lo que hace que el elemento de destino para la transición desde totalmente opaco a ser completamente invisible. Para que el elemento aparezca progresivamente en la vista antes de desaparecer, establezca el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad de la animación a `true`. Para que la animación se repita indefinidamente, establezca su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. La siguiente muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades en XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     La siguiente muestra cómo establecer el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Parte 2: Crear un guion gráfico  
 Para aplicar una animación a un objeto, se crea un <xref:System.Windows.Media.Animation.Storyboard> y usar el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> adjunta propiedades para especificar el objeto y propiedad que se va a animar.  
  
1. Crear el <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario. La siguiente muestra cómo se crea el <xref:System.Windows.Media.Animation.Storyboard> en XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     Para crear el <xref:System.Windows.Media.Animation.Storyboard> en el código, declare un <xref:System.Windows.Media.Animation.Storyboard> variable en el nivel de clase.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     A continuación, inicialice el <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2. El <xref:System.Windows.Media.Animation.Storyboard> tiene que saber dónde aplicar la animación. Use el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> propiedad adjunta para especificar el objeto que se va a animar. La continuación muestra cómo establecer el nombre de destino de la <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` en XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     La continuación muestra cómo establecer el nombre de destino de la <xref:System.Windows.Media.Animation.DoubleAnimation> a `MyRectangle` en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3. Use el <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedad adjunta para especificar la propiedad que se va a animar. La siguiente muestra cómo se configura la animación al destino la <xref:System.Windows.UIElement.Opacity%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> en XAML.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     La continuación muestra cómo se configura la animación al destino la <xref:System.Windows.UIElement.Opacity%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> en el código.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> sintaxis y ejemplos adicionales, vea el [Storyboards Overview](storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML): Asociar el guion gráfico a un desencadenador  
 La manera más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste en usar un desencadenador de eventos. En esta sección se muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un desencadenador en XAML.  
  
1. Crear un <xref:System.Windows.Media.Animation.BeginStoryboard> de objetos y asóciele su guion gráfico. Un <xref:System.Windows.Media.Animation.BeginStoryboard> es un tipo de <xref:System.Windows.TriggerAction> que aplica e inicia un <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2. Crear un <xref:System.Windows.EventTrigger> y agregue el <xref:System.Windows.Media.Animation.BeginStoryboard> a su <xref:System.Windows.EventTrigger.Actions%2A> colección. Establecer el <xref:System.Windows.EventTrigger.RoutedEvent%2A> propiedad de la <xref:System.Windows.EventTrigger> al evento enrutado que se desea iniciar la <xref:System.Windows.Media.Animation.Storyboard>. (Para obtener más información sobre los eventos enrutados, vea el [Routed Events Overview](../advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3. Agregar el <xref:System.Windows.EventTrigger> a la <xref:System.Windows.FrameworkElement.Triggers%2A> colección del rectángulo.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (código): Asociar el guion gráfico a un controlador de eventos  
 La manera más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en código es usar un controlador de eventos. En esta sección se muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un controlador de eventos en el código.  
  
1. Registrarse para el <xref:System.Windows.FrameworkElement.Loaded> eventos del rectángulo.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2. Declare el controlador de eventos. En el controlador de eventos, use el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método para aplicar el guión gráfico.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Ejemplo completo  
 La continuación muestra cómo crear un rectángulo que desaparece en XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 A continuación se muestra cómo crear un rectángulo que se intensifica y se atenúa hasta desaparecer en el código.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Tipos de animación  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad que acepta un <xref:System.Double>, como el <xref:System.Windows.FrameworkElement.Width%2A> propiedad de un elemento, use una animación que genera <xref:System.Double> valores. Para animar una propiedad que acepta un <xref:System.Windows.Point>, usa una animación que genera <xref:System.Windows.Point> valores y así sucesivamente. Debido al número de distintos tipos de propiedades, hay varias clases de animación en el <xref:System.Windows.Media.Animation> espacio de nombres. Afortunadamente se rigen por una convención de nomenclatura estricta que hace que sea fácil diferenciarlas:  
  
-   \<*Tipo*> animación  
  
     Conocidas como animaciones "From/To/By" o "basic", generan una animación entre un valor inicial y de destino o agregan un valor de desplazamiento al valor inicial.  
  
    -   Para especificar un valor inicial, establezca la propiedad From de la animación.  
  
    -   Para especificar un valor final, establezca la propiedad To de la animación.  
  
    -   Para especificar un valor de desplazamiento, establezca la propiedad By de la animación.  
  
     En los ejemplos de este tema se incluyen estas animaciones porque son las más fáciles de usar. Animaciones From/To/By se describen en detalle en la información general sobre animaciones From.  
  
-   \<*Type*>AnimationUsingKeyFrames  
  
     Las animaciones de fotogramas clave son más eficaces que las animaciones From/To/By porque se puede especificar cualquier número de valores de destino e incluso controlar su método de interpolación. Algunos tipos solo se pueden animar con animaciones de fotogramas clave. Animaciones de fotogramas clave se describen en detalle en la [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
-   \<*Type*>AnimationUsingPath  
  
     Las animaciones de trazado permiten usar un trazado geométrico para generar valores animados.  
  
-   \<*Tipo*> AnimationBase  
  
     Clase abstracta que, cuando se implementa, anima un \< *tipo*> valor. Esta clase actúa como clase base para \< *tipo*> animación y \< *tipo*> AnimationUsingKeyFrames clases. Tiene que tratar directamente con estas clases solo si desea crear sus propias animaciones personalizadas. En caso contrario, use un \< *tipo*> Animation o KeyFrame\<*tipo*> animación.  
  
 En la mayoría de los casos, desea utilizar el \< *tipo*> clases de animación, como <xref:System.Windows.Media.Animation.DoubleAnimation> y <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 En la tabla siguiente se muestran varios tipos de animación comunes y algunas propiedades con las que se usan.  
  
|Tipo de propiedad|Animación básica correspondiente (From/To/By)|Animación de fotogramas clave correspondiente|Animación de trazado correspondiente|Ejemplo de uso|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Ninguna|Animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> o <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animar el <xref:System.Windows.FrameworkElement.Width%2A> de un <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.FrameworkElement.Height%2A> de un <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animar el <xref:System.Windows.Media.EllipseGeometry.Center%2A> posición de un <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Ninguna|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Ninguna|Animar el <xref:System.Windows.Controls.TextBlock.Text%2A> de un <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Las animaciones son escalas de tiempo  
 Todos los tipos de animaciones heredan de la <xref:System.Windows.Media.Animation.Timeline> clase; por lo tanto, todas las animaciones son tipos especializados de escalas de tiempo. Un <xref:System.Windows.Media.Animation.Timeline> define un segmento de tiempo. Puede especificar el *comportamientos de temporización* de escala de tiempo: su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, cuántas veces se repite e incluso cómo rapidez pasa el tiempo para ella.  
  
 Dado que una animación es un <xref:System.Windows.Media.Animation.Timeline>, también representa un segmento de tiempo. Una animación también calcula los valores de salida de medida que avanza por su segmento de tiempo especificado (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). A medida que la animación avanza, o se "reproduce", actualiza la propiedad a la que está asociada.  
  
 Tres propiedades de sincronización usados con frecuencia son <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Propiedad Duration  
 Como se ha mencionado previamente, un objeto Timeline representa un segmento de tiempo. La longitud de ese segmento viene determinada por la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la escala de tiempo, que normalmente se especifica mediante el uso de un <xref:System.Windows.Duration.TimeSpan%2A> valor. Cuando una escala de tiempo llega al final de su duración, ha completado una iteración.  
  
 Una animación usa su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para determinar su valor actual. Si no especifica un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valor para una animación, se usa 1 segundo, que es el valor predeterminado.  
  
 La sintaxis siguiente muestra una versión simplificada de la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis para el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad.  
  
*horas* `:` *minutos* `:` *segundos*
  
 En la tabla siguiente se muestra varias <xref:System.Windows.Duration> configuraciones y sus valores resultantes.  
  
|Parámetro|Valor resultante|  
|-------------|---------------------|  
|0:0:5.5|5,5 segundos.|  
|0:30:5.5|30 minutos y 5,5 segundos.|  
|1:30:5.5|1 hora, 30 minutos y 5,5 segundos.|  
  
 Una manera de especificar un <xref:System.Windows.Duration> en código es usar el <xref:System.TimeSpan.FromSeconds%2A> método para crear un <xref:System.TimeSpan>, a continuación, declarar un nuevo <xref:System.Windows.Duration> estructura está utilizando <xref:System.TimeSpan>.  
  
 Para obtener más información acerca de <xref:System.Windows.Duration> valores y la completa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintaxis, vea el <xref:System.Windows.Duration> estructura.  
  
#### <a name="autoreverse"></a>AutoReverse  
 El <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad especifica si una escala de tiempo se reproduce con versiones anteriores una vez que llega al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Si establece esta propiedad de animación en `true`, la animación se invierte después de llegar al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, reproduce desde su valor final a su valor inicial. De forma predeterminada, esta propiedad es `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 El <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad especifica cuántas veces se reproduce una escala de tiempo. De forma predeterminada, las escalas de tiempo tienen una iteración de `1.0`, lo que significa que se reproducen una vez y no se repiten en absoluto.  
  
 Para obtener más información acerca de estas propiedades y otras, vea el [información general sobre comportamientos de temporización](timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Aplicar una animación a una propiedad  
 En las secciones anteriores se han descrito los distintos tipos de animaciones y sus propiedades de control de tiempo. En esta sección se muestra cómo aplicar la animación a la propiedad que se desea animar. <xref:System.Windows.Media.Animation.Storyboard> los objetos proporcionan una manera de aplicar animaciones a propiedades. Un <xref:System.Windows.Media.Animation.Storyboard> es un *escala de tiempo contenedora* que proporciona información de destino para las animaciones que contiene.  
  
### <a name="targeting-objects-and-properties"></a>Objetos y propiedades de destino  
 El <xref:System.Windows.Media.Animation.Storyboard> clase proporciona el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedades adjuntas. Al establecer estas propiedades en una animación, se indica a la animación qué debe animar. Sin embargo, para que una animación pueda tener un objeto como destino, normalmente se debe dar un nombre al objeto.  
  
 Asignar un nombre a un <xref:System.Windows.FrameworkElement> difiere de asignar un nombre a un <xref:System.Windows.Freezable> objeto. La mayoría de los controles y paneles son elementos de marco, pero los objetos gráficos más puros, como los pinceles, las transformaciones y las formas geométricas, son objetos inmovilizables. Si no estás seguro de si un tipo es un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.Freezable>, hacen referencia a la **jerarquía de herencia** sección de su documentación de referencia.  
  
-   Para realizar un <xref:System.Windows.FrameworkElement> un destino de animación, darle un nombre estableciendo su <xref:System.Windows.FrameworkElement.Name%2A> propiedad. En el código, también debe usar el <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el nombre del elemento con la página a la que pertenece.  
  
-   Para realizar un <xref:System.Windows.Freezable> objeto un destino de animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usa el [x: Name Directive](../../xaml-services/x-name-directive.md) para asignarle un nombre. En el código, use simplemente el <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el objeto con la página a la que pertenece.  
  
 Las secciones siguientes proporcionan un ejemplo de cómo asignar un elemento en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el código. Para obtener información más detallada sobre la nomenclatura y establecimiento de destinos, consulte el [Storyboards Overview](storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Aplicar e iniciar guiones gráficos  
 Para iniciar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], asóciela con un <xref:System.Windows.EventTrigger>. Un <xref:System.Windows.EventTrigger> es un objeto que describe qué acciones debe realizar cuando se produce un evento especificado. Una de esas acciones puede ser un <xref:System.Windows.Media.Animation.BeginStoryboard> acción, que se utiliza para iniciar el guion gráfico. Los desencadenadores de eventos son similares en concepto a los controladores de eventos, porque permiten especificar cómo responde una aplicación a un evento determinado. A diferencia de los controladores de eventos, los desencadenadores de eventos se pueden describir totalmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; no se requiere ningún otro código.  
  
 Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> en código, puede usar un <xref:System.Windows.EventTrigger> o usar el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método de la <xref:System.Windows.Media.Animation.Storyboard> clase.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Control interactivo de guiones gráficos  
 El ejemplo anterior mostró cómo iniciar un <xref:System.Windows.Media.Animation.Storyboard> cuando se produce un evento. Puede controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse: puede pausar, reanudar, detener, hacer que avance hasta su período de relleno, buscar y quitar el <xref:System.Windows.Media.Animation.Storyboard>. Para obtener más información y un ejemplo que muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard>, consulte el [Storyboards Overview](storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Comportamiento tras la finalización de una animación  
 El <xref:System.Windows.Media.Animation.FillBehavior> propiedad especifica cómo se comporta una escala de tiempo cuando finaliza. De forma predeterminada, se inicia una escala de tiempo <xref:System.Windows.Media.Animation.ClockState.Filling> cuando termina. Una animación que se <xref:System.Windows.Media.Animation.ClockState.Filling> mantiene su valor de salida final.  
  
 El <xref:System.Windows.Media.Animation.DoubleAnimation> en el ejemplo anterior no finaliza porque su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad está establecida en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. En el ejemplo siguiente se anima un rectángulo mediante el uso de una animación similar. A diferencia del ejemplo anterior, el <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> y <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> las propiedades de esta animación se dejan en sus valores predeterminados. Por consiguiente, la animación progresa de 1 a 0 en cinco segundos y luego se detiene.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Dado que su <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> no se ha cambiado respecto a su valor predeterminado, que es <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, la animación retiene el valor final, 0, cuando finaliza. Por lo tanto, el <xref:System.Windows.UIElement.Opacity%2A> de la permanece rectángulo en 0 después de la animación finaliza. Si establece la <xref:System.Windows.UIElement.Opacity%2A> del rectángulo en otro valor, el código parece que no tienen ningún efecto, porque la animación todavía influye la <xref:System.Windows.UIElement.Opacity%2A> propiedad.  
  
 Una manera de recobrar el control de una propiedad animada en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método y especifique null para el <xref:System.Windows.Media.Animation.AnimationTimeline> parámetro. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guión gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Tenga en cuenta que, aunque se establece un valor de propiedad que tiene un <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> animación parece no tener ningún efecto, cambie el valor de propiedad. Para obtener más información, consulte el [Animation and Timing System Overview](animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Animaciones con enlace de datos y animaciones animadas  
 La mayoría de las propiedades de animación pueden ser datos enlazados o animadas; Por ejemplo, puede animar el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad de un <xref:System.Windows.Media.Animation.DoubleAnimation>. Sin embargo, debido a la manera en que funciona el sistema de control de tiempo, las animaciones enlazadas a datos o animadas no se comportan como los demás objetos enlazados a datos o animados. Para entender su comportamiento, le será útil comprender el significado de aplicar una animación a una propiedad.  
  
 Consulte el ejemplo en la sección anterior que mostraba cómo animar el <xref:System.Windows.UIElement.Opacity%2A> de un rectángulo. Cuando se carga el rectángulo en el ejemplo anterior, su desencadenador de eventos se aplica el <xref:System.Windows.Media.Animation.Storyboard>. El sistema de temporización crea una copia de la <xref:System.Windows.Media.Animation.Storyboard> y su animación. Estas copias se inmovilizan (sólo lectura) y <xref:System.Windows.Media.Animation.Clock> se crean objetos de ellos. Estos relojes son los que realmente se encargan de animar las propiedades de destino.  
  
 El sistema de temporización crea un reloj para la <xref:System.Windows.Media.Animation.DoubleAnimation> y lo aplica al objeto y propiedad que se especifica mediante el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> de la <xref:System.Windows.Media.Animation.DoubleAnimation>. En este caso, el sistema de control de tiempo aplica el reloj para la <xref:System.Windows.UIElement.Opacity%2A> propiedad del objeto denominado "MyRectangle".  
  
 Aunque también se crea un reloj para la <xref:System.Windows.Media.Animation.Storyboard>, el reloj no se aplica a todas las propiedades. Su propósito es controlar su reloj secundario, el reloj que se crea para el <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Para que una animación refleje cambios de enlace de datos o de animación, su reloj se debe regenerar. Los relojes no se regeneran automáticamente. Para que una animación refleje los cambios, vuelva a aplicar su guion gráfico mediante el uso de un <xref:System.Windows.Media.Animation.BeginStoryboard> o <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método. Al usar cualquiera de estos métodos, la animación se reinicia. En el código, puede usar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> hacer una copia de método para el guion gráfico a su posición anterior.  
  
 Para un ejemplo de datos de una animación enlazada, consulte [ejemplo Key Spline Animation](https://go.microsoft.com/fwlink/?LinkID=160011). Para obtener más información acerca de cómo funciona el sistema de animación y temporización, vea [Animation and Timing System Overview](animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Otras maneras de crear animaciones  
 Los ejemplos de este tema muestran cómo aplicar animaciones mediante guiones gráficos. En el código se pueden aplicar animaciones de otras maneras. Para obtener más información, consulte el [técnicas de animación de información general sobre propiedades](property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Ejemplos de animaciones  
 Los ejemplos siguientes pueden ayudarle a familiarizarse con la forma de agregar animaciones a sus aplicaciones.  
  
-   [FROM, To y por el ejemplo de valores de destino de animación](https://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Muestra distintas configuraciones From/To/By.  
  
-   [Ejemplo de comportamiento de control de tiempo de animación](https://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Muestra las distintas maneras de controlar el comportamiento de control de tiempo de una animación. Este ejemplo también muestra cómo enlazar a datos el valor de destino de una animación.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md)|Describe cómo se utiliza el sistema de temporización el <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> clases, que le permiten crear animaciones.|  
|[Sugerencias y trucos para animaciones](animation-tips-and-tricks.md)|Enumera las sugerencias útiles para solucionar problemas con animaciones, como el rendimiento.|  
|[Información general sobre animaciones personalizadas](custom-animations-overview.md)|Describe cómo extender el sistema de animación con fotogramas clave, clases de animación o devoluciones de llamada por fotograma.|  
|Información general sobre animaciones From/To/By|Describe cómo crear una animación que realiza la transición entre dos valores.|  
|[Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)|Describe cómo crear una animación con varios valores de destino, incluida la capacidad de controlar el método de interpolación.|  
|[Funciones de aceleración](easing-functions.md)|Explica cómo aplicar fórmulas matemáticas a las animaciones para obtener un comportamiento realista, como el rebote.|  
|[Información general sobre animaciones en trazados](path-animations-overview.md)|Describe cómo mover o girar un objeto a lo largo de un trazado complejo.|  
|[Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)|Describe las animaciones de propiedades mediante guiones gráficos, animaciones locales, relojes y animaciones por fotograma.|  
|[Información general sobre objetos Storyboard](storyboards-overview.md)|Describe cómo utilizar guiones gráficos con varias escalas de tiempo para crear animaciones complejas.|  
|[Información general sobre comportamientos de control de tiempo](timing-behaviors-overview.md)|Describe el <xref:System.Windows.Media.Animation.Timeline> tipos y propiedades que se usan en animaciones.|  
|[Información general sobre eventos de control de tiempo](timing-events-overview.md)|Describe los eventos disponibles en el <xref:System.Windows.Media.Animation.Timeline> y <xref:System.Windows.Media.Animation.Clock> objetos para ejecutar código en los puntos de la escala de tiempo, como iniciar, pausar, reanudar, omitir o detener.|  
|[Temas "Cómo..."](animation-and-timing-how-to-topics.md)|Contiene ejemplos de código para usar animaciones y escalas de tiempo en una aplicación.|  
|[Temas "Cómo..." de relojes](clocks-how-to-topics.md)|Contiene ejemplos de código para usar la <xref:System.Windows.Media.Animation.Clock> objeto en la aplicación.|  
|[Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de fotogramas clave en una aplicación.|  
|[Temas "Cómo..." de animación de trazado](path-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de trazado en una aplicación.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
