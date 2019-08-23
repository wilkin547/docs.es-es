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
ms.openlocfilehash: 63a0b724b71c4a4901c2dedcf502045a75ec405c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933728"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizar la apariencia de un control existente creando una clase ControlTemplate
<a name="introduction"></a><xref:System.Windows.Controls.ControlTemplate> Especifica la estructura visual y el comportamiento visual de un control. Puede personalizar la apariencia de un control asignándole un nuevo <xref:System.Windows.Controls.ControlTemplate>. Al crear un <xref:System.Windows.Controls.ControlTemplate>, se reemplaza la apariencia de un control existente sin cambiar su funcionalidad. Por ejemplo, puede hacer que los botones de la aplicación se redondeen en lugar de la forma cuadrada predeterminada, pero el botón seguirá <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generando el evento.  
  
 En este tema se explican las distintas <xref:System.Windows.Controls.ControlTemplate>partes de, se muestra <xref:System.Windows.Controls.ControlTemplate> cómo crear <xref:System.Windows.Controls.Button>una sencilla para un y se explica cómo entender el contrato de control de un control para que pueda personalizar su apariencia. Dado que crea un <xref:System.Windows.Controls.ControlTemplate> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede cambiar la apariencia de un control sin escribir ningún código. También puede usar un diseñador, como Microsoft Expression Blend, para crear plantillas de control personalizado. En este tema se muestran ejemplos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de que personalizan la apariencia <xref:System.Windows.Controls.Button> de un y se muestra el ejemplo completo al final del tema. Para más información acerca del uso de Expression Blend, consulte [Aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 En las ilustraciones siguientes se <xref:System.Windows.Controls.Button> muestra un que <xref:System.Windows.Controls.ControlTemplate> utiliza el creado en este tema.  
  
 ![Un botón con una plantilla de control personalizado.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Un botón que usa una plantilla de control personalizado.  
  
 ![Botón con un borde rojo.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Un botón que usa una plantilla de control personalizado y tiene el puntero del mouse sobre él.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que sabe cómo crear y usar controles y estilos, como se describe en [Controls](index.md) (Controles). Los conceptos descritos en este tema se aplican a los elementos <xref:System.Windows.Controls.Control> que heredan de la <xref:System.Windows.Controls.UserControl>clase, excepto para. No se puede aplicar <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.UserControl>a.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Cuándo se debe crear un control ControlTemplate  
 Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>y <xref:System.Windows.Controls.Control.FontFamily%2A>, que se pueden establecer para especificar distintos aspectos de la apariencia del control, pero los cambios que se pueden realizar mediante el establecimiento de estas propiedades son limitados. Por ejemplo, puede establecer la <xref:System.Windows.Controls.Control.Foreground%2A> propiedad en azul y <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un <xref:System.Windows.Controls.CheckBox>.  
  
 Sin la capacidad de crear una nueva <xref:System.Windows.Controls.ControlTemplate> para los controles, todos los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]de cada aplicación basada en tendrían la misma apariencia general, lo que limitaría la capacidad de crear una aplicación con una apariencia personalizada. De forma predeterminada, <xref:System.Windows.Controls.CheckBox> cada tiene características similares. Por ejemplo, el contenido de <xref:System.Windows.Controls.CheckBox> siempre está a la derecha del indicador de selección y la marca de verificación siempre se utiliza para indicar <xref:System.Windows.Controls.CheckBox> que está seleccionado.  
  
 Cree un <xref:System.Windows.Controls.ControlTemplate> elemento cuando desee personalizar la apariencia del control más allá del valor que realizarán las demás propiedades del control. En el ejemplo de <xref:System.Windows.Controls.CheckBox>, supongamos que desea que el contenido de la casilla esté por encima del indicador de selección y desea que una X indique <xref:System.Windows.Controls.CheckBox> que está seleccionado. Estos cambios se especifican en <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>del.  
  
 En la ilustración siguiente se <xref:System.Windows.Controls.CheckBox> muestra un que usa <xref:System.Windows.Controls.ControlTemplate>un valor predeterminado.  
  
 ![Casilla con la plantilla de control predeterminada.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Un control CheckBox que usa la plantilla de control predeterminada  
  
 En la ilustración siguiente se <xref:System.Windows.Controls.CheckBox> muestra un que usa <xref:System.Windows.Controls.ControlTemplate> un personalizado para <xref:System.Windows.Controls.CheckBox> colocar el contenido de encima del indicador de <xref:System.Windows.Controls.CheckBox> selección y muestra una X cuando está seleccionado.  
  
 ![Una casilla con una plantilla de control personalizado.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Un control CheckBox que usa una plantilla de control personalizado  
  
 El <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ControlTemplate> de en este ejemplo es relativamente complejo, por lo que en este tema se usa un ejemplo más sencillo <xref:System.Windows.Controls.Button>de creación de para. <xref:System.Windows.Controls.CheckBox>  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Cambio de la estructura visual de un control  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un control suele ser un objeto <xref:System.Windows.FrameworkElement> compuesto. Al crear una <xref:System.Windows.Controls.ControlTemplate>, se combinan <xref:System.Windows.FrameworkElement> objetos para compilar un único control. Un <xref:System.Windows.Controls.ControlTemplate> solo debe tener uno <xref:System.Windows.FrameworkElement> como su elemento raíz. Normalmente, el elemento raíz contiene <xref:System.Windows.FrameworkElement> otros objetos. La combinación de objetos constituye la estructura visual del control.  
  
 En el ejemplo siguiente se crea <xref:System.Windows.Controls.ControlTemplate> un personalizado para. <xref:System.Windows.Controls.Button> Crea la estructura visual <xref:System.Windows.Controls.Button>del. <xref:System.Windows.Controls.ControlTemplate> En este ejemplo no cambia la apariencia del botón al mover el puntero del mouse sobre él o hacer clic en él. El cambio de la apariencia del botón cuando se encuentra en un estado diferente se explica más adelante en este tema.  
  
 En este ejemplo, la estructura visual consta de las siguientes partes:  
  
- Denominado que actúa como la raíz <xref:System.Windows.FrameworkElement>de la plantilla. `RootElement` <xref:System.Windows.Controls.Border>  
  
- Que es un elemento secundario de `RootElement`. <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.ContentPresenter> Que muestra el contenido del botón. <xref:System.Windows.Controls.ContentPresenter> Habilita cualquier tipo de objeto que se va a mostrar.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Conservación de la funcionalidad de las propiedades de un control mediante TemplateBinding  
 Al crear un nuevo <xref:System.Windows.Controls.ControlTemplate>, es posible que desee usar las propiedades públicas para cambiar la apariencia del control. La extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) enlaza una propiedad de un elemento que está en <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública definida por el control. Cuando se usa [TemplateBinding](../advanced/templatebinding-markup-extension.md), se habilitan propiedades en el control que actúan como parámetros de la plantilla. Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../advanced/templatebinding-markup-extension.md).  
  
 En el ejemplo siguiente se repite la parte del ejemplo anterior que usa la extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) para enlazar propiedades de elementos que <xref:System.Windows.Controls.ControlTemplate> están en las propiedades públicas definidas por el botón.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 En este ejemplo, el <xref:System.Windows.Controls.Grid> tiene su <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> plantilla de propiedades enlazada a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Dado <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> que está enlazado <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> a una plantilla, puede crear varios botones que <xref:System.Windows.Controls.ControlTemplate> usen el mismo y establecer en valores diferentes en cada botón. Si <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> no estaba enlazado a una plantilla a una propiedad de un <xref:System.Windows.Controls.ControlTemplate>elemento en, <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> el establecimiento del de un botón no tendría ningún impacto en la apariencia del botón.  
  
 Tenga en cuenta que los nombres de las dos propiedades no tienen que ser idénticos. En el ejemplo anterior, la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> propiedad de la <xref:System.Windows.Controls.Button> plantilla está enlazada <xref:System.Windows.Controls.ContentPresenter>a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> la propiedad de. Esto permite que el contenido del botón se sitúe horizontalmente. <xref:System.Windows.Controls.ContentPresenter>no tiene una propiedad denominada `HorizontalContentAlignment`, pero <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> se puede enlazar a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Cuando la plantilla enlaza una propiedad, asegúrese de que las propiedades de origen y de destino sean del mismo tipo.  
  
 La <xref:System.Windows.Controls.Control> clase define varias propiedades que la plantilla de control debe usar para tener un efecto en el control cuando se establecen. La forma en que utilizalapropiedaddependedelapropiedad.<xref:System.Windows.Controls.ControlTemplate> El <xref:System.Windows.Controls.ControlTemplate> debe utilizar la propiedad de una de las siguientes maneras:  
  
- Un elemento de la <xref:System.Windows.Controls.ControlTemplate> plantilla se enlaza a la propiedad.  
  
- Un elemento de <xref:System.Windows.Controls.ControlTemplate> hereda la propiedad de un elemento primario <xref:System.Windows.FrameworkElement>.  
  
 En la tabla siguiente se enumeran las propiedades visuales que hereda un <xref:System.Windows.Controls.Control> control de la clase. También se indica si la plantilla de control predeterminado de un control usa el valor de propiedad heredado o si debe estar enlazado a plantilla.  
  
|Propiedad|Método de uso|  
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
  
 En la tabla solo se enumeran las propiedades visuales <xref:System.Windows.Controls.Control> heredadas de la clase. Además de las propiedades enumeradas en la tabla, un control también puede heredar las <xref:System.Windows.FrameworkElement.DataContext%2A>propiedades <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> , <xref:System.Windows.FrameworkElement.Language%2A>y del elemento de marco primario.  
  
 Además <xref:System.Windows.Controls.ContentPresenter> , si se encuentra <xref:System.Windows.Controls.ControlTemplate> en de <xref:System.Windows.Controls.ContentControl>, el <xref:System.Windows.Controls.ContentPresenter> se enlazará automáticamente a las <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedades y <xref:System.Windows.Controls.ContentControl.Content%2A> . <xref:System.Windows.Controls.ControlTemplate> Del mismo modo <xref:System.Windows.Controls.ItemsPresenter> , un que se encuentra en <xref:System.Windows.Controls.ItemsControl> de un se enlazará <xref:System.Windows.Controls.ItemsControl.Items%2A> automáticamente <xref:System.Windows.Controls.ItemsPresenter> a las propiedades y.  
  
 En el ejemplo siguiente se crean dos botones que <xref:System.Windows.Controls.ControlTemplate> usan el definido en el ejemplo anterior. En el ejemplo se <xref:System.Windows.Controls.Control.Background%2A>establecen <xref:System.Windows.Controls.Control.Foreground%2A>las propiedades <xref:System.Windows.Controls.Control.FontSize%2A> , y en cada botón. La configuración <xref:System.Windows.Controls.Control.Background%2A> de la propiedad tiene un efecto porque está enlazada a <xref:System.Windows.Controls.ControlTemplate>la plantilla en. Aunque las <xref:System.Windows.Controls.Control.Foreground%2A> propiedades y <xref:System.Windows.Controls.Control.FontSize%2A> no tienen un enlace de plantilla, su configuración tiene un efecto porque sus valores son heredados.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 El ejemplo anterior genera un resultado similar a la siguiente ilustración.  
  
 ![Dos botones, uno azul y otro púrpura.](./media/ndp-buttontwo.png "NDP_ButtonTwo")  
Dos botones con diferentes colores de fondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Cambio de la apariencia de un control según su estado  
 La diferencia entre un botón con su apariencia predeterminada y el botón del ejemplo anterior es que el botón predeterminado cambia sutilmente cuando se encuentra en estados diferentes. Por ejemplo, la apariencia del botón predeterminado cambia cuando se presiona el botón o cuando se sitúa el puntero del mouse sobre él. <xref:System.Windows.Controls.ControlTemplate> Aunque no cambia la funcionalidad de un control, cambia el comportamiento visual del control. Un comportamiento visual describe la apariencia del control cuando se encuentra en un estado determinado. Para comprender la diferencia entre la funcionalidad y el comportamiento visual de un control, considere el ejemplo del botón. La funcionalidad del botón es generar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento cuando se hace clic en él, pero el comportamiento visual del botón es cambiar su apariencia cuando se señala o se presiona.  
  
 Los objetos <xref:System.Windows.VisualState> se usan para especificar la apariencia de un control cuando se encuentra en un estado determinado. Un <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> que cambia la apariencia de los <xref:System.Windows.Controls.ControlTemplate>elementos que se encuentran en. No es necesario escribir código para que esto suceda porque la lógica del control cambia de estado <xref:System.Windows.VisualStateManager>mediante. Cuando el control entra en el estado especificado por la <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> propiedad <xref:System.Windows.Media.Animation.Storyboard> , comienza. Cuando el control sale del estado, <xref:System.Windows.Media.Animation.Storyboard> se detiene.  
  
 En el ejemplo siguiente se <xref:System.Windows.VisualState> muestra el que cambia la apariencia <xref:System.Windows.Controls.Button> de cuando el puntero del mouse se sitúa sobre él. Cambia el color del borde del botón cambiando el color `BorderBrush`del. <xref:System.Windows.Media.Animation.Storyboard> Si hace <xref:System.Windows.Controls.ControlTemplate> referencia al ejemplo al principio de este tema, recordará que `BorderBrush` <xref:System.Windows.Media.SolidColorBrush> es el nombre del que está asignado al <xref:System.Windows.Controls.Border.Background%2A> de <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 El control es responsable de definir los estados como parte de su contrato de control, que se describe de manera detallada en [Personalización de otros controles mediante la comprensión del contrato de control](#customizing_other_controls_by_understanding_the_control_contract) más adelante en este tema. En la tabla siguiente se enumeran los Estados que se <xref:System.Windows.Controls.Button>especifican para.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|DESCRIPCIÓN|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Presionado|CommonStates|El control está presionado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
  
 `CommonStates` `MouseOver` `Normal` `Disabled` Define dos grupos de Estados: el`Pressed`grupo contiene los Estados,, y. <xref:System.Windows.Controls.Button> El grupo `FocusStates` contiene los estados `Focused` y `Unfocused`. Los estados en el mismo grupo de estado son mutuamente excluyentes. El control siempre está exactamente en un estado por grupo. Por ejemplo, un <xref:System.Windows.Controls.Button> puede tener el foco incluso cuando el puntero del mouse no se sitúa sobre él <xref:System.Windows.Controls.Button> , de `Focused` modo que un en el `MouseOver`estado puede estar `Normal` en el estado, `Pressed`o.  
  
 Los objetos <xref:System.Windows.VisualState> se agregan a <xref:System.Windows.VisualStateGroup> los objetos. Los objetos <xref:System.Windows.VisualStateGroup> se agregan <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> a la propiedad adjunta. En el ejemplo siguiente se <xref:System.Windows.VisualState> definen los objetos `Normal`para `MouseOver`los Estados `Pressed` , y, que están todos en `CommonStates` el grupo. La <xref:System.Windows.VisualState.Name%2A> de cada <xref:System.Windows.VisualState> coincide con el nombre de la tabla anterior. El estado `Disabled` y los estados del grupo `FocusStates` se omiten para abreviar el ejemplo, pero se incluyen en el ejemplo completo al final de este tema.  
  
> [!NOTE]
> Asegúrese de establecer la <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta en la raíz <xref:System.Windows.FrameworkElement> de <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 El ejemplo anterior genera un resultado similar a las siguientes ilustraciones.  
  
 ![Un botón con una plantilla de control personalizado.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Un botón que usa una plantilla de control personalizado en el estado normal  
  
 ![Botón con un borde rojo.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Un botón que usa una plantilla de control personalizado en el estado de pasar el mouse  
  
 ![El borde es transparente en un botón presionado.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Un botón que usa una plantilla de control personalizado en el estado presionado  
  
 Para encontrar los estados visuales de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Especificación del comportamiento de un control cuando realiza la transición entre estados  
 En el ejemplo anterior, la apariencia del botón también cambia cuando el usuario hace clic en él, pero a menos que se presione el botón durante un segundo completo, el usuario no verá el efecto. De forma predeterminada, la animación tarda un segundo en producirse. Dado que es probable que los usuarios haga clic y publiquen un botón en mucho menos tiempo, los comentarios visuales no serán efectivos <xref:System.Windows.Controls.ControlTemplate> si deja en su estado predeterminado.  
  
 Puede especificar la cantidad de tiempo que tarda en producirse una animación para pasar sin problemas un control de un estado a otro agregando <xref:System.Windows.VisualTransition> objetos <xref:System.Windows.Controls.ControlTemplate>a. Al crear una <xref:System.Windows.VisualTransition>, debe especificar una o varias de las siguientes opciones:  
  
- El tiempo que tarda en producirse una transición entre estados.  
  
- Los cambios adicionales en la apariencia del control que se producen en el momento de la transición.  
  
- A qué Estados <xref:System.Windows.VisualTransition> se aplica el.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Especificación de la duración de una transición  
 Puede especificar cuánto tiempo tarda una transición estableciendo la <xref:System.Windows.VisualTransition.GeneratedDuration%2A> propiedad. El ejemplo anterior tiene un <xref:System.Windows.VisualState> que especifica que el borde del botón se vuelve transparente cuando se presiona el botón, pero la animación tarda demasiado tiempo en ser perceptible si el botón se presiona y se suelta rápidamente. Puede utilizar un <xref:System.Windows.VisualTransition> para especificar la cantidad de tiempo que tarda el control en pasar al estado presionado. En el ejemplo siguiente se especifica que el control tarda una centésima de segundo en pasar al estado presionado.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Especificación de cambios en la apariencia del control durante una transición  
 <xref:System.Windows.VisualTransition> Contiene un<xref:System.Windows.Media.Animation.Storyboard> que comienza cuando el control realiza la transición entre Estados. Por ejemplo, puede especificar que se produzca una determinada animación cuando el control pase del estado `MouseOver` al estado `Normal`. En el ejemplo siguiente se <xref:System.Windows.VisualTransition> crea un que especifica que cuando el usuario mueve el puntero del mouse fuera del botón, el borde del botón cambia a azul, luego a amarillo y luego a negro en 1,5 segundos.  
  
 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Especificación de cuándo aplicar un objeto VisualTransition  
 Un <xref:System.Windows.VisualTransition> se puede restringir para que solo se aplique a determinados Estados, o bien se puede aplicar cada vez que el control realiza la transición entre Estados. En el ejemplo <xref:System.Windows.VisualTransition> anterior, se aplica cuando el control pasa `MouseOver` del estado al `Normal` estado <xref:System.Windows.VisualTransition> ; en el ejemplo anterior, se aplica cuando el control entra en el `Pressed` estado. Restrinja el momento <xref:System.Windows.VisualTransition> en que se aplica mediante el establecimiento <xref:System.Windows.VisualTransition.From%2A> de las <xref:System.Windows.VisualTransition.To%2A> propiedades y. En la tabla siguiente se describen los niveles de restricción del más al menos restrictivo.  
  
|Tipo de restricción|Valor de Desde|Valor de Hasta|  
|-------------------------|-------------------|-----------------|  
|Desde un estado especificado hasta otro estado especificado|El nombre de un<xref:System.Windows.VisualState>|El nombre de un<xref:System.Windows.VisualState>|  
|Desde cualquier estado hasta un estado especificado|Sin establecer|El nombre de un<xref:System.Windows.VisualState>|  
|Desde un estado especificado hasta cualquier estado|El nombre de un<xref:System.Windows.VisualState>|Sin establecer|  
|Desde cualquier estado hasta cualquier otro estado|Sin establecer|Sin establecer|  
  
 Puede tener varios <xref:System.Windows.VisualTransition> objetos en un <xref:System.Windows.VisualStateGroup> que hagan referencia al mismo estado, pero se usarán en el orden en que se especifica la tabla anterior. En el ejemplo siguiente, hay dos <xref:System.Windows.VisualTransition> objetos. Cuando el control realiza la transición del `Pressed` estado `MouseOver` al estado, se usa <xref:System.Windows.VisualTransition> <xref:System.Windows.VisualTransition.To%2A> el que tiene <xref:System.Windows.VisualTransition.From%2A> ambos conjuntos. Cuando el control realiza la transición de un estado que no es `Pressed` al estado `MouseOver`, se usa el otro estado.  
  
 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualStateGroup> Tiene una <xref:System.Windows.VisualTransition> <xref:System.Windows.VisualState> propiedadque<xref:System.Windows.VisualStateGroup>contiene los objetos que se aplican a los objetos de. <xref:System.Windows.VisualStateGroup.Transitions%2A> Como autor, puede incluir los <xref:System.Windows.VisualTransition> que desee. <xref:System.Windows.Controls.ControlTemplate> Sin embargo, si <xref:System.Windows.VisualTransition.To%2A> las <xref:System.Windows.VisualTransition.From%2A> propiedades y se establecen en nombres de estado <xref:System.Windows.VisualStateGroup>que <xref:System.Windows.VisualTransition> no están en, se omite.  
  
 En el ejemplo siguiente se <xref:System.Windows.VisualStateGroup> muestra el para. `CommonStates` En el ejemplo se <xref:System.Windows.VisualTransition> define un para cada una de las transiciones siguientes del botón.  
  
- Al estado `Pressed`.  
  
- Al estado `MouseOver`.  
  
- Desde el estado `Pressed` hasta el estado `MouseOver`.  
  
- Desde el estado `MouseOver` hasta el estado `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalización de otros controles mediante la comprensión del contrato de control  
 Un control que utiliza <xref:System.Windows.Controls.ControlTemplate> para especificar su estructura visual ( <xref:System.Windows.FrameworkElement> mediante objetos) y el comportamiento <xref:System.Windows.VisualState> visual (mediante objetos) utiliza el modelo de control de elementos. Muchos de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 emplean este modelo. Los elementos que debe <xref:System.Windows.Controls.ControlTemplate> conocer un autor se comunican a través del contrato de control. Una vez que comprende las partes de un contrato de control, puede personalizar la apariencia de cualquier control que utilice el modelo de control de elementos.  
  
 Un contrato de control tiene tres elementos:  
  
- Los elementos visuales que usa la lógica del control.  
  
- Los estados del control y el grupo al que pertenece cada estado.  
  
- Las propiedades públicas que afectan visualmente al control.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementos visuales del contrato de control  
 A veces, la lógica de un control interactúa <xref:System.Windows.FrameworkElement> con un que está <xref:System.Windows.Controls.ControlTemplate>en. Por ejemplo, el control podría controlar un evento de uno de sus elementos. Cuando un control espera encontrar un determinado <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>en, debe <xref:System.Windows.Controls.ControlTemplate> transmitir esa información al autor. El control utiliza <xref:System.Windows.TemplatePartAttribute> para transmitir el tipo de elemento que se espera y el nombre del elemento. No tiene <xref:System.Windows.FrameworkElement> elementos en su contrato de control, pero otros <xref:System.Windows.Controls.ComboBox>controles, como, sí. <xref:System.Windows.Controls.Button>  
  
 En el ejemplo siguiente se <xref:System.Windows.TemplatePartAttribute> muestran los objetos que se especifican en la <xref:System.Windows.Controls.ComboBox> clase. La lógica de <xref:System.Windows.Controls.ComboBox> espera encontrar un <xref:System.Windows.Controls.TextBox> denominado `PART_EditableTextBox` y un <xref:System.Windows.Controls.Primitives.Popup> denominado `PART_Popup` en <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.ControlTemplate> una clase <xref:System.Windows.Controls.ComboBox> simplificada para que incluye los elementos especificados <xref:System.Windows.TemplatePartAttribute> por los objetos <xref:System.Windows.Controls.ComboBox> de la clase.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Estados del contrato de control  
 Los estados de un control también forman parte del contrato de control. En el ejemplo de creación <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Controls.Button> para un se muestra cómo especificar la apariencia <xref:System.Windows.Controls.Button> de un dependiendo de sus Estados. Se crea un <xref:System.Windows.VisualState> para cada estado especificado y se colocan todos los <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> <xref:System.Windows.VisualState> objetos <xref:System.Windows.VisualStateGroup>que comparten un en, tal y como se describe en [cambiar la apariencia de un control en función de su estado](#changing_the_appearance_of_a_control_depending_on_its_state) anteriormente en este tema. Los controles de terceros deben especificar los Estados <xref:System.Windows.TemplateVisualStateAttribute>mediante, que permite que las herramientas del diseñador, como Expression Blend, expongan los Estados del control para crear plantillas de control.  
  
 Para encontrar el contrato de control de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Propiedades del contrato de control  
 Las propiedades públicas que afectan visualmente al control también se incluyen en el contrato de control. Puede establecer estas propiedades para cambiar la apariencia del control sin crear un nuevo <xref:System.Windows.Controls.ControlTemplate>. También puede usar la extensión de marcado [TemplateBinding](../advanced/templatebinding-markup-extension.md) para enlazar propiedades de elementos que están en <xref:System.Windows.Controls.ControlTemplate> las propiedades públicas definidas por <xref:System.Windows.Controls.Button>.  
  
 En el ejemplo siguiente se muestra el contrato de control del botón.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Al crear un <xref:System.Windows.Controls.ControlTemplate>, a menudo es más fácil empezar con un existente <xref:System.Windows.Controls.ControlTemplate> y realizar cambios en él. Puede realizar una de las siguientes acciones para cambiar una existente <xref:System.Windows.Controls.ControlTemplate>:  
  
- Utilice un diseñador, como Expression Blend, que proporciona una interfaz gráfica de usuario para crear plantillas de control. Para más información, consulte [Aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
- Obtiene el valor <xref:System.Windows.Controls.ControlTemplate> predeterminado y lo edita. Para encontrar las plantillas de control predeterminadas que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252) (Temas de WPF predeterminados).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Ejemplo completo  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Button> la completa <xref:System.Windows.Controls.ControlTemplate> que se describe en este tema.  
  
 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](styling-and-templating.md)
