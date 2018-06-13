---
title: Crear un control que tiene una apariencia personalizable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: 9f539e7dbb105591375857122d738fddd87f6776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558283"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Crear un control que tiene una apariencia personalizable
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece la capacidad para crear un control cuya apariencia puede personalizarse. Por ejemplo, puede cambiar la apariencia de un <xref:System.Windows.Controls.CheckBox> más allá de la configuración de propiedades hará al crear un nuevo <xref:System.Windows.Controls.ControlTemplate>. La siguiente ilustración muestra un <xref:System.Windows.Controls.CheckBox> que utiliza el valor predeterminado es <xref:System.Windows.Controls.ControlTemplate> y un <xref:System.Windows.Controls.CheckBox> que usa un personalizado <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Casilla con la plantilla de control predeterminada. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Un control CheckBox que usa la plantilla de control predeterminada  
  
 ![Casilla con una plantilla de control personalizada. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Un control CheckBox que usa una plantilla de control personalizado  
  
 Si sigue el modelo de Estados y elementos al crear un control, la apariencia del control será personalizable. Herramientas del diseñador, como Microsoft Expression Blend admiten el modelo de Estados y elementos, por lo que si sigue este modelo el control podrá personalizar en esos tipos de aplicaciones.  Este tema describe el modelo de Estados y elementos y cómo seguirlo al crear su propio control. Este tema utiliza un ejemplo de un control personalizado, `NumericUpDown`, para ilustrar la filosofía de este modelo.  El `NumericUpDown` control muestra un valor numérico, que un usuario puede aumentar o disminuir haciendo clic en los botones del control.  La siguiente ilustración muestra el `NumericUpDown` control que se describe en este tema.  
  
 ![Control personalizado NumericUpDown. ] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
Un control NumericUpDown personalizado  
  
 Este tema contiene las siguientes secciones:  
  
-   [Requisitos previos](#prerequisites)  
  
-   [Modelo de Estados y elementos](#parts_and_states_model)  
  
-   [Definir la estructura y el comportamiento Visual de un Control en ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Uso de elementos de ControlTemplate en el código](#using_parts_of_the_controltemplate_in_code)  
  
-   [Proporcionar el contrato de Control](#providing_the_control_contract)  
  
-   [Ejemplo completo](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Este tema se supone que sabe cómo crear un nuevo <xref:System.Windows.Controls.ControlTemplate> para un control existente, está familiarizado con cuáles son los elementos en un contrato de control y comprender los conceptos tratados en [personalizar la apariencia de un Control existente por Crear un elemento ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Para crear un control que puede tener su apariencia personalizada, debe crear un control que hereda de la <xref:System.Windows.Controls.Control> clase o una de sus subclases distinto de <xref:System.Windows.Controls.UserControl>.  Un control que hereda de <xref:System.Windows.Controls.UserControl> es un control que se puede crear rápidamente, pero no usa un <xref:System.Windows.Controls.ControlTemplate> y no se puede personalizar su apariencia.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Modelo de Estados y elementos  
 El modelo de Estados y elementos especifica cómo definir la estructura y el comportamiento visual de un control. Para seguir el modelo de Estados y elementos, debe hacer lo siguiente:  
  
-   Definir la estructura visual y el comportamiento visual en el <xref:System.Windows.Controls.ControlTemplate> de un control.  
  
-   Siga algunos procedimientos recomendados cuando la lógica del control interactúa con partes de la plantilla de control.  
  
-   Proporcione un contrato del control para especificar lo que deben incluirse en la <xref:System.Windows.Controls.ControlTemplate>.  
  
 Cuando se definen la estructura visual y el comportamiento visual en el <xref:System.Windows.Controls.ControlTemplate> de un control, los autores de aplicaciones pueden cambiar la estructura visual y el comportamiento visual del control creando un nuevo <xref:System.Windows.Controls.ControlTemplate> en lugar de escribir código.   Debe proporcionar un contrato del control que le indica a aplicación autores que <xref:System.Windows.FrameworkElement> objetos y Estados deben definirse en el <xref:System.Windows.Controls.ControlTemplate>. Debe seguir algunos procedimientos recomendados al interactuar con los elementos en el <xref:System.Windows.Controls.ControlTemplate> para que el control administre correctamente un incompleta <xref:System.Windows.Controls.ControlTemplate>.  Si sigue estos tres principios, los autores de la aplicación podrá crear un <xref:System.Windows.Controls.ControlTemplate> para el control solo tan fácilmente como puede para los controles que se incluyen en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En la siguiente sección se explica cada una de estas recomendaciones en detalle.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definir la estructura y el comportamiento Visual de un Control en ControlTemplate  
 Al crear el control personalizado mediante el modelo de Estados y elementos, definir la estructura y el comportamiento visual en el control su <xref:System.Windows.Controls.ControlTemplate> en lugar de en su lógica.  La estructura visual de un control es la composición <xref:System.Windows.FrameworkElement> objetos que componen el control.  El comportamiento visual es el modo en que el control aparece cuando se encuentra en un estado determinado.   Para obtener más información acerca de cómo crear un <xref:System.Windows.Controls.ControlTemplate> que especifica la estructura visual y el comportamiento visual de un control, vea [personalizar la apariencia de un Control existente mediante la creación de un elemento ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 En el ejemplo de la `NumericUpDown` (control), la estructura visual incluye dos <xref:System.Windows.Controls.Primitives.RepeatButton> controles y <xref:System.Windows.Controls.TextBlock>.  Si agrega estos controles en el código de la `NumericUpDown` control--en su constructor, por ejemplo, las posiciones de esos controles serían inalterables.  En lugar de definir la estructura visual y el comportamiento visual del control en el código, debe definir en el <xref:System.Windows.Controls.ControlTemplate>.  A continuación, un desarrollador de aplicaciones para personalizar la posición de los botones y <xref:System.Windows.Controls.TextBlock> y especificar qué ocurre cuando `Value` es negativo porque el <xref:System.Windows.Controls.ControlTemplate> puede reemplazarse.  
  
 En el ejemplo siguiente se muestra la estructura visual de la `NumericUpDown` control, que incluye un <xref:System.Windows.Controls.Primitives.RepeatButton> para aumentar `Value`, un <xref:System.Windows.Controls.Primitives.RepeatButton> reducir `Value`y un <xref:System.Windows.Controls.TextBlock> para mostrar `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Un comportamiento visual de la `NumericUpDown` control es que el valor es una fuente de color rojo si es negativo.  Si cambia la <xref:System.Windows.Controls.TextBlock.Foreground%2A> de la <xref:System.Windows.Controls.TextBlock> en el código cuando la `Value` es negativo, el `NumericUpDown` siempre mostrará un valor negativo en rojo. Especificar el comportamiento visual del control en el <xref:System.Windows.Controls.ControlTemplate> agregando <xref:System.Windows.VisualState> objetos a la <xref:System.Windows.Controls.ControlTemplate>.  El siguiente ejemplo se muestra la <xref:System.Windows.VisualState> de objetos para el `Positive` y `Negative` Estados.  `Positive` y `Negative` son mutuamente excluyente (el control siempre está en uno de los dos), por lo que en el ejemplo se coloca el <xref:System.Windows.VisualState> objetos en una sola <xref:System.Windows.VisualStateGroup>.  Cuando el control entra en el `Negative` estado, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de la <xref:System.Windows.Controls.TextBlock> cambia a rojo.  Cuando el control está en el `Positive` estado, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> devuelve el valor original.  Definir <xref:System.Windows.VisualState> objetos en un <xref:System.Windows.Controls.ControlTemplate> más se explica en [personalizar la apariencia de un Control existente mediante la creación de un elemento ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Asegúrese de establecer el <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> la raíz de la propiedad adjunta <xref:System.Windows.FrameworkElement> de la <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>Uso de elementos de ControlTemplate en el código  
 A <xref:System.Windows.Controls.ControlTemplate> autor podría omitir <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> objetos, ya sea intencionadamente o por error, pero la lógica del control podría necesitar esos elementos para funcionar correctamente. El modelo de Estados y elementos especifica que el control debe ser resistente a un <xref:System.Windows.Controls.ControlTemplate> falta <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> objetos.  El control no debería iniciar una excepción ni notificar un error si una <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, o <xref:System.Windows.VisualStateGroup> no está presente en el <xref:System.Windows.Controls.ControlTemplate>. Esta sección describen las prácticas recomendadas para interactuar con <xref:System.Windows.FrameworkElement> objetos y administración de Estados.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Prever FrameworkElement objetos ausentes  
 Cuando se define <xref:System.Windows.FrameworkElement> objetos en el <xref:System.Windows.Controls.ControlTemplate>, la lógica del control podría necesitar interactuar con algunos de ellos.  Por ejemplo, el `NumericUpDown` control se suscribe a los botones <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para aumentar o disminuir `Value` y establece la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> a `Value`. Si un personalizado <xref:System.Windows.Controls.ControlTemplate> omite el <xref:System.Windows.Controls.TextBlock> o botones, es aceptable que el control pierde parte de su funcionalidad, pero debe asegurarse de que el control no producirá un error. Por ejemplo, si un <xref:System.Windows.Controls.ControlTemplate> no contiene los botones para cambiar `Value`, `NumericUpDown` pierde esa funcionalidad, pero una aplicación que utiliza el <xref:System.Windows.Controls.ControlTemplate> seguirá ejecutándose.  
  
 Las siguientes prácticas se asegurará de que el control responda correctamente a los que falten <xref:System.Windows.FrameworkElement> objetos:  
  
1.  Establecer el `x:Name` atributo para cada <xref:System.Windows.FrameworkElement> que debe hacer referencia en código.  
  
2.  Defina las propiedades privadas para cada <xref:System.Windows.FrameworkElement> que necesita para interactuar con.  
  
3.  Suscribir y cancelar la suscripción a los eventos que controla el control de la <xref:System.Windows.FrameworkElement> descriptor de acceso set de la propiedad.  
  
4.  Establecer el <xref:System.Windows.FrameworkElement> propiedades que usted definió en el paso 2 el <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> método. Se trata de la más antigua que la <xref:System.Windows.FrameworkElement> en la <xref:System.Windows.Controls.ControlTemplate> está disponible para el control. Use la `x:Name` de la <xref:System.Windows.FrameworkElement> para obtenerlo desde el <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Compruebe que la <xref:System.Windows.FrameworkElement> no es `null` antes de acceder a sus miembros.  Si es `null`, no informan de un error.  
  
 Los ejemplos siguientes muestran cómo el `NumericUpDown` control interactúa con <xref:System.Windows.FrameworkElement> objetos de acuerdo con las recomendaciones de la lista anterior.  
  
 En el ejemplo que define la estructura visual de la `NumericUpDown` controlar en el <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton> que aumenta `Value` tiene su `x:Name` atributo establecido en `UpButton`.  En el ejemplo siguiente se declara una propiedad denominada `UpButtonElement` que representa el <xref:System.Windows.Controls.Primitives.RepeatButton> que se declara en el <xref:System.Windows.Controls.ControlTemplate>. El `set` descriptor de acceso primero elimina la suscripción para el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos si `UpDownElement` no `null`, a continuación, Establece la propiedad y, a continuación, se suscribe a la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos. También hay una propiedad definida, pero no se muestra aquí, para los demás <xref:System.Windows.Controls.Primitives.RepeatButton>, llamado `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 El siguiente ejemplo se muestra la <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para el `NumericUpDown` control.  El ejemplo se utiliza la <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> método para obtener el <xref:System.Windows.FrameworkElement> objetos desde el <xref:System.Windows.Controls.ControlTemplate>.  Tenga en cuenta que el ejemplo se evita los casos donde <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> busca un <xref:System.Windows.FrameworkElement> con el nombre especificado que no es del tipo esperado. También es una práctica recomendada para omitir los elementos que tienen especificado `x:Name` pero son del tipo incorrecto.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Al seguir las prácticas que se muestran en los ejemplos anteriores, se asegura de que el control continuará ejecutándose cuando la <xref:System.Windows.Controls.ControlTemplate> falta un <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Usar VisualStateManager para administrar estados  
 El <xref:System.Windows.VisualStateManager> realiza un seguimiento de los Estados de un control y ejecuta la lógica necesaria para realizar la transición entre Estados. Cuando se agrega <xref:System.Windows.VisualState> objetos a la <xref:System.Windows.Controls.ControlTemplate>, agregarlos a un <xref:System.Windows.VisualStateGroup> y agregue el <xref:System.Windows.VisualStateGroup> para el <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta para que el <xref:System.Windows.VisualStateManager> tiene acceso a ellos.  
  
 En el ejemplo siguiente se repite el ejemplo anterior que muestra la <xref:System.Windows.VisualState> objetos que se corresponde con el `Positive` y `Negative` Estados del control. El <xref:System.Windows.Media.Animation.Storyboard> en el `Negative` <xref:System.Windows.VisualState> activa el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de la <xref:System.Windows.Controls.TextBlock> rojo.   Cuando el `NumericUpDown` control se encuentra en la `Negative` estado, el guión gráfico en el `Negative` estado comienza.  La <xref:System.Windows.Media.Animation.Storyboard> en el `Negative` estado se detiene cuando el control vuelve a la `Positive` estado.  El `Positive` <xref:System.Windows.VisualState> no deben contener una <xref:System.Windows.Media.Animation.Storyboard> porque cuando el <xref:System.Windows.Media.Animation.Storyboard> para el `Negative` se detiene, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> vuelve a su color original.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Tenga en cuenta que la <xref:System.Windows.Controls.TextBlock> recibe un nombre, pero la <xref:System.Windows.Controls.TextBlock> no está en el contrato de control para `NumericUpDown` porque la lógica del control nunca hace referencia el <xref:System.Windows.Controls.TextBlock>.  Elementos que se hace referencia en el <xref:System.Windows.Controls.ControlTemplate> tienen nombres, pero no es necesario formar parte del contrato del control porque un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control no tendrán que hacen referencia a ese elemento.  Por ejemplo, alguien que crea un nuevo <xref:System.Windows.Controls.ControlTemplate> para `NumericUpDown` podría decidir no indicar que `Value` es negativo cambiando el <xref:System.Windows.Controls.Control.Foreground%2A>.  En ese caso, ni el código ni la <xref:System.Windows.Controls.ControlTemplate> referencias el <xref:System.Windows.Controls.TextBlock> por su nombre.  
  
 La lógica del control es responsable de cambiar el estado del control. En el ejemplo siguiente se muestra que la `NumericUpDown` controlar las llamadas de la <xref:System.Windows.VisualStateManager.GoToState%2A> método para entrar en el `Positive` estado cuando `Value` es 0 o mayor y la `Negative` estado cuando `Value` es menor que 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 El <xref:System.Windows.VisualStateManager.GoToState%2A> método realiza la lógica necesaria para iniciar y detener los guiones gráficos de forma adecuada. Cuando un control llama <xref:System.Windows.VisualStateManager.GoToState%2A> para cambiar su estado, el <xref:System.Windows.VisualStateManager> hace lo siguiente:  
  
-   Si el <xref:System.Windows.VisualState> que el control se va a tiene un <xref:System.Windows.Media.Animation.Storyboard>, comienza el guión gráfico. A continuación, si la <xref:System.Windows.VisualState> tiene que el control procede de un <xref:System.Windows.Media.Animation.Storyboard>, los extremos de guión gráfico.  
  
-   Si el control ya está en el estado que se especifica, <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `true`.  
  
-   Si el estado que se ha especificado no existe en el <xref:System.Windows.Controls.ControlTemplate> de `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Procedimientos recomendados para trabajar con VisualStateManager  
 Se recomienda que realice lo siguiente para mantener los Estados del control:  
  
-   Utilizar propiedades para realizar un seguimiento de su estado.  
  
-   Cree un método auxiliar para la transición entre Estados.  
  
 El `NumericUpDown` controlar usa su `Value` propiedad para realizar el seguimiento si se encuentra en la `Positive` o `Negative` estado.  El `NumericUpDown` control también define la `Focused` y `UnFocused` Estados, las pistas que la <xref:System.Windows.UIElement.IsFocused%2A> propiedad. Si utiliza los Estados que no corresponden naturalmente a una propiedad del control, puede definir una propiedad privada para realizar un seguimiento del estado.  
  
 Un único método que actualiza todos los Estados centraliza las llamadas a la <xref:System.Windows.VisualStateManager> y hace que el código sea fácil de administrar. El siguiente ejemplo se muestra la `NumericUpDown` método auxiliar del control NumericUpDown, `UpdateStates`. Cuando `Value` es mayor o igual que 0, el <xref:System.Windows.Controls.Control> está en el `Positive` estado.  Cuando `Value` es menor que 0, el control está en el `Negative` estado.  Cuando <xref:System.Windows.UIElement.IsFocused%2A> es `true`, el control está en el `Focused` estado; en caso contrario, se encuentra en la `Unfocused` estado.  El control puede llamar a `UpdateStates` siempre que sea necesario para cambiar su estado, independientemente de cuál es el estado cambia.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Si pasa el nombre de un estado a <xref:System.Windows.VisualStateManager.GoToState%2A> cuando el control ya está en ese estado, <xref:System.Windows.VisualStateManager.GoToState%2A> no hace nada, por lo que no es necesario comprobar el estado del control actual.  Por ejemplo, si `Value` cambia de un número negativo a otro número negativo, el guión gráfico para el `Negative` no se interrumpe el estado y el usuario no verá un cambio en el control.  
  
 El <xref:System.Windows.VisualStateManager> utiliza <xref:System.Windows.VisualStateGroup> objetos para determinar qué estado salir cuando se llama a <xref:System.Windows.VisualStateManager.GoToState%2A>. El control siempre está en un estado para cada <xref:System.Windows.VisualStateGroup> que se define en su <xref:System.Windows.Controls.ControlTemplate> y sólo deja un estado cuando entra en otro estado de la misma <xref:System.Windows.VisualStateGroup>. Por ejemplo, el <xref:System.Windows.Controls.ControlTemplate> de la `NumericUpDown` control define la `Positive` y `Negative` <xref:System.Windows.VisualState> objetos en una <xref:System.Windows.VisualStateGroup> y `Focused` y `Unfocused` <xref:System.Windows.VisualState> objetos en otra. (Puede ver el `Focused` y `Unfocused` <xref:System.Windows.VisualState> definido en el [ejemplo completo](#complete_example) en este tema cuando el control pasa de la `Positive` estado para el `Negative` estado, o viceversa, el control permanece en la vista la `Focused` o `Unfocused` estado.  
  
 Existen tres casos típicos donde puede cambiar el estado de un control:  
  
-   Cuando el <xref:System.Windows.Controls.ControlTemplate> se aplica a la <xref:System.Windows.Controls.Control>.  
  
-   Cuando se cambia una propiedad.  
  
-   Cuando se produce un evento.  
  
 Los ejemplos siguientes se muestra cómo actualizar el estado de la `NumericUpDown` control en estos casos.  
  
 Debe actualizar el estado del control en el <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> método para que el control aparece en el valor correcto estado cuando el <xref:System.Windows.Controls.ControlTemplate> se aplica. El ejemplo siguiente se llama `UpdateStates` en <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para asegurarse de que el control está en los Estados adecuados.  Por ejemplo, suponga que crea un `NumericUpDown` de control y, a continuación, establezca su <xref:System.Windows.Controls.Control.Foreground%2A> a verde y `Value` a -5.  Si no se llama `UpdateStates` cuando el <xref:System.Windows.Controls.ControlTemplate> se aplica a la `NumericUpDown` (control), el control no está en el `Negative` estado y el valor es verde en lugar de color rojo.  Debe llamar a `UpdateStates` para colocar el control el `Negative` estado.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 A menudo necesitará actualizar los Estados de un control cuando cambia una propiedad. En el ejemplo siguiente se muestra toda la matriz `ValueChangedCallback` método. Dado que `ValueChangedCallback` se llama cuando `Value` cambia, las llamadas al método `UpdateStates` en caso de que `Value` cambió de positivo a negativo o viceversa. Es aceptable llamar a `UpdateStates` cuando `Value` cambia pero permanece positivo o negativo, porque en ese caso, el control no cambiará de estado.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 También tendrá que actualizar los Estados cuando se produce un evento. En el ejemplo siguiente se muestra que la `NumericUpDown` llamadas `UpdateStates` en el <xref:System.Windows.Controls.Control> para controlar la <xref:System.Windows.UIElement.GotFocus> eventos.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 El <xref:System.Windows.VisualStateManager> le ayuda a administrar los Estados del control. Mediante el uso de la <xref:System.Windows.VisualStateManager>, asegúrese de que el control realiza las transiciones entre Estados correctamente.  Si sigue las recomendaciones que se describen en esta sección para trabajar con la <xref:System.Windows.VisualStateManager>, el código del control seguirá siendo legible y fácil de mantener.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Proporcionar el contrato de Control  
 Proporcione un contrato del control para que <xref:System.Windows.Controls.ControlTemplate> autores sepan qué incluir en la plantilla. Un contrato de control tiene tres elementos:  
  
-   Los elementos visuales que usa la lógica del control.  
  
-   Los estados del control y el grupo al que pertenece cada estado.  
  
-   Las propiedades públicas que afectan visualmente al control.  
  
 Un usuario que crea un nuevo <xref:System.Windows.Controls.ControlTemplate> necesita saber qué <xref:System.Windows.FrameworkElement> objetos usa la lógica del control, es el tipo de cada objeto y qué su nombre es. A <xref:System.Windows.Controls.ControlTemplate> autor también debe conocer el nombre de cada estado posible el control puede estar en y que <xref:System.Windows.VisualStateGroup> el estado es en.  
  
 Volver a la `NumericUpDown` ejemplo, se espera que el control de la <xref:System.Windows.Controls.ControlTemplate> tener lo siguiente <xref:System.Windows.FrameworkElement> objetos:  
  
-   A <xref:System.Windows.Controls.Primitives.RepeatButton> denominado `UpButton`.  
  
-   Un <xref:System.Windows.Controls.Primitives.RepeatButton> llama `DownButton.`  
  
 El control puede estar en los siguientes estados:  
  
-   En `ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   En `FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Para especificar qué <xref:System.Windows.FrameworkElement> espera que el control de objetos, utilizar el <xref:System.Windows.TemplatePartAttribute>, que especifica el nombre y tipo de los elementos esperados.  Para especificar los posibles estados de un control, utilice la <xref:System.Windows.TemplateVisualStateAttribute>, que especifica el nombre del estado y que <xref:System.Windows.VisualStateGroup> que pertenece.  Coloque el <xref:System.Windows.TemplatePartAttribute> y <xref:System.Windows.TemplateVisualStateAttribute> en la definición de clase del control.  
  
 Cualquier propiedad pública que afecta a la apariencia del control también es una parte del contrato de control.  
  
 En el ejemplo siguiente se especifica la <xref:System.Windows.FrameworkElement> objeto y estado de la `NumericUpDown` control.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Ejemplo completo  
 El ejemplo siguiente es todo el <xref:System.Windows.Controls.ControlTemplate> para el `NumericUpDown` control.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 En el ejemplo siguiente se muestra la lógica para el `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>Vea también  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)
