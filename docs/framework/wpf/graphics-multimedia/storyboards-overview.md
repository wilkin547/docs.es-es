---
title: Información general sobre objetos Storyboard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 4d5a5ee3f1fcbd09fad9e25773d0e508209e1492
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855842"
---
# <a name="storyboards-overview"></a>Información general sobre objetos Storyboard

En este tema se muestra cómo <xref:System.Windows.Media.Animation.Storyboard> utilizar objetos para organizar y aplicar animaciones. Describe cómo manipular <xref:System.Windows.Media.Animation.Storyboard> objetos de forma interactiva y describe la sintaxis de destinatarios de propiedades indirectas.

## <a name="prerequisites"></a>Requisitos previos

Para entender este tema, debe estar familiarizado con los distintos tipos de animaciones y sus características básicas. Para obtener una introducción a la animación, consulte [Información general sobre animaciones](animation-overview.md). También debe saber utilizar las propiedades asociadas. Para obtener más información sobre las propiedades adjuntas, consulte [Información general sobre propiedades asociadas](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>¿Qué es un guión gráfico?

Las animaciones no son el único tipo útil de escala de tiempo. Se proporcionan otras clases de escalas de tiempo para ayudarle a organizar conjuntos de escalas de tiempo y para aplicar las escalas de tiempo a las propiedades. Las escalas de tiempo de <xref:System.Windows.Media.Animation.TimelineGroup> contenedor se derivan <xref:System.Windows.Media.Animation.ParallelTimeline> de <xref:System.Windows.Media.Animation.Storyboard>la clase e incluyen y.

Un <xref:System.Windows.Media.Animation.Storyboard> es un tipo de escala de tiempo de contenedor que proporciona información de destino para las escalas de tiempo que contiene. Un guión gráfico puede contener cualquier tipo <xref:System.Windows.Media.Animation.Timeline>de, incluidas otras escalas de tiempo y animaciones de contenedor. <xref:System.Windows.Media.Animation.Storyboard>los objetos permiten combinar las escalas de tiempo que afectan a una variedad de objetos y propiedades en un único árbol de escala de tiempo, lo que facilita la organización y el control de los comportamientos complejos de temporización. Por ejemplo, supongamos que desea un botón que haga estas tres cosas.

- Aumentar de tamaño y cambiar de color cuando el usuario selecciona el botón.

- Disminuir de tamaño y volver a su tamaño original cuando se hace clic en él.

- Disminuir de tamaño y desvanecerse con un fundido al 50 % de opacidad al deshabilitarse.

En este caso, tenemos varios conjuntos de animaciones que se aplican al mismo objeto, y hay que reproducirlas en distintos momentos, según cuál sea el estado del botón. <xref:System.Windows.Media.Animation.Storyboard>los objetos permiten organizar animaciones y aplicarlas en grupos a uno o varios objetos.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>¿Dónde se puede utilizar un guión gráfico?

Se puede utilizar para animar propiedades de dependencia de clases que se pueden animar (para obtener más información sobre lo que hace que una clase se pueda animar, vea [información general sobre animaciones).](animation-overview.md) <xref:System.Windows.Media.Animation.Storyboard> Sin embargo, dado que el guion gráfico es una característica de nivel <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> de marco, el objeto debe pertenecer a <xref:System.Windows.FrameworkContentElement>la de o.

Por ejemplo, puede usar <xref:System.Windows.Media.Animation.Storyboard> para hacer lo siguiente:

- Animar <xref:System.Windows.Media.SolidColorBrush> un (elemento que no es de marco) que pinta el fondo de un botón ( <xref:System.Windows.FrameworkElement>un tipo de),

- Anima un <xref:System.Windows.Media.SolidColorBrush> (elemento que no es de marco) que pinta el relleno <xref:System.Windows.Media.GeometryDrawing> de un (elemento que no es de marco <xref:System.Windows.Controls.Image> )<xref:System.Windows.FrameworkElement>mostrado mediante un ().

- En el código, Anime <xref:System.Windows.Media.SolidColorBrush> un declarado por una clase que también contenga un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Media.SolidColorBrush> si el nombre de registró con ese <xref:System.Windows.FrameworkElement>.

Sin embargo, no se puede usar <xref:System.Windows.Media.Animation.Storyboard> para animar <xref:System.Windows.Media.SolidColorBrush> un que no haya <xref:System.Windows.FrameworkElement> registrado su nombre con o <xref:System.Windows.FrameworkContentElement>, o no se haya utilizado para establecer una propiedad de <xref:System.Windows.FrameworkElement> un <xref:System.Windows.FrameworkContentElement>o.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Cómo aplicar animaciones mediante un guión gráfico

Para usar un <xref:System.Windows.Media.Animation.Storyboard> objeto para organizar y aplicar animaciones, agregue las animaciones como escalas <xref:System.Windows.Media.Animation.Storyboard>de tiempo secundarias de. La <xref:System.Windows.Media.Animation.Storyboard> clase proporciona las <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> propiedades <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> adjuntas y. Se establecen estas propiedades de una animación para especificar su objeto y propiedad de destino.

Para aplicar animaciones a sus destinos, comienza <xref:System.Windows.Media.Animation.Storyboard> con una acción de desencadenador o un método. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se utiliza un <xref:System.Windows.Media.Animation.BeginStoryboard> objeto con <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>o <xref:System.Windows.DataTrigger>. En el código, también puede utilizar el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método.

En la tabla siguiente se muestran los distintos lugares <xref:System.Windows.Media.Animation.Storyboard> en los que se admite cada técnica de Inicio: por instancia, estilo, plantilla de control y plantilla de datos. "Por instancia" se refiere a la técnica de aplicar directamente una animación o guión gráfico a las instancias de un objeto, en lugar de en un estilo, una plantilla de control o una plantilla de datos.

|El guión gráfico se comienza utilizando...|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>y una propiedad<xref:System.Windows.Trigger>|Sin|Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.DataTrigger>|Sin|Sí|Sí|Sí|[Cómo: Desencadenar una animación cuando cambien los datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|Método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sí|No|No|Sin|[Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)|

<xref:System.Windows.Media.Animation.Storyboard> En el ejemplo siguiente se usa para animar el <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A> de un elemento <xref:System.Windows.Media.SolidColorBrush.Color%2A> y el <xref:System.Windows.Media.SolidColorBrush> de un que se <xref:System.Windows.Shapes.Rectangle>usa para pintar ese.

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

En las secciones siguientes se <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> describen <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> los y las propiedades adjuntas con más detalle.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Establecer como destino elementos de marco, elementos de contenido de marco y elementos inmovilizables

En la sección anterior se menciona que, para que una animación encuentre su destino, debe conocer el nombre del mismo y la propiedad que debe animar. Especificar la propiedad que se va a animar es sencillo: <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> simplemente se establece con el nombre de la propiedad que se va a animar.  El nombre del objeto cuya propiedad se desea animar se especifica estableciendo la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> propiedad en la animación.

Para que <xref:System.Windows.Setter.TargetName%2A> la propiedad funcione, el objeto de destino debe tener un nombre. Asignar <xref:System.Windows.FrameworkElement> un nombre a un <xref:System.Windows.FrameworkContentElement> o a en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es diferente de asignar un nombre a un <xref:System.Windows.Freezable> objeto.

Los elementos de marco son las clases que heredan de la <xref:System.Windows.FrameworkElement> clase. Entre los ejemplos de elementos <xref:System.Windows.Window>de <xref:System.Windows.Controls.DockPanel>marco se incluyen <xref:System.Windows.Shapes.Rectangle>,, <xref:System.Windows.Controls.Button>y. En esencia, todas las ventanas, los paneles y los controles son elementos. Los elementos de contenido de marco son las clases que <xref:System.Windows.FrameworkContentElement> heredan de la clase. Entre los ejemplos de elementos de <xref:System.Windows.Documents.FlowDocument> contenido <xref:System.Windows.Documents.Paragraph>de marco se incluyen y. Si no está seguro de si un tipo es un elemento de marco o un elemento de contenido de marco, compruebe si tiene una propiedad Name. Si la tiene, probablemente sea un elemento de marco o un elemento de contenido de marco. Para estar seguro, compruebe la sección de jerarquía de herencia de su página de tipo.

Para habilitar el destino de un elemento de marco o un elemento de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]marco en, establezca <xref:System.Windows.FrameworkElement.Name%2A> su propiedad. En el código, también debe usar el <xref:System.Windows.NameScope.RegisterName%2A> método para registrar el nombre del elemento con el elemento para el que ha creado un. <xref:System.Windows.NameScope>

En el ejemplo siguiente, tomado del ejemplo anterior, se asigna el nombre `MyRectangle` a <xref:System.Windows.Shapes.Rectangle>, un tipo de <xref:System.Windows.FrameworkElement>.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

Una vez que tenga un nombre, puede animar una propiedad de ese elemento.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable>los tipos son las clases que heredan <xref:System.Windows.Freezable> de la clase. Entre los <xref:System.Windows.Freezable> ejemplos <xref:System.Windows.Media.SolidColorBrush>de <xref:System.Windows.Media.RotateTransform>se incluyen <xref:System.Windows.Media.GradientStop>, y.

Para habilitar el destino de un <xref:System.Windows.Freezable> mediante una animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice la [Directiva x:Name](../../xaml-services/x-name-directive.md) para asignarle un nombre. En el código, se usa <xref:System.Windows.NameScope.RegisterName%2A> el método para registrar su nombre en el elemento para el que se ha <xref:System.Windows.NameScope>creado.

En el ejemplo siguiente se asigna un nombre a un <xref:System.Windows.Freezable> objeto.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

A continuación, ya se puede establecer el objeto como destino de una animación.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>los objetos utilizan ámbitos de nombres para resolver <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> la propiedad. Para obtener más información sobre los ámbitos de nombres de WPF, consulte [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md). Si se <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> omite la propiedad, la animación tiene como destino el elemento en el que se define o, en el caso de los estilos, el elemento con estilo.

A veces no se puede asignar un nombre <xref:System.Windows.Freezable> a un objeto. Por ejemplo, si <xref:System.Windows.Freezable> se declara como recurso o se utiliza para establecer un valor de propiedad en un estilo, no se le puede asignar un nombre. Al no tener nombre, no se puede establecer como destino directamente, pero sí de manera indirecta. En las secciones siguientes se describe cómo utilizar el establecimiento indirecto de destinos.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Establecimiento indirecto de destinos

Hay veces <xref:System.Windows.Freezable> que una animación no puede destinarla directamente, como <xref:System.Windows.Freezable> cuando se declara como recurso o se utiliza para establecer un valor de propiedad en un estilo. En estos casos, aunque no pueda dirigirse directamente a él, todavía puede animar <xref:System.Windows.Freezable> el objeto. En lugar de establecer la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> propiedad con el nombre <xref:System.Windows.Freezable>de, se le asigna el nombre del elemento al que <xref:System.Windows.Freezable> pertenece ". Por ejemplo, <xref:System.Windows.Media.SolidColorBrush> que se usa para establecer <xref:System.Windows.Shapes.Shape.Fill%2A> el de un elemento de rectángulo pertenece a ese rectángulo. Para animar el pincel, debería establecer la propiedad de <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> la animación con una cadena de propiedades que comienza en la propiedad del elemento de marco o <xref:System.Windows.Freezable> elemento de contenido de marco que se usó para establecer <xref:System.Windows.Freezable> y termina con la propiedad que se va a animar.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Tenga en cuenta que, <xref:System.Windows.Freezable> si el está inmovilizado, se realizará un clon y ese clon se animará. Cuando esto sucede, la propiedad del <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> objeto original continúa devolviendo `false`, porque el objeto original no se anima realmente. Para obtener más información sobre la clonación, vea [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).

Además, tenga en cuenta que, al utilizar el establecimiento indirecto de propiedades de destino, es posible establecer como destino objetos que no existen. Por ejemplo, puede suponer que el <xref:System.Windows.Controls.Control.Background%2A> de un botón determinado se ha establecido con <xref:System.Windows.Media.SolidColorBrush> un e intenta animar su color <xref:System.Windows.Media.LinearGradientBrush> , cuando de hecho se ha utilizado para establecer el fondo del botón. En estos casos, no se produce ninguna excepción; la animación no tiene ningún efecto visible porque <xref:System.Windows.Media.LinearGradientBrush> no reacciona a los cambios en la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad.

En las secciones siguientes se describe con mayor detalle la sintaxis de establecimiento indirecto de propiedades de destino.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable en XAML

Para establecer como destino una propiedad de un Freezable [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en, utilice la siguiente sintaxis.

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Where

- *ElementPropertyName* es la propiedad de la <xref:System.Windows.FrameworkElement> que <xref:System.Windows.Freezable> se usa para establecer y

- *FreezablePropertyName* es la propiedad del <xref:System.Windows.Freezable> que se va a animar.

En el código siguiente se muestra cómo animar <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> que se usa <xref:System.Windows.Shapes.Shape.Fill%2A> para establecer el de un elemento de rectángulo.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz.

Para establecer como destino un objeto inmovilizable contenido en una colección, se utiliza la sintaxis de ruta de acceso siguiente.

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

Donde *CollectionIndex* es el índice del objeto en su matriz o colección.

Por ejemplo, supongamos que un rectángulo <xref:System.Windows.Media.TransformGroup> tiene un recurso aplicado <xref:System.Windows.UIElement.RenderTransform%2A> a su propiedad y desea animar una de las transformaciones que contiene.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

En el código siguiente <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform> se muestra cómo animar la propiedad del que se muestra en el ejemplo anterior.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable mediante código

En el código, se crea <xref:System.Windows.PropertyPath> un objeto. Al crear el <xref:System.Windows.PropertyPath>, se <xref:System.Windows.PropertyPath.Path%2A> especifican y <xref:System.Windows.PropertyPath.PathParameters%2A>.

Para crear <xref:System.Windows.PropertyPath.PathParameters%2A>, cree una matriz de tipo <xref:System.Windows.DependencyProperty> que contenga una lista de campos de identificador de propiedad de dependencia. El primer campo de identificador es para la propiedad de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> que <xref:System.Windows.Freezable> se usa para establecer. El siguiente campo de identificador representa la propiedad de <xref:System.Windows.Freezable> destino. Considérelo como una cadena de propiedades que conecta <xref:System.Windows.Freezable> con el <xref:System.Windows.FrameworkElement> objeto.

El siguiente es un ejemplo de una cadena de propiedades de dependencia que <xref:System.Windows.Media.SolidColorBrush.Color%2A> tiene como <xref:System.Windows.Media.SolidColorBrush> destino el de un <xref:System.Windows.Shapes.Shape.Fill%2A> que se usa para establecer el de un elemento de rectángulo.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

También debe especificar un <xref:System.Windows.PropertyPath.Path%2A>. Un <xref:System.Windows.PropertyPath.Path%2A> es un <xref:System.String> que indica <xref:System.Windows.PropertyPath.Path%2A> a cómo interpretar su <xref:System.Windows.PropertyPath.PathParameters%2A>. Se usa la siguiente sintaxis:

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Where

- *OwnerPropertyArrayIndex* es el índice de la <xref:System.Windows.DependencyProperty> matriz que contiene el identificador de la <xref:System.Windows.FrameworkElement> propiedad del objeto que <xref:System.Windows.Freezable> se usa para establecer y

- *FreezablePropertyArrayIndex* es el índice de la <xref:System.Windows.DependencyProperty> matriz que contiene el identificador de la propiedad que se va a usar como destino.

En el ejemplo siguiente se <xref:System.Windows.PropertyPath.Path%2A> muestra el que acompañaría al <xref:System.Windows.PropertyPath.PathParameters%2A> definido en el ejemplo anterior.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

En el ejemplo siguiente se combina el código de los ejemplos anteriores para <xref:System.Windows.Media.SolidColorBrush.Color%2A> animar <xref:System.Windows.Media.SolidColorBrush> el de un que <xref:System.Windows.Shapes.Shape.Fill%2A> se usa para establecer el de un elemento de rectángulo.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz. Por ejemplo, supongamos que un rectángulo <xref:System.Windows.Media.TransformGroup> tiene un recurso aplicado <xref:System.Windows.UIElement.RenderTransform%2A> a su propiedad y desea animar una de las transformaciones que contiene.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Para establecer como <xref:System.Windows.Freezable> destino un contenido en una colección, use la sintaxis de ruta de acceso siguiente.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

Donde *CollectionIndex* es el índice del objeto en su matriz o colección.

Para establecer como <xref:System.Windows.Media.RotateTransform.Angle%2A> destino la propiedad <xref:System.Windows.Media.RotateTransform>de, <xref:System.Windows.Media.TransformGroup>la segunda transformación de, usaría los siguientes elementos <xref:System.Windows.PropertyPath.Path%2A> y <xref:System.Windows.PropertyPath.PathParameters%2A>.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

En el ejemplo siguiente se muestra el código completo para <xref:System.Windows.Media.RotateTransform.Angle%2A> animar <xref:System.Windows.Media.RotateTransform> el de un <xref:System.Windows.Media.TransformGroup>contenido dentro de un.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Establecimiento indirecto de destinos con un objeto inmovilizable como punto de partida

En las secciones anteriores se describe cómo establecer como <xref:System.Windows.Freezable> destino indirectamente un <xref:System.Windows.FrameworkElement> objeto <xref:System.Windows.FrameworkContentElement> a partir de un o y crear <xref:System.Windows.Freezable> una cadena de propiedades a una subpropiedad. También puede usar <xref:System.Windows.Freezable> como punto de partida y dirigirse indirectamente a una de <xref:System.Windows.Freezable> sus subpropiedades. Cuando se usa un <xref:System.Windows.Freezable> como punto de partida para el establecimiento indirecto de destinos, se aplica una restricción adicional: el inicio <xref:System.Windows.Freezable> y el de cada uno <xref:System.Windows.Freezable> de ellos y la subpropiedad de destino indirecta no se deben inmovilizar.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Controlar guiones gráficos de forma interactiva en XAML

Para iniciar un guion gráfico [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]en, se usa <xref:System.Windows.Media.Animation.BeginStoryboard> una acción de desencadenador. <xref:System.Windows.Media.Animation.BeginStoryboard>distribuye las animaciones a los objetos y propiedades que animan e inicia el guion gráfico. (Para obtener más información acerca de este proceso, consulte [información general sobre el sistema de control de tiempo y animación](animation-and-timing-system-overview.md)). Si asigna un nombre <xref:System.Windows.Media.Animation.BeginStoryboard> mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, lo convierte en un guión gráfico controlable. A continuación, podrá controlar interactivamente el guión gráfico una vez iniciado. Esta es una lista de acciones de guión gráfico controlables que se utiliza con desencadenadores de eventos para controlar un guión gráfico.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guion gráfico.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Reanuda un guion gráfico en pausa.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si tiene uno.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guion gráfico.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guion gráfico.

En el ejemplo siguiente se utilizan acciones para controlar interactivamente un guión gráfico.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Controlar interactivamente un guión gráfico mediante código

En los ejemplos anteriores se muestra cómo animar mediante acciones de desencadenador. En el código, también puede controlar un guión gráfico mediante métodos interactivos de la <xref:System.Windows.Media.Animation.Storyboard> clase. Para que <xref:System.Windows.Media.Animation.Storyboard> un se convierta en interactivo en el código, debe usar la sobrecarga adecuada del método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> del guión gráfico `true` y especificar para que sea controlable. Vea la <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> página para obtener más información.

En la lista siguiente se muestran los métodos que se pueden utilizar para manipular <xref:System.Windows.Media.Animation.Storyboard> una después de que se haya iniciado:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

La ventaja de utilizar estos métodos es que no es necesario crear <xref:System.Windows.Trigger> objetos o <xref:System.Windows.TriggerAction> ; solo necesita una <xref:System.Windows.Media.Animation.Storyboard> referencia al objeto controlable que desea manipular.

> [!NOTE]
> Todas las acciones interactivas <xref:System.Windows.Media.Animation.Clock>realizadas en un y, por <xref:System.Windows.Media.Animation.Storyboard> lo tanto, también en se producirán en el siguiente paso del motor de control de tiempo, que se producirá poco antes de la siguiente representación. Por ejemplo, si usa el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método para saltar a otro punto de una animación, el valor de la propiedad no cambia al instante, sino que el valor cambia en el siguiente paso del motor de control de tiempo.

En el ejemplo siguiente se muestra cómo aplicar y controlar animaciones mediante los métodos interactivos de la <xref:System.Windows.Media.Animation.Storyboard> clase.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Animar en un estilo

Puede utilizar <xref:System.Windows.Media.Animation.Storyboard> objetos para definir animaciones en un <xref:System.Windows.Style>. Animar con <xref:System.Windows.Media.Animation.Storyboard> un en <xref:System.Windows.Style> un es similar a usar <xref:System.Windows.Media.Animation.Storyboard> un en otra parte, con las tres excepciones siguientes:

- No se especifica un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard> ; siempre tiene como destino <xref:System.Windows.Style> el elemento al que se aplica. Para los <xref:System.Windows.Freezable> objetos de destino, debe utilizar el establecimiento indirecto de destinos. Para obtener más información sobre el establecimiento indirecto de destinos, consulte la sección de [destinatarios indirectos](#pathsyntaxforchangeable) .

- No se puede especificar <xref:System.Windows.EventTrigger.SourceName%2A> un para <xref:System.Windows.EventTrigger> un o <xref:System.Windows.Trigger>un.

- No se pueden usar referencias de recursos dinámicos o expresiones de <xref:System.Windows.Media.Animation.Storyboard> enlace de datos para establecer o animar los valores de propiedad. Esto se debe a que todo <xref:System.Windows.Style> lo que hay dentro de debe ser seguro para subprocesos y el sistema de control de tiempo debe <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> ser objeto para hacerlos seguros para subprocesos. No <xref:System.Windows.Media.Animation.Storyboard> se puede inmovilizar si o sus escalas de tiempo secundarias contienen referencias de recursos dinámicos o expresiones de enlace de datos. Para obtener más información sobre la inmovilización y otras <xref:System.Windows.Freezable> características, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).

- En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se pueden declarar controladores de eventos <xref:System.Windows.Media.Animation.Storyboard> para eventos de animación o.

Para ver un ejemplo en el que se muestra cómo definir un guion gráfico en un estilo, vea el ejemplo de [animar en un estilo](how-to-animate-in-a-style.md) .

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Animar en un ControlTemplate

Puede utilizar <xref:System.Windows.Media.Animation.Storyboard> objetos para definir animaciones en un <xref:System.Windows.Controls.ControlTemplate>. Animar con <xref:System.Windows.Media.Animation.Storyboard> un en <xref:System.Windows.Controls.ControlTemplate> un es similar a usar <xref:System.Windows.Media.Animation.Storyboard> un en otra parte, con las dos excepciones siguientes:

- Solo puede hacer referencia a objetos secundarios <xref:System.Windows.Controls.ControlTemplate>de. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Si <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> no se especifica, la animación tiene como destino el elemento al <xref:System.Windows.Controls.ControlTemplate> que se aplica.

- <xref:System.Windows.EventTrigger.SourceName%2A> Para un <xref:System.Windows.Controls.ControlTemplate>o un <xref:System.Windows.Trigger> solo puede hacer referencia a los <xref:System.Windows.EventTrigger> objetos secundarios de.

- No se pueden usar referencias de recursos dinámicos o expresiones de <xref:System.Windows.Media.Animation.Storyboard> enlace de datos para establecer o animar los valores de propiedad. Esto se debe a que todo <xref:System.Windows.Controls.ControlTemplate> lo que hay dentro de debe ser seguro para subprocesos y el sistema de control de tiempo debe <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> ser objeto para hacerlos seguros para subprocesos. No <xref:System.Windows.Media.Animation.Storyboard> se puede inmovilizar si o sus escalas de tiempo secundarias contienen referencias de recursos dinámicos o expresiones de enlace de datos. Para obtener más información sobre la inmovilización y otras <xref:System.Windows.Freezable> características, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).

- En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se pueden declarar controladores de eventos <xref:System.Windows.Media.Animation.Storyboard> para eventos de animación o.

Para ver un ejemplo en el que se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate>un guion gráfico en un, vea el ejemplo de [animar en un ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Animar cuando cambia el valor de una propiedad

En estilos y plantillas de control, puede utilizar objetos Trigger para iniciar un guión gráfico cuando cambia una propiedad. Para obtener ejemplos, vea [desencadenar una animación cuando cambia el valor de una propiedad](how-to-trigger-an-animation-when-a-property-value-changes.md) y [animar en un ControlTemplate](how-to-animate-in-a-controltemplate.md).

Las animaciones aplicadas <xref:System.Windows.Trigger> por objetos de propiedad se comportan <xref:System.Windows.EventTrigger> de manera más compleja que las animaciones o animaciones que se inician mediante <xref:System.Windows.Media.Animation.Storyboard> métodos.  "Se colocan" con animaciones definidas <xref:System.Windows.Trigger> por otros objetos, pero <xref:System.Windows.EventTrigger> se componen con y animaciones desencadenadas por el método.

## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
- [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md)
