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
ms.openlocfilehash: c98035ef0b4ea1add22b09fb9927bcd49c00cd9b
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920042"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Crear un control que tiene una apariencia personalizable

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece la posibilidad de crear un control cuya apariencia se puede personalizar. Por ejemplo, puede cambiar la apariencia de un <xref:System.Windows.Controls.CheckBox> más allá de las propiedades de configuración que se van a crear mediante la creación de un nuevo <xref:System.Windows.Controls.ControlTemplate>. En la ilustración siguiente se muestra un <xref:System.Windows.Controls.CheckBox> que usa una <xref:System.Windows.Controls.ControlTemplate> predeterminada y una <xref:System.Windows.Controls.CheckBox> que utiliza un <xref:System.Windows.Controls.ControlTemplate>personalizado.

![Casilla con la plantilla de control predeterminada.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Un control CheckBox que usa la plantilla de control predeterminada

![Casilla con una plantilla de control personalizado.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Un control CheckBox que usa una plantilla de control personalizado

Si sigue el modelo Parts and States al crear un control, la apariencia del control se podrá personalizar. Las herramientas de diseñador como Blend para Visual Studio admiten el modelo de elementos y Estados, por lo que, al seguir este modelo, el control se podrá personalizar en esos tipos de aplicaciones.  En este tema se describe el modelo de partes y Estados y cómo seguirlo al crear su propio control. En este tema se usa un ejemplo de un control personalizado, `NumericUpDown`, para ilustrar la filosofía de este modelo.  El control `NumericUpDown` muestra un valor numérico, que un usuario puede aumentar o disminuir al hacer clic en los botones del control.  En la ilustración siguiente se muestra el control `NumericUpDown` que se describe en este tema.

![Control personalizado NumericUpDown.](./media/ndp-numericupdown.png "NDP_NumericUPDown")
Un control NumericUpDown personalizado

Este tema contiene las siguientes secciones:

- [Requisitos previos](#prerequisites)

- [Modelo de elementos y Estados](#parts_and_states_model)

- [Definir la estructura visual y el comportamiento visual de un control en una ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [Usar partes de ControlTemplate en el código](#using_parts_of_the_controltemplate_in_code)

- [Proporcionar el contrato de control](#providing_the_control_contract)

- [Ejemplo completo](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Requisitos previos

En este tema se supone que sabe cómo crear un nuevo <xref:System.Windows.Controls.ControlTemplate> para un control existente, está familiarizado con lo que son los elementos de un contrato de control y comprende los conceptos que se describen en [Personalización de la apariencia de un control existente mediante la creación de un ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

> [!NOTE]
> Para crear un control que pueda personalizar su apariencia, debe crear un control que herede de la clase <xref:System.Windows.Controls.Control> o de una de sus subclases distintas de <xref:System.Windows.Controls.UserControl>.  Un control que hereda de <xref:System.Windows.Controls.UserControl> es un control que se puede crear rápidamente, pero que no utiliza un <xref:System.Windows.Controls.ControlTemplate> y no se puede personalizar su apariencia.

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>Modelo de elementos y Estados

El modelo Parts and States especifica cómo definir la estructura visual y el comportamiento visual de un control. Para seguir el modelo de elementos y Estados, debe hacer lo siguiente:

- Defina la estructura visual y el comportamiento visual en la <xref:System.Windows.Controls.ControlTemplate> de un control.

- Siga ciertas prácticas recomendadas cuando la lógica del control interactúe con partes de la plantilla de control.

- Proporcione un contrato de control para especificar lo que debe incluirse en el <xref:System.Windows.Controls.ControlTemplate>.

Cuando se define la estructura visual y el comportamiento visual en el <xref:System.Windows.Controls.ControlTemplate> de un control, los autores de la aplicación pueden cambiar la estructura visual y el comportamiento visual del control creando un nuevo <xref:System.Windows.Controls.ControlTemplate> en lugar de escribir código.   Debe proporcionar un contrato de control que indique a los autores de la aplicación que <xref:System.Windows.FrameworkElement> objetos y Estados deben definirse en el <xref:System.Windows.Controls.ControlTemplate>. Debe seguir algunas prácticas recomendadas al interactuar con las partes de la <xref:System.Windows.Controls.ControlTemplate> para que el control administre correctamente una <xref:System.Windows.Controls.ControlTemplate>incompleta.  Si sigue estos tres principios, los autores de aplicaciones podrán crear un <xref:System.Windows.Controls.ControlTemplate> para el control de la misma manera que para los controles que se distribuyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En la siguiente sección se explica con detalle cada una de estas recomendaciones.

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definir la estructura visual y el comportamiento visual de un control en una ControlTemplate

Al crear el control personalizado mediante el modelo Parts and States, se define la estructura visual del control y el comportamiento visual en su <xref:System.Windows.Controls.ControlTemplate> en lugar de en su lógica.  La estructura visual de un control es el compuesto de <xref:System.Windows.FrameworkElement> objetos que componen el control.  El comportamiento visual es la forma en que el control aparece cuando está en un estado determinado.   Para obtener más información sobre la creación de una <xref:System.Windows.Controls.ControlTemplate> que especifica la estructura visual y el comportamiento visual de un control, vea [personalizar la apariencia de un control existente mediante la creación de un ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

En el ejemplo del control `NumericUpDown`, la estructura visual incluye dos controles <xref:System.Windows.Controls.Primitives.RepeatButton> y un <xref:System.Windows.Controls.TextBlock>.  Si agrega estos controles en el código del control `NumericUpDown` (en su constructor, por ejemplo), las posiciones de esos controles serían inalterables.  En lugar de definir la estructura visual del control y el comportamiento visual en su código, debe definirlo en el <xref:System.Windows.Controls.ControlTemplate>.  Después, un desarrollador de aplicaciones puede personalizar la posición de los botones y <xref:System.Windows.Controls.TextBlock> y especificar el comportamiento que se produce cuando `Value` es negativo porque el <xref:System.Windows.Controls.ControlTemplate> se puede reemplazar.

En el ejemplo siguiente se muestra la estructura visual del control `NumericUpDown`, que incluye un <xref:System.Windows.Controls.Primitives.RepeatButton> para aumentar `Value`, un <xref:System.Windows.Controls.Primitives.RepeatButton> para reducir `Value`y un <xref:System.Windows.Controls.TextBlock> para mostrar `Value`.

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

Un comportamiento visual del control `NumericUpDown` es que el valor se encuentra en una fuente roja si es negativo.  Si cambia el <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> en el código cuando el `Value` es negativo, el `NumericUpDown` mostrará siempre un valor negativo rojo. Especifique el comportamiento visual del control en el <xref:System.Windows.Controls.ControlTemplate> agregando <xref:System.Windows.VisualState> objetos a la <xref:System.Windows.Controls.ControlTemplate>.  En el ejemplo siguiente se muestra el <xref:System.Windows.VisualState> objetos para los Estados `Positive` y `Negative`.  `Positive` y `Negative` se excluyen mutuamente (el control siempre está en exactamente uno de los dos), por lo que en el ejemplo se colocan los objetos <xref:System.Windows.VisualState> en un solo <xref:System.Windows.VisualStateGroup>.  Cuando el control entra en el estado `Negative`, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de la <xref:System.Windows.Controls.TextBlock> se vuelve de color rojo.  Cuando el control está en el estado `Positive`, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> vuelve a su valor original.  La definición de objetos de <xref:System.Windows.VisualState> en un <xref:System.Windows.Controls.ControlTemplate> se describe con más detalle en [la personalización de la apariencia de un control existente mediante la creación de una ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

> [!NOTE]
> Asegúrese de establecer la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> en la <xref:System.Windows.FrameworkElement> raíz de la <xref:System.Windows.Controls.ControlTemplate>.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>Usar partes de ControlTemplate en el código

Un autor de <xref:System.Windows.Controls.ControlTemplate> podría omitir <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState> objetos, ya sea de forma intencionada o por equivocación, pero es posible que la lógica del control necesite que esas partes funcionen correctamente. El modelo Parts and States especifica que el control debe ser resistente a una <xref:System.Windows.Controls.ControlTemplate> a la que le faltan objetos <xref:System.Windows.FrameworkElement> o <xref:System.Windows.VisualState>.  El control no debe producir una excepción o notificar un error si falta un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>o <xref:System.Windows.VisualStateGroup> en el <xref:System.Windows.Controls.ControlTemplate>. En esta sección se describen los procedimientos recomendados para interactuar con los objetos de <xref:System.Windows.FrameworkElement> y la administración de Estados.

### <a name="anticipate-missing-frameworkelement-objects"></a>Previsión de objetos FrameworkElement que faltan

Al definir <xref:System.Windows.FrameworkElement> objetos en el <xref:System.Windows.Controls.ControlTemplate>, es posible que la lógica del control tenga que interactuar con algunos de ellos.  Por ejemplo, el control `NumericUpDown` se suscribe al evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de los botones para aumentar o disminuir `Value` y establece la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> del <xref:System.Windows.Controls.TextBlock> en `Value`. Si una <xref:System.Windows.Controls.ControlTemplate> personalizada omite la <xref:System.Windows.Controls.TextBlock> o los botones, es aceptable que el control pierda parte de su funcionalidad, pero debe asegurarse de que el control no produzca un error. Por ejemplo, si un <xref:System.Windows.Controls.ControlTemplate> no contiene los botones para cambiar `Value`, el `NumericUpDown` pierde esa funcionalidad, pero una aplicación que utiliza la <xref:System.Windows.Controls.ControlTemplate> continuará ejecutándose.

Los procedimientos siguientes garantizarán que el control responda correctamente a los objetos <xref:System.Windows.FrameworkElement> que faltan:

1. Establezca el atributo `x:Name` para cada <xref:System.Windows.FrameworkElement> al que tenga que hacer referencia en el código.

2. Defina las propiedades privadas de cada <xref:System.Windows.FrameworkElement> con el que tenga que interactuar.

3. Suscríbase y cancele la suscripción a los eventos que el control administre en el descriptor de acceso set de la propiedad <xref:System.Windows.FrameworkElement>.

4. Establezca las propiedades de <xref:System.Windows.FrameworkElement> que definió en el paso 2 en el método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>. Esta es la primera vez que el <xref:System.Windows.FrameworkElement> del <xref:System.Windows.Controls.ControlTemplate> está disponible para el control. Use el `x:Name` del <xref:System.Windows.FrameworkElement> para obtenerlo de la <xref:System.Windows.Controls.ControlTemplate>.

5. Compruebe que el <xref:System.Windows.FrameworkElement> no se `null` antes de tener acceso a sus miembros.  Si está `null`, no notifica un error.

En los siguientes ejemplos se muestra cómo interactúa el control `NumericUpDown` con <xref:System.Windows.FrameworkElement> objetos de acuerdo con las recomendaciones de la lista anterior.

En el ejemplo que define la estructura visual del control `NumericUpDown` en el <xref:System.Windows.Controls.ControlTemplate>, el <xref:System.Windows.Controls.Primitives.RepeatButton> que aumenta `Value` tiene su `x:Name` atributo establecido en `UpButton`.  En el ejemplo siguiente se declara una propiedad denominada `UpButtonElement` que representa el <xref:System.Windows.Controls.Primitives.RepeatButton> declarado en el <xref:System.Windows.Controls.ControlTemplate>. En primer lugar, el descriptor de acceso `set` cancela la suscripción al evento de <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón si `UpDownElement` no está `null`, establece la propiedad y, a continuación, se suscribe al evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. También hay una propiedad definida, pero que no se muestra aquí, para los demás <xref:System.Windows.Controls.Primitives.RepeatButton>, denominada `DownButtonElement`.

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

En el ejemplo siguiente se muestra la <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para el control `NumericUpDown`.  En el ejemplo se usa el método <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> para obtener los objetos <xref:System.Windows.FrameworkElement> de la <xref:System.Windows.Controls.ControlTemplate>.  Observe que en el ejemplo se protege en los casos en los que <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> encuentra un <xref:System.Windows.FrameworkElement> con el nombre especificado que no es del tipo esperado. También se recomienda omitir los elementos que tienen el `x:Name` especificado pero que son del tipo incorrecto.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Al seguir los procedimientos que se muestran en los ejemplos anteriores, se asegura de que el control se seguirá ejecutando cuando el <xref:System.Windows.Controls.ControlTemplate> no tenga un <xref:System.Windows.FrameworkElement>.

### <a name="use-the-visualstatemanager-to-manage-states"></a>Uso de VisualStateManager para administrar Estados

El <xref:System.Windows.VisualStateManager> realiza un seguimiento de los Estados de un control y realiza la lógica necesaria para realizar la transición entre Estados. Cuando se agregan objetos <xref:System.Windows.VisualState> a la <xref:System.Windows.Controls.ControlTemplate>, se agregan a un <xref:System.Windows.VisualStateGroup> y se agregan los <xref:System.Windows.VisualStateGroup> a la <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> propiedad adjunta para que el <xref:System.Windows.VisualStateManager> tenga acceso a ellos.

En el ejemplo siguiente se repite el ejemplo anterior en el que se muestra el <xref:System.Windows.VisualState> objetos que corresponden a los Estados `Positive` y `Negative` del control. El <xref:System.Windows.Media.Animation.Storyboard> en el `Negative`<xref:System.Windows.VisualState> activa el <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> rojo.   Cuando el control de `NumericUpDown` está en el estado `Negative`, comienza el guión gráfico en el estado de `Negative`.  A continuación, el <xref:System.Windows.Media.Animation.Storyboard> en el estado de `Negative` se detiene cuando el control vuelve al estado de `Positive`.  No es necesario que el<xref:System.Windows.VisualState> `Positive`contenga un <xref:System.Windows.Media.Animation.Storyboard> porque, cuando se detiene el <xref:System.Windows.Media.Animation.Storyboard> del `Negative`, el <xref:System.Windows.Controls.TextBlock.Foreground%2A> vuelve a su color original.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

Tenga en cuenta que al <xref:System.Windows.Controls.TextBlock> se le asigna un nombre, pero el <xref:System.Windows.Controls.TextBlock> no está en el contrato de control para `NumericUpDown` porque la lógica del control nunca hace referencia al <xref:System.Windows.Controls.TextBlock>.  Los elementos a los que se hace referencia en el <xref:System.Windows.Controls.ControlTemplate> tienen nombres, pero no es necesario que formen parte del contrato de control porque es posible que no sea necesario que una nueva <xref:System.Windows.Controls.ControlTemplate> para el control haga referencia a ese elemento.  Por ejemplo, alguien que crea un nuevo <xref:System.Windows.Controls.ControlTemplate> para `NumericUpDown` podría decidir no indicar que `Value` es negativo cambiando el <xref:System.Windows.Controls.Control.Foreground%2A>.  En ese caso, ni el código ni el <xref:System.Windows.Controls.ControlTemplate> hacen referencia al <xref:System.Windows.Controls.TextBlock> por nombre.

La lógica del control es responsable de cambiar el estado del control. En el ejemplo siguiente se muestra que el control `NumericUpDown` llama al método <xref:System.Windows.VisualStateManager.GoToState%2A> para entrar en el estado `Positive` cuando `Value` es 0 o superior y el estado `Negative` cuando `Value` es menor que 0.

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

El método <xref:System.Windows.VisualStateManager.GoToState%2A> realiza la lógica necesaria para iniciar y detener los guiones gráficos de forma adecuada. Cuando un control llama a <xref:System.Windows.VisualStateManager.GoToState%2A> para cambiar su estado, el <xref:System.Windows.VisualStateManager> hace lo siguiente:

- Si el <xref:System.Windows.VisualState> que el control va a tener un <xref:System.Windows.Media.Animation.Storyboard>, comienza el guión gráfico. A continuación, si el <xref:System.Windows.VisualState> del que procede el control tiene un <xref:System.Windows.Media.Animation.Storyboard>, el guión gráfico finaliza.

- Si el control ya está en el estado especificado, <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `true`.

- Si el estado especificado no existe en el <xref:System.Windows.Controls.ControlTemplate> de `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `false`.

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Prácticas recomendadas para trabajar con VisualStateManager

Se recomienda hacer lo siguiente para mantener los Estados del control:

- Use las propiedades para realizar el seguimiento de su estado.

- Cree un método auxiliar para realizar la transición entre Estados.

El control `NumericUpDown` utiliza su propiedad `Value` para hacer un seguimiento de si está en el estado `Positive` o `Negative`.  El control `NumericUpDown` también define los Estados `Focused` y `UnFocused`, que realiza el seguimiento de la propiedad <xref:System.Windows.UIElement.IsFocused%2A>. Si utiliza Estados que no corresponden de forma natural a una propiedad del control, puede definir una propiedad privada para realizar el seguimiento del estado.

Un único método que actualiza todos los Estados centraliza las llamadas al <xref:System.Windows.VisualStateManager> y mantiene el código que se pueda administrar. En el ejemplo siguiente se muestra el método auxiliar del control `NumericUpDown`, `UpdateStates`. Cuando `Value` es mayor o igual que 0, el <xref:System.Windows.Controls.Control> está en el estado `Positive`.  Cuando `Value` es menor que 0, el control está en el estado `Negative`.  Cuando se `true`<xref:System.Windows.UIElement.IsFocused%2A>, el control está en el estado `Focused`; de lo contrario, se encuentra en el estado `Unfocused`.  El control puede llamar `UpdateStates` siempre que sea necesario cambiar su estado, independientemente del estado que cambie.

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

Si pasa un nombre de estado a <xref:System.Windows.VisualStateManager.GoToState%2A> cuando el control ya está en ese estado, <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción, por lo que no es necesario comprobar el estado actual del control.  Por ejemplo, si `Value` cambia de un número negativo a otro número negativo, el guion gráfico para el estado `Negative` no se interrumpe y el usuario no verá un cambio en el control.

El <xref:System.Windows.VisualStateManager> utiliza <xref:System.Windows.VisualStateGroup> objetos para determinar qué estado salir al llamar a <xref:System.Windows.VisualStateManager.GoToState%2A>. El control siempre está en un estado para cada <xref:System.Windows.VisualStateGroup> que se define en su <xref:System.Windows.Controls.ControlTemplate> y solo deja un estado cuando entra en otro estado del mismo <xref:System.Windows.VisualStateGroup>. Por ejemplo, el <xref:System.Windows.Controls.ControlTemplate> del control `NumericUpDown` define los objetos `Positive` y `Negative`<xref:System.Windows.VisualState> de una <xref:System.Windows.VisualStateGroup> y los objetos `Focused` y `Unfocused`de otro. (Puede ver los `Focused` y `Unfocused`<xref:System.Windows.VisualState> definidos en la sección [ejemplo completa](#complete_example) de este tema cuando el control pasa del estado `Positive` al estado `Negative`, o viceversa, el control permanece en `Focused` o `Unfocused` State.

Hay tres lugares típicos en los que el estado de un control puede cambiar:

- Cuando el <xref:System.Windows.Controls.ControlTemplate> se aplica al <xref:System.Windows.Controls.Control>.

- Cuando cambia una propiedad.

- Cuando se produce un evento.

En los siguientes ejemplos se muestra cómo actualizar el estado del control `NumericUpDown` en estos casos.

Debe actualizar el estado del control en el método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para que el control aparezca en el estado correcto cuando se aplique el <xref:System.Windows.Controls.ControlTemplate>. En el ejemplo siguiente se llama a `UpdateStates` en <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para asegurarse de que el control se encuentra en los Estados adecuados.  Por ejemplo, suponga que crea un control de `NumericUpDown` y, a continuación, establece su <xref:System.Windows.Controls.Control.Foreground%2A> en verde y `Value` en-5.  Si no llama a `UpdateStates` cuando el <xref:System.Windows.Controls.ControlTemplate> se aplica al control `NumericUpDown`, el control no está en el estado `Negative` y el valor es verde en lugar de rojo.  Debe llamar a `UpdateStates` para colocar el control en el estado `Negative`.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

A menudo es necesario actualizar los Estados de un control cuando cambia una propiedad. En el ejemplo siguiente se muestra todo el método de `ValueChangedCallback`. Dado que se llama a `ValueChangedCallback` cuando `Value` cambia, el método llama a `UpdateStates` en caso de que `Value` cambie de positivo a negativo, o viceversa. Es aceptable llamar a `UpdateStates` cuando `Value` cambia pero sigue siendo positivo o negativo porque, en ese caso, el control no cambiará de estado.

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

También podría ser necesario actualizar los Estados cuando se produce un evento. En el ejemplo siguiente se muestra que el `NumericUpDown` llama a `UpdateStates` en el <xref:System.Windows.Controls.Control> para controlar el evento de <xref:System.Windows.UIElement.GotFocus>.

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

El <xref:System.Windows.VisualStateManager> le ayuda a administrar los Estados del control. Mediante el <xref:System.Windows.VisualStateManager>, se asegura de que el control realiza correctamente la transición entre Estados.  Si sigue las recomendaciones descritas en esta sección para trabajar con el <xref:System.Windows.VisualStateManager>, el código de su control seguirá siendo legible y fácil de mantener.

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>Proporcionar el contrato de control

Debe proporcionar un contrato de control para que <xref:System.Windows.Controls.ControlTemplate> autores sepan qué se debe incluir en la plantilla. Un contrato de control tiene tres elementos:

- Los elementos visuales que usa la lógica del control.

- Los estados del control y el grupo al que pertenece cada estado.

- Las propiedades públicas que afectan visualmente al control.

Alguien que crea un nuevo <xref:System.Windows.Controls.ControlTemplate> necesita saber qué <xref:System.Windows.FrameworkElement> objetos utiliza la lógica del control, el tipo de cada objeto y su nombre. Un autor de <xref:System.Windows.Controls.ControlTemplate> también necesita conocer el nombre de cada posible estado en el que el control puede estar y en el que <xref:System.Windows.VisualStateGroup> el estado.

Volviendo al ejemplo `NumericUpDown`, el control espera que el <xref:System.Windows.Controls.ControlTemplate> tenga los siguientes objetos <xref:System.Windows.FrameworkElement>:

- <xref:System.Windows.Controls.Primitives.RepeatButton> denominada `UpButton`.

- <xref:System.Windows.Controls.Primitives.RepeatButton> llamada `DownButton.`

 El control puede tener los siguientes Estados:

- En el `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- En el `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

Para especificar qué <xref:System.Windows.FrameworkElement> objetos espera el control, use el <xref:System.Windows.TemplatePartAttribute>, que especifica el nombre y el tipo de los elementos esperados.  Para especificar los posibles estados de un control, use el <xref:System.Windows.TemplateVisualStateAttribute>, que especifica el nombre del estado y el <xref:System.Windows.VisualStateGroup> al que pertenece.  Coloque el <xref:System.Windows.TemplatePartAttribute> y <xref:System.Windows.TemplateVisualStateAttribute> en la definición de clase del control.

Cualquier propiedad pública que afecte a la apariencia del control también forma parte del contrato de control.

En el ejemplo siguiente se especifica el objeto <xref:System.Windows.FrameworkElement> y los Estados para el control `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>Ejemplo completo

El ejemplo siguiente es el <xref:System.Windows.Controls.ControlTemplate> completo para el control `NumericUpDown`.

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

En el ejemplo siguiente se muestra la lógica para el `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>Vea también

- [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
- [Control Customization](control-customization.md) (Personalización de controles)
