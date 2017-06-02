---
title: "Crear un control que tiene una apariencia personalizable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles [WPF], personalizar"
  - "controles [WPF], definir el comportamiento y la estructura visual de"
  - "ControlTemplate [WPF], personalizar apariencia"
  - "personalizar la apariencia [WPF], ControlTemplate"
  - "administrar los estados de los controles [WPF], VisualStateManager"
  - "VisualStateManager [WPF], procedimiento recomendado"
  - "VisualStateManager [WPF], administrar el estado de un control"
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Crear un control que tiene una apariencia personalizable
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece la posibilidad de crear un control cuya apariencia se puede personalizar.  Por ejemplo, puede cambiar la apariencia de un control <xref:System.Windows.Controls.CheckBox> más de lo que las propiedades de configuración permiten hacer mediante la creación de un nuevo objeto <xref:System.Windows.Controls.ControlTemplate>.  En la ilustración siguiente se muestra un control <xref:System.Windows.Controls.CheckBox> que usa un <xref:System.Windows.Controls.ControlTemplate> predeterminado y un control <xref:System.Windows.Controls.CheckBox> que usa un <xref:System.Windows.Controls.ControlTemplate>personalizado.  
  
 ![Casilla con la plantilla de control predeterminada.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Control CheckBox que usa la plantilla de control predeterminada  
  
 ![Casilla con una plantilla de control personalizada.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Control CheckBox que usa una plantilla de control personalizada  
  
 Si sigue el modelo de estados y elementos al crear un control, la apariencia del control será personalizable.  Existen herramientas de diseño como Microsoft Expression Blend que admiten el modelo de estados y elementos, por lo que si sigue dicho modelo, podrá personalizar el control en ese tipo de aplicaciones.  En este tema se trata el modelo de estados y elementos, y cómo seguirlo al crear su propio control.  En este tema se emplea un ejemplo de un control personalizado, `NumericUpDown`, con el fin de ilustrar la filosofía de este modelo.  El control `NumericUpDown` muestra un valor numérico, que los usuarios pueden aumentar o disminuir haciendo clic en los botones del control.  En la ilustración siguiente se muestra el control `NumericUpDown` que se explica en este tema.  
  
 ![Control personalizado NumericUpDown.](../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP\_NumericUPDown")  
Control NumericUpDown personalizado  
  
 Este tema contiene las siguientes secciones:  
  
-   [Requisitos previos](#prerequisites)  
  
-   [Modelo de estados y elementos](#parts_and_states_model)  
  
-   [Definir la estructura y el comportamiento visuales de un control en ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Usar elementos de ControlTemplate en el código](#using_parts_of_the_controltemplate_in_code)  
  
-   [Proporcionar el contrato de un control](#providing_the_control_contract)  
  
-   [Ejemplo completo](#complete_example)  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se da por supuesto que sabe crear un <xref:System.Windows.Controls.ControlTemplate> nuevo para un control existente, que está familiarizado con cuáles son los elementos del contrato de un control y que entiende los conceptos tratados en [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Para crear un control cuya apariencia se pueda personalizar, debe crear un control que herede de la clase <xref:System.Windows.Controls.Control> o alguna de sus subclases que no sea <xref:System.Windows.Controls.UserControl>.  Un control que hereda de <xref:System.Windows.Controls.UserControl> se puede crear rápidamente, pero al no usar <xref:System.Windows.Controls.ControlTemplate> no se puede personalizar su apariencia.  
  
<a name="parts_and_states_model"></a>   
## Modelo de estados y elementos  
 El modelo de estados y elementos especifica cómo definir la estructura y el comportamiento visuales de un control.  Para seguir el modelo de estados y elementos, haga lo siguiente:  
  
-   Defina la estructura y el comportamiento visuales en el <xref:System.Windows.Controls.ControlTemplate> de un control.  
  
-   Siga algunos procedimientos recomendados cuando la lógica de su control interactúe con elementos de la plantilla de control.  
  
-   Proporcione un contrato del control para especificar lo que se debe incluir en <xref:System.Windows.Controls.ControlTemplate>.  
  
 Al definir la estructura y el comportamiento visuales en el <xref:System.Windows.Controls.ControlTemplate> de un control, los autores de la aplicación pueden cambiar la estructura y el comportamiento visuales del mismo creando un nuevo <xref:System.Windows.Controls.ControlTemplate> en lugar de escribir código.  Debe proporcionar un contrato del control que indique a los autores de la aplicación qué objetos y estados de <xref:System.Windows.FrameworkElement> se deben definir en <xref:System.Windows.Controls.ControlTemplate>.  Debe seguir algunos procedimientos recomendados al interactuar con los elementos de <xref:System.Windows.Controls.ControlTemplate> para que el control administre correctamente un <xref:System.Windows.Controls.ControlTemplate> incompleto.  Si sigue estos tres principios, los autores de la aplicación podrán crear un <xref:System.Windows.Controls.ControlTemplate> para el control con la misma facilidad que para los controles que se incluyen en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En la próxima sección se explica en detalle cada una de estas recomendaciones.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## Definir la estructura y el comportamiento visuales de un control en ControlTemplate  
 Al crear un control personalizado usando el modelo de estados y elementos, se define la estructura y el comportamiento visuales del control en su <xref:System.Windows.Controls.ControlTemplate> en lugar de en su lógica.  La estructura visual de un control es la composición de los objetos <xref:System.Windows.FrameworkElement> que constituyen el control.  El comportamiento visual es el modo en que aparece el control cuando está en determinado estado.  Para obtener más información sobre cómo crear un <xref:System.Windows.Controls.ControlTemplate> que especifique la estructura y el comportamiento visuales de un control, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 En el ejemplo del control `NumericUpDown`, la estructura visual incluye dos controles <xref:System.Windows.Controls.Primitives.RepeatButton> y un <xref:System.Windows.Controls.TextBlock>.  Si agrega estos controles en el código del control `NumericUpDown` \(en su constructor, por ejemplo\), las posiciones de esos controles serían inalterables.  En lugar de definir la estructura y el comportamiento visuales del control en el código, debe hacerlo en el <xref:System.Windows.Controls.ControlTemplate>.  A continuación, un desarrollador de aplicaciones personaliza la posición de los botones y de <xref:System.Windows.Controls.TextBlock>, y especifica qué comportamiento se produce cuando `Value` es negativo porque el <xref:System.Windows.Controls.ControlTemplate> se puede reemplazar.  
  
 En el ejemplo siguiente se muestra la estructura visual del control `NumericUpDown`, que incluye un <xref:System.Windows.Controls.Primitives.RepeatButton> para aumentar `Value`, un <xref:System.Windows.Controls.Primitives.RepeatButton> para disminuir `Value` y un <xref:System.Windows.Controls.TextBlock> para mostrar `Value`.  
  
 [!code-xml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Un comportamiento visual del control `NumericUpDown` es que el valor aparece en una fuente de color rojo si es negativo.  Si cambia la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> del <xref:System.Windows.Controls.TextBlock> en el código cuando `Value` es negativo, `NumericUpDown` siempre mostrará un valor negativo en rojo.  Se especifica el comportamiento visual del control en <xref:System.Windows.Controls.ControlTemplate> agregando objetos <xref:System.Windows.VisualState> al <xref:System.Windows.Controls.ControlTemplate>.  En el ejemplo siguiente se muestran los objetos <xref:System.Windows.VisualState> para los estados `Positive` y `Negative`.  `Positive` y `Negative` son mutuamente excluyentes \(el control siempre está en uno de los dos\), por lo que en el ejemplo se colocan los objetos <xref:System.Windows.VisualState> en un mismo <xref:System.Windows.VisualStateGroup>.  Cuando el control entra en el estado `Negative`, la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> de <xref:System.Windows.Controls.TextBlock> cambia a rojo.  Cuando el control está en el estado `Positive`, la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> vuelve a su valor original.  La definición de objetos <xref:System.Windows.VisualState> en <xref:System.Windows.Controls.ControlTemplate> se explica más detalladamente en [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Asegúrese de establecer la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> del <xref:System.Windows.FrameworkElement> raíz de <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## Usar elementos de ControlTemplate en el código  
 Un autor de <xref:System.Windows.Controls.ControlTemplate> podría omitir los objetos <xref:System.Windows.VisualState> o <xref:System.Windows.FrameworkElement> a propósito o por error, pero la lógica del control podría necesitar esos elementos para funcionar correctamente.  El modelo de estados y elementos especifica que el control debe adaptarse a un <xref:System.Windows.Controls.ControlTemplate> al que le falten objetos <xref:System.Windows.VisualState> o <xref:System.Windows.FrameworkElement>.  El control no debe producir una excepción ni notificar un error si falta un <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState> o <xref:System.Windows.VisualStateGroup> en <xref:System.Windows.Controls.ControlTemplate>.  En esta sección se describen los procedimientos recomendados para interactuar con objetos <xref:System.Windows.FrameworkElement> y administrar estados.  
  
### Prever los objetos FrameworkElement que puedan faltar  
 Al definir objetos <xref:System.Windows.FrameworkElement> en <xref:System.Windows.Controls.ControlTemplate>, la lógica del control podría necesitar interactuar con algunos de ellos.  Por ejemplo, el control `NumericUpDown` se suscribe al evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de los botones para aumentar o disminuir `Value` y establece la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> de <xref:System.Windows.Controls.TextBlock> en `Value`.  Si un <xref:System.Windows.Controls.ControlTemplate> personalizado omite el <xref:System.Windows.Controls.TextBlock> o los botones, es aceptable que el control pierda parte de su funcionalidad, pero debe asegurarse de que el control no produzca un error.  Por ejemplo, si un <xref:System.Windows.Controls.ControlTemplate> no contiene los botones para cambiar `Value`, el control `NumericUpDown` pierde esa funcionalidad, pero una aplicación que use el <xref:System.Windows.Controls.ControlTemplate> continuará ejecutándose.  
  
 Con los procedimientos siguientes se asegurará de que el control responda correctamente a los objetos <xref:System.Windows.FrameworkElement> que falten:  
  
1.  Establezca el atributo `x:Name` para cada <xref:System.Windows.FrameworkElement> al que necesite hacer referencia en el código.  
  
2.  Defina las propiedades privadas para cada <xref:System.Windows.FrameworkElement> con el que necesite interactuar.  
  
3.  Suscriba y cancele la suscripción de cualquier evento que el control administre en el descriptor de acceso set de la propiedad del objeto <xref:System.Windows.FrameworkElement>.  
  
4.  Establezca las propiedades del objeto <xref:System.Windows.FrameworkElement> que definió en el paso 2 del método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>.  Esto es lo antes que el <xref:System.Windows.FrameworkElement> está disponible para el control en el <xref:System.Windows.Controls.ControlTemplate>.  Use el atributo `x:Name` del <xref:System.Windows.FrameworkElement> para obtenerlo de <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Compruebe que <xref:System.Windows.FrameworkElement> no es `null` antes de tener acceso a sus miembros.  Si es `null`, no notifique un error.  
  
 En los ejemplos siguientes se muestra cómo interactúa el control `NumericUpDown` con objetos <xref:System.Windows.FrameworkElement> de acuerdo con las recomendaciones de la lista anterior.  
  
 En el ejemplo que define la estructura visual del control `NumericUpDown` en <xref:System.Windows.Controls.ControlTemplate>, el <xref:System.Windows.Controls.Primitives.RepeatButton> que aumenta `Value` tiene el atributo `x:Name` establecido en `UpButton`.  En el ejemplo siguiente se declara una propiedad denominada `UpButtonElement` que representa el <xref:System.Windows.Controls.Primitives.RepeatButton> que se declara en <xref:System.Windows.Controls.ControlTemplate>.  El descriptor de acceso `set` cancela primero la suscripción al evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón si `UpDownElement` no es `null`; a continuación, establece la propiedad y después se suscribe al evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  Aunque no se muestra aquí, también se define una propiedad del otro <xref:System.Windows.Controls.Primitives.RepeatButton>, denominado `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 En el ejemplo siguiente se muestra el método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para el control `NumericUpDown`.  Se usa el método <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> para obtener los objetos <xref:System.Windows.FrameworkElement> de <xref:System.Windows.Controls.ControlTemplate>.  Observe que en el ejemplo se evitan los casos donde <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> busca un <xref:System.Windows.FrameworkElement> con el nombre especificado que no es del tipo esperado.  También es un procedimiento recomendado omitir los elementos que tienen el atributo `x:Name` especificado pero son del tipo equivocado.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Siguiendo los procedimientos que se muestran en los ejemplos anteriores, se asegura de que el control continuará ejecutándose cuando a <xref:System.Windows.Controls.ControlTemplate> le falte un <xref:System.Windows.FrameworkElement>.  
  
### Usar VisualStateManager para administrar estados  
 <xref:System.Windows.VisualStateManager> realiza un seguimiento de los estados de un control y ejecuta la lógica necesaria para la transición entre estados.  Al agregar objetos <xref:System.Windows.VisualState> a <xref:System.Windows.Controls.ControlTemplate>, los agrega a un <xref:System.Windows.VisualStateGroup> y agrega este <xref:System.Windows.VisualStateGroup> a la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> de modo que <xref:System.Windows.VisualStateManager> tenga acceso a ellos.  
  
 En el ejemplo siguiente se repite el ejemplo anterior donde se muestran los objetos <xref:System.Windows.VisualState> correspondientes a los estados `Positive` y `Negative` del control.  El <xref:System.Windows.Media.Animation.Storyboard> de `Negative` <xref:System.Windows.VisualState> cambia la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> de <xref:System.Windows.Controls.TextBlock> a rojo.  Cuando el control `NumericUpDown` está en estado `Negative`, comienza el guión gráfico en el estado `Negative`.  A continuación, el <xref:System.Windows.Media.Animation.Storyboard> del estado `Negative` se detiene cuando el control vuelve al estado `Positive`.  El <xref:System.Windows.VisualState> con estado `Positive` no necesita contener un <xref:System.Windows.Media.Animation.Storyboard> porque cuando el <xref:System.Windows.Media.Animation.Storyboard> para el estado `Negative` se detiene, la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> vuelve a su color original.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Observe que se asigna un nombre a <xref:System.Windows.Controls.TextBlock>, pero <xref:System.Windows.Controls.TextBlock> no es en el contrato del control para `NumericUpDown` porque la lógica del control nunca hace referencia a <xref:System.Windows.Controls.TextBlock>.  Los elementos a los que se hacen referencia en <xref:System.Windows.Controls.ControlTemplate> tienen nombres, pero no necesitan formar parte del contrato del control porque un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control quizás no necesite hacer referencia a ese elemento.  Por ejemplo, alguien que crea un nuevo <xref:System.Windows.Controls.ControlTemplate> para `NumericUpDown` podría decidir no indicar que `Value` es negativo cambiando la propiedad <xref:System.Windows.Controls.Control.Foreground%2A>.  En ese caso, ni el código ni <xref:System.Windows.Controls.ControlTemplate> hace referencia a <xref:System.Windows.Controls.TextBlock> por nombre.  
  
 La lógica del control es responsable de cambiar el estado del control.  En el ejemplo siguiente se muestra que el control `NumericUpDown` llama al método <xref:System.Windows.VisualStateManager.GoToState%2A> para entrar en el estado `Positive` cuando `Value` es 0 o mayor, y en el estado `Negative` cuando `Value` es menor que 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 El método <xref:System.Windows.VisualStateManager.GoToState%2A> ejecuta la lógica necesaria para iniciar y detener los guiones gráficos correctamente.  Cuando un control llama a <xref:System.Windows.VisualStateManager.GoToState%2A> para cambiar su estado, <xref:System.Windows.VisualStateManager> hace lo siguiente:  
  
-   Si el <xref:System.Windows.VisualState> hacia el que va el control tiene un <xref:System.Windows.Media.Animation.Storyboard>, comienza el guión gráfico.  A continuación, si el <xref:System.Windows.VisualState> del que procede el control tiene un <xref:System.Windows.Media.Animation.Storyboard>, el guión gráfico se detiene.  
  
-   Si el control ya está en el estado que se especifica, el método <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `true`.  
  
-   Si el estado que se especifica no existe en el <xref:System.Windows.Controls.ControlTemplate> de `control`, el método <xref:System.Windows.VisualStateManager.GoToState%2A> no realiza ninguna acción y devuelve `false`.  
  
#### Procedimientos recomendados para trabajar con VisualStateManager  
 Se recomienda que haga lo siguiente para mantener los estados del control:  
  
-   Use propiedades para realizar un seguimiento del estado.  
  
-   Cree un método auxiliar para la transición entre estados.  
  
 El control `NumericUpDown` usa su propiedad `Value` para comprobar si está en estado `Positive` o `Negative`.  El control `NumericUpDown` también define los estados `Focused` y `UnFocused`, lo que hace un seguimiento de la propiedad <xref:System.Windows.UIElement.IsFocused%2A>.  Si emplea estados que no corresponden naturalmente a una propiedad del control, puede definir una propiedad privada para realizar un seguimiento del estado.  
  
 Un único método que actualiza todos los estados centraliza las llamadas a <xref:System.Windows.VisualStateManager> y hace que el código se pueda controlar.  En el ejemplo siguiente se muestra el método auxiliar `UpdateStates` del control `NumericUpDown`.  Cuando `Value` es mayor o igual a 0, el <xref:System.Windows.Controls.Control> está en estado `Positive`.  Cuando `Value` es menor que 0, el control está en estado `Negative`.  Cuando la propiedad <xref:System.Windows.UIElement.IsFocused%2A> es `true`, el control está en estado `Focused`; de lo contrario, está en estado `Unfocused`.  El control puede llamar a `UpdateStates` siempre que necesite cambiar su estado, independientemente del estado que cambie.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Si pasa el nombre de un estado a <xref:System.Windows.VisualStateManager.GoToState%2A> cuando el control ya está en dicho estado, <xref:System.Windows.VisualStateManager.GoToState%2A> no hace nada, por lo que no necesita comprobar el estado actual del control.  Por ejemplo, si `Value` cambia de un número negativo a otro número negativo, no se interrumpe el guión gráfico para el estado `Negative` y el usuario no verá ningún cambio en el control.  
  
 <xref:System.Windows.VisualStateManager> usa objetos de <xref:System.Windows.VisualStateGroup> para determinar de qué estado salir cuando se llama al método <xref:System.Windows.VisualStateManager.GoToState%2A>.  El control siempre está en un estado para cada <xref:System.Windows.VisualStateGroup> que se define en su <xref:System.Windows.Controls.ControlTemplate> correspondiente y únicamente abandona un estado cuando entra en otro estado del mismo <xref:System.Windows.VisualStateGroup>.  Por ejemplo, el control <xref:System.Windows.Controls.ControlTemplate> del `NumericUpDown` define los objetos `Positive` y `Negative` <xref:System.Windows.VisualState> de un <xref:System.Windows.VisualStateGroup>, y los objetos `Focused` y `Unfocused` <xref:System.Windows.VisualState> de otro.  \(Puede ver la definición de <xref:System.Windows.VisualState> en los estados `Focused` y `Unfocused` en la sección [Ejemplo completo](#complete_example) de este tema.\) Cuando el control pasa del estado `Positive` al estado `Negative` o viceversa, el control permanece en el estado `Focused` o `Unfocused`.  
  
 Hay tres casos típicos en los que el estado de un control podría cambiar:  
  
-   Cuando se aplica <xref:System.Windows.Controls.ControlTemplate> a <xref:System.Windows.Controls.Control>.  
  
-   Cuando cambia una propiedad.  
  
-   Cuando se produce un evento.  
  
 En los ejemplos siguientes se muestra cómo actualizar el estado del control `NumericUpDown` en estos casos.  
  
 Debe actualizar el estado del control en el método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> de forma que el control aparezca en el estado correcto cuando se aplique <xref:System.Windows.Controls.ControlTemplate>.  En el ejemplo siguiente se llama a `UpdateStates` en el método <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> para garantizar que el control esté en los estados adecuados.  Por ejemplo, suponga que crea un control `NumericUpDown`, y que establece su propiedad <xref:System.Windows.Controls.Control.Foreground%2A> en verde y `Value` en \-5.  Si no llama a `UpdateStates` cuando el objeto <xref:System.Windows.Controls.ControlTemplate> se aplica al control `NumericUpDown`, el control no está en el estado `Negative` y el valor es verde en lugar de rojo.  Debe llamar a `UpdateStates` para poner el control en el estado `Negative`.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Con frecuencia necesita actualizar los estados de un control cuando una propiedad cambia.  En el ejemplo siguiente se muestra todo el método `ValueChangedCallback`.  Puesto que se llama a `ValueChangedCallback` cuando `Value` cambia, el método llama a `UpdateStates` si `Value` cambió de positivo a negativo o viceversa.  Es aceptable llamar a `UpdateStates` cuando `Value` cambia pero sigue siendo positivo o negativo, ya que en ese caso el control no cambiará de estado.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 También podría necesitar actualizar los estados cuando se produce un evento.  En el ejemplo siguiente se muestra que `NumericUpDown` llama a `UpdateStates` en el <xref:System.Windows.Controls.Control> para controlar el evento <xref:System.Windows.UIElement.GotFocus>.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager> ayuda a administrar los estados del control.  Usando <xref:System.Windows.VisualStateManager>, se asegura de que el control realiza las transiciones entre estados correctamente.  Si sigue las recomendaciones descritas en esta sección para trabajar con <xref:System.Windows.VisualStateManager>, el código del control seguirá siendo legible y podrá mantenerse.  
  
<a name="providing_the_control_contract"></a>   
## Proporcionar el contrato de un control  
 Se proporciona el contrato de un control para que los autores de <xref:System.Windows.Controls.ControlTemplate> sepan qué deben incluir en la plantilla.  El contrato de un control tiene tres elementos:  
  
-   Los elementos visuales que usa la lógica del control.  
  
-   Los estados del control y el grupo al que pertenece cada estado.  
  
-   Las propiedades públicas que afectan visualmente al control.  
  
 Alguien que cree un nuevo <xref:System.Windows.Controls.ControlTemplate> debe saber qué objetos <xref:System.Windows.FrameworkElement> usa la lógica del control, el tipo de objeto que es cada uno y cómo se denomina.  Un autor de <xref:System.Windows.Controls.ControlTemplate> también necesita conocer el nombre de los posibles estados en los que se puede hallar el control y en qué <xref:System.Windows.VisualStateGroup> se encuentra el estado.  
  
 Volviendo al ejemplo de `NumericUpDown`, el control espera que <xref:System.Windows.Controls.ControlTemplate> tenga los siguientes objetos <xref:System.Windows.FrameworkElement>:  
  
-   Un control <xref:System.Windows.Controls.Primitives.RepeatButton> denominado `UpButton`.  
  
-   Un <xref:System.Windows.Controls.Primitives.RepeatButton> denominado `DownButton.`  
  
 El control puede estar en los estados siguientes:  
  
-   En el <xref:System.Windows.VisualStateGroup> `ValueStates`  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   En el <xref:System.Windows.VisualStateGroup> `FocusStates`  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Para especificar qué objetos <xref:System.Windows.FrameworkElement> espera el control, se utiliza la clase <xref:System.Windows.TemplatePartAttribute>, que especifica el nombre y tipo de los elementos esperados.  Para especificar los posibles estados de un control, se usa la clase <xref:System.Windows.TemplateVisualStateAttribute>, que especifica el nombre del estado y a qué <xref:System.Windows.VisualStateGroup> pertenece.  Coloque las clases <xref:System.Windows.TemplatePartAttribute> y <xref:System.Windows.TemplateVisualStateAttribute> en la definición de clase del control.  
  
 Cualquier propiedad pública que afecte a la apariencia del control también forma parte del contrato de un control.  
  
 En el ejemplo siguiente se especifica el objeto <xref:System.Windows.FrameworkElement> y los estados del control `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## Ejemplo completo  
 El ejemplo siguiente es todo el <xref:System.Windows.Controls.ControlTemplate> para el control `NumericUpDown`.  
  
 [!code-xml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 En el ejemplo siguiente se muestra la lógica de `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## Vea también  
 [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)