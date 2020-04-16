---
title: Estilos y plantillas
description: Obtén información sobre los recursos XAML en Windows Presentation Foundation (WPF) para .NET Core. Comprender los tipos de recursos XAML relacionados con estilos y temas.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433101"
---
# <a name="styles-and-templates-in-wpf"></a>Estilos y plantillas en WPF

El estilo y la plantillas de Windows Presentation Foundation (WPF) hacen referencia a un conjunto de características que permiten a los desarrolladores y diseñadores crear efectos visualmente atractivos y una apariencia coherente para su producto. Al personalizar la apariencia de una aplicación, desea un modelo de estilo y plantillas fuerte que permita el mantenimiento y el uso compartido de la apariencia dentro y entre aplicaciones. WPFWPF proporciona ese modelo.

Otra característica del modelo de estilo WPFWPF es la separación de la presentación y la lógica. Los diseñadores pueden trabajar en la apariencia de una aplicación mediante el uso de xaml al mismo tiempo que los desarrolladores trabajan en la lógica de programación mediante C o Visual Basic.

Esta información general se centra en los aspectos de estilo y plantillas de la aplicación y no analiza ningún concepto de enlace de datos. Para información sobre el enlace de datos, consulte [Data Binding Overview](../data/data-binding-overview.md) (Introducción al enlace de datos).

Es importante comprender los recursos, que son los que permiten reutilizar estilos y plantillas. Para más información acerca de los recursos, consulte [XAML Resources](xaml-resources-define.md) (Recursos de XAML).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Muestra

El código de ejemplo proporcionado en esta información general se basa en una sencilla aplicación de [exploración](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) de fotos que se muestra en la siguiente ilustración.

![ListView con estilo](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

En esta sencilla foto de ejemplo se aplican estilos y plantillas para crear una experiencia de usuario visualmente atractiva. El ejemplo <xref:System.Windows.Controls.TextBlock> tiene dos <xref:System.Windows.Controls.ListBox> elementos y un control que está enlazado a una lista de imágenes.

Para el ejemplo completo, consulte [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Estilos

Puede pensar en <xref:System.Windows.Style> una forma cómoda de aplicar un conjunto de valores de propiedad a varios elementos. Puede utilizar un estilo en cualquier <xref:System.Windows.FrameworkElement> elemento <xref:System.Windows.FrameworkContentElement> que <xref:System.Windows.Window> derive <xref:System.Windows.Controls.Button>de o como un archivo o un archivo .

La forma más común de declarar un `Resources` estilo es como un recurso en la sección de un archivo XAML. Dado que los estilos son recursos, obedecen las mismas reglas de ámbito que se aplican a todos los recursos. En pocas palabras, donde se declara un estilo afecta a donde se puede aplicar el estilo. Por ejemplo, si declara el estilo en el elemento raíz del archivo XAML de definición de aplicación, el estilo se puede usar en cualquier lugar de la aplicación.

Por ejemplo, el siguiente código XAML `TextBlock`declara dos estilos `TextBlock` para un , uno aplicado automáticamente a todos los elementos y otro al que se debe hacer referencia explícitamente.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Este es un ejemplo de los estilos declarados anteriormente que se utilizan.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Bloques de texto con estilo](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Para obtener más información, vea [Crear un estilo para un control.](styles-templates-create-apply-style.md)

## <a name="controltemplates"></a>ControlTemplates

En WPFWPF, el <xref:System.Windows.Controls.ControlTemplate> de un control define la apariencia del control. Puede cambiar la estructura y el aspecto de <xref:System.Windows.Controls.ControlTemplate> un control definiendo un nuevo y asignándolo a un control. En muchos casos, las plantillas le ofrecen suficiente flexibilidad para que no tenga que escribir sus propios controles personalizados.

Cada control tiene una plantilla predeterminada asignada a la [Control.Template](xref:System.Windows.Controls.Control.Template) propiedad. La plantilla conecta la presentación visual del control con las capacidades del control. Dado que define una plantilla en XAML, puede cambiar la apariencia del control sin escribir ningún código. Cada plantilla está diseñada para un <xref:System.Windows.Controls.Button>control específico, como un archivo .

Normalmente se declara una plantilla `Resources` como un recurso en la sección de un archivo XAML. Al igual que con todos los recursos, se aplican las reglas de ámbito.

Las plantillas de control están mucho más involucradas que un estilo. Esto se debe a que la plantilla de control reescribe la apariencia visual de todo el control, mientras que un estilo simplemente aplica cambios de propiedad al control existente. Sin embargo, dado que la plantilla de un control se aplica estableciendo el [Control.Template](xref:System.Windows.Controls.Control.Template) propiedad, puede usar un estilo para definir o establecer una plantilla.

Por lo general, los diseñadores permiten crear una copia de una plantilla existente y modificarla. Por ejemplo, en el diseñador de `CheckBox` Visual Studio WPF, seleccione un control y, a continuación, haga clic con el botón secundario y seleccione **Editar plantilla** > **Crear una copia**. Este comando genera un *estilo que define una plantilla.*

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

Editar una copia de una plantilla es una excelente manera de aprender cómo funcionan las plantillas. En lugar de crear una nueva plantilla en blanco, es más fácil editar una copia y cambiar algunos aspectos de la presentación visual.

Para obtener un ejemplo, vea [Crear una plantilla para un control.](../themes/how-to-create-apply-template.md)

### <a name="templatebinding"></a>TemplateBinding

Es posible que haya observado que el recurso de plantilla definido en la sección anterior usa la extensión de [marcado TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md). A `TemplateBinding` es una forma optimizada de un enlace para escenarios `{Binding RelativeSource={RelativeSource TemplatedParent}}`de plantilla, análogo a un enlace construido con . `TemplateBinding`es útil para enlazar partes de la plantilla a las propiedades del control. Por ejemplo, cada <xref:System.Windows.Controls.Control.BorderThickness> control tiene una propiedad. Utilice `TemplateBinding` a para administrar qué elemento de la plantilla se ve afectado por esta configuración de control.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl y ItemsControl

Si <xref:System.Windows.Controls.ContentPresenter> a se <xref:System.Windows.Controls.ControlTemplate> declara <xref:System.Windows.Controls.ContentControl>en <xref:System.Windows.Controls.ContentPresenter> el de un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.Content%2A> , el se enlazará automáticamente a las propiedades y. Del mismo <xref:System.Windows.Controls.ItemsPresenter> modo, un <xref:System.Windows.Controls.ControlTemplate> que <xref:System.Windows.Controls.ItemsControl> está en <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> el <xref:System.Windows.Controls.ItemsControl.Items%2A> de un se enlazará automáticamente a las propiedades y.

## <a name="datatemplates"></a>DataTemplates

En esta aplicación de <xref:System.Windows.Controls.ListBox> ejemplo, hay un control que está enlazado a una lista de fotos.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Esto <xref:System.Windows.Controls.ListBox> actualmente se parece a lo siguiente.

![ListBox antes de aplicar una plantilla](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

La mayoría de los controles tiene algún tipo de contenido, que a menudo procede de datos a los cuales se va a enlazar. En este ejemplo, los datos son la lista de fotos. En WPFWPF, <xref:System.Windows.DataTemplate> use a para definir la representación visual de los datos. Básicamente, lo que <xref:System.Windows.DataTemplate> se pone en un determina cómo se ven los datos en la aplicación representada.

En nuestra aplicación de `Photo` ejemplo, `Source` cada objeto personalizado tiene una propiedad de tipo cadena que especifica la ruta de acceso del archivo de la imagen. Actualmente, los objetos de foto aparecen como rutas de acceso de archivo.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Para que las fotos aparezcan <xref:System.Windows.DataTemplate> como imágenes, se crea como un recurso.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Observe que <xref:System.Windows.DataTemplate.DataType%2A> la propiedad <xref:System.Windows.Style.TargetType%2A> es similar <xref:System.Windows.Style>a la propiedad de la . Si <xref:System.Windows.DataTemplate> se encuentra en la sección <xref:System.Windows.DataTemplate.DataType%2A> resources, al especificar `x:Key`la <xref:System.Windows.DataTemplate> propiedad a un tipo y omitir un , se aplica cada vez que aparece ese tipo. Siempre tiene la opción <xref:System.Windows.DataTemplate> de `x:Key` asignar el con `StaticResource` un y, <xref:System.Windows.DataTemplate> a continuación, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> establecerlo <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> como un para las propiedades que toman tipos, como la propiedad o la propiedad.

Esencialmente, <xref:System.Windows.DataTemplate> el ejemplo anterior define que `Photo` siempre que hay un <xref:System.Windows.Controls.Image> objeto, debe aparecer como un <xref:System.Windows.Controls.Border>archivo . Con <xref:System.Windows.DataTemplate>esto , nuestra aplicación ahora se ve así.

![Imagen fotográfica](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

El modelo de plantillas de datos proporciona otras características. Por ejemplo, si está mostrando datos de <xref:System.Windows.Controls.HeaderedItemsControl> recopilación <xref:System.Windows.Controls.Menu> que <xref:System.Windows.Controls.TreeView>contienen otras <xref:System.Windows.HierarchicalDataTemplate>colecciones con un tipo como a o a , existe el archivo . Otra característica de plantillas <xref:System.Windows.Controls.DataTemplateSelector>de datos es la <xref:System.Windows.DataTemplate> , que le permite elegir a para usar en función de la lógica personalizada. Para más información, consulte [Data Templating Overview](../../framework/wpf/data/data-templating-overview.md) (Introducción a las plantillas de datos), que proporciona una explicación más detallada de las características de las distintas plantillas de datos.

## <a name="triggers"></a>Desencadenadores

Un desencadenador establece propiedades o inicia acciones, como una animación, cuando se genera un evento o cambia un valor de propiedad. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate> y `Triggers` todos tienen una propiedad que puede contener un conjunto de desencadenadores. Hay varios tipos de desencadenadores.

### <a name="propertytriggers"></a>PropertyTriggers

A <xref:System.Windows.Trigger> que establece valores de propiedad o inicia acciones basadas en el valor de una propiedad se denomina desencadenador de propiedad.

Para demostrar cómo utilizar desencadenadores de <xref:System.Windows.Controls.ListBoxItem> propiedades, puede hacer que cada uno sea parcialmente transparente a menos que esté seleccionado. El estilo siguiente <xref:System.Windows.UIElement.Opacity%2A> establece <xref:System.Windows.Controls.ListBoxItem> el `0.5`valor de a to . Sin <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> embargo, cuando la propiedad es `true`, se establece en <xref:System.Windows.UIElement.Opacity%2A> . `1.0`

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

En este <xref:System.Windows.Trigger> ejemplo se usa a para <xref:System.Windows.Trigger> establecer un <xref:System.Windows.TriggerBase.EnterActions%2A> valor <xref:System.Windows.TriggerBase.ExitActions%2A> de propiedad, pero tenga en cuenta que la clase también tiene las propiedades y que permiten a un desencadenador realizar acciones.

Observe que <xref:System.Windows.FrameworkElement.MaxHeight%2A> la <xref:System.Windows.Controls.ListBoxItem> propiedad de `75`la se establece en . En la siguiente ilustración, el tercer elemento es el elemento seleccionado.

![ListView con estilo](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>Clases EventTrigger y objetos Storyboard

Otro tipo de <xref:System.Windows.EventTrigger>desencadenador es el , que inicia un conjunto de acciones en función de la aparición de un evento. Por ejemplo, <xref:System.Windows.EventTrigger> los siguientes objetos especifican que <xref:System.Windows.Controls.ListBoxItem>cuando <xref:System.Windows.FrameworkElement.MaxHeight%2A> el puntero del `90` mouse `0.2` entra en el , la propiedad se anima a un valor de más de un segundo período. Cuando se desplaza el mouse fuera del elemento, la propiedad vuelve al valor original durante un período de `1` segundo. Observe cómo no es necesario <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> especificar <xref:System.Windows.ContentElement.MouseLeave> un valor para la animación. Esto se debe a que la animación realiza el seguimiento del valor original.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Para obtener más información, consulte [introducción a guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

En la siguiente ilustración, el ratón apunta al tercer elemento.

![Captura de pantalla de ejemplo de estilo](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Clases MultiTrigger, DataTrigger y MultiDataTrigger

Además <xref:System.Windows.Trigger> <xref:System.Windows.EventTrigger>de y , hay otros tipos de desencadenadores. <xref:System.Windows.MultiTrigger>le permite establecer valores de propiedad basados en varias condiciones. Se <xref:System.Windows.DataTrigger> utiliza <xref:System.Windows.MultiDataTrigger> y cuando la propiedad de la condición está enlazada a datos.

## <a name="visual-states"></a>Estados visuales

Los controles siempre están en un **estado**específico. Por ejemplo, cuando el mouse se mueve sobre la superficie de un `MouseOver`control, se considera que el control está en un estado común de . Un control sin un estado específico `Normal` se considera que está en el estado común. Los estados se dividen en grupos, y los `CommonStates`estados mencionados anteriormente forman parte del grupo estatal. La mayoría de los `CommonStates` `FocusStates`controles tienen dos grupos de estados: y . De cada grupo de estado aplicado a un control, un control `CommonStates.MouseOver` `FocusStates.Unfocused`siempre está en un estado de cada grupo, como y . Sin embargo, un control no puede estar en dos `CommonStates.Normal` `CommonStates.Disabled`estados diferentes dentro del mismo grupo, como y . Aquí hay una tabla de estados que la mayoría de los controles reconocen y usan.

| Nombre de VisualState | Nombre de VisualStateGroup | Descripción |
| ---------------- | --------------------- | ----------- |
| Normal           | CommonStates          | El estado predeterminado. |
| MouseOver        | CommonStates          | El puntero del mouse se coloca sobre el control. |
| Presionado          | CommonStates          | El control está presionado. |
| Disabled         | CommonStates          | El control está deshabilitado. |
| Con foco          | FocusStates           | El control tiene el foco. |
| Sin foco        | FocusStates           | El control no tiene el foco. |

Al definir <xref:System.Windows.VisualStateManager?displayProperty=fullName> un elemento raíz de una plantilla de control, puede desencadenar animaciones cuando un control entra en un estado específico. El `VisualStateManager` declara qué combinaciones de <xref:System.Windows.VisualStateGroup> y <xref:System.Windows.VisualState> para ver. Cuando el control entra en un estado vigilado, se inicia la animación definida por el. `VisaulStateManager`

Por ejemplo, el siguiente `CommonStates.MouseOver` código XAML observa el estado `backgroundElement`para animar el color de relleno del elemento denominado . Cuando el control `CommonStates.Normal` vuelve al estado, se `backgroundElement` restaura el color de relleno del elemento denominado.

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

Para obtener más información acerca de los guiones gráficos, vea Información general sobre [guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Recursos y temas compartidos

Una aplicación WPF típica puede tener varios recursos de interfaz de usuario que se aplican en toda la aplicación. Colectivamente, este conjunto de recursos se puede considerar el tema de la aplicación. WPFWPF proporciona compatibilidad para empaquetar recursos de interfaz de usuario <xref:System.Windows.ResourceDictionary> como un tema mediante un diccionario de recursos que se encapsula como la clase.

WPFWPF temas se definen mediante el mecanismo de estilo y plantillas que WPFWPF expone para personalizar los objetos visuales de cualquier elemento.

Los recursos de tema de WPFWPF se almacenan en diccionarios de recursos incrustados. Estos diccionarios de recursos deben estar incrustados en un ensamblado firmado, ya sea en el mismo ensamblado que el propio código o en uno en paralelo. Para PresentationFramework.dll, el ensamblado que contiene CONTROLES WPFWPF, los recursos de tema están en una serie de ensamblados en paralelo.

El tema se convierte en el último lugar donde buscar el estilo de un elemento. Normalmente, la búsqueda comenzará subiendo por el árbol de elementos buscando un recurso adecuado, luego buscar en la colección de recursos de la aplicación y, finalmente, consultar el sistema. Esto da a los desarrolladores de aplicaciones la oportunidad de redefinir el estilo de cualquier objeto en el nivel de árbol o aplicación antes de llegar al tema.

Puede definir diccionarios de recursos como archivos individuales que le permiten reutilizar un tema en varias aplicaciones. También se pueden crear temas intercambiables al definir varios diccionarios de recursos que proporcionen los mismos tipos de recursos, pero con diferentes valores. Redefinir estos estilos u otros recursos en el nivel de aplicación es el enfoque recomendado para despellejar una aplicación.

Para compartir un conjunto de recursos, incluidos estilos y plantillas, entre <xref:System.Windows.ResourceDictionary> aplicaciones, puede `shared.xaml` crear un archivo XAML y definir un archivo que incluya una referencia a un archivo.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Es el uso `shared.xaml`compartido de <xref:System.Windows.ResourceDictionary> , que a su vez define un que contiene un conjunto de recursos de estilo y pincel, lo que permite que los controles de una aplicación tengan un aspecto coherente.

Para obtener más información, consulte Diccionarios de [recursos combinados](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Si está creando un tema para el control personalizado, consulte la sección **Definición de recursos en el nivel** de tema de la [introducción a](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)la creación de control .

## <a name="see-also"></a>Consulte también

- [Empaquetar URI en WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Procedimiento para buscar elementos generados por un objeto ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Encontrar elementos generados por DataTemplate](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
