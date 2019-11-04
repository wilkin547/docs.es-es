---
title: Personalizar la apariencia de un control existente creando una clase ControlTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: 6d7401f9614e663351968dc6a2f85548735a176d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460424"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizar la apariencia de un control existente creando una clase ControlTemplate
<a name="introduction"></a>Un <xref:System.Windows.Controls.ControlTemplate> especifica la estructura visual y el comportamiento visual de un control. Puede personalizar la apariencia de un control asignándole un nuevo <xref:System.Windows.Controls.ControlTemplate>. Cuando se crea una <xref:System.Windows.Controls.ControlTemplate>, se reemplaza la apariencia de un control existente sin cambiar su funcionalidad. Por ejemplo, puede hacer que los botones de la aplicación se redondeen en lugar de la forma cuadrada predeterminada, pero el botón seguirá generando el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.

 En este tema se explican las distintas partes de un <xref:System.Windows.Controls.ControlTemplate>, se muestra cómo crear un <xref:System.Windows.Controls.ControlTemplate> simple para un <xref:System.Windows.Controls.Button>y se explica cómo entender el contrato de control de un control para que pueda personalizar su apariencia. Dado que crea un <xref:System.Windows.Controls.ControlTemplate> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede cambiar la apariencia de un control sin necesidad de escribir ningún código. También puede utilizar un diseñador, como Blend para Visual Studio, para crear plantillas de control personalizadas. En este tema se muestran ejemplos del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que personalizan la apariencia de un <xref:System.Windows.Controls.Button> y se muestra el ejemplo completo al final del tema. Para obtener más información sobre el uso de Blend para Visual Studio, vea [aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).

 En las ilustraciones siguientes se muestra un <xref:System.Windows.Controls.Button> que usa el <xref:System.Windows.Controls.ControlTemplate> que se crea en este tema.

 ![Botón con una plantilla de control personalizado.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Un botón que usa una plantilla de control personalizado.

 ![Botón con un borde rojo.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Un botón que usa una plantilla de control personalizado y tiene el puntero del mouse sobre él.

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos
 En este tema se supone que sabe cómo crear y usar controles y estilos, como se describe en [Controls](index.md) (Controles). Los conceptos descritos en este tema se aplican a los elementos que heredan de la clase <xref:System.Windows.Controls.Control>, excepto en el <xref:System.Windows.Controls.UserControl>. No se puede aplicar un <xref:System.Windows.Controls.ControlTemplate> a un <xref:System.Windows.Controls.UserControl>.

<a name="when_you_should_create_a_controltemplate"></a>
## <a name="when-you-should-create-a-controltemplate"></a>Cuándo se debe crear un control ControlTemplate
 Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>y <xref:System.Windows.Controls.Control.FontFamily%2A>, que se pueden establecer para especificar distintos aspectos de la apariencia del control, pero los cambios que se pueden realizar mediante el establecimiento de estas propiedades están limitados. Por ejemplo, puede establecer la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> en Blue y <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un <xref:System.Windows.Controls.CheckBox>.

 Sin la capacidad de crear una nueva <xref:System.Windows.Controls.ControlTemplate> para los controles, todos los controles de cada aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]tendrían la misma apariencia general, lo que limitaría la capacidad de crear una aplicación con una apariencia personalizada. De forma predeterminada, cada <xref:System.Windows.Controls.CheckBox> tiene características similares. Por ejemplo, el contenido del <xref:System.Windows.Controls.CheckBox> siempre está a la derecha del indicador de selección y la marca de verificación siempre se usa para indicar que el <xref:System.Windows.Controls.CheckBox> está seleccionado.

 Puede crear una <xref:System.Windows.Controls.ControlTemplate> si desea personalizar la apariencia del control más allá de lo que hará la configuración de las otras propiedades del control. En el ejemplo del <xref:System.Windows.Controls.CheckBox>, supongamos que desea que el contenido de la casilla esté por encima del indicador de selección y desea que una X indique que la <xref:System.Windows.Controls.CheckBox> está seleccionada. Estos cambios se especifican en la <xref:System.Windows.Controls.ControlTemplate> de la <xref:System.Windows.Controls.CheckBox>.

 En la ilustración siguiente se muestra un <xref:System.Windows.Controls.CheckBox> que usa una <xref:System.Windows.Controls.ControlTemplate>predeterminada.

 ![Casilla con la plantilla de control predeterminada.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Un control CheckBox que usa la plantilla de control predeterminada

 En la ilustración siguiente se muestra un <xref:System.Windows.Controls.CheckBox> que usa una <xref:System.Windows.Controls.ControlTemplate> personalizada para colocar el contenido del <xref:System.Windows.Controls.CheckBox> encima del indicador de selección y muestra una X cuando se selecciona el <xref:System.Windows.Controls.CheckBox>.

 ![Casilla con una plantilla de control personalizado.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Un control CheckBox que usa una plantilla de control personalizado

 El <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.CheckBox> de este ejemplo es relativamente complejo, por lo que en este tema se usa un ejemplo más sencillo de creación de un <xref:System.Windows.Controls.ControlTemplate> para una <xref:System.Windows.Controls.Button>.

<a name="changing_the_visual_structure_of_a_control"></a>
## <a name="changing-the-visual-structure-of-a-control"></a>Cambio de la estructura visual de un control
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un control suele ser un objeto <xref:System.Windows.FrameworkElement> compuesto. Al crear un <xref:System.Windows.Controls.ControlTemplate>, se combinan <xref:System.Windows.FrameworkElement> objetos para compilar un único control. Un <xref:System.Windows.Controls.ControlTemplate> debe tener solo un <xref:System.Windows.FrameworkElement> como su elemento raíz. Normalmente, el elemento raíz contiene otros objetos <xref:System.Windows.FrameworkElement>. La combinación de objetos constituye la estructura visual del control.

 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ControlTemplate> personalizado para el <xref:System.Windows.Controls.Button>. El <xref:System.Windows.Controls.ControlTemplate> crea la estructura visual del <xref:System.Windows.Controls.Button>. En este ejemplo no cambia la apariencia del botón al mover el puntero del mouse sobre él o hacer clic en él. El cambio de la apariencia del botón cuando se encuentra en un estado diferente se explica más adelante en este tema.

 En este ejemplo, la estructura visual consta de las siguientes partes:

- <xref:System.Windows.Controls.Border> denominada `RootElement` que actúa como <xref:System.Windows.FrameworkElement>raíz de la plantilla.

- <xref:System.Windows.Controls.Grid> que es un elemento secundario de `RootElement`.

- <xref:System.Windows.Controls.ContentPresenter> que muestra el contenido del botón. El <xref:System.Windows.Controls.ContentPresenter> permite mostrar cualquier tipo de objeto.

 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]

### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Conservación de la funcionalidad de las propiedades de un control mediante TemplateBinding
 Al crear una nueva <xref:System.Windows.Controls.ControlTemplate>, es posible que desee usar las propiedades públicas para cambiar la apariencia del control. La extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) enlaza una propiedad de un elemento que está en el <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública definida por el control. Cuando se usa [TemplateBinding](../advanced/templatebinding-markup-extension.md), se habilitan propiedades en el control que actúan como parámetros de la plantilla. Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../advanced/templatebinding-markup-extension.md).

 En el ejemplo siguiente se repite la parte del ejemplo anterior que usa la extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) para enlazar propiedades de los elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate> a las propiedades públicas definidas por el botón.

 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]

 En este ejemplo, el <xref:System.Windows.Controls.Grid> tiene su plantilla de propiedad <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> enlazada a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Dado que <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> está enlazado a una plantilla, puede crear varios botones que usen el mismo <xref:System.Windows.Controls.ControlTemplate> y establecer el <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> en valores diferentes en cada botón. Si <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> no estaba enlazada a una plantilla a una propiedad de un elemento en el <xref:System.Windows.Controls.ControlTemplate>, el establecimiento del <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> de un botón no tendría ningún impacto en la apariencia del botón.

 Tenga en cuenta que los nombres de las dos propiedades no tienen que ser idénticos. En el ejemplo anterior, la propiedad <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> del <xref:System.Windows.Controls.Button> está enlazada a la plantilla <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> de la <xref:System.Windows.Controls.ContentPresenter>. Esto permite que el contenido del botón se sitúe horizontalmente. <xref:System.Windows.Controls.ContentPresenter> no tiene una propiedad denominada `HorizontalContentAlignment`, pero <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> se puede enlazar a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Cuando la plantilla enlaza una propiedad, asegúrese de que las propiedades de origen y de destino sean del mismo tipo.

 La clase <xref:System.Windows.Controls.Control> define varias propiedades que la plantilla de control debe usar para tener un efecto en el control cuando se establecen. La forma en que el <xref:System.Windows.Controls.ControlTemplate> utiliza la propiedad depende de la propiedad. El <xref:System.Windows.Controls.ControlTemplate> debe utilizar la propiedad de una de las siguientes maneras:

- Un elemento de la plantilla <xref:System.Windows.Controls.ControlTemplate> se enlaza a la propiedad.

- Un elemento de la <xref:System.Windows.Controls.ControlTemplate> hereda la propiedad de un <xref:System.Windows.FrameworkElement>primario.

 En la tabla siguiente se enumeran las propiedades visuales que hereda un control de la clase <xref:System.Windows.Controls.Control>. También se indica si la plantilla de control predeterminado de un control usa el valor de propiedad heredado o si debe estar enlazado a plantilla.

|Propiedad.|Método de uso|
|--------------|------------------|
|<xref:System.Windows.Controls.Control.Background%2A>|Enlace a plantilla|
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Enlace a plantilla|
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Enlace a plantilla|
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Herencia de propiedad o enlace a plantilla|
|<xref:System.Windows.Controls.Control.FontSize%2A>|Herencia de propiedad o enlace a plantilla|
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Herencia de propiedad o enlace a plantilla|
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Herencia de propiedad o enlace a plantilla|
|<xref:System.Windows.Controls.Control.Foreground%2A>|Herencia de propiedad o enlace a plantilla|
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Enlace a plantilla|
|<xref:System.Windows.Controls.Control.Padding%2A>|Enlace a plantilla|
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Enlace a plantilla|

 En la tabla solo se enumeran las propiedades visuales heredadas de la clase <xref:System.Windows.Controls.Control>. Además de las propiedades enumeradas en la tabla, un control también puede heredar las propiedades <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>y <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> del elemento de marco de trabajo primario.

 Además, si el <xref:System.Windows.Controls.ContentPresenter> está en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Controls.ContentControl>, el <xref:System.Windows.Controls.ContentPresenter> se enlazará automáticamente a las propiedades <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>. Del mismo modo, un <xref:System.Windows.Controls.ItemsPresenter> que se encuentra en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Controls.ItemsControl> se enlazará automáticamente a las propiedades <xref:System.Windows.Controls.ItemsControl.Items%2A> y <xref:System.Windows.Controls.ItemsPresenter>.

 En el ejemplo siguiente se crean dos botones que usan el <xref:System.Windows.Controls.ControlTemplate> definido en el ejemplo anterior. En el ejemplo se establecen las propiedades <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>y <xref:System.Windows.Controls.Control.FontSize%2A> en cada botón. Establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A> tiene un efecto porque está enlazada a la plantilla en el <xref:System.Windows.Controls.ControlTemplate>. Aunque las propiedades <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontSize%2A> no están enlazadas a una plantilla, su configuración tiene un efecto porque sus valores son heredados.

 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]

 El ejemplo anterior genera un resultado similar a la siguiente ilustración.

 ![Dos botones, uno azul y otro púrpura.](./media/ndp-buttontwo.png "NDP_ButtonTwo")
Dos botones con diferentes colores de fondo

<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Cambio de la apariencia de un control según su estado
 La diferencia entre un botón con su apariencia predeterminada y el botón del ejemplo anterior es que el botón predeterminado cambia sutilmente cuando se encuentra en estados diferentes. Por ejemplo, la apariencia del botón predeterminado cambia cuando se presiona el botón o cuando se sitúa el puntero del mouse sobre él. Aunque el <xref:System.Windows.Controls.ControlTemplate> no cambia la funcionalidad de un control, cambia el comportamiento visual del control. Un comportamiento visual describe la apariencia del control cuando se encuentra en un estado determinado. Para comprender la diferencia entre la funcionalidad y el comportamiento visual de un control, considere el ejemplo del botón. La funcionalidad del botón es generar el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> cuando se hace clic en él, pero el comportamiento visual del botón es cambiar su apariencia cuando se señala o se presiona.

 Los objetos <xref:System.Windows.VisualState> se usan para especificar la apariencia de un control cuando se encuentra en un estado determinado. Un <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> que cambia la apariencia de los elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate>. No es necesario escribir código para que esto suceda porque la lógica del control cambia de estado mediante el <xref:System.Windows.VisualStateManager>. Cuando el control entra en el estado especificado por la propiedad <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType>, comienza el <xref:System.Windows.Media.Animation.Storyboard>. Cuando el control sale del estado, el <xref:System.Windows.Media.Animation.Storyboard> se detiene.

 En el ejemplo siguiente se muestra el <xref:System.Windows.VisualState> que cambia la apariencia de un <xref:System.Windows.Controls.Button> cuando el puntero del mouse se sitúa sobre él. El <xref:System.Windows.Media.Animation.Storyboard> cambia el color del borde del botón cambiando el color del `BorderBrush`. Si hace referencia al ejemplo <xref:System.Windows.Controls.ControlTemplate> al principio de este tema, recordará que `BorderBrush` es el nombre de la <xref:System.Windows.Media.SolidColorBrush> que se asigna al <xref:System.Windows.Controls.Border.Background%2A> del <xref:System.Windows.Controls.Border>.

 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]

 El control es responsable de definir los estados como parte de su contrato de control, que se describe de manera detallada en [Personalización de otros controles mediante la comprensión del contrato de control](#customizing_other_controls_by_understanding_the_control_contract) más adelante en este tema. En la tabla siguiente se enumeran los Estados que se especifican para el <xref:System.Windows.Controls.Button>.

|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|
|----------------------|---------------------------|-----------------|
|Normal|CommonStates|El estado predeterminado.|
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|
|Presionado|CommonStates|El control está presionado.|
|Deshabilitado|CommonStates|El control está deshabilitado.|
|Con foco|FocusStates|El control tiene el foco.|
|Sin foco|FocusStates|El control no tiene el foco.|

 El <xref:System.Windows.Controls.Button> define dos grupos de Estados: el `CommonStates` grupo contiene los Estados `Normal`, `MouseOver`, `Pressed`y `Disabled`. El grupo `FocusStates` contiene los estados `Focused` y `Unfocused`. Los estados en el mismo grupo de estado son mutuamente excluyentes. El control siempre está exactamente en un estado por grupo. Por ejemplo, un <xref:System.Windows.Controls.Button> puede tener el foco incluso cuando el puntero del mouse no se sitúa sobre él, por lo que un <xref:System.Windows.Controls.Button> en el estado de la `Focused` puede estar en el estado `MouseOver`, `Pressed`o `Normal`.

 Agregue <xref:System.Windows.VisualState> objetos a <xref:System.Windows.VisualStateGroup> objetos. Agregue <xref:System.Windows.VisualStateGroup> objetos a la <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta. En el ejemplo siguiente se define el <xref:System.Windows.VisualState> objetos para los Estados `Normal`, `MouseOver`y `Pressed`, que están todos en el grupo `CommonStates`. El <xref:System.Windows.VisualState.Name%2A> de cada <xref:System.Windows.VisualState> coincide con el nombre de la tabla anterior. El estado `Disabled` y los estados del grupo `FocusStates` se omiten para abreviar el ejemplo, pero se incluyen en el ejemplo completo al final de este tema.

> [!NOTE]
> Asegúrese de establecer la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> en la <xref:System.Windows.FrameworkElement> raíz de la <xref:System.Windows.Controls.ControlTemplate>.

 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]

 El ejemplo anterior genera un resultado similar a las siguientes ilustraciones.

 ![Botón con una plantilla de control personalizado.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Un botón que usa una plantilla de control personalizado en el estado normal

 ![Botón con un borde rojo.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Un botón que usa una plantilla de control personalizado en el estado de pasar el mouse

 ![El borde es transparente en un botón presionado.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")
Un botón que usa una plantilla de control personalizado en el estado presionado

 Para encontrar los estados visuales de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](control-styles-and-templates.md).

<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Especificación del comportamiento de un control cuando realiza la transición entre estados
 En el ejemplo anterior, la apariencia del botón también cambia cuando el usuario hace clic en él, pero a menos que se presione el botón durante un segundo completo, el usuario no verá el efecto. De forma predeterminada, la animación tarda un segundo en producirse. Dado que es probable que los usuarios haga clic y publiquen un botón en mucho menos tiempo, los comentarios visuales no serán efectivos si deja el <xref:System.Windows.Controls.ControlTemplate> en su estado predeterminado.

 Puede especificar la cantidad de tiempo que tarda en producirse una animación para pasar sin problemas un control de un estado a otro agregando <xref:System.Windows.VisualTransition> objetos a la <xref:System.Windows.Controls.ControlTemplate>. Cuando se crea una <xref:System.Windows.VisualTransition>, se especifican uno o varios de los siguientes elementos:

- El tiempo que tarda en producirse una transición entre estados.

- Los cambios adicionales en la apariencia del control que se producen en el momento de la transición.

- En qué Estados se aplica el <xref:System.Windows.VisualTransition>.

### <a name="specifying-the-duration-of-a-transition"></a>Especificación de la duración de una transición
 Puede especificar cuánto tiempo tarda una transición estableciendo la propiedad <xref:System.Windows.VisualTransition.GeneratedDuration%2A>. El ejemplo anterior tiene una <xref:System.Windows.VisualState> que especifica que el borde del botón se vuelve transparente cuando se presiona el botón, pero la animación tarda demasiado tiempo en ser apreciable si el botón se presiona y se suelta rápidamente. Puede usar un <xref:System.Windows.VisualTransition> para especificar la cantidad de tiempo que tarda el control en pasar al estado presionado. En el ejemplo siguiente se especifica que el control tarda una centésima de segundo en pasar al estado presionado.

 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]

### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Especificación de cambios en la apariencia del control durante una transición
 El <xref:System.Windows.VisualTransition> contiene un <xref:System.Windows.Media.Animation.Storyboard> que comienza cuando el control realiza la transición entre Estados. Por ejemplo, puede especificar que se produzca una determinada animación cuando el control pase del estado `MouseOver` al estado `Normal`. En el ejemplo siguiente se crea una <xref:System.Windows.VisualTransition> que especifica que cuando el usuario mueve el puntero del mouse fuera del botón, el borde del botón cambia a azul, luego a amarillo y luego a negro en 1,5 segundos.

 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]

### <a name="specifying-when-a-visualtransition-is-applied"></a>Especificación de cuándo aplicar un objeto VisualTransition
 Un <xref:System.Windows.VisualTransition> se puede restringir para que solo se aplique a determinados Estados, o bien se puede aplicar cada vez que el control realiza la transición entre Estados. En el ejemplo anterior, se aplica el <xref:System.Windows.VisualTransition> cuando el control pasa del estado `MouseOver` al estado `Normal`; en el ejemplo anterior, se aplica el <xref:System.Windows.VisualTransition> cuando el control entra en el estado `Pressed`. Restrinja el momento en que se aplica un <xref:System.Windows.VisualTransition> estableciendo las propiedades <xref:System.Windows.VisualTransition.To%2A> y <xref:System.Windows.VisualTransition.From%2A>. En la tabla siguiente se describen los niveles de restricción del más al menos restrictivo.

|Tipo de restricción|Valor de Desde|Valor de Hasta|
|-------------------------|-------------------|-----------------|
|Desde un estado especificado hasta otro estado especificado|Nombre de un <xref:System.Windows.VisualState>|Nombre de un <xref:System.Windows.VisualState>|
|Desde cualquier estado hasta un estado especificado|Sin establecer|Nombre de un <xref:System.Windows.VisualState>|
|Desde un estado especificado hasta cualquier estado|Nombre de un <xref:System.Windows.VisualState>|Sin establecer|
|Desde cualquier estado hasta cualquier otro estado|Sin establecer|Sin establecer|

 Puede tener varios objetos <xref:System.Windows.VisualTransition> en una <xref:System.Windows.VisualStateGroup> que hagan referencia al mismo estado, pero se usarán en el orden en que se especifica la tabla anterior. En el ejemplo siguiente, hay dos objetos <xref:System.Windows.VisualTransition>. Cuando el control realiza la transición desde el estado `Pressed` al estado `MouseOver`, se utiliza el <xref:System.Windows.VisualTransition> que tiene <xref:System.Windows.VisualTransition.From%2A> y <xref:System.Windows.VisualTransition.To%2A> establecido. Cuando el control realiza la transición de un estado que no es `Pressed` al estado `MouseOver`, se usa el otro estado.

 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]

 El <xref:System.Windows.VisualStateGroup> tiene una propiedad <xref:System.Windows.VisualStateGroup.Transitions%2A> que contiene los objetos <xref:System.Windows.VisualTransition> que se aplican a los objetos <xref:System.Windows.VisualState> del <xref:System.Windows.VisualStateGroup>. Como autor del <xref:System.Windows.Controls.ControlTemplate>, puede incluir cualquier <xref:System.Windows.VisualTransition> que desee. Sin embargo, si las propiedades <xref:System.Windows.VisualTransition.To%2A> y <xref:System.Windows.VisualTransition.From%2A> se establecen en nombres de estado que no están en el <xref:System.Windows.VisualStateGroup>, se omite el <xref:System.Windows.VisualTransition>.

 En el ejemplo siguiente se muestra el <xref:System.Windows.VisualStateGroup> para la `CommonStates`. En el ejemplo se define una <xref:System.Windows.VisualTransition> para cada una de las transiciones siguientes del botón.

- Al estado `Pressed`.

- Al estado `MouseOver`.

- Desde el estado `Pressed` hasta el estado `MouseOver`.

- Desde el estado `MouseOver` hasta el estado `Normal`.

 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]

<a name="customizing_other_controls_by_understanding_the_control_contract"></a>
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalización de otros controles mediante la comprensión del contrato de control
 Un control que usa un <xref:System.Windows.Controls.ControlTemplate> para especificar su estructura visual (mediante objetos <xref:System.Windows.FrameworkElement>) y el comportamiento visual (mediante objetos <xref:System.Windows.VisualState>) utiliza el modelo de control de elementos. Muchos de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 emplean este modelo. Los elementos que debe tener en cuenta el autor de <xref:System.Windows.Controls.ControlTemplate> se comunican a través del contrato de control. Una vez que comprende las partes de un contrato de control, puede personalizar la apariencia de cualquier control que utilice el modelo de control de elementos.

 Un contrato de control tiene tres elementos:

- Los elementos visuales que usa la lógica del control.

- Los estados del control y el grupo al que pertenece cada estado.

- Las propiedades públicas que afectan visualmente al control.

### <a name="visual-elements-in-the-control-contract"></a>Elementos visuales del contrato de control
 A veces, la lógica de un control interactúa con un <xref:System.Windows.FrameworkElement> que se encuentra en el <xref:System.Windows.Controls.ControlTemplate>. Por ejemplo, el control podría controlar un evento de uno de sus elementos. Cuando un control espera encontrar una <xref:System.Windows.FrameworkElement> determinada en el <xref:System.Windows.Controls.ControlTemplate>, debe transmitir esa información al autor de la <xref:System.Windows.Controls.ControlTemplate>. El control utiliza el <xref:System.Windows.TemplatePartAttribute> para transmitir el tipo de elemento que se espera y el nombre del elemento. El <xref:System.Windows.Controls.Button> no tiene elementos <xref:System.Windows.FrameworkElement> en su contrato de control, pero sí otros controles, como el <xref:System.Windows.Controls.ComboBox>.

 En el ejemplo siguiente se muestra la <xref:System.Windows.TemplatePartAttribute> objetos que se especifican en la clase <xref:System.Windows.Controls.ComboBox>. La lógica de <xref:System.Windows.Controls.ComboBox> espera encontrar un <xref:System.Windows.Controls.TextBox> denominado `PART_EditableTextBox` y una <xref:System.Windows.Controls.Primitives.Popup> denominada `PART_Popup` en su <xref:System.Windows.Controls.ControlTemplate>.

 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]

 En el ejemplo siguiente se muestra una <xref:System.Windows.Controls.ControlTemplate> simplificada para la <xref:System.Windows.Controls.ComboBox> que incluye los elementos especificados por los objetos <xref:System.Windows.TemplatePartAttribute> en la clase <xref:System.Windows.Controls.ComboBox>.

 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]

### <a name="states-in-the-control-contract"></a>Estados del contrato de control
 Los estados de un control también forman parte del contrato de control. En el ejemplo de creación de un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button> se muestra cómo especificar la apariencia de un <xref:System.Windows.Controls.Button> en función de sus Estados. Se crea un <xref:System.Windows.VisualState> para cada estado especificado y se colocan todos los objetos <xref:System.Windows.VisualState> que comparten un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> en un <xref:System.Windows.VisualStateGroup>, tal y como se describe en [cambiar la apariencia de un control en función de su estado](#changing_the_appearance_of_a_control_depending_on_its_state) anterior en este tema. Los controles de terceros deben especificar los Estados mediante el <xref:System.Windows.TemplateVisualStateAttribute>, que permite a las herramientas del diseñador, como la [Diseñador XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio) en Visual Studio y Blend para Visual Studio, exponer los Estados del control para crear plantillas de control.

 Para encontrar el contrato de control de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](control-styles-and-templates.md).

### <a name="properties-in-the-control-contract"></a>Propiedades del contrato de control
 Las propiedades públicas que afectan visualmente al control también se incluyen en el contrato de control. Puede establecer estas propiedades para cambiar la apariencia del control sin crear un nuevo <xref:System.Windows.Controls.ControlTemplate>. También puede usar la extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) para enlazar propiedades de los elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate> a las propiedades públicas definidas por el <xref:System.Windows.Controls.Button>.

 En el ejemplo siguiente se muestra el contrato de control del botón.

 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]

 Al crear una <xref:System.Windows.Controls.ControlTemplate>, a menudo es más fácil comenzar con una <xref:System.Windows.Controls.ControlTemplate> existente y realizar cambios en ella. Puede realizar una de las siguientes acciones para cambiar una <xref:System.Windows.Controls.ControlTemplate>existente:

- Utilice un diseñador, como Blend para Visual Studio, que proporciona una interfaz gráfica de usuario para crear plantillas de control. Para más información, consulte [Aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).

- Obtiene la <xref:System.Windows.Controls.ControlTemplate> predeterminada y edítela. Para encontrar las plantillas de control predeterminadas que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252) (Temas de WPF predeterminados).

<a name="complete_example"></a>
## <a name="complete-example"></a>Ejemplo completo
 En el ejemplo siguiente se muestra el<xref:System.Windows.Controls.ControlTemplate> completo <xref:System.Windows.Controls.Button>que se describe en este tema.

 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]

## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
