---
title: Estilos y plantillas
description: Obtenga información sobre los recursos XAML en Windows Presentation Foundation (WPF) para .NET Core. Comprenda los tipos de recursos de XAML relacionados con estilos y temas.
author: adegeo
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: faa54e0a3c827717114ca6ca4f033c1c4c3acfa8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325779"
---
# <a name="styles-and-templates-in-wpf"></a>Estilos y plantillas en WPF

La aplicación de estilos y plantillas de Windows Presentation Foundation (WPF) hace referencia a un conjunto de características que permiten a los desarrolladores y diseñadores crear efectos visualmente atractivos y una apariencia coherente para su producto. Al personalizar la apariencia de una aplicación, le interesa un modelo de plantillas y estilos sólido que permita el mantenimiento y el uso compartido de la apariencia dentro de las aplicaciones y entre ellas. WPF ofrece ese modelo.

Otra característica del modelo de aplicación de estilos y plantillas de WPF es la separación de la presentación y la lógica. Los diseñadores pueden trabajar en la apariencia de una aplicación solo con XAML, mientras que los desarrolladores trabajan en la lógica de programación con C# o Visual Basic.

Esta información general se centra en los aspectos de los estilos y las plantillas de la aplicación, y no abarca los conceptos de enlace de datos. Para información sobre el enlace de datos, consulte [Data Binding Overview](../data/data-binding-overview.md) (Introducción al enlace de datos).

Es importante entender los recursos, que son los que permiten reutilizar los estilos y las plantillas. Para más información acerca de los recursos, consulte [XAML Resources](xaml-resources-define.md) (Recursos de XAML).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Ejemplo

El ejemplo de código proporcionado en esta introducción se basa en una [sencilla aplicación de búsqueda de fotografías](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating), que se muestra en la ilustración siguiente.

![ListView con estilo](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

En esta sencilla foto de ejemplo se aplican estilos y plantillas para crear una experiencia de usuario visualmente atractiva. El ejemplo tiene dos elementos <xref:System.Windows.Controls.TextBlock> y un control <xref:System.Windows.Controls.ListBox> que está enlazado a una lista de imágenes.

Para el ejemplo completo, consulte [Introducción a la aplicación de estilos y plantillas de ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Estilos

Puede considerar a <xref:System.Windows.Style>una manera cómoda de aplicar un conjunto de valores de propiedad a varios elementos. Puede usar un estilo en cualquier elemento que se derive de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, como <xref:System.Windows.Window> o <xref:System.Windows.Controls.Button>.

La manera más común de declarar un estilo es como un recurso en la sección `Resources` de un archivo XAML. Como los estilos son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos. Simplemente, la ubicación de la declaración de un estilo afecta a dónde se puede aplicar el estilo. Por ejemplo, si declara el estilo en el elemento raíz del archivo XAML de definición de la aplicación, el estilo se puede usar en cualquier parte de la aplicación.

Por ejemplo, el código XAML siguiente declara dos estilos para un objeto `TextBlock`, uno que se aplica de forma automática a todos los elementos `TextBlock`, y otro al que se debe hacer referencia explícitamente.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Este es un ejemplo de uso de los estilos declarados antes.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Bloques de texto con estilo](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Para obtener más información, vea [Creación de un estilo para un control](styles-templates-create-apply-style.md).

## <a name="controltemplates"></a>ControlTemplates

En WPF, el elemento <xref:System.Windows.Controls.ControlTemplate> de un control define la apariencia del control. Puede cambiar la estructura y la apariencia de un control si define un elemento <xref:System.Windows.Controls.ControlTemplate> nuevo y lo asigna a un control. En muchos casos, las plantillas ofrecen flexibilidad suficiente para no tener que escribir controles personalizados propios.

Cada control tiene una plantilla predeterminada asignada a la propiedad [Control.Template](xref:System.Windows.Controls.Control.Template). La plantilla conecta la presentación visual del control con sus funciones. Como una plantilla se define en XAML, puede cambiar la apariencia del control sin escribir código. Cada plantilla está diseñada para un control específico, como <xref:System.Windows.Controls.Button>.

Normalmente, una plantilla se declara como un recurso en la sección `Resources` de un archivo XAML. Como sucede con todos los recursos, se aplican las reglas de ámbito.

Las plantillas de control son mucho más complicadas que un estilo. Esto se debe a que la plantilla de control vuelve a escribir la apariencia visual del control completo, mientras que un estilo simplemente aplica los cambios de propiedad al control existente. Pero como para aplicar la plantilla de un control se establece la propiedad [Control.Template](xref:System.Windows.Controls.Control.Template), puede usar un estilo para definir o establecer una plantilla.

Los diseñadores generalmente permiten crear una copia de una plantilla existente y modificarla. Por ejemplo, en el diseñador WPF de Visual Studio, seleccione un control `CheckBox` y, después, haga clic con el botón derecho y seleccione **Editar plantilla** > **Crear una copia**. Este comando genera un *estilo que define una plantilla*.

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

La modificación de una copia de una plantilla es una excelente manera de aprender cómo funcionan las plantillas. En lugar de crear una plantilla en blanco, es más fácil editar una copia y cambiar algunos aspectos de la presentación visual.

Para obtener un ejemplo, vea [Creación de una plantilla para un control](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Es posible que haya observado que el recurso de plantilla definido en la sección anterior usa la [extensión de marcado TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md). `TemplateBinding` es una forma optimizada de enlace para escenarios de plantilla, similar al enlace que se crea con `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` resulta útil para enlazar elementos de la plantilla a las propiedades del control. Por ejemplo, cada control tiene una propiedad <xref:System.Windows.Controls.Control.BorderThickness>. Use una instancia de `TemplateBinding` para administrar qué elemento de la plantilla se ve afectado por esta configuración de control.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl e ItemsControl

Si se declara una instancia de <xref:System.Windows.Controls.ContentPresenter> en el elemento <xref:System.Windows.Controls.ControlTemplate> de un objeto <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter> se enlazará de forma automática a las propiedades <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>. De forma similar, una instancia de <xref:System.Windows.Controls.ItemsPresenter> en el elemento <xref:System.Windows.Controls.ControlTemplate> de un objeto <xref:System.Windows.Controls.ItemsControl> se enlazará de forma automática a las propiedades <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>.

## <a name="datatemplates"></a>DataTemplates

En esta aplicación de ejemplo, hay un control <xref:System.Windows.Controls.ListBox> enlazado a una lista de fotos.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

El aspecto actual de <xref:System.Windows.Controls.ListBox> es similar al siguiente.

![ListBox antes de aplicar una plantilla](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

La mayoría de los controles tiene algún tipo de contenido, que a menudo procede de datos a los cuales se va a enlazar. En este ejemplo, los datos son la lista de fotos. En WPF, <xref:System.Windows.DataTemplate> se usa para definir la representación visual de los datos. Básicamente, lo que se incluye en una instancia de <xref:System.Windows.DataTemplate> determina el aspecto de los datos en la aplicación representada.

En la aplicación de ejemplo, cada objeto `Photo` personalizado tiene una propiedad `Source` de tipo cadena que especifica la ruta de acceso de la imagen. Actualmente, los objetos de foto aparecen como rutas de acceso de archivo.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Para que las fotos aparezcan como imágenes, se crea una instancia de <xref:System.Windows.DataTemplate> como un recurso.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Observe que la propiedad <xref:System.Windows.DataTemplate.DataType%2A> es similar a la propiedad <xref:System.Windows.Style.TargetType%2A> de <xref:System.Windows.Style>. Si <xref:System.Windows.DataTemplate> está en la sección de recursos, cuando se especifica la propiedad <xref:System.Windows.DataTemplate.DataType%2A> en un tipo y se omite `x:Key`, cada vez que aparece ese tipo se aplica <xref:System.Windows.DataTemplate>. Siempre tiene la opción de asignar <xref:System.Windows.DataTemplate> con una instancia de `x:Key` y, después, establecerlo como `StaticResource` para las propiedades que toman tipos <xref:System.Windows.DataTemplate>, como <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> o <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.

En esencia, en el ejemplo anterior <xref:System.Windows.DataTemplate> define que siempre que haya un objeto `Photo`, debe aparecer como <xref:System.Windows.Controls.Image> en un elemento <xref:System.Windows.Controls.Border>. Con esta instancia de <xref:System.Windows.DataTemplate>, ahora la aplicación tiene este aspecto.

![Imagen fotográfica](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

El modelo de plantillas de datos proporciona otras características. Por ejemplo, si va a mostrar datos de colección que contienen otras colecciones mediante un tipo <xref:System.Windows.Controls.HeaderedItemsControl> como <xref:System.Windows.Controls.Menu> o <xref:System.Windows.Controls.TreeView>, dispone de <xref:System.Windows.HierarchicalDataTemplate>. Otra característica de plantillas de datos es <xref:System.Windows.Controls.DataTemplateSelector>, que le permite elegir un objeto <xref:System.Windows.DataTemplate> para usarlo en función de lógica personalizada. Para más información, consulte [Data Templating Overview](../../framework/wpf/data/data-templating-overview.md) (Introducción a las plantillas de datos), que proporciona una explicación más detallada de las características de las distintas plantillas de datos.

## <a name="triggers"></a>Desencadenadores

Un desencadenador establece propiedades o inicia acciones, como una animación, cuando se genera un evento o cambia un valor de propiedad. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> y <xref:System.Windows.DataTemplate> tienen una propiedad `Triggers` que puede contener un conjunto de desencadenadores. Hay varios tipos de desencadenadores.

### <a name="propertytriggers"></a>PropertyTriggers

Un objeto <xref:System.Windows.Trigger> que establece valores de propiedad o inicia acciones en función del valor de una propiedad se denomina desencadenador de propiedad.

Para demostrar cómo se usan los desencadenadores de propiedad, puede hacer que cada objeto <xref:System.Windows.Controls.ListBoxItem> sea parcialmente transparente a menos que esté seleccionado. El estilo siguiente establece el valor <xref:System.Windows.UIElement.Opacity%2A> de un objeto <xref:System.Windows.Controls.ListBoxItem> en `0.5`. Pero cuando la propiedad <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> es `true`, <xref:System.Windows.UIElement.Opacity%2A> se establece en `1.0`.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

En este ejemplo se usa un elemento <xref:System.Windows.Trigger> para establecer un valor de propiedad, pero observe que la clase <xref:System.Windows.Trigger> también tiene las propiedades <xref:System.Windows.TriggerBase.EnterActions%2A> y <xref:System.Windows.TriggerBase.ExitActions%2A> que permiten a un desencadenador realizar acciones.

Tenga en cuenta que la propiedad <xref:System.Windows.FrameworkElement.MaxHeight%2A> de <xref:System.Windows.Controls.ListBoxItem> está establecida en `75`. En la ilustración siguiente, el tercer elemento es el seleccionado.

![ListView con estilo](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>Clases EventTrigger y objetos Storyboard

Otro tipo de desencadenador es <xref:System.Windows.EventTrigger>, que inicia un conjunto de acciones cuando sucede un evento. Por ejemplo, los objetos <xref:System.Windows.EventTrigger> siguientes especifican que cuando el puntero del mouse entra en <xref:System.Windows.Controls.ListBoxItem>, la propiedad <xref:System.Windows.FrameworkElement.MaxHeight%2A> se anima hasta un valor de `90` durante un periodo de `0.2` segundos. Cuando se desplaza el mouse fuera del elemento, la propiedad vuelve al valor original durante un período de `1` segundo. Tenga en cuenta que no es necesario especificar un valor <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> para la animación de <xref:System.Windows.ContentElement.MouseLeave>. Esto se debe a que la animación realiza el seguimiento del valor original.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Para obtener más información, vea [Introducción a los guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

En la ilustración siguiente, el mouse apunta al tercer elemento.

![Captura de pantalla de ejemplo de aplicación de estilo](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Clases MultiTrigger, DataTrigger y MultiDataTrigger

Además de <xref:System.Windows.Trigger> y <xref:System.Windows.EventTrigger>, hay otros tipos de desencadenadores. <xref:System.Windows.MultiTrigger> permite establecer valores de propiedad en función de varias condiciones. <xref:System.Windows.DataTrigger> y <xref:System.Windows.MultiDataTrigger> se usan cuando la propiedad de la condición está enlazada a datos.

## <a name="visual-states"></a>Estados visuales

Los controles siempre se encuentran en un **estado** específico. Por ejemplo, cuando el mouse se mueve sobre la superficie de un control, se considera que el control está en un estado común de `MouseOver`. Un control sin un estado específico se considera que está en el estado `Normal` común. Los estados se dividen en grupos y los que se han mencionado antes forman parte del grupo de estados `CommonStates`. La mayoría de los controles tienen dos grupos de estados: `CommonStates` y `FocusStates`. De cada grupo de estados que se aplica a un control, un control siempre está en un estado de cada grupo, como `CommonStates.MouseOver` y `FocusStates.Unfocused`. Pero un control no puede estar en dos estados diferentes dentro del mismo grupo, como `CommonStates.Normal` y `CommonStates.Disabled`. A continuación se muestra una tabla de estados que la mayoría de los controles reconocen y usan.

| Nombre de VisualState | Nombre de VisualStateGroup | Descripción |
| ---------------- | --------------------- | ----------- |
| Normal           | CommonStates          | El estado predeterminado. |
| MouseOver        | CommonStates          | El puntero del mouse se coloca sobre el control. |
| Presionado          | CommonStates          | El control está presionado. |
| Deshabilitado         | CommonStates          | El control está deshabilitado. |
| Con foco          | FocusStates           | El control tiene el foco. |
| Sin foco        | FocusStates           | El control no tiene el foco. |

Al definir una instancia de <xref:System.Windows.VisualStateManager?displayProperty=fullName> en el elemento raíz de una plantilla de control, puede desencadenar animaciones cuando un control entra en un estado específico. En `VisualStateManager` se declaran las combinaciones de <xref:System.Windows.VisualStateGroup> y <xref:System.Windows.VisualState> que se van a inspeccionar. Cuando el control entra en un estado inspeccionado, se inicia la animación definida por `VisaulStateManager`.

Por ejemplo, en el código XAML siguiente se inspecciona el estado `CommonStates.MouseOver` para animar el color de relleno del elemento denominado `backgroundElement`. Cuando el control vuelve al estado `CommonStates.Normal`, se restaura el color de relleno del elemento `backgroundElement`.

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

Para obtener más información sobre los guiones gráficos, vea [Información general sobre guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Recursos compartidos y temas

Es posible que una aplicación WPF típica tenga varios recursos de interfaz de usuario que se apliquen en toda la aplicación. De forma colectiva, este conjunto de recursos se pueden considerar el tema para la aplicación. WPF proporciona compatibilidad para empaquetar recursos de interfaz de usuario como un tema a través de un diccionario de recursos que se encapsula como la clase <xref:System.Windows.ResourceDictionary>.

Los temas de WPF se definen mediante el mecanismo de aplicación de estilos y plantillas que WPF expone para personalizar los objetos visuales de cualquier elemento.

Los recursos de tema de WPF se almacenan en diccionarios de recursos incrustados. Estos diccionarios de recursos deben estar incrustados en un ensamblado firmado, ya sea en el mismo ensamblado que el propio código o en uno en paralelo. En el caso de PresentationFramework.dll, el ensamblado que contiene los controles de WPF, los recursos de tema se encuentran en una serie de ensamblados en paralelo.

El tema se convierte en el último lugar donde buscar el estilo de un elemento. Normalmente, se comenzará por el árbol de elementos en busca de un recurso adecuado, después se buscará en la colección de recursos de aplicación y, finalmente, se consultará el sistema. Esto proporciona a los desarrolladores de aplicaciones una oportunidad para volver a definir el estilo de cualquier objeto en el nivel de árbol o de aplicación antes de alcanzar el tema.

Los diccionarios de recursos se pueden redefinir como archivos individuales para reutilizar un tema en varias aplicaciones. También se pueden crear temas intercambiables al definir varios diccionarios de recursos que proporcionen los mismos tipos de recursos, pero con diferentes valores. La redefinición de estos estilos u otros recursos en el nivel de aplicación es el enfoque recomendado para cambiar el aspecto visual de una aplicación.

Para compartir un conjunto de recursos entre las aplicaciones (estilos y plantillas inclusive) puede crear un archivo XAML y definir un elemento <xref:System.Windows.ResourceDictionary> que incluya una referencia a un archivo `shared.xaml`.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Al compartir `shared.xaml` se define un objeto <xref:System.Windows.ResourceDictionary> que contiene un conjunto de recursos de pincel y estilos que otorga una apariencia coherente a los controles de una aplicación.

Para obtener más información, vea [Diccionarios de recursos combinados](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Si va a crear un tema para un control personalizado, vea la sección **Definición de recursos en el nivel de tema** de [Introducción a la creación de controles](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level).

## <a name="see-also"></a>Vea también

- [Identificadores URI de paquete en WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Cómo: para buscar elementos generados por un objeto ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Find DataTemplate-Generated Elements](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)
