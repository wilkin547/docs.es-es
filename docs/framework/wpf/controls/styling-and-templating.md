---
title: Aplicar estilos y plantillas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- triggers [WPF]
- styles [WPF], referencing
- event triggers [WPF]
- styles [WPF], prerequisites
- styles [WPF], declaring
- styles [WPF], overview
- styles [WPF], extending
- styles [WPF], triggers
- styles [WPF], event triggers
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
ms.openlocfilehash: bc77d6e32588f48d3a4e0dd841b98b8bc65ea4f5
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055331"
---
# <a name="styling-and-templating"></a>Aplicar estilos y plantillas
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicar estilos y plantillas que hacen referencia a un conjunto de características (estilos, plantillas, desencadenadores y guiones gráficos) que permite a los desarrolladores y diseñadores crear efectos visualmente atractivos y para crear una apariencia coherente para su producto. Aunque los desarrolladores y los diseñadores pueden personalizar muchas apariencias aplicación por aplicación, es necesario un modelo de aplicación de estilos y plantillas para el mantenimiento y el uso compartido de la apariencia entre las distintas aplicaciones. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece ese modelo.  
  
 Otra característica del modelo de aplicación de estilos y plantillas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es la separación de la presentación y la lógica. Esto significa que los diseñadores pueden trabajar en la apariencia de una aplicación solo con usar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mientras los desarrolladores trabajan en la lógica de programación con C# o Visual Basic.  
  
 Esta información general se centra en los aspectos de los estilos y las plantillas de la aplicación y no abarca los conceptos de enlace de datos. Para información sobre el enlace de datos, consulte [Data Binding Overview](../data/data-binding-overview.md) (Introducción al enlace de datos).  
  
 Además, es importante entender los recursos, gracias a los cuales se pueden reutilizar los estilos y las plantillas. Para más información acerca de los recursos, consulte [XAML Resources](../advanced/xaml-resources.md) (Recursos de XAML).

<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Ejemplo de aplicación de estilos y plantillas  
 Los ejemplos de código de esta introducción se basan en la sencilla foto de ejemplo de la siguiente ilustración:  
  
 ![ListView con estilo](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 En esta sencilla foto de ejemplo se aplican estilos y plantillas para crear una experiencia de usuario visualmente atractiva. El ejemplo tiene dos <xref:System.Windows.Controls.TextBlock> elementos y un <xref:System.Windows.Controls.ListBox> control que está enlazado a una lista de imágenes. Para el ejemplo completo, consulte [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Conceptos básicos del estilo  
 Se puede considerar un <xref:System.Windows.Style> como una manera cómoda para aplicar un conjunto de valores de propiedad a más de un elemento. Por ejemplo, considere la siguiente <xref:System.Windows.Controls.TextBlock> elementos y su apariencia predeterminada:  
  
 [!code-xaml[StylingIntroSample_snippet#TextBlocks](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](./media/stylingintro-textblocksbefore.PNG "StylingIntro_TextBlocksBefore")  
  
 Puede cambiar la apariencia predeterminada estableciendo las propiedades, como <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A>, en cada <xref:System.Windows.Controls.TextBlock> directamente el elemento. Sin embargo, si desea que su <xref:System.Windows.Controls.TextBlock> elementos que se van a compartir algunas propiedades, puede crear un <xref:System.Windows.Style> en el `Resources` sección de su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos, como se muestra aquí:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb1](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Al establecer el <xref:System.Windows.Style.TargetType%2A> de su estilo para el <xref:System.Windows.Controls.TextBlock> tipo, el estilo se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos en la ventana.  
  
 Ahora el <xref:System.Windows.Controls.TextBlock> elementos aparecerán como sigue:  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](./media/stylingintro-textblocksbasestyle.PNG "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Ampliación de los estilos  
 Quizás desee que los dos <xref:System.Windows.Controls.TextBlock> elementos compartan algunos valores de propiedad, como el <xref:System.Windows.Controls.Control.FontFamily%2A> y el texto centrado <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, pero también desea que el texto "My Pictures" tenga propiedades adicionales. Puede conseguirlo al crear un nuevo estilo basado en el primero, como se muestra aquí:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Observe que el estilo anterior tiene un valor `x:Key`. Para aplicar el estilo, establezca la <xref:System.Windows.FrameworkElement.Style%2A> propiedad en su <xref:System.Windows.Controls.TextBlock> a la `x:Key` valor, como se muestra aquí:  
  
 [!code-xaml[StylingIntroSnippet#UIText](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Esto <xref:System.Windows.Controls.TextBlock> estilo tiene ahora un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valor de <xref:System.Windows.HorizontalAlignment.Center>, un <xref:System.Windows.Controls.TextBlock.FontFamily%2A> valor de `Comic Sans MS`, un <xref:System.Windows.Controls.TextBlock.FontSize%2A> valor 26 y un <xref:System.Windows.Controls.TextBlock.Foreground%2A> valor establecido en el <xref:System.Windows.Media.LinearGradientBrush> se muestra en el ejemplo. Tenga en cuenta que reemplaza el <xref:System.Windows.Controls.Control.FontSize%2A> valor del estilo base. Si hay más de un <xref:System.Windows.Setter> establecen la misma propiedad un <xref:System.Windows.Style>, el <xref:System.Windows.Setter> es declarada última tiene prioridad.  
  
 La continuación muestra lo que el <xref:System.Windows.Controls.TextBlock> elementos el aspecto siguiente:  
  
 ![TextBlocks con estilo](./media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Esto `TitleText` estilo amplía el estilo que se ha creado para el <xref:System.Windows.Controls.TextBlock> tipo. También puede ampliar un estilo con `x:Key` mediante el valor `x:Key`. Para obtener un ejemplo, vea el ejemplo proporcionado para el <xref:System.Windows.Style.BasedOn%2A> propiedad.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relación entre la propiedad TargetType y el atributo x:Key  
 Como se muestra en el primer ejemplo, establecer el <xref:System.Windows.Style.TargetType%2A> propiedad `TextBlock` sin asignar al estilo un `x:Key` hace que el estilo que se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos. En este caso, `x:Key` se establece implícitamente en `{x:Type TextBlock}`. Esto significa que si se establece explícitamente el `x:Key` a cualquier otro valor distinto `{x:Type TextBlock}`, <xref:System.Windows.Style> no se aplica a todos los <xref:System.Windows.Controls.TextBlock> elementos automáticamente. En su lugar, debe aplicar el estilo (mediante el uso de la `x:Key` valor) a la <xref:System.Windows.Controls.TextBlock> elementos explícitamente. Si el estilo está en la sección de recursos y no se establece la <xref:System.Windows.Style.TargetType%2A> la propiedad en su estilo, a continuación, se debe proporcionar un `x:Key`.  
  
 Además de proporcionar un valor predeterminado para el `x:Key`, el <xref:System.Windows.Style.TargetType%2A> propiedad especifica el tipo al que se aplican las propiedades del establecedor. Si no especifica un <xref:System.Windows.Style.TargetType%2A>, debe calificar las propiedades en su <xref:System.Windows.Setter> objetos con un nombre de clase mediante la sintaxis `Property="ClassName.Property"`. Por ejemplo, en lugar de establecer `Property="FontSize"`, debe establecer <xref:System.Windows.Setter.Property%2A> a `"TextBlock.FontSize"` o `"Control.FontSize"`.  
  
 Tenga en cuenta también que muchos controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son una combinación de otros controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Si crea un estilo aplicable a todos los controles de un tipo, podría obtener resultados inesperados. Por ejemplo, si crea un estilo que tiene como destino el <xref:System.Windows.Controls.TextBlock> escriba en un <xref:System.Windows.Window>, el estilo se aplica a todos los <xref:System.Windows.Controls.TextBlock> controles en la ventana, incluso si la <xref:System.Windows.Controls.TextBlock> forma parte de otro control, como un <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Estilos y recursos  
 Puede utilizar un estilo en cualquier elemento que se deriva de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. La manera más común de declarar un estilo es como recurso en la sección `Resources` de un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como se muestra en los ejemplos anteriores. Dado que los estilos son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos; el lugar donde se declara un estilo afecta al lugar donde se aplica. Por ejemplo, si se declara el estilo en el elemento raíz del archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de definición de aplicación, este se puede usar en cualquier parte de la aplicación. Si se crea una aplicación de navegación y se declara en uno de los archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de la aplicación, el estilo se puede usar únicamente en ese archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Para más información acerca de las reglas de ámbito de los recursos, consulte [Recursos XAML](../advanced/xaml-resources.md).  
  
 Además, encontrará más información sobre estilos y recursos en [Recursos y temas compartidos](#styling_themes) más adelante en esta introducción.  
  
### <a name="setting-styles-programmatically"></a>Establecer estilos mediante programación  
 Para asignar un estilo con nombre a un elemento mediante programación, obtenga el estilo de la colección de recursos y la asigna a la propiedad del elemento <xref:System.Windows.FrameworkElement.Style%2A> propiedad. Tenga en cuenta que los elementos de una colección de recursos son del tipo <xref:System.Object>. Por lo tanto, debe convertir el estilo recuperado a un <xref:System.Windows.Style> antes de asignarlo a la <xref:System.Windows.FrameworkElement.Style%2A> propiedad. Por ejemplo, para establecer el definido `TitleText` estilo en un <xref:System.Windows.Controls.TextBlock> denominado `textblock1`, realice lo siguiente:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Tenga en cuenta que una vez que se ha aplicado un estilo, queda sellado y no se puede cambiar. Si desea cambiar dinámicamente un estilo que ya se han aplicado, debe crear uno nuevo que reemplace el existente. Para obtener más información, vea la propiedad <xref:System.Windows.Style.IsSealed%2A>.  
  
 Puede crear un objeto que elija un estilo que se aplique según una lógica personalizada. Para obtener un ejemplo, vea el ejemplo proporcionado para el <xref:System.Windows.Controls.StyleSelector> clase.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Enlaces, recursos dinámicos y controladores de eventos  
 Tenga en cuenta que puede utilizar la propiedad `Setter.Value` para especificar una [Extensión de marcado de enlace](../advanced/binding-markup-extension.md) o una [Extensión de marcado DynamicResource](../advanced/dynamicresource-markup-extension.md). Para obtener más información, vea los ejemplos proporcionados para el <xref:System.Windows.Setter.Value%2A?displayProperty=nameWithType> propiedad.  
  
 Hasta ahora, en esta introducción solo se trata el uso de establecedores para establecer el valor de propiedad. También puede especificar controladores de eventos en un estilo. Para obtener más información, consulta <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Plantillas de datos  
 En esta aplicación de ejemplo, hay un <xref:System.Windows.Controls.ListBox> control que está enlazado a una lista de fotos:  
  
 [!code-xaml[StylingIntroSnippet#UIListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Esto <xref:System.Windows.Controls.ListBox> actualmente el siguiente aspecto:  
  
 ![ListBox antes de la plantilla](./media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 La mayoría de los controles tiene algún tipo de contenido, que a menudo procede de datos a los cuales se va a enlazar. En este ejemplo, los datos son la lista de fotos. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], usa un <xref:System.Windows.DataTemplate> para definir la representación visual de los datos. Básicamente, lo que se incluye en un <xref:System.Windows.DataTemplate> determina el aspecto de los datos en la aplicación representada.  
  
 En nuestra aplicación de ejemplo, cada objeto `Photo` personalizado tiene una propiedad `Source` de tipo cadena que especifica la ruta de acceso de la imagen. Actualmente, los objetos de foto aparecen como rutas de acceso de archivo.  
  
 Para que las fotos aparezcan como imágenes, crea un <xref:System.Windows.DataTemplate> como un recurso:  
  
 [!code-xaml[StylingIntroSnippet#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#DataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xaml[StylingIntroSnippet#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Tenga en cuenta que el <xref:System.Windows.DataTemplate.DataType%2A> propiedad es muy similar a la <xref:System.Windows.Style.TargetType%2A> propiedad de la <xref:System.Windows.Style>. Si su <xref:System.Windows.DataTemplate> está en la sección de recursos, cuando se especifica la <xref:System.Windows.DataTemplate.DataType%2A> propiedad a un tipo y no asignarle un `x:Key`, el <xref:System.Windows.DataTemplate> se aplica cada vez que aparezca ese tipo. Siempre tiene la opción para asignar el <xref:System.Windows.DataTemplate> con un `x:Key` y vuelva a establecerla como un `StaticResource` para propiedades que toman <xref:System.Windows.DataTemplate> tipos, como la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad o el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad.  
  
 En esencia, el <xref:System.Windows.DataTemplate> en el ejemplo anterior define que siempre que haya un `Photo` objeto, debe aparecer como un <xref:System.Windows.Controls.Image> dentro de un <xref:System.Windows.Controls.Border>. Con esto <xref:System.Windows.DataTemplate>, nuestra aplicación ahora tiene este aspecto:  
  
 ![Imagen de foto](./media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 El modelo de plantillas de datos proporciona otras características. Por ejemplo, si se va a mostrar datos de la colección que contienen otras colecciones mediante un <xref:System.Windows.Controls.HeaderedItemsControl> escriba como un <xref:System.Windows.Controls.Menu> o un <xref:System.Windows.Controls.TreeView>, existe la <xref:System.Windows.HierarchicalDataTemplate>. Otra característica de plantillas de datos es el <xref:System.Windows.Controls.DataTemplateSelector>, que le permite elegir un <xref:System.Windows.DataTemplate> usar según una lógica personalizada. Para más información, consulte [Data Templating Overview](../data/data-templating-overview.md) (Introducción a las plantillas de datos), que proporciona una explicación más detallada de las características de las distintas plantillas de datos.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Plantillas de control  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el <xref:System.Windows.Controls.ControlTemplate> de un control define la apariencia del control. Puede cambiar la estructura y la apariencia de un control mediante la definición de un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control. En muchos casos, esto ofrece la flexibilidad suficiente para no tener que escribir controles personalizados. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Desencadenadores  
 Un desencadenador establece propiedades o inicia acciones, como una animación, cuando se genera un evento o cambia un valor de propiedad. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, y <xref:System.Windows.DataTemplate> todos tienen un `Triggers` propiedad que puede contener un conjunto de desencadenadores. Hay varios tipos de desencadenadores.  
  
### <a name="property-triggers"></a>Desencadenadores de propiedad  
 Un <xref:System.Windows.Trigger> valores de propiedad de conjuntos, o inicia acciones en función del valor de una propiedad se llama a un desencadenador de propiedad.  
  
 Para demostrar cómo usar desencadenadores de propiedad, puede realizar con cada <xref:System.Windows.Controls.ListBoxItem> parcialmente transparente a menos que lo está. El siguiente estilo establece la <xref:System.Windows.UIElement.Opacity%2A> valor de un <xref:System.Windows.Controls.ListBoxItem> a `0.5`. Cuando el <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> propiedad es `true`, sin embargo, el <xref:System.Windows.UIElement.Opacity%2A> está establecido en `1.0`:  
  
 [!code-xaml[StylingIntroSample_snippet#Triggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xaml[StylingIntroSample_snippet#EndTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 Este ejemplo se usa un <xref:System.Windows.Trigger> para establecer un valor de propiedad, pero tenga en cuenta que el <xref:System.Windows.Trigger> clase también tiene la <xref:System.Windows.TriggerBase.EnterActions%2A> y <xref:System.Windows.TriggerBase.ExitActions%2A> propiedades que permiten a un desencadenador realizar acciones.  
  
 Tenga en cuenta que el <xref:System.Windows.FrameworkElement.MaxHeight%2A> propiedad de la <xref:System.Windows.Controls.ListBoxItem> está establecido en `75`. En la siguiente ilustración, el tercer elemento es el seleccionado:  
  
 ![ListView con estilo](./media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>Clases EventTrigger y objetos Storyboard  
 Otro tipo de desencadenador es la <xref:System.Windows.EventTrigger>, que inicia un conjunto de acciones en función de la aparición de un evento. Por ejemplo, la siguiente <xref:System.Windows.EventTrigger> objetos especifican que, cuando el puntero del mouse entra en el <xref:System.Windows.Controls.ListBoxItem>, el <xref:System.Windows.FrameworkElement.MaxHeight%2A> propiedad anima a un valor de `90` a través de un `0.2` segundo período. Cuando se desplaza el mouse fuera del elemento, la propiedad vuelve al valor original durante un período de `1` segundo. Tenga en cuenta cómo no es necesario especificar un <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valor para el <xref:System.Windows.ContentElement.MouseLeave> animación. Esto se debe a que la animación realiza el seguimiento del valor original.  
  
 [!code-xaml[StylingIntroSample_snippet#EventTriggers](~/samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Para más información, consulte [Storyboards Overview](../graphics-multimedia/storyboards-overview.md) (Introducción a los objetos Storyboard).  
  
 En la siguiente ilustración, el mouse apunta al tercer elemento:  
  
 ![Captura de pantalla de ejemplo de aplicación de estilos](./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Clases MultiTrigger, DataTrigger y MultiDataTrigger  
 Además <xref:System.Windows.Trigger> y <xref:System.Windows.EventTrigger>, existen otros tipos de desencadenadores. <xref:System.Windows.MultiTrigger> permite establecer valores de propiedad según varias condiciones. Usa <xref:System.Windows.DataTrigger> y <xref:System.Windows.MultiDataTrigger> cuando la propiedad de la condición está enlazada a datos.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Recursos compartidos y temas  
 Una aplicación típica de Windows Presentation Foundation (WPF) podría tener varios recursos de interfaz de usuario que se aplican en toda la aplicación. En su conjunto, estos recursos pueden considerarse el tema para la aplicación. Windows Presentation Foundation (WPF) proporciona soporte técnico para el usuario de empaquetado recursos de la interfaz (IU) como un tema mediante un diccionario de recursos que se encapsula como el <xref:System.Windows.ResourceDictionary> clase.  
  
 Los temas de Windows Presentation Foundation (WPF) se definen mediante el estilo y el mecanismo de plantillas que Windows Presentation Foundation (WPF) expone para personalizar los objetos visuales de cualquier elemento.  
  
 Los recursos de tema de Windows Presentation Foundation (WPF) se almacenan en diccionarios de recursos incrustados. Estos diccionarios de recursos deben estar incrustados en un ensamblado firmado, ya sea en el mismo ensamblado que el propio código o en uno en paralelo. En el caso de PresentationFramework.dll, el ensamblado que contiene controles de Windows Presentation Foundation (WPF), los recursos de tema están en una serie de ensamblados en paralelo.  
  
 El tema se convierte en el último lugar donde buscar el estilo de un elemento. Normalmente, se comenzará por el árbol de elementos en busca de un recurso adecuado, a continuación, se buscará en la colección de recursos de aplicación y finalmente, se consultará el sistema. Esto proporciona a los desarrolladores de aplicaciones una oportunidad para volver a definir el estilo de cualquier objeto en el nivel de árbol o de aplicación antes de alcanzar el tema.  
  
 Los diccionarios de recursos se pueden redefinir como archivos individuales para reutilizar un tema en varias aplicaciones. También se pueden crear temas intercambiables al definir varios diccionarios de recursos que proporcionen los mismos tipos de recursos, pero con diferentes valores. Redefinir estos estilos u otros recursos en el nivel de aplicación es el enfoque recomendado para aplicar una máscara a una aplicación.  
  
 Para compartir un conjunto de recursos, incluidos los estilos y plantillas, en todas las aplicaciones, puede crear un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos y definir un <xref:System.Windows.ResourceDictionary>. Por ejemplo, eche un vistazo en la ilustración siguiente, donde se muestra parte del [ejemplo de aplicación de estilo con la clase ControlTemplate](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating):

![Ejemplos de Control Template](./media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Si observa los archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del ejemplo, observará que todos tienen lo siguiente:  
  
 [!code-xaml[ControlTemplateExamples#MergedDictionaries](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Es el uso compartido de `shared.xaml`, que define un <xref:System.Windows.ResourceDictionary> que contiene un conjunto de recursos de pincel y estilos que permite a los controles en el ejemplo para tener una apariencia coherente.  
  
 Para más información, consulte [Merged Resource Dictionaries](../advanced/merged-resource-dictionaries.md) (Diccionarios de recursos combinados).  
  
 Si va a crear un tema para su control personalizado, consulte la sección de la biblioteca de controles externos de [Control Authoring Overview](control-authoring-overview.md) (Introducción a la creación de controles).  
  
## <a name="see-also"></a>Vea también
- [Pack URI en WPF](../app-development/pack-uris-in-wpf.md)
- [Filtrar para buscar elementos generados por un objeto ControlTemplate](how-to-find-controltemplate-generated-elements.md)
- [Buscar elementos generados por una clase DataTemplate](../data/how-to-find-datatemplate-generated-elements.md)
