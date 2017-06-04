---
title: "Informaci&#243;n general sobre objetos Storyboard | Microsoft Docs"
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
  - "sintaxis de guión gráfico"
  - "sintaxis, Guión gráfico"
  - "Escalas de tiempo"
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Informaci&#243;n general sobre objetos Storyboard
En este tema se muestra cómo utilizar objetos <xref:System.Windows.Media.Animation.Storyboard> para organizar y aplicar animaciones.  Se describe cómo manipular interactivamente los objetos <xref:System.Windows.Media.Animation.Storyboard> y la sintaxis de establecimiento indirecto de propiedades de destino.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de animaciones y sus características básicas.  Para obtener una introducción a la animación, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  También debe saber utilizar las propiedades asociadas.  Para obtener más información sobre propiedades asociadas, consulte [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## ¿Qué es un guión gráfico?  
 Las animaciones no son el único tipo útil de escala de tiempo.  Se proporcionan otras clases de escalas de tiempo para ayudarle a organizar conjuntos de escalas de tiempo y para aplicar las escalas de tiempo a las propiedades.  Las escalas de tiempo contenedoras se derivan de la clase <xref:System.Windows.Media.Animation.TimelineGroup>, e incluyen <xref:System.Windows.Media.Animation.ParallelTimeline> y <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Un objeto <xref:System.Windows.Media.Animation.Storyboard> es un tipo de escala de tiempo contenedora que proporciona información de destino para las escalas de tiempo que contiene.  Un guión gráfico puede contener cualquier tipo de <xref:System.Windows.Media.Animation.Timeline>, incluso otras escalas de tiempo contenedoras y animaciones.  Los objetos <xref:System.Windows.Media.Animation.Storyboard> permiten combinar escalas de tiempo que afectan a diversos objetos y propiedades en un solo árbol de escalas de tiempo, lo que facilita la organización y el control de comportamientos de control de tiempo complejos.  Por ejemplo, supongamos que desea un botón que haga estas tres cosas.  
  
-   Aumentar de tamaño y cambiar de color cuando el usuario selecciona el botón.  
  
-   Disminuir de tamaño y volver a su tamaño original cuando se hace clic en él.  
  
-   Disminuir de tamaño y desvanecerse con un fundido al 50% de opacidad al deshabilitarse.  
  
 En este caso, tenemos varios conjuntos de animaciones que se aplican al mismo objeto, y hay que reproducirlas en distintos momentos, según cuál sea el estado del botón.  Los objetos <xref:System.Windows.Media.Animation.Storyboard> permiten organizar las animaciones y aplicarlas en grupos a uno o más objetos.  
  
<a name="wherecanyouuseastoryboard"></a>   
## ¿Dónde se puede utilizar un guión gráfico?  
 Un <xref:System.Windows.Media.Animation.Storyboard> se utiliza para animar [propiedades de dependencia](GTMT) de clases que se pueden animar \(para obtener más información sobre qué hace que una clase pueda animar, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)\).  Sin embargo, al ser la creación de guiones gráficos una característica del marco de trabajo, el objeto debe pertenecer al <xref:System.Windows.NameScope> de <xref:System.Windows.FrameworkElement> o de <xref:System.Windows.FrameworkContentElement>.  
  
 Por ejemplo, puede utilizar <xref:System.Windows.Media.Animation.Storyboard> para hacer lo siguiente:  
  
-   Animar un <xref:System.Windows.Media.SolidColorBrush> \(elemento que no es de marco\) que pinta el fondo de un botón \(un tipo de <xref:System.Windows.FrameworkElement>\)  
  
-   Animar un <xref:System.Windows.Media.SolidColorBrush> \(elemento que no es de marco\) que pinta el relleno de un <xref:System.Windows.Media.GeometryDrawing> \(elemento que no es de marco\) mostrado mediante una <xref:System.Windows.Controls.Image> \(<xref:System.Windows.FrameworkElement>\).  
  
-   Mediante código, animar un <xref:System.Windows.Media.SolidColorBrush> declarado por una clase que también contiene un <xref:System.Windows.FrameworkElement>, si <xref:System.Windows.Media.SolidColorBrush> ha registrado su nombre con <xref:System.Windows.FrameworkElement>.  
  
 Sin embargo, no se puede utilizar un <xref:System.Windows.Media.Animation.Storyboard> para animar un <xref:System.Windows.Media.SolidColorBrush> que no ha registrado su nombre con un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o que no se ha utilizado para establecer una propiedad de un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## Cómo aplicar animaciones mediante un guión gráfico  
 Si desea utilizar <xref:System.Windows.Media.Animation.Storyboard> para organizar y aplicar animaciones, agregue las animaciones como escalas de tiempo secundarias de <xref:System.Windows.Media.Animation.Storyboard>.  La clase <xref:System.Windows.Media.Animation.Storyboard> proporciona las propiedades asociadas <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName>.  Se establecen estas propiedades de una animación para especificar su objeto y propiedad de destino.  
  
 Para aplicar animaciones a sus destinos, se comienza el <xref:System.Windows.Media.Animation.Storyboard> utilizando una acción desencadenante o un método.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se usa un objeto <xref:System.Windows.Media.Animation.BeginStoryboard> con un <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger> o <xref:System.Windows.DataTrigger>.  En el código, puede utilizar también el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 En la tabla siguiente se muestran los distintos espacios en que se admite cada técnica de comienzo de <xref:System.Windows.Media.Animation.Storyboard>: por instancia, estilo, plantilla de control y plantilla de datos. "  Por instancia" se refiere a la técnica de aplicar directamente una animación o un guión gráfico a las instancias de un objeto, en lugar de un estilo, una plantilla de control o una plantilla de datos.  
  
|El guión gráfico se comienza utilizando…|Por instancia|Estilo|Plantilla de control|Plantilla de datos|Ejemplo|  
|----------------------------------------------|-------------------|------------|--------------------------|------------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y <xref:System.Windows.EventTrigger>|Sí|Sí|Sí|Sí|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y un <xref:System.Windows.Trigger> de propiedad|No|Sí|Sí|Sí|[Activar una animación al cambiar el valor de una propiedad](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> y <xref:System.Windows.DataTrigger>|No|Sí|Sí|Sí|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/es-es/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sí|No|No|No|[Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.FrameworkElement.Width%2A> de un elemento <xref:System.Windows.Shapes.Rectangle> y <xref:System.Windows.Media.SolidColorBrush.Color%2A> de <xref:System.Windows.Media.SolidColorBrush> utilizado para pintar <xref:System.Windows.Shapes.Rectangle>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 En las secciones siguientes se describen las propiedades asociadas <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> con mayor detalle.  
  
<a name="targetingelementsandfreezables"></a>   
## Establecer como destino elementos de marco, elementos de contenido de marco y elementos inmovilizables  
 En la sección anterior se menciona que, para que una animación encuentre su destino, debe conocer el nombre del mismo y la propiedad que debe animar.  Especificar la propiedad que se va a animar es sencillo: basta con establecer <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName> en el nombre de la propiedad que se va a animar.  Para especificar el nombre del objeto cuya la propiedad se desea animar se establece la propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> de la animación.  
  
 Para que la propiedad <xref:System.Windows.Setter.TargetName%2A> funcione, el objeto de destino debe tener nombre.  Asignar un nombre a un <xref:System.Windows.FrameworkElement> o a un <xref:System.Windows.FrameworkContentElement> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es distinto que asignar un nombre a un objeto <xref:System.Windows.Freezable>.  
  
 Los elementos de marco son las clases que heredan de la clase <xref:System.Windows.FrameworkElement>.  Ejemplos de elementos de marco son <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button> y <xref:System.Windows.Shapes.Rectangle>.  En esencia, todas las ventanas, los paneles y los controles son elementos.  Los elementos de contenido de marco son las clases que heredan de la clase <xref:System.Windows.FrameworkContentElement>.  Ejemplos de elementos de contenido de marco son <xref:System.Windows.Documents.FlowDocument> y <xref:System.Windows.Documents.Paragraph>.  Si no está seguro de si un tipo es un elemento de marco o un elemento de contenido de marco, compruebe si tiene una propiedad Name.  Si la tiene, probablemente sea un elemento de marco o un elemento de contenido de marco.  Para estar seguro, compruebe la sección de jerarquía de herenciade su página de tipo.  
  
 Para habilitar el establecimiento de destinos de un elemento de marco o un elemento de contenido de marco en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se establece su propiedad <xref:System.Windows.FrameworkElement.Name%2A>.  En el código también es preciso usar el método <xref:System.Windows.NameScope.RegisterName%2A> para registrar el nombre del elemento en el elemento para el que se ha creado un <xref:System.Windows.NameScope>.  
  
 En el ejemplo siguiente, tomado del ejemplo anterior, se asigna el nombre `MyRectangle` a un <xref:System.Windows.Shapes.Rectangle>, un tipo de <xref:System.Windows.FrameworkElement>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Una vez que tenga un nombre, puede animar una propiedad de ese elemento.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 Los tipos <xref:System.Windows.Freezable> son las clases que heredan de la clase <xref:System.Windows.Freezable>.  Ejemplos de elementos inmovilizables \(objetos <xref:System.Windows.Freezable>\) incluyen <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform> y <xref:System.Windows.Media.GradientStop>.  
  
 Para habilitar el establecimiento de destinos de un objeto <xref:System.Windows.Freezable> por parte de una animación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se emplea [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md) para asignarle un nombre.  En el código, también se usa el método <xref:System.Windows.NameScope.RegisterName%2A> para registrar su nombre en el elemento para el que se ha creado un <xref:System.Windows.NameScope>.  
  
 En el ejemplo siguiente se asigna un nombre a un objeto <xref:System.Windows.Freezable>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 A continuación, ya se puede establecer el objeto como destino de una animación.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 Los objetos <xref:System.Windows.Media.Animation.Storyboard> utilizan ámbitos de nombres para resolver la propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>.  Para obtener más información ámbitos de nombres en WPF, consulte [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  Si se omite la propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>, la animación establece como destino el elemento en el que se define o, en el caso de los estilos, el elemento al que se aplica el estilo.  
  
 A veces, no se puede asignar un nombre a un objeto <xref:System.Windows.Freezable>.  Por ejemplo, si un objeto <xref:System.Windows.Freezable> se declara como recurso o se utiliza para establecer el valor de una propiedad de un estilo, no se le puede asignar un nombre.  Al no tener nombre, no se puede establecer como destino directamente, pero sí de manera indirecta.  En las secciones siguientes se describe cómo utilizar el establecimiento indirecto de destinos.  
  
<a name="pathsyntaxforchangeable"></a>   
## Establecimiento indirecto de destinos  
 Existen ocasiones en que una animación no puede establecer directamente un objeto <xref:System.Windows.Freezable> como destino, como cuando el objeto <xref:System.Windows.Freezable> se declara como recurso o se utiliza para establecer el valor de una propiedad en un estilo.  En estos casos, aunque no se puede establecer como destino directamente, el objeto <xref:System.Windows.Freezable> se puede animar.  En lugar de establecer la propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> con el nombre de <xref:System.Windows.Freezable>, se establece en el nombre del elemento al que "pertenece" el objeto <xref:System.Windows.Freezable>. Por ejemplo, <xref:System.Windows.Media.SolidColorBrush> utilizado para establecer la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo pertenece a ese rectángulo.  Para animar el pincel, se establece la propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> de la animación con una cadena de propiedades que se inicia con la propiedad del elemento de marco o elemento de contenido de marco para cuyo establecimiento se ha utilizado el objeto <xref:System.Windows.Freezable> y que finaliza con la propiedad de <xref:System.Windows.Freezable> que se desea animar.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Tenga en cuenta que, si se inmoviliza <xref:System.Windows.Freezable>, se crea un clon y se anima ese clon.  Cuando esto sucede, la propiedad <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> del objeto original continúa devolviendo `false`, porque en realidad el objeto original no se anima.  Para obtener más información sobre la clonación, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Además, tenga en cuenta que, al utilizar el establecimiento indirecto de propiedades de destino, es posible establecer como destino objetos que no existen.  Por ejemplo, podría suponer que la propiedad <xref:System.Windows.Controls.Control.Background%2A> de un botón determinado se ha establecido mediante un pincel <xref:System.Windows.Media.SolidColorBrush> e intentar animar el color, aunque en realidad se ha utilizado un pincel <xref:System.Windows.Media.LinearGradientBrush> establecer el fondo del botón.  En estos casos, no se inicia ninguna excepción; la animación no tiene ningún efecto visible porque <xref:System.Windows.Media.LinearGradientBrush> no reacciona a los cambios de la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A>.  
  
 En las secciones siguientes se describe con mayor detalle la sintaxis de establecimiento indirecto de propiedades de destino.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable en XAML  
 Para establecer como destino una propiedad de un objeto inmovilizable en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se utiliza la sintaxis siguiente.  
  
||  
|-|  
|*ElementPropertyName*`.`*FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* es la propiedad de <xref:System.Windows.FrameworkElement> que se establece mediante <xref:System.Windows.Freezable> y  
  
-   *FreezablePropertyName* es la propiedad de <xref:System.Windows.Freezable> que se va a animar.  
  
 En el código siguiente se muestra cómo animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> que se utiliza para establecer el  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo.  
  
  
  
 En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz.  
  
 Para establecer como destino un objeto inmovilizable contenido en una colección, se utiliza la sintaxis de ruta de acceso siguiente.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Donde *CollectionIndex* es el índice del objeto en su matriz o colección.  
  
 Por ejemplo, supongamos que un rectángulo tiene un recurso <xref:System.Windows.Media.TransformGroup> aplicado a su propiedad <xref:System.Windows.UIElement.RenderTransform%2A>, y que desea animar una de las transformaciones que contiene.  
  
  
  
 En el código siguiente se muestra cómo animar la propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform> mostrada en el ejemplo anterior.  
  
  
  
<a name="targetingpropertyofchangeableincode"></a>   
### Establecer de manera indirecta una propiedad de destino de un objeto inmovilizable mediante código  
 En el código, se crea un objeto <xref:System.Windows.PropertyPath>.  Al crear <xref:System.Windows.PropertyPath>, se especifican las propiedades <xref:System.Windows.PropertyPath.Path%2A> y <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Para crear <xref:System.Windows.PropertyPath.PathParameters%2A>, se crea una matriz de tipo <xref:System.Windows.DependencyProperty> que contiene una lista de campos de identificadores de propiedades de dependencia.  El primer campo de identificador es para la propiedad de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> que se establecen mediante <xref:System.Windows.Freezable>.  El campo de identificador siguiente representa la propiedad de <xref:System.Windows.Freezable> que se establece como destino.  Piense en ello como una cadena de propiedades que conecta el objeto <xref:System.Windows.Freezable> al objeto <xref:System.Windows.FrameworkElement>.  
  
 A continuación se muestra ejemplo de cadena de propiedades de dependencia que establecen como destino el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> utilizado para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 También es preciso especificar una <xref:System.Windows.PropertyPath.Path%2A>.  Una <xref:System.Windows.PropertyPath.Path%2A> es una <xref:System.String> que indica a <xref:System.Windows.PropertyPath.Path%2A> cómo debe interpretar sus <xref:System.Windows.PropertyPath.PathParameters%2A>.  Utiliza la sintaxis siguiente.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(`*FreezablePropertyArrayIndex*`)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* es el índice de la matriz de <xref:System.Windows.DependencyProperty> que contiene el identificador de la propiedad del objeto <xref:System.Windows.FrameworkElement> que se establece mediante <xref:System.Windows.Freezable> y  
  
-   *FreezablePropertyArrayIndex* es el índice de la matriz de <xref:System.Windows.DependencyProperty> que contiene el identificador de la propiedad que se establece como destino.  
  
 En el ejemplo siguiente se muestra la <xref:System.Windows.PropertyPath.Path%2A> que acompañaría a los <xref:System.Windows.PropertyPath.PathParameters%2A> definidos en el ejemplo anterior.  
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 En el ejemplo siguiente se combina el código de los ejemplos anteriores para animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> utilizado para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> de un elemento de rectángulo.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 En ocasiones, es preciso establecer como destino un objeto inmovilizable contenido en una colección o matriz.  Por ejemplo, supongamos que un rectángulo tiene un recurso <xref:System.Windows.Media.TransformGroup> aplicado a su propiedad <xref:System.Windows.UIElement.RenderTransform%2A>, y que desea animar una de las transformaciones que contiene.  
  
 [!code-xml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Para establecer como destino un objeto <xref:System.Windows.Freezable> contenido en una colección, se utiliza la sintaxis de ruta de acceso siguiente.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(` *CollectionChildrenPropertyArrayIndex*`)` `[`*CollectionIndex* `].(`*FreezablePropertyArrayIndex*`)`|  
  
 Donde *CollectionIndex* es el índice del objeto en su matriz o colección.  
  
 Para establecer como destino la propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A> de <xref:System.Windows.Media.RotateTransform>, la segunda transformación de <xref:System.Windows.Media.TransformGroup>, se utilizan la <xref:System.Windows.PropertyPath.Path%2A> y los <xref:System.Windows.PropertyPath.PathParameters%2A> siguientes.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 En el ejemplo siguiente se muestra el código completo para animar el <xref:System.Windows.Media.RotateTransform.Angle%2A> de una <xref:System.Windows.Media.RotateTransform> contenida en un <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### Establecimiento indirecto de destinos con un objeto inmovilizable como punto de partida  
 En las secciones anteriores se ha descrito cómo establecer indirectamente un objeto <xref:System.Windows.Freezable> como destino comenzando por un <xref:System.Windows.FrameworkElement> o un <xref:System.Windows.FrameworkContentElement> y creando una cadena de propiedades a una subpropiedad de <xref:System.Windows.Freezable>.  También se puede utilizar un objeto <xref:System.Windows.Freezable> como punto de partida y establecer indirectamente como destino una de las subpropiedades de <xref:System.Windows.Freezable>.  Cuando se utiliza un objeto <xref:System.Windows.Freezable> como punto de partida para el establecimiento indirecto de destinos se aplica una restricción adicional: el objeto <xref:System.Windows.Freezable> inicial y todos los objetos <xref:System.Windows.Freezable> entre éste y la subpropiedad establecida indirectamente como destino no pueden estar inmovilizados.  
  
<a name="controllable_storyboards"></a>   
## Controlar guiones gráficos de forma interactiva en XAML  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], use una acción de desencadenador <xref:System.Windows.Media.Animation.BeginStoryboard>.  <xref:System.Windows.Media.Animation.BeginStoryboard> distribuye las animaciones a los objetos y las propiedades que se animan y, a continuación, inicia el guión gráfico.  \(Para obtener información detallada acerca de este proceso, consulte [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).\) Si asigna un nombre a <xref:System.Windows.Media.Animation.BeginStoryboard> especificando su propiedad <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>, lo convierte en un guión gráfico controlable.  A continuación, podrá controlar interactivamente el guión gráfico una vez iniciado.  Ésta es una lista de acciones de guión gráfico controlables que se utiliza con desencadenadores de eventos para controlar un guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: pone en pausa el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: reanuda un guión gráfico que se ha puesto en pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: cambia la velocidad del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: avanza un guión gráfico hasta el final de su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: quita el guión gráfico.  
  
 En el ejemplo siguiente se utilizan acciones para controlar interactivamente un guión gráfico.  
  
 [!code-xml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## Controlar interactivamente un guión gráfico mediante código  
 En los ejemplos anteriores se muestra cómo animar mediante acciones desencadenantes.  En el código, también puede controlar un guión gráfico mediante los métodos interactivos de la clase <xref:System.Windows.Media.Animation.Storyboard>.  Para que un <xref:System.Windows.Media.Animation.Storyboard> sea interactivo en el código, debe utilizar la sobrecarga apropiada del método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> del guión gráfico y especificar `true` para que sea controlable.  Para obtener más información, consulte <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.  
  
 En la lista siguiente se muestran los métodos que se pueden utilizar para manipular <xref:System.Windows.Media.Animation.Storyboard> después de haberse iniciado:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 La ventaja de utilizar estos métodos es que no es preciso crear objetos <xref:System.Windows.Trigger> o <xref:System.Windows.TriggerAction>; únicamente se necesita una referencia al <xref:System.Windows.Media.Animation.Storyboard> controlable que desea manipular.  
  
 **Nota:** todas las acciones interactivas llevadas a cabo sobre un objeto <xref:System.Windows.Media.Animation.Clock> y, por tanto, sobre un objeto <xref:System.Windows.Media.Animation.Storyboard>, se producen en el siguiente paso del motor de control de tiempo, lo que tiene lugar un poco antes de que se produzca la siguiente representación.  Por ejemplo, si utiliza el método <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> para saltar a otro punto de una animación, el valor de propiedad no cambia al instante, más bien, el valor cambia en el paso siguiente del motor de control de tiempo.  
  
 En el ejemplo siguiente se muestra cómo aplicar y controlar animaciones mediante los métodos interactivos de la clase <xref:System.Windows.Media.Animation.Storyboard>.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## Animar en un estilo  
 Puede utilizar los objetos <xref:System.Windows.Media.Animation.Storyboard> para definir animaciones en una <xref:System.Windows.Style>.  Animar con un <xref:System.Windows.Media.Animation.Storyboard> en un <xref:System.Windows.Style> es similar a utilizar un <xref:System.Windows.Media.Animation.Storyboard> en otros objetos, con las tres excepciones siguientes:  
  
-   No se especifica un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; <xref:System.Windows.Media.Animation.Storyboard> siempre establece como destino el elemento al que se aplica el <xref:System.Windows.Style>.  Para establecer como destino objetos <xref:System.Windows.Freezable>, debe utilizar el establecimiento indirecto de destinos.  Para obtener más información sobre el establecimiento indirecto de destinos, consulte la sección [Establecimiento indirecto de destinos](#pathsyntaxforchangeable).  
  
-   No se puede especificar un <xref:System.Windows.EventTrigger.SourceName%2A> para un <xref:System.Windows.EventTrigger> o un <xref:System.Windows.Trigger>.  
  
-   No se pueden utilizar referencias de recursos dinámicos ni expresiones de enlace de datos para establecer <xref:System.Windows.Media.Animation.Storyboard> o valores de propiedades de animación.  Esto se debe a que todo lo que esté dentro de un <xref:System.Windows.Style> debe ser seguro para subprocesos y el sistema de control de tiempo debe inmovilizar \(<xref:System.Windows.Freezable.Freeze%2A>\) los objetos <xref:System.Windows.Media.Animation.Storyboard> a fin de hacerlos seguros para subprocesos.  No se puede inmovilizar un <xref:System.Windows.Media.Animation.Storyboard> si éste o sus escalas de tiempo secundarias contienen referencias de recursos dinámicos o expresiones de enlace de datos.  Para obtener más información sobre la inmovilización y otras características de <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se pueden declarar controladores de eventos para <xref:System.Windows.Media.Animation.Storyboard> ni eventos de animación.  
  
 Para obtener un ejemplo en el que se muestra cómo definir un guión gráfico en un estilo, consulte el ejemplo [Animar en un estilo](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md).  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## Animar en una ControlTemplate  
 Puede utilizar los objetos <xref:System.Windows.Media.Animation.Storyboard> para definir animaciones en una <xref:System.Windows.Controls.ControlTemplate>.  Animar con un <xref:System.Windows.Media.Animation.Storyboard> en una <xref:System.Windows.Controls.ControlTemplate> es similar a utilizar un <xref:System.Windows.Media.Animation.Storyboard> en otros objetos, con las dos excepciones siguientes:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> sólo puede hacer referencia a los objetos secundarios de <xref:System.Windows.Controls.ControlTemplate>.  Si no se especifica <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>, la animación establece como destino el elemento al que se aplica <xref:System.Windows.Controls.ControlTemplate>.  
  
-   El <xref:System.Windows.EventTrigger.SourceName%2A> de un <xref:System.Windows.EventTrigger> o de un <xref:System.Windows.Trigger> únicamente puede hacer referencia a objetos secundarios de <xref:System.Windows.Controls.ControlTemplate>.  
  
-   No se pueden utilizar referencias de recursos dinámicos ni expresiones de enlace de datos para establecer <xref:System.Windows.Media.Animation.Storyboard> o valores de propiedades de animación.  Esto se debe a que todo lo que esté dentro de un <xref:System.Windows.Controls.ControlTemplate> debe ser seguro para subprocesos y el sistema de control de tiempo debe inmovilizar \(<xref:System.Windows.Freezable.Freeze%2A>\) los objetos <xref:System.Windows.Media.Animation.Storyboard> a fin de hacerlos seguros para subprocesos.  No se puede inmovilizar un <xref:System.Windows.Media.Animation.Storyboard> si éste o sus escalas de tiempo secundarias contienen referencias de recursos dinámicos o expresiones de enlace de datos.  Para obtener más información sobre la inmovilización y otras características de <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se pueden declarar controladores de eventos para <xref:System.Windows.Media.Animation.Storyboard> ni eventos de animación.  
  
 Para obtener un ejemplo en el que se muestra cómo definir un guión gráfico en una <xref:System.Windows.Controls.ControlTemplate>, consulte el ejemplo [Animar en un ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## Animar cambia el valor de una propiedad  
 En los estilos y las plantillas de control, puede utilizar objetos Trigger para iniciar un guión gráfico cuando cambia una propiedad.  Para obtener ejemplos, vea [Activar una animación al cambiar el valor de una propiedad](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) y [Animar en un ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Las animaciones aplicadas por objetos <xref:System.Windows.Trigger> de propiedad se comportan de un modo más complejo que las animaciones de <xref:System.Windows.EventTrigger> o que aquéllas que se inician mediante métodos de <xref:System.Windows.Media.Animation.Storyboard>.  Se "continúan" con animaciones definidas por otros objetos <xref:System.Windows.Trigger>, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)