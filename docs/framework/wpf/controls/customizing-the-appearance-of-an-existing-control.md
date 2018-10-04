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
ms.openlocfilehash: 435789e0d1bc601a9eb51488254407fefd334e05
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778054"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Personalizar la apariencia de un control existente creando una clase ControlTemplate
<a name="introduction"></a> Un <xref:System.Windows.Controls.ControlTemplate> especifica la estructura visual y el comportamiento visual de un control. Puede personalizar la apariencia de un control proporcionando una nueva <xref:System.Windows.Controls.ControlTemplate>. Cuando creas un <xref:System.Windows.Controls.ControlTemplate>, reemplace la apariencia de un control existente sin cambiar su funcionalidad. Por ejemplo, puede que los botones de la aplicación redondos en lugar de la forma cuadrada predeterminada, pero el botón seguirá generando el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
 En este tema se explica las distintas partes de un <xref:System.Windows.Controls.ControlTemplate>, se muestra cómo crear una sencilla <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button>y se explica cómo entender el contrato de un control para que pueda personalizar su apariencia. Dado que se crea un <xref:System.Windows.Controls.ControlTemplate> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede cambiar el aspecto de un control sin escribir ningún código. También puede usar un diseñador, como Microsoft Expression Blend, para crear plantillas de control personalizado. En este tema se muestra ejemplos en los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que personalizar la apariencia de un <xref:System.Windows.Controls.Button> y muestra el ejemplo completo al final del tema. Para más información acerca del uso de Expression Blend, consulte [Aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Las siguientes ilustraciones muestran un <xref:System.Windows.Controls.Button> que usa el <xref:System.Windows.Controls.ControlTemplate> que se crea en este tema.  
  
 ![Botón con una plantilla de control personalizado. ](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Un botón que usa una plantilla de control personalizado.  
  
 ![Botón con un borde rojo. ](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Un botón que usa una plantilla de control personalizado y tiene el puntero del mouse sobre él.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que sabe cómo crear y usar controles y estilos, como se describe en [Controls](../../../../docs/framework/wpf/controls/index.md) (Controles). Los conceptos tratados en este tema se aplican a los elementos que heredan de la <xref:System.Windows.Controls.Control> (clase), excepto para el <xref:System.Windows.Controls.UserControl>. No se puede aplicar un <xref:System.Windows.Controls.ControlTemplate> a un <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Cuándo se debe crear un control ControlTemplate  
 Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, y <xref:System.Windows.Controls.Control.FontFamily%2A>, que puede establecer para especificar distintos aspectos de la apariencia del control, pero los cambios que puede hacer al establecer estas propiedades son limitados. Por ejemplo, puede establecer el <xref:System.Windows.Controls.Control.Foreground%2A> propiedad a azul y <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un <xref:System.Windows.Controls.CheckBox>.  
  
 Sin la capacidad para crear un nuevo <xref:System.Windows.Controls.ControlTemplate> para los controles, todos los controles de cada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en tendría el mismo aspecto general, lo que limitaría la capacidad de crear una aplicación con una apariencia personalizada. De forma predeterminada, cada <xref:System.Windows.Controls.CheckBox> tiene características similares. Por ejemplo, el contenido de la <xref:System.Windows.Controls.CheckBox> siempre está a la derecha del indicador de selección, y siempre se utiliza la marca de verificación para indicar que el <xref:System.Windows.Controls.CheckBox> está seleccionada.  
  
 Crear un <xref:System.Windows.Controls.ControlTemplate> cuando desee personalizar la apariencia del control más allá de hará lo hace la configuración de las demás propiedades en el control. En el ejemplo de la <xref:System.Windows.Controls.CheckBox>, suponga que desea que el contenido de la casilla de verificación por encima del indicador de selección y desea que una X para indicar que el <xref:System.Windows.Controls.CheckBox> está seleccionada. Especifique estos cambios en el <xref:System.Windows.Controls.ControlTemplate> de la <xref:System.Windows.Controls.CheckBox>.  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.CheckBox> que usa un valor predeterminado <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Casilla con la plantilla de control predeterminada. ](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Un control CheckBox que usa la plantilla de control predeterminada  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.CheckBox> que usa un <xref:System.Windows.Controls.ControlTemplate> para colocar el contenido de la <xref:System.Windows.Controls.CheckBox> anteriormente el indicador de selección y muestra una X cuando el <xref:System.Windows.Controls.CheckBox> está seleccionada.  
  
 ![Casilla con una plantilla de control personalizado. ](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Un control CheckBox que usa una plantilla de control personalizado  
  
 El <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.CheckBox> en este ejemplo es relativamente compleja, por lo que en este tema se usa un ejemplo más sencillo de creación de un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Cambio de la estructura visual de un control  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un control a menudo es una composición <xref:System.Windows.FrameworkElement> objetos. Cuando creas un <xref:System.Windows.Controls.ControlTemplate>, combina <xref:System.Windows.FrameworkElement> objetos que se va a crear un control único. Un <xref:System.Windows.Controls.ControlTemplate> debe tener una única <xref:System.Windows.FrameworkElement> como su elemento raíz. El elemento raíz normalmente contiene otros <xref:System.Windows.FrameworkElement> objetos. La combinación de objetos constituye la estructura visual del control.  
  
 En el ejemplo siguiente se crea un personalizado <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button>. El <xref:System.Windows.Controls.ControlTemplate> crea la estructura visual de la <xref:System.Windows.Controls.Button>. En este ejemplo no cambia la apariencia del botón al mover el puntero del mouse sobre él o hacer clic en él. El cambio de la apariencia del botón cuando se encuentra en un estado diferente se explica más adelante en este tema.  
  
 En este ejemplo, la estructura visual consta de las siguientes partes:  
  
-   Un <xref:System.Windows.Controls.Border> denominado `RootElement` que sirve como raíz de la plantilla <xref:System.Windows.FrameworkElement>.  
  
-   Un <xref:System.Windows.Controls.Grid> que es un elemento secundario de `RootElement`.  
  
-   Un <xref:System.Windows.Controls.ContentPresenter> que muestra el contenido del botón. El <xref:System.Windows.Controls.ContentPresenter> permite cualquier tipo de objeto que se mostrará.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Conservación de la funcionalidad de las propiedades de un control mediante TemplateBinding  
 Cuando se crea un nuevo <xref:System.Windows.Controls.ControlTemplate>, todavía puede usar las propiedades públicas para cambiar la apariencia del control. El [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensión de marcado enlaza una propiedad de un elemento que se encuentra en la <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública que está definida por el control. Cuando se usa [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), se habilitan propiedades en el control que actúan como parámetros de la plantilla. Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 En el ejemplo siguiente se repite la parte del ejemplo anterior que usa el [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensión de marcado para enlazar propiedades de elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate> a las propiedades públicas definidas por el botón.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 En este ejemplo, el <xref:System.Windows.Controls.Grid> tiene su <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> plantilla de la propiedad enlazada a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Porque <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> está enlazado a plantilla, puede crear varios botones que usan los mismos <xref:System.Windows.Controls.ControlTemplate> y establezca el <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> en valores distintos en cada botón. Si <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> plantilla no se enlazó a una propiedad de un elemento en el <xref:System.Windows.Controls.ControlTemplate>, estableciendo el <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> de un botón no tendría ningún impacto en la apariencia del botón.  
  
 Tenga en cuenta que los nombres de las dos propiedades no tienen que ser idénticos. En el ejemplo anterior, el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> propiedad de la <xref:System.Windows.Controls.Button> plantilla depende de la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> propiedad de la <xref:System.Windows.Controls.ContentPresenter>. Esto permite que el contenido del botón se sitúe horizontalmente. <xref:System.Windows.Controls.ContentPresenter> no tiene una propiedad denominada `HorizontalContentAlignment`, pero <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> pueden estar limitados por <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Cuando la plantilla enlaza una propiedad, asegúrese de que las propiedades de origen y de destino sean del mismo tipo.  
  
 La <xref:System.Windows.Controls.Control> clase define varias propiedades que deben usarse para tener un efecto en el control cuando se configuran mediante la plantilla de control. El modo <xref:System.Windows.Controls.ControlTemplate> usa la propiedad depende de la propiedad. El <xref:System.Windows.Controls.ControlTemplate> debe usar la propiedad en una de las maneras siguientes:  
  
-   Un elemento en el <xref:System.Windows.Controls.ControlTemplate> plantilla se enlaza a la propiedad.  
  
-   Un elemento en el <xref:System.Windows.Controls.ControlTemplate> hereda la propiedad de un elemento primario <xref:System.Windows.FrameworkElement>.  
  
 En la tabla siguiente se enumera las propiedades visuales heredadas por un control desde el <xref:System.Windows.Controls.Control> clase. También se indica si la plantilla de control predeterminado de un control usa el valor de propiedad heredado o si debe estar enlazado a plantilla.  
  
|Property|Método de uso|  
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
  
 La tabla enumeran las propiedades visuales heredadas de la <xref:System.Windows.Controls.Control> clase. Además de las propiedades enumeradas en la tabla, un control puede heredar también las <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, y <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> las propiedades del elemento de marco de trabajo primario.  
  
 Además, si la <xref:System.Windows.Controls.ContentPresenter> está en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Controls.ContentControl>, el <xref:System.Windows.Controls.ContentPresenter> se enlazará automáticamente a la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A> propiedades. Del mismo modo, un <xref:System.Windows.Controls.ItemsPresenter> que se encuentra en la <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Controls.ItemsControl> se enlazará automáticamente a la <xref:System.Windows.Controls.ItemsControl.Items%2A> y <xref:System.Windows.Controls.ItemsPresenter> propiedades.  
  
 El ejemplo siguiente crea dos botones que usan el <xref:System.Windows.Controls.ControlTemplate> definido en el ejemplo anterior. El ejemplo se establece la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, y <xref:System.Windows.Controls.Control.FontSize%2A> las propiedades de cada botón. Establecer el <xref:System.Windows.Controls.Control.Background%2A> propiedad tiene un efecto porque está enlazada a plantilla en el <xref:System.Windows.Controls.ControlTemplate>. Aunque el <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontSize%2A> propiedades no están enlazado a plantilla, establecerlas tiene un efecto porque sus valores son heredados.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 El ejemplo anterior genera un resultado similar a la siguiente ilustración.  
  
 ![Dos botones, uno azul y otro púrpura. ](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
Dos botones con diferentes colores de fondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Cambio de la apariencia de un control según su estado  
 La diferencia entre un botón con su apariencia predeterminada y el botón del ejemplo anterior es que el botón predeterminado cambia sutilmente cuando se encuentra en estados diferentes. Por ejemplo, la apariencia del botón predeterminado cambia cuando se presiona el botón o cuando se sitúa el puntero del mouse sobre él. Aunque el <xref:System.Windows.Controls.ControlTemplate> no cambia la funcionalidad de un control, cambia el comportamiento visual del control. Un comportamiento visual describe la apariencia del control cuando se encuentra en un estado determinado. Para comprender la diferencia entre la funcionalidad y el comportamiento visual de un control, considere el ejemplo del botón. La funcionalidad del botón consiste en generar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos cuando se hace clic en, pero el comportamiento visual del botón es cambiar su apariencia cuando está señalado o presiona.  
  
 Usa <xref:System.Windows.VisualState> objetos para especificar la apariencia de un control cuando se encuentra en un estado determinado. Un <xref:System.Windows.VisualState> contiene un <xref:System.Windows.Media.Animation.Storyboard> que cambia la apariencia de los elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate>. No tiene que escribir ningún código para que esto suceda, porque la lógica del control cambia de estado mediante el <xref:System.Windows.VisualStateManager>. Cuando el control entra en el estado especificado por el <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> propiedad, el <xref:System.Windows.Media.Animation.Storyboard> comienza. Cuando el control sale del estado, el <xref:System.Windows.Media.Animation.Storyboard> se detiene.  
  
 El ejemplo siguiente se muestra el <xref:System.Windows.VisualState> que cambia la apariencia de un <xref:System.Windows.Controls.Button> cuando el puntero del mouse está encima de él. El <xref:System.Windows.Media.Animation.Storyboard> cambia el color del borde del botón cambiando el color de la `BorderBrush`. Si hace referencia a la <xref:System.Windows.Controls.ControlTemplate> ejemplo al principio de este tema, recordará que `BorderBrush` es el nombre de la <xref:System.Windows.Media.SolidColorBrush> que se asigna a la <xref:System.Windows.Controls.Border.Background%2A> de la <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 El control es responsable de definir los estados como parte de su contrato de control, que se describe de manera detallada en [Personalización de otros controles mediante la comprensión del contrato de control](#customizing_other_controls_by_understanding_the_control_contract) más adelante en este tema. En la tabla siguiente se muestra los Estados que se especifican para el <xref:System.Windows.Controls.Button>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Presionado|CommonStates|El control está presionado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
  
 El <xref:System.Windows.Controls.Button> define dos grupos de estados: el `CommonStates` grupo contiene el `Normal`, `MouseOver`, `Pressed`, y `Disabled` Estados. El grupo `FocusStates` contiene los estados `Focused` y `Unfocused`. Los estados en el mismo grupo de estado son mutuamente excluyentes. El control siempre está exactamente en un estado por grupo. Por ejemplo, un <xref:System.Windows.Controls.Button> puede tener el foco cuando el puntero del mouse no está sobre él, por lo tanto un <xref:System.Windows.Controls.Button> en el `Focused` estado puede estar en el `MouseOver`, `Pressed`, o `Normal` estado.  
  
 Agregar <xref:System.Windows.VisualState> objetos <xref:System.Windows.VisualStateGroup> objetos. Agregar <xref:System.Windows.VisualStateGroup> objetos a la <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta. En el ejemplo siguiente se define la <xref:System.Windows.VisualState> de objetos para el `Normal`, `MouseOver`, y `Pressed` Estados, que están en el `CommonStates` grupo. El <xref:System.Windows.VisualState.Name%2A> de cada <xref:System.Windows.VisualState> coincide con el nombre de la tabla anterior. El estado `Disabled` y los estados del grupo `FocusStates` se omiten para abreviar el ejemplo, pero se incluyen en el ejemplo completo al final de este tema.  
  
> [!NOTE]
>  Asegúrese de establecer el <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta en la raíz <xref:System.Windows.FrameworkElement> de la <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 El ejemplo anterior genera un resultado similar a las siguientes ilustraciones.  
  
 ![Botón con una plantilla de control personalizado. ](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Un botón que usa una plantilla de control personalizado en el estado normal  
  
 ![Botón con un borde rojo. ](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Un botón que usa una plantilla de control personalizado en el estado de pasar el mouse  
  
 ![El borde es transparente en un botón presionado. ](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Un botón que usa una plantilla de control personalizado en el estado presionado  
  
 Para encontrar los estados visuales de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Especificación del comportamiento de un control cuando realiza la transición entre estados  
 En el ejemplo anterior, la apariencia del botón también cambia cuando el usuario hace clic en él, pero a menos que se presione el botón durante un segundo completo, el usuario no verá el efecto. De forma predeterminada, la animación tarda un segundo en producirse. Dado que es probable que los usuarios hacer clic y suelte un botón en mucho menos tiempo, los comentarios visuales no será efectivo si deja el <xref:System.Windows.Controls.ControlTemplate> en su estado predeterminado.  
  
 Puede especificar la cantidad de tiempo que tarda en producirse para una transición suave de un control de un estado a otro mediante la adición de una animación <xref:System.Windows.VisualTransition> objetos a la <xref:System.Windows.Controls.ControlTemplate>. Cuando creas un <xref:System.Windows.VisualTransition>, especifique uno o varios de los siguientes:  
  
-   El tiempo que tarda en producirse una transición entre estados.  
  
-   Los cambios adicionales en la apariencia del control que se producen en el momento de la transición.  
  
-   Qué estados el <xref:System.Windows.VisualTransition> se aplica a.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Especificación de la duración de una transición  
 Puede especificar cuánto tiempo tarda una transición estableciendo el <xref:System.Windows.VisualTransition.GeneratedDuration%2A> propiedad. El ejemplo anterior tiene un <xref:System.Windows.VisualState> que especifica que el borde del botón se vuelve transparente cuando se presiona el botón, pero la animación tarda demasiado tiempo en advertirse si el botón está presionado y soltado de rápidamente. Puede usar un <xref:System.Windows.VisualTransition> para especificar la cantidad de tiempo que tarda el control para realizar la transición al estado presionado. En el ejemplo siguiente se especifica que el control tarda una centésima de segundo en pasar al estado presionado.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Especificación de cambios en la apariencia del control durante una transición  
 El <xref:System.Windows.VisualTransition> contiene un <xref:System.Windows.Media.Animation.Storyboard> que comienza cuando el control realiza la transición entre Estados. Por ejemplo, puede especificar que se produzca una determinada animación cuando el control pase del estado `MouseOver` al estado `Normal`. En el ejemplo siguiente se crea un <xref:System.Windows.VisualTransition> que especifica que, cuando el usuario mueve el puntero del mouse fuera del botón, el borde del botón cambia a azul, y, luego a amarillo, negro en 1,5 segundos.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Especificación de cuándo aplicar un objeto VisualTransition  
 Un <xref:System.Windows.VisualTransition> puede restringirse para aplicar solo a determinados Estados, o se puede aplicar cada vez que el control realiza la transición entre Estados. En el ejemplo anterior, el <xref:System.Windows.VisualTransition> se aplica cuando el control pasa de la `MouseOver` estado el `Normal` estado; en el ejemplo anterior, el <xref:System.Windows.VisualTransition> se aplica cuando el control entra en el `Pressed` estado. Restringir cuándo un <xref:System.Windows.VisualTransition> se aplica estableciendo el <xref:System.Windows.VisualTransition.To%2A> y <xref:System.Windows.VisualTransition.From%2A> propiedades. En la tabla siguiente se describen los niveles de restricción del más al menos restrictivo.  
  
|Tipo de restricción|Valor de Desde|Valor de Hasta|  
|-------------------------|-------------------|-----------------|  
|Desde un estado especificado hasta otro estado especificado|El nombre de un <xref:System.Windows.VisualState>|El nombre de un <xref:System.Windows.VisualState>|  
|Desde cualquier estado hasta un estado especificado|Sin establecer|El nombre de un <xref:System.Windows.VisualState>|  
|Desde un estado especificado hasta cualquier estado|El nombre de un <xref:System.Windows.VisualState>|Sin establecer|  
|Desde cualquier estado hasta cualquier otro estado|Sin establecer|Sin establecer|  
  
 Puede tener varios <xref:System.Windows.VisualTransition> objetos en un <xref:System.Windows.VisualStateGroup> que hacen referencia al mismo estado, pero que se usarán en el orden que especifica la tabla anterior. En el ejemplo siguiente, hay dos <xref:System.Windows.VisualTransition> objetos. Cuando el control realiza la transición desde el `Pressed` estado el `MouseOver` estado, el <xref:System.Windows.VisualTransition> que tiene ambos <xref:System.Windows.VisualTransition.From%2A> y <xref:System.Windows.VisualTransition.To%2A> se usa el conjunto. Cuando el control realiza la transición de un estado que no es `Pressed` al estado `MouseOver`, se usa el otro estado.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 El <xref:System.Windows.VisualStateGroup> tiene un <xref:System.Windows.VisualStateGroup.Transitions%2A> propiedad que contiene el <xref:System.Windows.VisualTransition> objetos que se aplican a la <xref:System.Windows.VisualState> objetos en el <xref:System.Windows.VisualStateGroup>. Como el <xref:System.Windows.Controls.ControlTemplate> autor, es gratuitas incluirlos <xref:System.Windows.VisualTransition> que desee. Sin embargo, si la <xref:System.Windows.VisualTransition.To%2A> y <xref:System.Windows.VisualTransition.From%2A> propiedades se establecen en los nombres de estado que no están en el <xref:System.Windows.VisualStateGroup>, el <xref:System.Windows.VisualTransition> se omite.  
  
 El ejemplo siguiente se muestra el <xref:System.Windows.VisualStateGroup> para el `CommonStates`. El ejemplo define un <xref:System.Windows.VisualTransition> para cada uno de los siguientes del botón realiza la transición.  
  
-   Al estado `Pressed`.  
  
-   Al estado `MouseOver`.  
  
-   Desde el estado `Pressed` hasta el estado `MouseOver`.  
  
-   Desde el estado `MouseOver` hasta el estado `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Personalización de otros controles mediante la comprensión del contrato de control  
 Un control que utiliza un <xref:System.Windows.Controls.ControlTemplate> para especificar su estructura visual (mediante el uso de <xref:System.Windows.FrameworkElement> objetos) y el comportamiento visual (mediante el uso de <xref:System.Windows.VisualState> objetos) usa el modelo de control de elementos. Muchos de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 emplean este modelo. Las partes que un <xref:System.Windows.Controls.ControlTemplate> autor debe ser consciente de que se comunica a través del contrato de control. Una vez que comprende las partes de un contrato de control, puede personalizar la apariencia de cualquier control que utilice el modelo de control de elementos.  
  
 Un contrato de control tiene tres elementos:  
  
-   Los elementos visuales que usa la lógica del control.  
  
-   Los estados del control y el grupo al que pertenece cada estado.  
  
-   Las propiedades públicas que afectan visualmente al control.  
  
### <a name="visual-elements-in-the-control-contract"></a>Elementos visuales del contrato de control  
 A veces, la lógica de un control interactúa con un <xref:System.Windows.FrameworkElement> que se encuentra en la <xref:System.Windows.Controls.ControlTemplate>. Por ejemplo, el control podría controlar un evento de uno de sus elementos. Cuando un control espera encontrar un determinado <xref:System.Windows.FrameworkElement> en el <xref:System.Windows.Controls.ControlTemplate>, debe transmitir esa información a la <xref:System.Windows.Controls.ControlTemplate> autor. El control utiliza el <xref:System.Windows.TemplatePartAttribute> para transmitir el tipo de elemento que se espera y cuál debe ser el nombre del elemento. El <xref:System.Windows.Controls.Button> no tiene <xref:System.Windows.FrameworkElement> piezas en su contrato de control, pero otros controles, como el <xref:System.Windows.Controls.ComboBox>, hacer.  
  
 El ejemplo siguiente se muestra el <xref:System.Windows.TemplatePartAttribute> objetos que se especifican en el <xref:System.Windows.Controls.ComboBox> clase. La lógica de <xref:System.Windows.Controls.ComboBox> espera encontrar una <xref:System.Windows.Controls.TextBox> denominado `PART_EditableTextBox` y un <xref:System.Windows.Controls.Primitives.Popup> denominado `PART_Popup` en su <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 El ejemplo siguiente muestra una página simplificada <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ComboBox> que incluye los elementos especificados por el <xref:System.Windows.TemplatePartAttribute> objetos en el <xref:System.Windows.Controls.ComboBox> clase.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Estados del contrato de control  
 Los estados de un control también forman parte del contrato de control. El ejemplo de cómo crear un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button> se muestra cómo especificar la apariencia de un <xref:System.Windows.Controls.Button> según sus Estados. Crear un <xref:System.Windows.VisualState> para cada estado especificado y todos los <xref:System.Windows.VisualState> objetos que comparten un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> en un <xref:System.Windows.VisualStateGroup>, tal y como se describe en [cambiar la apariencia de un Control según su estado](#changing_the_appearance_of_a_control_depending_on_its_state) anteriormente en este tema. Controles de terceros deben especificar estados mediante la <xref:System.Windows.TemplateVisualStateAttribute>, lo que permite que herramientas de diseñador, como Expression Blend, para exponer los Estados del control para la creación de plantillas de control.  
  
 Para encontrar el contrato de control de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Propiedades del contrato de control  
 Las propiedades públicas que afectan visualmente al control también se incluyen en el contrato de control. Puede establecer estas propiedades para cambiar la apariencia del control sin crear un nuevo <xref:System.Windows.Controls.ControlTemplate>. También puede usar el [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) extensión de marcado para enlazar propiedades de elementos que se encuentran en el <xref:System.Windows.Controls.ControlTemplate> a las propiedades públicas definidas por el <xref:System.Windows.Controls.Button>.  
  
 En el ejemplo siguiente se muestra el contrato de control del botón.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Al crear un <xref:System.Windows.Controls.ControlTemplate>, a menudo resulta más fácil empezar con una existente <xref:System.Windows.Controls.ControlTemplate> y realizar cambios en ella. Puede realizar una de las siguientes opciones para cambiar una existente <xref:System.Windows.Controls.ControlTemplate>:  
  
-   Utilice un diseñador, como Expression Blend, que proporciona una interfaz gráfica de usuario para crear plantillas de control. Para más información, consulte [Aplicar estilos a un control que admite plantillas](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Obtener el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> y editarlo. Para encontrar las plantillas de control predeterminadas que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252) (Temas de WPF predeterminados).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Ejemplo completo  
 El ejemplo siguiente muestra toda <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> que se describe en este tema.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
