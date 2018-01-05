---
title: "Información general sobre objetos Storyboard"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efb6db7758319d2d3c6b403e12fe0edabe7c5ff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="storyboards-overview"></a>Información general sobre objetos Storyboard
Este tema muestra cómo usar <xref:System.Windows.Media.Animation.Storyboard> objetos para organizar y aplicar animaciones. Describe cómo manipular interactivamente <xref:System.Windows.Media.Animation.Storyboard> objetos y se describe la sintaxis de establecimiento indirecto de propiedades.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de animaciones y sus características básicas. Para obtener una introducción a la animación, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). También debe saber utilizar las propiedades asociadas. Para obtener más información sobre las propiedades adjuntas, consulte [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>¿Qué es un guión gráfico?  
 Las animaciones no son el único tipo útil de escala de tiempo. Se proporcionan otras clases de escalas de tiempo para ayudarle a organizar conjuntos de escalas de tiempo y para aplicar las escalas de tiempo a las propiedades. Escalas de tiempo contenedoras se derivan de la <xref:System.Windows.Media.Animation.TimelineGroup> clase e incluyen <xref:System.Windows.Media.Animation.ParallelTimeline> y <xref:System.Windows.Media.Animation.Storyboard>.  
  
 A <xref:System.Windows.Media.Animation.Storyboard> es un tipo de escala de tiempo contenedora que proporciona información de destino para las escalas de tiempo contiene. Un guión gráfico puede contener cualquier tipo de <xref:System.Windows.Media.Animation.Timeline>, incluidas otras escalas de tiempo contenedoras y las animaciones. <xref:System.Windows.Media.Animation.Storyboard>objetos permiten combinar escalas de tiempo que afectan a una variedad de objetos y propiedades en un árbol único de la escala de tiempo, lo que facilita organizar y controlar los comportamientos de control de tiempo complejos. Por ejemplo, supongamos que desea un botón que haga estas tres cosas.  
  
-   Aumentar de tamaño y cambiar de color cuando el usuario selecciona el botón.  
  
-   Disminuir de tamaño y volver a su tamaño original cuando se hace clic en él.  
  
-   Disminuir de tamaño y desvanecerse con un fundido al 50 % de opacidad al deshabilitarse.  
  
 En este caso, tenemos varios conjuntos de animaciones que se aplican al mismo objeto, y hay que reproducirlas en distintos momentos, según cuál sea el estado del botón. <xref:System.Windows.Media.Animation.Storyboard>objetos permiten organizar las animaciones y aplicarlas en grupos a uno o varios objetos.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>¿Dónde se puede utilizar un guión gráfico?  
 A <xref:System.Windows.Media.Animation.Storyboard> puede utilizarse para animar las propiedades de dependencia de clases pueden animar (para obtener más información sobre lo que hace que una clase pueda animar, vea el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). Sin embargo, dado que guiones gráficos es una característica de nivel de marco, el objeto debe pertenecer a la <xref:System.Windows.NameScope> de un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
 Por ejemplo, podría utilizar un <xref:System.Windows.Media.Animation.Storyboard> para hacer lo siguiente:  
  
-   Animar un <xref:System.Windows.Media.SolidColorBrush> (elemento no es de marco) que pinta el fondo de un botón (un tipo de <xref:System.Windows.FrameworkElement>),  
  
-   Animar un <xref:System.Windows.Media.SolidColorBrush> (elemento no es de marco) que pinta el relleno de un <xref:System.Windows.Media.GeometryDrawing> (elemento no es de marco) muestra con un <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   En el código, animar un <xref:System.Windows.Media.SolidColorBrush> declarado por una clase que también contiene un <xref:System.Windows.FrameworkElement>, si la <xref:System.Windows.Media.SolidColorBrush> registrado su nombre con el que <xref:System.Windows.FrameworkElement>.  
  
 Sin embargo, no podría usar un <xref:System.Windows.Media.Animation.Storyboard> para animar un <xref:System.Windows.Media.SolidColorBrush> que no registró su nombre con un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o no se usa para establecer una propiedad de un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Cómo aplicar animaciones mediante un guión gráfico  
 Para usar un <xref:System.Windows.Media.Animation.Storyboard> para organizar y aplicar animaciones, agregue las animaciones como escalas de tiempo secundarias de la <xref:System.Windows.Media.Animation.Storyboard>. El <xref:System.Windows.Media.Animation.Storyboard> clase proporciona el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> propiedades adjuntas. Se establecen estas propiedades de una animación para especificar su objeto y propiedad de destino.  
  
 Para aplicar animaciones a sus destinos, comenzar la <xref:System.Windows.Media.Animation.Storyboard> con una acción de desencadenador o un método. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utiliza un <xref:System.Windows.Media.Animation.BeginStoryboard> objeto con un <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, o <xref:System.Windows.DataTrigger>. En el código, también puede usar el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método.  
  
 La siguiente tabla muestra los distintos lugares donde cada <xref:System.Windows.Media.Animation.Storyboard> comenzar se admite la técnica: por instancia, estilo, plantilla de control o una plantilla de datos. "Por instancia" se refiere a la técnica de aplicar directamente una animación o guión gráfico a las instancias de un objeto, en lugar de en un estilo, una plantilla de control o una plantilla de datos.  
  
|El guión gráfico se comienza utilizando...|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y una propiedad<xref:System.Windows.Trigger>|No|Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>y un<xref:System.Windows.DataTrigger>|No|Sí|Sí|Sí|[Cómo: Activar una animación cuando se cambian datos](http://msdn.microsoft.com/en-us/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sí|No|No|No|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.Storyboard> para animar la <xref:System.Windows.FrameworkElement.Width%2A> de un <xref:System.Windows.Shapes.Rectangle> elemento y el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> usado para pintar que <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 Las secciones siguientes describen la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> adjunta propiedades con más detalle.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Establecer como destino elementos de marco, elementos de contenido de marco y elementos inmovilizables  
 En la sección anterior se menciona que, para que una animación encuentre su destino, debe conocer el nombre del mismo y la propiedad que debe animar. Especifica la propiedad que se va a animar es sencillo: basta con establecer <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> con el nombre de la propiedad que se va a animar.  Especifique el nombre del objeto cuya propiedad desea animar estableciendo la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> propiedad en la animación.  
  
 Para el <xref:System.Windows.Setter.TargetName%2A> propiedad funcione, el objeto de destino debe tener un nombre. Asignar un nombre a un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.FrameworkContentElement> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es diferente de la asignación de un nombre a un <xref:System.Windows.Freezable> objeto.  
  
 Los elementos de marco son las clases que heredan de la <xref:System.Windows.FrameworkElement> clase. Algunos ejemplos de elementos de marco son <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, y <xref:System.Windows.Shapes.Rectangle>. En esencia, todas las ventanas, los paneles y los controles son elementos. Elementos de contenido de marco son las clases que heredan de la <xref:System.Windows.FrameworkContentElement> clase. Ejemplos de elementos de contenido de framework <xref:System.Windows.Documents.FlowDocument> y <xref:System.Windows.Documents.Paragraph>. Si no está seguro de si un tipo es un elemento de marco o un elemento de contenido de marco, compruebe si tiene una propiedad Name. Si la tiene, probablemente sea un elemento de marco o un elemento de contenido de marco. Para estar seguro, compruebe la sección de jerarquía de herencia de su página de tipo.  
  
 Para habilitar los destinatarios de un elemento de marco o un elemento de contenido de marco en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], establece su <xref:System.Windows.FrameworkElement.Name%2A> propiedad. En el código, también debe usar el <xref:System.Windows.NameScope.RegisterName%2A> método para registrar el nombre del elemento con el elemento para el que ha creado un <xref:System.Windows.NameScope>.  
  
 El ejemplo siguiente, tomado del ejemplo anterior, asigna el nombre `MyRectangle` una <xref:System.Windows.Shapes.Rectangle>, un tipo de <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Una vez que tenga un nombre, puede animar una propiedad de ese elemento.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable>los tipos son las clases que heredan de la <xref:System.Windows.Freezable> clase. Ejemplos de <xref:System.Windows.Freezable> incluyen <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, y <xref:System.Windows.Media.GradientStop>.  
  
 Para habilitar los destinatarios de un <xref:System.Windows.Freezable> una animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usa el [Directiva x: Name](../../../../docs/framework/xaml-services/x-name-directive.md) para asignar un nombre. En el código, utilice la <xref:System.Windows.NameScope.RegisterName%2A> método para registrar su nombre en el elemento para el que ha creado un <xref:System.Windows.NameScope>.  
  
 En el ejemplo siguiente se asigna un nombre a un <xref:System.Windows.Freezable> objeto.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 A continuación, ya se puede establecer el objeto como destino de una animación.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>objetos usan ámbitos de nombres para resolver la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> propiedad. Para obtener más información sobre los ámbitos de nombres de WPF, consulte [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md). Si el <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> propiedad se omite, la animación establece como destino el elemento en la que se define o, en el caso de los estilos, el elemento de estilo.  
  
 En ocasiones, no se puede asignar un nombre a un <xref:System.Windows.Freezable> objeto. Por ejemplo, si un <xref:System.Windows.Freezable> se declara como un recurso o que utiliza para establecer un valor de propiedad en un estilo, no puede asignarse un nombre. Al no tener nombre, no se puede establecer como destino directamente, pero sí de manera indirecta. En las secciones siguientes se describe cómo utilizar el establecimiento indirecto de destinos.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>Establecimiento indirecto de destinos  
 Hay veces un <xref:System.Windows.Freezable> no se puede destinar directamente por una animación, como cuando el <xref:System.Windows.Freezable> se declara como un recurso o que utiliza para establecer un valor de propiedad en un estilo. En estos casos, aunque no se puede establecer como destino directamente, se puede animar la <xref:System.Windows.Freezable> objeto. En lugar de establecer la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> propiedad con el nombre de la <xref:System.Windows.Freezable>, se proporciona el nombre del elemento al que el <xref:System.Windows.Freezable> "pertenece". Por ejemplo, un <xref:System.Windows.Media.SolidColorBrush> usa para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> de un rectángulo elemento pertenece a dicho rectángulo. Para animar el pincel, establecería la animación <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> con una cadena de propiedades que comienza en la propiedad del elemento de marco o elemento de contenido de marco de trabajo la <xref:System.Windows.Freezable> se usa para establecer y termina con el <xref:System.Windows.Freezable> propiedad que se va a animar.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Tenga en cuenta que, si la <xref:System.Windows.Freezable> está inmovilizado, se realizará un clon y ese clon se animará. Cuando esto sucede, el objeto original <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> propiedad continúa devolviendo `false`, ya que el objeto original no se anima realmente. Para obtener más información acerca de la clonación, consulte el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Además, tenga en cuenta que, al utilizar el establecimiento indirecto de propiedades de destino, es posible establecer como destino objetos que no existen. Por ejemplo, puede suponer que la <xref:System.Windows.Controls.Control.Background%2A> de un botón determinado se estableció con un <xref:System.Windows.Media.SolidColorBrush> e intentar animar el Color, cuando en realidad un <xref:System.Windows.Media.LinearGradientBrush> se usa para establecer el fondo del botón. En estos casos, se inicia ninguna excepción; la animación no tiene ningún efecto visible porque <xref:System.Windows.Media.LinearGradientBrush> no reaccione ante los cambios a la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad.  
  
 En las secciones siguientes se describe con mayor detalle la sintaxis de establecimiento indirecto de propiedades de destino.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable en XAML  
 Para tener como destino una propiedad de un objeto inmovilizable en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use la siguiente sintaxis.  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* es la propiedad de la <xref:System.Windows.FrameworkElement> que la <xref:System.Windows.Freezable> se usa para establecer, y  
  
-   *FreezablePropertyName* es la propiedad de la <xref:System.Windows.Freezable> a animar.  
  
 El código siguiente muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> usa para establecer el  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A>de un elemento de rectángulo.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz.  
  
 Para establecer como destino un objeto inmovilizable contenido en una colección, se utiliza la sintaxis de ruta de acceso siguiente.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Donde *índicecolección* es el índice del objeto en su matriz o colección.  
  
 Por ejemplo, supongamos que un rectángulo tiene una <xref:System.Windows.Media.TransformGroup> aplicado a recurso su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad y desea animar una de las transformaciones que contiene.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 El código siguiente muestra cómo animar la <xref:System.Windows.Media.RotateTransform.Angle%2A> propiedad de la <xref:System.Windows.Media.RotateTransform> se muestra en el ejemplo anterior.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable mediante código  
 En código, cree un <xref:System.Windows.PropertyPath> objeto. Cuando se crea el <xref:System.Windows.PropertyPath>, especifique un <xref:System.Windows.PropertyPath.Path%2A> y <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Para crear <xref:System.Windows.PropertyPath.PathParameters%2A>, se crea una matriz de tipo <xref:System.Windows.DependencyProperty> que contiene una lista de campos de identificador de propiedad de dependencia. El primer campo de identificador es para la propiedad de la <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> que la <xref:System.Windows.Freezable> se usa para establecer. El campo de identificador siguiente representa la propiedad de la <xref:System.Windows.Freezable> al destino. Considérelo como una cadena de propiedades que se conecta el <xref:System.Windows.Freezable> a la <xref:System.Windows.FrameworkElement> objeto.  
  
 El siguiente es un ejemplo de una cadena de propiedad de dependencia que tenga como destino el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> usa para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 También debe especificar un <xref:System.Windows.PropertyPath.Path%2A>. A <xref:System.Windows.PropertyPath.Path%2A> es un <xref:System.String> que indica la <xref:System.Windows.PropertyPath.Path%2A> cómo interpretar sus <xref:System.Windows.PropertyPath.PathParameters%2A>. Se usa la siguiente sintaxis:  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* es el índice de la <xref:System.Windows.DependencyProperty> matriz que contiene el identificador de la <xref:System.Windows.FrameworkElement> propiedad del objeto que el <xref:System.Windows.Freezable> se usa para establecer, y  
  
-   *FreezablePropertyArrayIndex* es el índice de la <xref:System.Windows.DependencyProperty> matriz que contiene el identificador de propiedad de destino.  
  
 El siguiente ejemplo se muestra la <xref:System.Windows.PropertyPath.Path%2A> que se acompañan a la <xref:System.Windows.PropertyPath.PathParameters%2A> definido en el ejemplo anterior.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 En el ejemplo siguiente se combina el código en los ejemplos anteriores para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> usa para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz. Por ejemplo, supongamos que un rectángulo tiene una <xref:System.Windows.Media.TransformGroup> aplicado a recurso su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad y desea animar una de las transformaciones que contiene.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Destino un <xref:System.Windows.Freezable> contenidos en una colección, use la siguiente sintaxis de ruta de acceso.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 Donde *índicecolección* es el índice del objeto en su matriz o colección.  
  
 Al destino la <xref:System.Windows.Media.RotateTransform.Angle%2A> propiedad de la <xref:System.Windows.Media.RotateTransform>, la segunda transformación en el <xref:System.Windows.Media.TransformGroup>, utilizaría la siguiente <xref:System.Windows.PropertyPath.Path%2A> y <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 En el ejemplo siguiente se muestra el código completo para animar la <xref:System.Windows.Media.RotateTransform.Angle%2A> de un <xref:System.Windows.Media.RotateTransform> dentro de un <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Establecimiento indirecto de destinos con un objeto inmovilizable como punto de partida  
 Las secciones anteriores describen cómo establecer indirectamente como destino un <xref:System.Windows.Freezable> a partir de un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> y creando una cadena de propiedad para un <xref:System.Windows.Freezable> subpropiedad. También puede usar un <xref:System.Windows.Freezable> como un valor de inicio, elija y establecer indirectamente como destino una de sus <xref:System.Windows.Freezable> subpropiedades. Se aplica una restricción adicional cuando se usa un <xref:System.Windows.Freezable> como punto de partida para indirecto: el inicio <xref:System.Windows.Freezable> y cada <xref:System.Windows.Freezable> entre él y el destino indirectamente subpropiedad debe no ser inmovilizado.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Controlar guiones gráficos de forma interactiva en XAML  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utiliza un <xref:System.Windows.Media.Animation.BeginStoryboard> desencadenar la acción. <xref:System.Windows.Media.Animation.BeginStoryboard>distribuye las animaciones a los objetos y propiedades que se animan e inicia el guión gráfico. (Para obtener más información acerca de este proceso, consulte la [animación y temporización información general del sistema](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) Si asigna el <xref:System.Windows.Media.Animation.BeginStoryboard> un nombre mediante la especificación de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, permite que un guión gráfico controlable. A continuación, podrá controlar interactivamente el guión gráfico una vez iniciado. Esta es una lista de acciones de guión gráfico controlables que se utiliza con desencadenadores de eventos para controlar un guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Se detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Se reanuda un guión gráfico en pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Hace avanzar un guión gráfico hasta el final de su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico.  
  
 En el ejemplo siguiente se utilizan acciones para controlar interactivamente un guión gráfico.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Controlar interactivamente un guión gráfico mediante código  
 En los ejemplos anteriores se muestra cómo animar mediante acciones de desencadenador. En el código, también puede controlar un guión gráfico mediante los métodos interactivos de la <xref:System.Windows.Media.Animation.Storyboard> clase. Para una <xref:System.Windows.Media.Animation.Storyboard> para estar interactivo en el código, debe utilizar la sobrecarga adecuada del guión gráfico <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método y especifique `true` para que sea controlable. Consulte la <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> página para obtener más información.  
  
 La lista siguiente muestra los métodos que pueden utilizarse para manipular un <xref:System.Windows.Media.Animation.Storyboard> después de haberse iniciado:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 La ventaja de usar estos métodos es que no es necesario crear <xref:System.Windows.Trigger> o <xref:System.Windows.TriggerAction> objetos; solo necesita una referencia a la controlable <xref:System.Windows.Media.Animation.Storyboard> desea manipular.  
  
 **Nota:** todas las acciones interactivas tomadas un <xref:System.Windows.Media.Animation.Clock>y, por tanto, también en un <xref:System.Windows.Media.Animation.Storyboard> se producirá en el siguiente paso del motor de tiempo que se realizará en breve antes de la siguiente representación. Por ejemplo, si usa el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método para saltar a otro punto en una animación, el valor de propiedad no cambia al instante, en su lugar, se cambia el valor en el siguiente paso del motor de temporización.  
  
 En el ejemplo siguiente se muestra cómo aplicar y controlar animaciones mediante los métodos interactivos de la <xref:System.Windows.Media.Animation.Storyboard> clase.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>Animar en un estilo  
 Puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para definir animaciones en una <xref:System.Windows.Style>. Animar con un <xref:System.Windows.Media.Animation.Storyboard> en un <xref:System.Windows.Style> es similar al uso de un <xref:System.Windows.Media.Animation.Storyboard> en otra parte, con las tres excepciones siguientes:  
  
-   No se especifica un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; el <xref:System.Windows.Media.Animation.Storyboard> siempre tiene como destino el elemento al que el <xref:System.Windows.Style> se aplica. Destino <xref:System.Windows.Freezable> objetos, debe utilizar la identificación indirecta. Para obtener más información sobre cómo destinar indirectos, vea el [indirecto](#pathsyntaxforchangeable) sección.  
  
-   No se puede especificar un <xref:System.Windows.EventTrigger.SourceName%2A> para un <xref:System.Windows.EventTrigger> o <xref:System.Windows.Trigger>.  
  
-   No se puede usar expresiones de enlace de datos o referencias de recursos dinámicos para establecer <xref:System.Windows.Media.Animation.Storyboard> o valores de propiedad de animación. La razón es que todos los datos una <xref:System.Windows.Style> debe ser seguro para subprocesos, y el sistema de control de tiempo debe <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> objetos para que sean seguros para subprocesos. Un <xref:System.Windows.Media.Animation.Storyboard> no se pueden inmovilizar si lo o sus escalas de tiempo secundarias contienen expresiones de enlace de datos o las referencias de recurso dinámico. Para obtener más información sobre la inmovilización y otras <xref:System.Windows.Freezable> características, consulte la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no puede declarar controladores de eventos para <xref:System.Windows.Media.Animation.Storyboard> o eventos de animación.  
  
 Para obtener un ejemplo que muestra cómo definir un guión gráfico en un estilo, vea el [animar en un estilo](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) ejemplo.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>Animar en un ControlTemplate  
 Puede usar <xref:System.Windows.Media.Animation.Storyboard> objetos para definir animaciones en una <xref:System.Windows.Controls.ControlTemplate>. Animar con un <xref:System.Windows.Media.Animation.Storyboard> en un <xref:System.Windows.Controls.ControlTemplate> es similar al uso de un <xref:System.Windows.Media.Animation.Storyboard> en otra parte, con las dos excepciones siguientes:  
  
-   El <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> solo pueden hacer referencia a los objetos secundarios de la <xref:System.Windows.Controls.ControlTemplate>. Si <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> no se especifica, la animación establece como destino el elemento al que el <xref:System.Windows.Controls.ControlTemplate> se aplica.  
  
-   El <xref:System.Windows.EventTrigger.SourceName%2A> para un <xref:System.Windows.EventTrigger> o un <xref:System.Windows.Trigger> solo pueden hacer referencia a los objetos secundarios de la <xref:System.Windows.Controls.ControlTemplate>.  
  
-   No se puede usar expresiones de enlace de datos o referencias de recursos dinámicos para establecer <xref:System.Windows.Media.Animation.Storyboard> o valores de propiedad de animación. La razón es que todos los datos una <xref:System.Windows.Controls.ControlTemplate> debe ser seguro para subprocesos, y el sistema de control de tiempo debe <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> objetos para que sean seguros para subprocesos. Un <xref:System.Windows.Media.Animation.Storyboard> no se pueden inmovilizar si lo o sus escalas de tiempo secundarias contienen expresiones de enlace de datos o las referencias de recurso dinámico. Para obtener más información sobre la inmovilización y otras <xref:System.Windows.Freezable> características, consulte la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no puede declarar controladores de eventos para <xref:System.Windows.Media.Animation.Storyboard> o eventos de animación.  
  
 Para obtener un ejemplo que muestra cómo definir un guión gráfico en un <xref:System.Windows.Controls.ControlTemplate>, consulte el [animar en un ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) ejemplo.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>Animar cuando cambia el valor de una propiedad  
 En estilos y plantillas de control, puede utilizar objetos Trigger para iniciar un guión gráfico cuando cambia una propiedad. Para obtener ejemplos, vea [desencadenar una animación cuando una propiedad cambia el valor](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) y [animar en un ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Las animaciones aplicadas por la propiedad <xref:System.Windows.Trigger> objetos se comportan de forma más compleja que <xref:System.Windows.EventTrigger> copia las animaciones ni animaciones a usar <xref:System.Windows.Media.Animation.Storyboard> métodos.  Se "continúan" con animaciones definida por otros <xref:System.Windows.Trigger> objetos, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
