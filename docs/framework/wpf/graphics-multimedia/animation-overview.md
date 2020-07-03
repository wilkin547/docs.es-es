---
title: Información general sobre animaciones
description: Haga que una atractiva interfaz de usuario sea aún más espectacular con transiciones de pantalla espectaculares o indicaciones visuales intensas en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: d761be0c95fb8aa7eb39cb26b57979185226b8fb
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853859"
---
# <a name="animation-overview"></a>Información general sobre animaciones

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un conjunto eficaz de características de gráficos y diseño que permite crear interfaces de usuario y documentos atractivos. Las animaciones pueden hacer que una interfaz de usuario sea más vistosa y práctica. Simplemente animando un color de fondo o aplicando una animación <xref:System.Windows.Media.Transform> , puede crear transiciones de pantalla espectaculares o proporcionar indicaciones visuales útiles.

Esta información general proporciona una introducción a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animación y al sistema de control de tiempo. Se centra en la animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos mediante guiones gráficos.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Introducción a las animaciones

Una animación es una ilusión que se crea mediante el cambio rápido entre una serie de imágenes, cada una de las cuales es ligeramente diferente de la anterior. El cerebro percibe el grupo de imágenes como una sola escena cambiante. En las películas, este efecto se obtiene mediante el uso de cámaras que graban muchas fotografías, o fotogramas, cada segundo. Cuando un proyector reproduce estos fotogramas, los espectadores ven una imagen en movimiento.

La animación en un equipo es similar. Por ejemplo, un programa que hace que un dibujo de un rectángulo se desvanezca hasta desaparecer de la vista podría funcionar de la siguiente manera.

- El programa crea un temporizador.

- El programa comprueba el temporizador en los intervalos establecidos para ver cuánto tiempo ha transcurrido.

- Cada vez que el programa comprueba el temporizador, calcula el valor de opacidad actual del rectángulo en función del tiempo que ha transcurrido.

- Después, el programa actualiza el rectángulo con el nuevo valor y lo redibuja.

Antes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , los desarrolladores de Microsoft Windows tenían que crear y administrar sus propios sistemas de control de tiempo o usar bibliotecas personalizadas especiales. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]incluye un sistema de control de tiempo eficaz que se expone a través del código administrado y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que está profundamente integrado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] marco. La animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] facilita la animación de controles y otros objetos gráficos.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controla de forma eficiente todo el trabajo de administración del sistema de control de tiempo y de actualización de la pantalla que se produce en segundo plano. Proporciona clases de control de tiempo que permiten centrarse en los efectos que se desea crear, en lugar de la mecánica para lograr esos efectos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también facilita la creación de sus propias animaciones exponiendo clases base de animación de las que se pueden heredar sus clases, para generar animaciones personalizadas. Estas animaciones personalizadas se benefician de la mayoría de las ventajas de rendimiento de las clases de animación estándar.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Sistema de animación de propiedades de WPF

Si comprende algunos conceptos importantes sobre el sistema de control de tiempo, las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animaciones pueden ser más fáciles de usar. Lo más importante es que, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , Anime objetos aplicando animación a sus propiedades individuales. Por ejemplo, para aumentar el tamaño de un elemento de marco, se animan sus <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> propiedades y. Para hacer que un objeto se atenúe desde la vista, se anima su <xref:System.Windows.UIElement.Opacity%2A> propiedad.

Para tener funcionalidad de animación, una propiedad debe cumplir los tres requisitos siguientes:

- Debe ser una propiedad de dependencia.

- Debe pertenecer a una clase que hereda de <xref:System.Windows.DependencyObject> e implementa la <xref:System.Windows.Media.Animation.IAnimatable> interfaz.

- Debe haber un tipo de animación compatible disponible. (Si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona uno, puede crear el suyo propio. Vea la [información general sobre animaciones personalizadas](custom-animations-overview.md)).

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]contiene muchos objetos que tienen <xref:System.Windows.Media.Animation.IAnimatable> propiedades. Los controles como <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.TabControl> , y también <xref:System.Windows.Controls.Panel> los <xref:System.Windows.Shapes.Shape> objetos y heredan de <xref:System.Windows.DependencyObject> . La mayoría de sus propiedades son propiedades de dependencia.

Las animaciones pueden usarse casi en cualquier parte, lo que incluye estilos y plantillas de control. Las animaciones no tienen que ser visuales; puede animar objetos que no formen parte de la interfaz de usuario siempre y cuando cumplan los criterios que se describen en esta sección.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Ejemplo: Hacer que un elemento se intensifique y se atenúe hasta desaparecer

En este ejemplo se muestra cómo usar una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] animación para animar el valor de una propiedad de dependencia. Usa un <xref:System.Windows.Media.Animation.DoubleAnimation> , que es un tipo de animación que genera <xref:System.Double> valores, para animar la <xref:System.Windows.UIElement.Opacity%2A> propiedad de un <xref:System.Windows.Shapes.Rectangle> . Como resultado, el <xref:System.Windows.Shapes.Rectangle> fundido se atenúa y sale de la vista.

En la primera parte del ejemplo se crea un <xref:System.Windows.Shapes.Rectangle> elemento. En los pasos siguientes se muestra cómo crear una animación y aplicarla a la propiedad del rectángulo <xref:System.Windows.UIElement.Opacity%2A> .

A continuación se muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

A continuación se muestra cómo crear un <xref:System.Windows.Shapes.Rectangle> elemento en un <xref:System.Windows.Controls.StackPanel> en el código.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Parte 1: Crear una DoubleAnimation

Una manera de hacer que un elemento se atenúe y no está en la vista es animar su <xref:System.Windows.UIElement.Opacity%2A> propiedad. Dado que la <xref:System.Windows.UIElement.Opacity%2A> propiedad es de tipo <xref:System.Double> , necesita una animación que genere valores double. Una <xref:System.Windows.Media.Animation.DoubleAnimation> es una animación de este tipo. Un <xref:System.Windows.Media.Animation.DoubleAnimation> crea una transición entre dos valores double. Para especificar su valor inicial, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad. Para especificar su valor final, establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.

1. Un valor de opacidad de `1.0` hace que el objeto sea completamente opaco y un valor de opacidad de `0.0` hace que sea completamente invisible. Para realizar la transición de la animación desde `1.0` a `0.0` , establezca su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad en `1.0` y su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad en `0.0` . A continuación se muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    A continuación se muestra cómo crear un <xref:System.Windows.Media.Animation.DoubleAnimation> en el código.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. A continuación, debe especificar un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . La <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una animación especifica cuánto tiempo se tarda en pasar de su valor inicial a su valor de destino. A continuación se muestra cómo establecer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en cinco segundos en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    A continuación se muestra cómo establecer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> en cinco segundos en el código.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. En el código anterior se mostró una animación que realiza `1.0` la transición de a `0.0` , lo que hace que el elemento de destino se atenúe de completamente opaco a completamente invisible. Para que el elemento se atenúe hacia la vista después de desaparecer, establezca la <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad de la animación en `true` . Para que la animación se repita indefinidamente, establezca su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . A continuación se muestra cómo establecer las <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades y en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    A continuación se muestra cómo establecer las <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedades y en el código.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Parte 2: Crear un guion gráfico

Para aplicar una animación a un objeto, se crea <xref:System.Windows.Media.Animation.Storyboard> y se utiliza <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y las <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedades adjuntas para especificar el objeto y la propiedad que se va a animar.

1. Cree el <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario. A continuación se muestra cómo crear <xref:System.Windows.Media.Animation.Storyboard> en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Para crear <xref:System.Windows.Media.Animation.Storyboard> en el código, declare una <xref:System.Windows.Media.Animation.Storyboard> variable en el nivel de clase.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    A continuación, inicialice <xref:System.Windows.Media.Animation.Storyboard> y agregue la animación como su elemento secundario.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. <xref:System.Windows.Media.Animation.Storyboard>Tiene que saber dónde aplicar la animación. Utilice la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> propiedad adjunta para especificar el objeto que se va a animar. A continuación se muestra cómo establecer el nombre de destino de <xref:System.Windows.Media.Animation.DoubleAnimation> en `MyRectangle` en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    A continuación se muestra cómo establecer el nombre de destino de <xref:System.Windows.Media.Animation.DoubleAnimation> `MyRectangle` en en el código.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Utilice la <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedad adjunta para especificar la propiedad que se va a animar. A continuación se muestra cómo se configura la animación para que tenga como destino la <xref:System.Windows.UIElement.Opacity%2A> propiedad de <xref:System.Windows.Shapes.Rectangle> en XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    A continuación se muestra cómo se configura la animación para tener como destino la <xref:System.Windows.UIElement.Opacity%2A> propiedad de <xref:System.Windows.Shapes.Rectangle> en el código.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Para obtener más información sobre <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> la sintaxis y ejemplos adicionales, vea la [información general sobre los guiones gráficos](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Parte 3 (XAML): Asociar el guion gráfico a un desencadenador

La forma más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es usar un desencadenador de eventos. En esta sección se muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un desencadenador en XAML.

1. Cree un <xref:System.Windows.Media.Animation.BeginStoryboard> objeto y asocie su guion gráfico. Un <xref:System.Windows.Media.Animation.BeginStoryboard> es un tipo de <xref:System.Windows.TriggerAction> que se aplica e inicia un <xref:System.Windows.Media.Animation.Storyboard> .

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Cree un <xref:System.Windows.EventTrigger> y agregue <xref:System.Windows.Media.Animation.BeginStoryboard> a su <xref:System.Windows.EventTrigger.Actions%2A> colección. Establezca la <xref:System.Windows.EventTrigger.RoutedEvent%2A> propiedad de <xref:System.Windows.EventTrigger> en el evento enrutado en el que desea iniciar <xref:System.Windows.Media.Animation.Storyboard> . (Para obtener más información sobre los eventos enrutados, vea [información general sobre eventos enrutados](../advanced/routed-events-overview.md)).

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Agregue <xref:System.Windows.EventTrigger> a la <xref:System.Windows.FrameworkElement.Triggers%2A> colección del rectángulo.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Parte 3 (código): Asociar el guion gráfico a un controlador de eventos

La forma más fácil de aplicar e iniciar un <xref:System.Windows.Media.Animation.Storyboard> en el código es usar un controlador de eventos. En esta sección se muestra cómo asociar el <xref:System.Windows.Media.Animation.Storyboard> con un controlador de eventos en el código.

1. Regístrese para el <xref:System.Windows.FrameworkElement.Loaded> evento del rectángulo.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Declare el controlador de eventos. En el controlador de eventos, use el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método para aplicar el guion gráfico.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]

### <a name="complete-example"></a>Ejemplo completo

A continuación se muestra cómo crear un rectángulo que se intensifica y se atenúa en la vista en XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]

A continuación se muestra cómo crear un rectángulo que se intensifica y se atenúa hasta desaparecer en el código.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]

<a name="animationtypes"></a>

## <a name="animation-types"></a>Tipos de animación

Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad que toma un <xref:System.Double> , como la <xref:System.Windows.FrameworkElement.Width%2A> propiedad de un elemento, utilice una animación que genere <xref:System.Double> valores. Para animar una propiedad que toma un <xref:System.Windows.Point> , utilice una animación que genere <xref:System.Windows.Point> valores, etc. Debido al número de tipos de propiedad diferentes, hay varias clases de animación en el <xref:System.Windows.Media.Animation> espacio de nombres. Afortunadamente se rigen por una convención de nomenclatura estricta que hace que sea fácil diferenciarlas:

- \<*Type*>Animación

  Conocidas como animaciones "From/To/By" o "basic", generan una animación entre un valor inicial y de destino o agregan un valor de desplazamiento al valor inicial.

  - Para especificar un valor inicial, establezca la propiedad From de la animación.

  - Para especificar un valor final, establezca la propiedad To de la animación.

  - Para especificar un valor de desplazamiento, establezca la propiedad By de la animación.

  En los ejemplos de este tema se incluyen estas animaciones porque son las más fáciles de usar. Las animaciones From/to/by se describen en detalle en la información general de las animaciones From/to/by.

- \<*Type*>AnimationUsingKeyFrames

  Las animaciones de fotogramas clave son más eficaces que las animaciones From/To/By porque se puede especificar cualquier número de valores de destino e incluso controlar su método de interpolación. Algunos tipos solo se pueden animar con animaciones de fotogramas clave. Las animaciones de fotogramas clave se describen en detalle en [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).

- \<*Type*>AnimationUsingPath

  Las animaciones de trazado permiten usar un trazado geométrico para generar valores animados.

- \<*Type*>AnimationBase

  Clase abstracta que, cuando se implementa, anima un \<*Type*> valor. Esta clase actúa como la clase base para \<*Type*> \<*Type*> las clases Animation y AnimationUsingKeyFrames. Tiene que tratar directamente con estas clases solo si desea crear sus propias animaciones personalizadas. De lo contrario, utilice una animación \<*Type*> de animación o fotogramas clave \<*Type*> .

En la mayoría de los casos, querrá usar las \<*Type*> clases de animación, como <xref:System.Windows.Media.Animation.DoubleAnimation> y <xref:System.Windows.Media.Animation.ColorAnimation> .

En la tabla siguiente se muestran varios tipos de animación comunes y algunas propiedades con las que se usan.

|Tipo de propiedad|Animación básica correspondiente (From/To/By)|Animación de fotogramas clave correspondiente|Animación de trazado correspondiente|Ejemplo de uso|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|None|Anima el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> o un <xref:System.Windows.Media.GradientStop> .|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Anima el <xref:System.Windows.FrameworkElement.Width%2A> de un <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.FrameworkElement.Height%2A> de un <xref:System.Windows.Controls.Button> .|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> posición de un <xref:System.Windows.Media.EllipseGeometry> .|
|<xref:System.String>|None|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|None|Anima el <xref:System.Windows.Controls.TextBlock.Text%2A> de un <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.Button> .|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Las animaciones son escalas de tiempo

Todos los tipos de animación heredan de la <xref:System.Windows.Media.Animation.Timeline> clase; por lo tanto, todas las animaciones son tipos especializados de escalas de tiempo. Un <xref:System.Windows.Media.Animation.Timeline> define un segmento de tiempo. Puede especificar los *comportamientos de control de tiempo* de una escala de tiempo: su, cuántas <xref:System.Windows.Media.Animation.Timeline.Duration%2A> veces se repiten e incluso cuánto tiempo progresa.

Dado que una animación es un <xref:System.Windows.Media.Animation.Timeline> , también representa un segmento de tiempo. Una animación también calcula los valores de salida a medida que progresa a través de su segmento de tiempo especificado (o <xref:System.Windows.Media.Animation.Timeline.Duration%2A> ). A medida que la animación avanza, o se "reproduce", actualiza la propiedad a la que está asociada.

Tres propiedades de temporización usadas con frecuencia son <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> y <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> .

#### <a name="the-duration-property"></a>Propiedad Duration

Como se ha mencionado previamente, una escala de tiempo representa un segmento de tiempo. La longitud de ese segmento viene determinada por la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la escala de tiempo, que normalmente se especifica mediante un <xref:System.Windows.Duration.TimeSpan%2A> valor. Cuando una escala de tiempo llega al final de su duración, ha completado una iteración.

Una animación utiliza su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para determinar su valor actual. Si no especifica un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> valor para una animación, utilizará 1 segundo, que es el valor predeterminado.

La sintaxis siguiente muestra una versión simplificada de la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Sintaxis de atributo para la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad.

*horas* `:` *minutos* `:` *segundos*

En la tabla siguiente se muestran varias <xref:System.Windows.Duration> configuraciones y sus valores resultantes.

|Configuración|Valor resultante|
|-------------|---------------------|
|0:0:5.5|5,5 segundos.|
|0:30:5.5|30 minutos y 5,5 segundos.|
|1:30:5.5|1 hora, 30 minutos y 5,5 segundos.|

Una manera de especificar un <xref:System.Windows.Duration> en el código es usar el <xref:System.TimeSpan.FromSeconds%2A> método para crear un <xref:System.TimeSpan> y, a continuación, declarar una nueva <xref:System.Windows.Duration> estructura con esa <xref:System.TimeSpan> .

Para obtener más información sobre <xref:System.Windows.Duration> los valores y la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintaxis completa, vea la <xref:System.Windows.Duration> estructura.

#### <a name="autoreverse"></a>AutoReverse

La <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad especifica si una escala de tiempo se reproduce hacia atrás una vez que llega al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Si establece esta propiedad de animación en `true` , una animación se invierte una vez que llega al final de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> y reproduce desde su valor final a su valor inicial. De forma predeterminada, esta propiedad es `false` .

#### <a name="repeatbehavior"></a>RepeatBehavior

La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad especifica el número de veces que se reproduce una escala de tiempo. De forma predeterminada, las escalas de tiempo tienen un recuento de iteraciones `1.0` , lo que significa que se reproducen una vez y no se repiten.

Para obtener más información acerca de estas propiedades y otras, consulte la [información general sobre los comportamientos de control de tiempo](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Aplicar una animación a una propiedad

En las secciones anteriores se han descrito los distintos tipos de animaciones y sus propiedades de control de tiempo. En esta sección se muestra cómo aplicar la animación a la propiedad que se desea animar. <xref:System.Windows.Media.Animation.Storyboard>los objetos proporcionan una manera de aplicar animaciones a propiedades. Una <xref:System.Windows.Media.Animation.Storyboard> es una *escala de tiempo contenedora* que proporciona información de destino para las animaciones que contiene.

### <a name="targeting-objects-and-properties"></a>Objetos y propiedades de destino

La <xref:System.Windows.Media.Animation.Storyboard> clase proporciona las <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedades adjuntas y. Al establecer estas propiedades en una animación, se indica a la animación qué debe animar. Sin embargo, para que una animación pueda tener un objeto como destino, normalmente se debe dar un nombre al objeto.

La asignación de un nombre a un <xref:System.Windows.FrameworkElement> difiere de la asignación de un nombre a un <xref:System.Windows.Freezable> objeto. La mayoría de los controles y paneles son elementos de marco, pero los objetos gráficos más puros, como los pinceles, las transformaciones y las formas geométricas, son objetos inmovilizables. Si no está seguro de si un tipo es <xref:System.Windows.FrameworkElement> o <xref:System.Windows.Freezable> , consulte la sección jerarquía de **herencia** de su documentación de referencia.

- Para convertir un <xref:System.Windows.FrameworkElement> destino de animación, asígnele un nombre estableciendo su <xref:System.Windows.FrameworkElement.Name%2A> propiedad. En el código, también debe usar el <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el nombre del elemento con la página a la que pertenece.

- Para convertir un <xref:System.Windows.Freezable> objeto en un destino de animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , utilice la [Directiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) para asignarle un nombre. En el código, solo se usa el <xref:System.Windows.FrameworkElement.RegisterName%2A> método para registrar el objeto con la página a la que pertenece.

En las secciones siguientes se proporciona un ejemplo de asignación de nombres a un elemento en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] código y. Para obtener información más detallada sobre la asignación de nombres y destinos, vea la [información general sobre los guiones gráficos](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Aplicar e iniciar guiones gráficos

Para iniciar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , debe asociarlo con un <xref:System.Windows.EventTrigger> . Un <xref:System.Windows.EventTrigger> es un objeto que describe qué acciones se deben llevar a cabo cuando se produce un evento especificado. Una de esas acciones puede ser una <xref:System.Windows.Media.Animation.BeginStoryboard> acción, que se usa para iniciar el guion gráfico. Los desencadenadores de eventos son similares en concepto a los controladores de eventos, porque permiten especificar cómo responde una aplicación a un evento determinado. A diferencia de los controladores de eventos, los desencadenadores de eventos se pueden describir por completo en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ; no se requiere ningún otro código.

Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> en el código, puede usar un <xref:System.Windows.EventTrigger> o utilizar el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método de la <xref:System.Windows.Media.Animation.Storyboard> clase.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Control interactivo de guiones gráficos

En el ejemplo anterior se mostró cómo iniciar una <xref:System.Windows.Media.Animation.Storyboard> cuando se produce un evento. También puede controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard> después de que se inicie: puede pausar, reanudar, detener, avanzar hasta su período de relleno, buscar y quitar el <xref:System.Windows.Media.Animation.Storyboard> . Para obtener más información y un ejemplo en el que se muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Storyboard> , vea la [información general sobre los guiones gráficos](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Comportamiento tras la finalización de una animación

La <xref:System.Windows.Media.Animation.FillBehavior> propiedad especifica cómo se comporta una escala de tiempo cuando finaliza. De forma predeterminada, una escala de tiempo se inicia <xref:System.Windows.Media.Animation.ClockState.Filling> cuando finaliza. Animación que <xref:System.Windows.Media.Animation.ClockState.Filling> contiene su valor de salida final.

<xref:System.Windows.Media.Animation.DoubleAnimation>En el ejemplo anterior no finaliza porque su <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> propiedad está establecida en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . En el ejemplo siguiente se anima un rectángulo mediante el uso de una animación similar. A diferencia del ejemplo anterior, las <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedades y de esta animación se dejan en sus valores predeterminados. Por consiguiente, la animación progresa de 1 a 0 en cinco segundos y luego se detiene.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Dado <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> que no se ha cambiado de su valor predeterminado, que es <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> , la animación contiene su valor final, 0, cuando finaliza. Por lo tanto, el <xref:System.Windows.UIElement.Opacity%2A> del rectángulo permanece en 0 una vez finalizada la animación. Si establece el <xref:System.Windows.UIElement.Opacity%2A> del rectángulo en otro valor, el código parece que no tiene ningún efecto, ya que la animación todavía está afectando a la <xref:System.Windows.UIElement.Opacity%2A> propiedad.

Una manera de recuperar el control de una propiedad animada en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método y especificar null para el <xref:System.Windows.Media.Animation.AnimationTimeline> parámetro. Para obtener más información y un ejemplo, vea [establecer una propiedad después de animarla con un guion gráfico](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Tenga en cuenta que, aunque la configuración de un valor de propiedad que tiene una <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> animación o parece no tener ningún efecto, el valor de la propiedad cambia. Para obtener más información, vea [información general sobre el sistema de control de tiempo y animación](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Animaciones con enlace de datos y animaciones animadas

La mayoría de las propiedades de animación pueden estar enlazadas a datos o animarse; por ejemplo, puede animar la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad de un <xref:System.Windows.Media.Animation.DoubleAnimation> . Sin embargo, debido a la manera en que funciona el sistema de control de tiempo, las animaciones enlazadas a datos o animadas no se comportan como los demás objetos enlazados a datos o animados. Para entender su comportamiento, le será útil comprender el significado de aplicar una animación a una propiedad.

Consulte el ejemplo de la sección anterior que mostró cómo animar el <xref:System.Windows.UIElement.Opacity%2A> de un rectángulo. Cuando se carga el rectángulo en el ejemplo anterior, su desencadenador de eventos aplica <xref:System.Windows.Media.Animation.Storyboard> . El sistema de control de tiempo crea una copia de <xref:System.Windows.Media.Animation.Storyboard> y su animación. Estas copias se inmovilizan (se convierten en de solo lectura) y los <xref:System.Windows.Media.Animation.Clock> objetos se crean a partir de ellas. Estos relojes son los que realmente se encargan de animar las propiedades de destino.

El sistema de control de tiempo crea un reloj para <xref:System.Windows.Media.Animation.DoubleAnimation> y lo aplica al objeto y la propiedad especificados por <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> de <xref:System.Windows.Media.Animation.DoubleAnimation> . En este caso, el sistema de control de tiempo aplica el reloj a la <xref:System.Windows.UIElement.Opacity%2A> propiedad del objeto denominado "microrectangle".

Aunque también se crea un reloj para <xref:System.Windows.Media.Animation.Storyboard> , el reloj no se aplica a ninguna propiedad. Su finalidad es controlar su reloj secundario, el reloj que se crea para <xref:System.Windows.Media.Animation.DoubleAnimation> .

Para que una animación refleje cambios de enlace de datos o de animación, su reloj se debe regenerar. Los relojes no se regeneran automáticamente. Para que una animación refleje los cambios, vuelva a aplicar su guion gráfico mediante <xref:System.Windows.Media.Animation.BeginStoryboard> el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método o. Al usar cualquiera de estos métodos, la animación se reinicia. En el código, puede utilizar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método para volver a desplazar el guion gráfico a su posición anterior.

Para ver un ejemplo de una animación enlazada a datos, vea [ejemplo de animación de curva spline clave](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations). Para obtener más información sobre cómo funciona la animación y el sistema de control de tiempo, vea [información general sobre el sistema de control de tiempo y animación](animation-and-timing-system-overview.md).

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Otras maneras de crear animaciones

Los ejemplos de este tema muestran cómo aplicar animaciones mediante guiones gráficos. En el código se pueden aplicar animaciones de otras maneras. Para obtener más información, vea [información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Ejemplos de animaciones

Los ejemplos siguientes pueden ayudarle a familiarizarse con la forma de agregar animaciones a sus aplicaciones.

- [Ejemplo de valores de destino de animación From, To y By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)

  Muestra distintas configuraciones From/To/By.

- [Ejemplo del comportamiento del control de tiempo de la animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)

  Muestra las distintas maneras de controlar el comportamiento de control de tiempo de una animación. Este ejemplo también muestra cómo enlazar a datos el valor de destino de una animación.

<a name="related_topics"></a>

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Información general sobre sistemas de temporización y animación](animation-and-timing-system-overview.md)|Describe cómo el sistema de control de tiempo utiliza las <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> clases y, que permiten crear animaciones.|
|[Sugerencias y trucos para animaciones](animation-tips-and-tricks.md)|Enumera las sugerencias útiles para solucionar problemas con animaciones, como el rendimiento.|
|[Información general sobre animaciones personalizadas](custom-animations-overview.md)|Describe cómo extender el sistema de animación con fotogramas clave, clases de animación o devoluciones de llamada por fotograma.|
|[Información general sobre animaciones From/To/By](from-to-by-animations-overview.md)|Describe cómo crear una animación que realiza la transición entre dos valores.|
|[Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)|Describe cómo crear una animación con varios valores de destino, incluida la capacidad de controlar el método de interpolación.|
|[Funciones de aceleración](easing-functions.md)|Explica cómo aplicar fórmulas matemáticas a las animaciones para obtener un comportamiento realista, como el rebote.|
|[Información general sobre animaciones en trazados](path-animations-overview.md)|Describe cómo mover o girar un objeto a lo largo de un trazado complejo.|
|[Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)|Describe las animaciones de propiedades mediante guiones gráficos, animaciones locales, relojes y animaciones por fotograma.|
|[Información general sobre objetos Storyboard](storyboards-overview.md)|Describe cómo utilizar guiones gráficos con varias escalas de tiempo para crear animaciones complejas.|
|[Información general sobre comportamientos de control de tiempo](timing-behaviors-overview.md)|Describe los <xref:System.Windows.Media.Animation.Timeline> tipos y las propiedades que se usan en las animaciones.|
|[Información general sobre eventos de control de tiempo](timing-events-overview.md)|Describe los eventos disponibles en los <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> objetos y para ejecutar código en los puntos de la escala de tiempo, como iniciar, pausar, reanudar, omitir o detener.|
|[Temas "Cómo..."](animation-and-timing-how-to-topics.md)|Contiene ejemplos de código para usar animaciones y escalas de tiempo en una aplicación.|
|[Temas "Cómo..." de relojes](clocks-how-to-topics.md)|Contiene ejemplos de código para usar el <xref:System.Windows.Media.Animation.Clock> objeto en la aplicación.|
|[Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de fotogramas clave en una aplicación.|
|[Temas "Cómo..." de animación de trazado](path-animation-how-to-topics.md)|Contiene ejemplos de código para usar animaciones de trazado en una aplicación.|

<a name="reference"></a>

## <a name="reference"></a>Referencia

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
