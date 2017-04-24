---
title: "Aplicar estilos y plantillas | Microsoft Docs"
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
  - "desencadenadores"
  - "estilos de referencia"
  - "desencadenadores de eventos"
  - "estilos de requisitos previos"
  - "estilos, declarar"
  - "estilos, información general"
  - "estilos, extender"
  - "estilos, desencadenadores"
  - "estilos de desencadenadores de eventos"
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Aplicar estilos y plantillas
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]estilos y plantillas que hacen referencia a un conjunto de características (estilos, plantillas, desencadenadores y guiones gráficos) que permiten a los desarrolladores y diseñadores para crear efectos visualmente atractivos y crear una apariencia coherente para su producto. Aunque los desarrolladores y diseñadores pueden personalizar la apariencia ampliamente en la aplicación por aplicación, es necesario para permitir el mantenimiento y el uso compartido de la apariencia dentro y entre las aplicaciones un modelo robusto de estilos y plantillas. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona ese modelo.  
  
 Otra característica de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el modelo de estilo es la separación de la presentación y lógica. Esto significa que los diseñadores pueden trabajar en la apariencia de una aplicación solo mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] al mismo tiempo que los desarrolladores trabajan en la lógica de programación usando C# o Visual Basic.  
  
 Esta información general se centra en los aspectos de estilos y plantillas de la aplicación y no describe los conceptos de enlace de datos. Para obtener información sobre el enlace de datos, consulte [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Además, es importante entender los recursos, que permiten estilos y plantillas que se reutilice. Para obtener más información acerca de los recursos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
   
  
<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Ejemplo de plantillas y estilos  
 Los ejemplos de código utilizados en esta información general se basan en un foto sencilla de ejemplo que se muestra en la siguiente ilustración:  
  
 ![Estilo de ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 Esta foto sencilla de ejemplo usa estilos y plantillas para crear una experiencia de usuario visualmente atractiva. El ejemplo tiene dos <xref:System.Windows.Controls.TextBlock> elementos y un <xref:System.Windows.Controls.ListBox> control que está enlazado a una lista de imágenes. Para obtener un ejemplo completo, vea [Introducción al ejemplo de plantillas y estilos](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Fundamentos de estilos  
 Puede pensar en un <xref:System.Windows.Style> como una manera cómoda para aplicar un conjunto de valores de propiedad a más de un elemento. Por ejemplo, considere el siguiente <xref:System.Windows.Controls.TextBlock> elementos y su apariencia predeterminada:  
  
 [!code-xml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Captura de pantalla de ejemplo de estilo](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")  
  
 Puede cambiar la apariencia predeterminada estableciendo propiedades, como <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A>, en cada <xref:System.Windows.Controls.TextBlock> elemento directamente. Sin embargo, si desea que su <xref:System.Windows.Controls.TextBlock> elementos compartir algunas propiedades, puede crear un <xref:System.Windows.Style> en el `Resources` sección de su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos, como se muestra aquí:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Al establecer el <xref:System.Windows.Style.TargetType%2A> del estilo a la <xref:System.Windows.Controls.TextBlock> tipo, el estilo se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos en la ventana.  
  
 Ahora el <xref:System.Windows.Controls.TextBlock> elementos aparecen como sigue:  
  
 ![Captura de pantalla de ejemplo de estilo](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Extender los estilos  
 Quizás desee que los dos <xref:System.Windows.Controls.TextBlock> elementos compartan algunos valores de propiedad, como el <xref:System.Windows.Controls.Control.FontFamily%2A> y el texto centrado <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, pero también desea que el texto "My Pictures" tenga algunas propiedades adicionales. Puede hacerlo creando un nuevo estilo basado en el primer estilo, como se muestra aquí:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Observe que el estilo anterior tiene un `x:Key`. Para aplicar el estilo, establezca la <xref:System.Windows.FrameworkElement.Style%2A> propiedad en su <xref:System.Windows.Controls.TextBlock> a la `x:Key` de valor, como se muestra aquí:  
  
 [!code-xml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Esto <xref:System.Windows.Controls.TextBlock> estilo tiene ahora un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valor de <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> valor de `Comic Sans MS`, un <xref:System.Windows.Controls.TextBlock.FontSize%2A> valor 26 y un <xref:System.Windows.Controls.TextBlock.Foreground%2A> valor establecido en el <xref:System.Windows.Media.LinearGradientBrush> se muestra en el ejemplo. Observe que invalida el <xref:System.Windows.Controls.Control.FontSize%2A> valor del estilo base. Si hay más de un <xref:System.Windows.Setter> establecen la misma propiedad un <xref:System.Windows.Style>, <xref:System.Windows.Setter> es declarado último tiene prioridad.  
  
 Lo siguiente muestra lo que el <xref:System.Windows.Controls.TextBlock> elementos tener el siguiente aspecto:  
  
 ![Bloques de texto con el estilo](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Esto `TitleText` estilo amplía el estilo que se ha creado para el <xref:System.Windows.Controls.TextBlock> tipo. También puede extender un estilo que tiene un `x:Key` utilizando la `x:Key` valor. Para obtener un ejemplo, vea el ejemplo proporcionado para el <xref:System.Windows.Style.BasedOn%2A> propiedad.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relación de la propiedad TargetType y el atributo x: Key  
 Como se muestra en el primer ejemplo, establecer el <xref:System.Windows.Style.TargetType%2A> propiedad `TextBlock` sin asignar al estilo un `x:Key` hace que el estilo se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos. En este caso, el `x:Key` se establece implícitamente en `{x:Type TextBlock}`. Esto significa que si se establece explícitamente la `x:Key` valor en algo distinto de `{x:Type TextBlock}`, <xref:System.Windows.Style> no se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos automáticamente. En su lugar, debe aplicar el estilo (utilizando el `x:Key` valor) a la <xref:System.Windows.Controls.TextBlock> elementos explícitamente. Si el estilo está en la sección de recursos y no se establece la <xref:System.Windows.Style.TargetType%2A> propiedad en su estilo, a continuación, se debe proporcionar un `x:Key`.  
  
 Además de proporcionar un valor predeterminado para la `x:Key`, <xref:System.Windows.Style.TargetType%2A> propiedad especifica el tipo al que se aplican las propiedades del establecedor. Si no especifica un <xref:System.Windows.Style.TargetType%2A>, debe calificar las propiedades en su <xref:System.Windows.Setter> objetos con un nombre de clase mediante la sintaxis `Property="ClassName.Property"`. Por ejemplo, en lugar de establecer `Property="FontSize"`, debe establecer <xref:System.Windows.Setter.Property%2A> a `"TextBlock.FontSize"` o `"Control.FontSize"`.  
  
 Tenga en cuenta también que muchas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles constan de una combinación de otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles. Si crea un estilo que se aplica a todos los controles de un tipo, podría obtener resultados inesperados. Por ejemplo, si crea un estilo que tiene como destino el <xref:System.Windows.Controls.TextBlock> escriba en un <xref:System.Windows.Window>, el estilo se aplica a todos los <xref:System.Windows.Controls.TextBlock> controles de la ventana, incluso si la <xref:System.Windows.Controls.TextBlock> forme parte de otro control, como un <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Estilos y recursos  
 Puede utilizar un estilo en cualquier elemento que se deriva de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Es la manera más común de declarar un estilo como un recurso en el `Resources` sección un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos, como se muestra en los ejemplos anteriores. Dado que los estilos son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos; donde se declara un estilo afecta a dónde se puede aplicar el estilo. Por ejemplo, si se declara el estilo en el elemento raíz de la definición de aplicación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo, el estilo se puede usar en cualquier parte de la aplicación. Si se crea una aplicación de navegación y se declara el estilo en uno de la aplicación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos, el estilo se pueden usar únicamente en que [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo. Para obtener más información acerca de las reglas para los recursos de ámbito, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Además, puede encontrar más información sobre los estilos y recursos en [recursos y temas compartidos](#styling_themes) más adelante en esta información general.  
  
### <a name="setting-styles-programmatically"></a>Establecer estilos mediante programación  
 Para asignar un estilo con nombre a un elemento mediante programación, obtener el estilo de la colección de recursos y asígnelo al elemento <xref:System.Windows.FrameworkElement.Style%2A> propiedad. Tenga en cuenta que los elementos de una colección de recursos son del tipo <xref:System.Object>. Por lo tanto, debe convertir el estilo recuperado a un <xref:System.Windows.Style> antes de asignarlo a la <xref:System.Windows.FrameworkElement.Style%2A> propiedad. Por ejemplo, para establecer definido `TitleText` estilo en un <xref:System.Windows.Controls.TextBlock> denominado `textblock1`, realice lo siguiente:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Tenga en cuenta que una vez que se ha aplicado un estilo, está sellada y no se puede cambiar. Si desea cambiar dinámicamente un estilo que ya se han aplicado, debe crear un nuevo estilo para reemplazar el existente. Para obtener más información, consulte el <xref:System.Windows.Style.IsSealed%2A> propiedad.  
  
 Puede crear un objeto que se elige un estilo para aplicar en función de lógica personalizada. Para obtener un ejemplo, vea el ejemplo proporcionado para el <xref:System.Windows.Controls.StyleSelector> clase.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Enlaces, los recursos dinámicos y los controladores de eventos  
 Tenga en cuenta que puede utilizar el `Setter.Value` propiedad para especificar un [extensión de marcado Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) o un [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Para obtener más información, vea los ejemplos proporcionados para la <xref:System.Windows.Setter.Value%2A?displayProperty=fullName> propiedad.  
  
 Hasta ahora, esta información general solo trata el uso de establecedores para establecer el valor de propiedad. También puede especificar controladores de eventos en un estilo. Para obtener más información, consulte <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Plantillas de datos  
 En esta aplicación de ejemplo, hay un <xref:System.Windows.Controls.ListBox> control que está enlazado a una lista de fotos:  
  
 [!code-xml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Esto <xref:System.Windows.Controls.ListBox> actualmente el siguiente aspecto:  
  
 ![ListBox antes de aplicar la plantilla](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 Mayoría de los controles tiene algún tipo de contenido y ese contenido suele proceder de datos que va a enlazar. En este ejemplo, los datos están la lista de fotos. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], utiliza un <xref:System.Windows.DataTemplate> para definir la representación visual de los datos. Básicamente, lo que se incluye en un <xref:System.Windows.DataTemplate> determina el aspecto de los datos en la aplicación representada.  
  
 En nuestra aplicación de ejemplo, cada personalizada `Photo` objeto tiene una `Source` propiedad de tipo string que especifica la ruta de acceso de la imagen. Actualmente, los objetos de la foto aparecen como rutas de acceso de archivo.  
  
 Las fotos aparezcan como imágenes, crear un <xref:System.Windows.DataTemplate> como un recurso:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Observe que la <xref:System.Windows.DataTemplate.DataType%2A> propiedad es muy similar a la <xref:System.Windows.Style.TargetType%2A> propiedad de la <xref:System.Windows.Style>. Si su <xref:System.Windows.DataTemplate> está en la sección de recursos, cuando se especifica la <xref:System.Windows.DataTemplate.DataType%2A> propiedad a un tipo y no asignarle un `x:Key`, el <xref:System.Windows.DataTemplate> se aplica siempre que aparezca ese tipo. Siempre tiene la opción para asignar la <xref:System.Windows.DataTemplate> con una `x:Key` y establézcalo como un `StaticResource` para propiedades que toman <xref:System.Windows.DataTemplate> tipos, como la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad o <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
 Básicamente, el <xref:System.Windows.DataTemplate> en el ejemplo anterior define que siempre que hay un `Photo` objeto, debe aparecer como una <xref:System.Windows.Controls.Image> dentro de un <xref:System.Windows.Controls.Border>. Con este <xref:System.Windows.DataTemplate>, nuestra aplicación ahora tiene el siguiente aspecto:  
  
 ![Imagen fotográfica](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 El modelo de plantillas de datos proporciona otras características. Por ejemplo, si se muestran datos de colección que contengan otras colecciones con un <xref:System.Windows.Controls.HeaderedItemsControl> escriba como un <xref:System.Windows.Controls.Menu> o un <xref:System.Windows.Controls.TreeView>, existe la <xref:System.Windows.HierarchicalDataTemplate>. Otra característica de plantillas de datos es el <xref:System.Windows.Controls.DataTemplateSelector>, que le permite elegir un <xref:System.Windows.DataTemplate> a utilizar basándose en una lógica personalizada. Para obtener más información, consulte [información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md), que proporciona una explicación más detallada de las características de creación de plantillas de datos diferentes.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Plantillas de control  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> de un control define la apariencia del control. Puede cambiar la estructura y la apariencia de un control definiendo un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control. En muchos casos, esto ofrece suficiente flexibilidad para que no tiene que escribir sus propios controles personalizados. Para obtener más información, consulte [personalizar la apariencia de un Control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Desencadenadores  
 Un desencadenador establece propiedades o acciones, como una animación, inicia cuando cambia un valor de propiedad o cuando se genera un evento. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, y <xref:System.Windows.DataTemplate> todos tienen un `Triggers` propiedad que puede contener un conjunto de desencadenadores. Existen varios tipos de desencadenadores.  
  
### <a name="property-triggers"></a>Desencadenadores de propiedad  
 Un <xref:System.Windows.Trigger> valores de propiedad de conjuntos, o inicia acciones en función del valor de una propiedad se llama a un desencadenador de propiedad.  
  
 Para demostrar cómo usar desencadenadores de propiedad, puede hacer cada uno <xref:System.Windows.Controls.ListBoxItem> parcialmente transparente a menos que está seleccionado. El siguiente estilo establece la <xref:System.Windows.UIElement.Opacity%2A> valor de un <xref:System.Windows.Controls.ListBoxItem> a `0.5`. Cuando el <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> propiedad es `true`, sin embargo, el <xref:System.Windows.UIElement.Opacity%2A> está establecido en `1.0`:  
  
 [!code-xml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 Este ejemplo utiliza un <xref:System.Windows.Trigger> para configurar un valor de propiedad, pero tenga en cuenta que el <xref:System.Windows.Trigger> clase también tiene la <xref:System.Windows.TriggerBase.EnterActions%2A> y <xref:System.Windows.TriggerBase.ExitActions%2A> propiedades que permiten a un desencadenador realizar acciones.  
  
 Observe que la <xref:System.Windows.FrameworkElement.MaxHeight%2A> propiedad de la <xref:System.Windows.Controls.ListBoxItem> está establecido en `75`. En la siguiente ilustración, el tercer elemento es el elemento seleccionado:  
  
 ![Estilo de ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTriggers y guiones gráficos  
 Otro tipo de desencadenador es el <xref:System.Windows.EventTrigger>, lo que inicia un conjunto de acciones en función de la aparición de un evento. Por ejemplo, la siguiente <xref:System.Windows.EventTrigger> objetos especifican que, cuando el puntero del mouse entra en el <xref:System.Windows.Controls.ListBoxItem>, el <xref:System.Windows.FrameworkElement.MaxHeight%2A> propiedad anima a un valor de `90` sobre un `0.2` segundo período. Cuando se desplaza el mouse fuera del elemento, la propiedad devuelve el valor original durante un período de `1` segundo. Tenga en cuenta cómo no es necesario especificar un <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valor para el <xref:System.Windows.ContentElement.MouseLeave> animación. Esto es porque la animación es capaz de realizar un seguimiento del valor original.  
  
 [!code-xml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Para obtener más información, consulte el [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 En la siguiente ilustración, el mouse está señalando el tercer elemento:  
  
 ![Captura de pantalla de ejemplo de estilo](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger y MultiDataTrigger  
 Además <xref:System.Windows.Trigger> y <xref:System.Windows.EventTrigger>, hay otros tipos de desencadenadores. <xref:System.Windows.MultiTrigger> permite establecer valores de propiedad según varias condiciones. Utiliza <xref:System.Windows.DataTrigger> y <xref:System.Windows.MultiDataTrigger> cuando la propiedad de la condición está enlazada a datos.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Recursos y temas compartidos  
 Una típica [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicación podría tener varios recursos de interfaz de usuario que se aplican en toda la aplicación. Colectivamente, este conjunto de recursos puede considerarse el tema para la aplicación. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]proporciona compatibilidad para usuario empaquetar recursos de la interfaz (IU) como un tema usando un diccionario de recursos que se encapsula como la <xref:System.Windows.ResourceDictionary> clase.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]los temas se definen mediante el mecanismo de estilos y plantillas que [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] expone para personalizar los efectos visuales de cualquier elemento.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]los recursos de tema se almacenan en diccionarios de recursos incrustados. Estos diccionarios de recursos deben estar incrustados en un ensamblado firmado y pueden incrustarse en el mismo ensamblado que el propio código o en un ensamblado en paralelo. En el caso de PresentationFramework.dll, el ensamblado que contiene [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] controles, recursos de tema que se encuentran en una serie de ensamblados en paralelo.  
  
 El tema se convierte en el último lugar para buscar al buscar el estilo de un elemento. Normalmente, la búsqueda comenzará por recorrer el árbol de elementos, buscar un recurso adecuado, a continuación, buscar en la colección de recursos de aplicación y finalmente, consultar el sistema. Esto proporciona a los desarrolladores de aplicaciones una oportunidad para volver a definir el estilo de cualquier objeto en el nivel de árbol o de aplicación antes de alcanzar el tema.  
  
 Puede definir los diccionarios de recursos como archivos individuales que permiten reutilizar un tema en varias aplicaciones. También puede crear temas intercambiables definiendo varios diccionarios de recursos que proporcionen los mismos tipos de recursos, pero con valores diferentes. Redefinir estos estilos u otros recursos en el nivel de aplicación es el enfoque recomendado para la aplicación de aspectos de una aplicación.  
  
 Para compartir un conjunto de recursos, incluidos los estilos y plantillas, entre las aplicaciones, puede crear un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos y definir una <xref:System.Windows.ResourceDictionary>. Por ejemplo, eche un vistazo en la ilustración siguiente se muestra parte de la [estilo with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041):  
  
 ![Ejemplos de la plantilla del control](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Si observa la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos en el ejemplo, observará que todos los archivos tienen lo siguiente:  
  
 [!code-xml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Es el uso compartido de `shared.xaml`, que define un <xref:System.Windows.ResourceDictionary> que contiene un conjunto de recursos de estilo y pincel que permite a los controles del ejemplo tengan una apariencia coherente.  
  
 Para obtener más información, consulte [combinan los diccionarios de recursos](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Si está creando un tema para su control personalizado, vea la sección de la biblioteca de controles externos de la [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Empaquetar a URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Cómo: buscar elementos generados por el ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Buscar elementos generados por el DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)