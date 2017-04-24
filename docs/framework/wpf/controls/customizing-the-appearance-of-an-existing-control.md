---
title: "Personalizar la apariencia de un control existente creando una clase ControlTemplate | Microsoft Docs"
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
  - "contrato de control [WPF]"
  - "controles [WPF], apariencia especificada mediante el estado"
  - "controles [WPF], cambios en la estructura visual"
  - "ControlTemplate [WPF], personalización de los controles existentes"
  - "cambiar el aspecto visual de los controles [WPF]"
  - "plantillas [WPF], personalizar los controles existentes"
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Personalizar la apariencia de un control existente creando una clase ControlTemplate
<a name="introduction"></a> Una plantilla <xref:System.Windows.Controls.ControlTemplate> especifica la estructura y el comportamiento visuales de un control.  Puede personalizar la apariencia de un control proporcionándole una nueva plantilla <xref:System.Windows.Controls.ControlTemplate>.  Cuando se crea una plantilla <xref:System.Windows.Controls.ControlTemplate>, se reemplaza la apariencia de un control existente sin cambiar su funcionalidad.  Por ejemplo, puede hacer que los botones de la aplicación sean redondos en lugar de rectangulares como son de forma predeterminada, pero cada botón seguirá generando el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
 En este tema se explican las distintas partes de una plantilla <xref:System.Windows.Controls.ControlTemplate>, se muestra cómo se crea una plantilla <xref:System.Windows.Controls.ControlTemplate> sencilla para un control <xref:System.Windows.Controls.Button> y se explica cómo entender el contrato de un control para que pueda personalizar su apariencia.  Puesto que las plantillas <xref:System.Windows.Controls.ControlTemplate> se crean en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede cambiar la apariencia de un control sin escribir código.  También puede usar un diseñador, como Microsoft expression Blend, para crear plantillas de control personalizado.  En este tema se muestran ejemplos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que personalizan la apariencia de un control <xref:System.Windows.Controls.Button> y se muestra el ejemplo completo al final del tema.  Para obtener más información sobre cómo usar Expression Blend, vea [Aplicar estilo a un control que admite plantillas](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 En las ilustraciones siguientes se muestra un control <xref:System.Windows.Controls.Button> que usa la plantilla <xref:System.Windows.Controls.ControlTemplate> que se crea en este tema.  
  
 ![Botón con una plantilla de control personalizada.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Botón que usa una plantilla de control personalizada  
  
 ![Botón con un borde rojo.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Botón que usa una plantilla de control personalizada y tiene el puntero del mouse sobre él  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se da por supuesto que entiende cómo crear y usar controles y estilos tal como se describe en [Controles](../../../../docs/framework/wpf/controls/index.md).  Los conceptos descritos en este tema se aplican a los elementos que heredan de la clase <xref:System.Windows.Controls.Control>, salvo <xref:System.Windows.Controls.UserControl>.  No se puede aplicar una plantilla <xref:System.Windows.Controls.ControlTemplate> a un control <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## Cuándo se debe crear una plantilla ControlTemplate  
 Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A>, que puede establecer para especificar distintos aspectos de la apariencia del control, pero los cambios que puede realizar estableciendo estas propiedades son limitados.  Por ejemplo, puede establecer la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> en azul y la propiedad <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un control <xref:System.Windows.Controls.CheckBox>.  
  
 Sin la capacidad de crear una nueva plantilla <xref:System.Windows.Controls.ControlTemplate> para los controles, todos los controles de todas las aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tendrían la misma apariencia general, lo que limitaría la capacidad de crear una aplicación con una apariencia y un funcionamiento personalizados.  De forma predeterminada, todos los controles <xref:System.Windows.Controls.CheckBox> tienen características similares.  Por ejemplo, el contenido de <xref:System.Windows.Controls.CheckBox> aparece siempre a la derecha del indicador de selección y la marca de verificación siempre se emplea para indicar que el control <xref:System.Windows.Controls.CheckBox> está activado.  
  
 Una plantilla <xref:System.Windows.Controls.ControlTemplate> se crea cuando se desea personalizar la apariencia del control más allá de las posibilidades que ofrece establecer otras propiedades del mismo.  En el ejemplo del control <xref:System.Windows.Controls.CheckBox>, suponga que desea que el contenido de la casilla se encuentre encima del indicador de selección y que aparezca una X para indicar que <xref:System.Windows.Controls.CheckBox> está activado.  Se debe especificar estos cambios en la plantilla <xref:System.Windows.Controls.ControlTemplate> del control <xref:System.Windows.Controls.CheckBox>.  
  
 En la ilustración siguiente se muestra un control <xref:System.Windows.Controls.CheckBox> que usa un objeto <xref:System.Windows.Controls.ControlTemplate> predeterminado.  
  
 ![Casilla con la plantilla de control predeterminada.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Control CheckBox que usa la plantilla de control predeterminada  
  
 En la ilustración siguiente se muestra un control <xref:System.Windows.Controls.CheckBox> que usa un <xref:System.Windows.Controls.ControlTemplate> personalizado para colocar el contenido de <xref:System.Windows.Controls.CheckBox> sobre el indicador de la selección y muestra una X cuando <xref:System.Windows.Controls.CheckBox> está activado.  
  
 ![Casilla con una plantilla de control personalizada.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Control CheckBox que usa una plantilla de control personalizada  
  
 La plantilla <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.CheckBox> de este ejemplo es relativamente compleja, por lo que en este tema se usa un ejemplo más sencillo para crear una plantilla <xref:System.Windows.Controls.ControlTemplate> para un control <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## Cambiar la estructura visual de un control  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un control suele estar compuesto de objetos <xref:System.Windows.FrameworkElement>.  Al crear una plantilla <xref:System.Windows.Controls.ControlTemplate>, se combinan objetos <xref:System.Windows.FrameworkElement> para compilar un único control.  Una plantilla <xref:System.Windows.Controls.ControlTemplate> debe tener un solo objeto <xref:System.Windows.FrameworkElement> como su elemento raíz.  El elemento raíz normalmente contiene otros objetos <xref:System.Windows.FrameworkElement>.  La combinación de objetos constituye la estructura visual del control.  
  
 En el ejemplo siguiente se crea una plantilla <xref:System.Windows.Controls.ControlTemplate> personalizada para el control <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> crea la estructura visual de <xref:System.Windows.Controls.Button>.  En este ejemplo no se modifica la apariencia del botón al situar el puntero del mouse sobre él o al hacer clic en él.  La modificación de la apariencia del botón cuando se encuentra en un estado diferente se explica más adelante en este mismo tema.  
  
 En este ejemplo, la estructura visual consta de las partes siguientes:  
  
-   Un control <xref:System.Windows.Controls.Border> denominado `RootElement` que actúa como objeto <xref:System.Windows.FrameworkElement> raíz de la plantilla.  
  
-   Un control <xref:System.Windows.Controls.Grid> que es un elemento secundario de `RootElement`.  
  
-   Un control <xref:System.Windows.Controls.ContentPresenter> que muestra el contenido del botón.  <xref:System.Windows.Controls.ContentPresenter> permite mostrar cualquier tipo de objeto.  
  
 [!code-xml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### Conservar la funcionalidad de las propiedades de un control mediante TemplateBinding  
 Al crear una nueva plantilla <xref:System.Windows.Controls.ControlTemplate>, puede que desee seguir usando las propiedades públicas para cambiar la apariencia del control.  La extensión de marcado [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) enlaza una propiedad de un elemento que se encuentra en la plantilla <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública definida por el control.  Cuando se usa [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), se permite a las propiedades del control actuar como parámetros de la plantilla.  Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 En el ejemplo siguiente se repite la parte del ejemplo anterior que usa la extensión de marcado [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) para enlazar propiedades de elementos que se encuentran en la plantilla <xref:System.Windows.Controls.ControlTemplate> a las propiedades públicas definidas por el botón.  
  
 [!code-xml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 En este ejemplo, el control <xref:System.Windows.Controls.Grid> tiene su plantilla de propiedad <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> enlazada a <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>.  Puesto que <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> está enlazado a la plantilla, puede crear varios botones que usen la misma plantilla <xref:System.Windows.Controls.ControlTemplate> y establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> en valores diferentes para cada botón.  Si la propiedad <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> no estuviera enlazada a una propiedad de un elemento de la plantilla <xref:System.Windows.Controls.ControlTemplate>, establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> de un botón no afectaría a la apariencia del botón.  
  
 Tenga en cuenta que los nombres de las dos propiedades no tienen por qué ser idénticos.  En el ejemplo anterior, la propiedad <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> del control <xref:System.Windows.Controls.Button> está enlazada a la plantilla a la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName> del control <xref:System.Windows.Controls.ContentPresenter>.  Esto permite colocar el contenido del botón horizontalmente.  <xref:System.Windows.Controls.ContentPresenter> no tiene una propiedad denominada `HorizontalContentAlignment`, pero <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> se puede enlazar a <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName>.  Cuando el enlace la plantilla a una propiedad, asegúrese de que las propiedades de origen y de destino sean del mismo tipo.  
  
 La clase <xref:System.Windows.Controls.Control> define varias propiedades que la plantilla de control debe usar para provocar un efecto sobre el control cuando se establecen.  La forma en que <xref:System.Windows.Controls.ControlTemplate> usa la propiedad depende de la propiedad.  <xref:System.Windows.Controls.ControlTemplate> debe usar la propiedad de una de las maneras siguientes:  
  
-   Un elemento de la plantilla <xref:System.Windows.Controls.ControlTemplate> se enlaza a la propiedad.  
  
-   Un elemento de la plantilla <xref:System.Windows.Controls.ControlTemplate> hereda la propiedad de un elemento <xref:System.Windows.FrameworkElement> primario.  
  
 En la tabla siguiente se enumeran las propiedades visuales heredadas por un control de la clase <xref:System.Windows.Controls.Control>.  También se indica si la plantilla de control predeterminada de un control usa el valor de propiedad heredado o si debe estar enlazada a la plantilla.  
  
|Propiedad.|Método de uso|  
|----------------|-------------------|  
|<xref:System.Windows.Controls.Control.Background%2A>|Enlace a plantilla|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Enlace a plantilla|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Enlace a plantilla|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Herencia de propiedades o enlace a plantilla|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|Herencia de propiedades o enlace a plantilla|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Herencia de propiedades o enlace a plantilla|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Herencia de propiedades o enlace a plantilla|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|Herencia de propiedades o enlace a plantilla|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Enlace a plantilla|  
|<xref:System.Windows.Controls.Control.Padding%2A>|Enlace a plantilla|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Enlace a plantilla|  
  
 En la tabla solo se muestran las propiedades visuales heredadas de la clase <xref:System.Windows.Controls.Control>.  Aparte de las propiedades enumeradas en la tabla anterior, un control puede heredar también las propiedades <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> y <xref:System.Windows.FrameworkElement.Language%2A> del elemento de marco de trabajo primario.  
  
 Además, si <xref:System.Windows.Controls.ContentPresenter> se encuentra en la plantilla <xref:System.Windows.Controls.ControlTemplate> de un control <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter> se enlazará automáticamente a las propiedades <xref:System.Windows.Controls.ContentControl.Content%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  Del mismo modo, un control <xref:System.Windows.Controls.ItemsPresenter> que se encuentre en la plantilla <xref:System.Windows.Controls.ControlTemplate> de un control <xref:System.Windows.Controls.ItemsControl> se enlazará automáticamente a las propiedades <xref:System.Windows.Controls.ItemsPresenter> y <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 En el ejemplo siguiente se crean dos botones que usan la plantilla <xref:System.Windows.Controls.ControlTemplate> definida en el ejemplo anterior.  En el ejemplo se establecen las propiedades <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontSize%2A> de cada botón.  Establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A> surte efecto, porque está enlazada a plantilla en <xref:System.Windows.Controls.ControlTemplate>.  Aunque las propiedades <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.Foreground%2A> no están enlazadas a plantilla, establecerlas surte efecto porque sus valores se heredan.  
  
 [!code-xml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 En el ejemplo anterior se generan unos resultados similares a los mostrados en la siguiente ilustración.  
  
 ![Dos botones, uno azul y otro púrpura.](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP\_ButtonTwo")  
Dos botones con distintos colores de fondo  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## Cambiar la apariencia de un control según su estado  
 La diferencia entre un botón con su apariencia predeterminada y el botón del ejemplo anterior es que el botón predeterminado cambia sutilmente cuando se encuentra en estados diferentes.  Por ejemplo, la apariencia del botón predeterminado cambia cuando está presionado o cuando el puntero del mouse está encima de él.  Si bien la plantilla <xref:System.Windows.Controls.ControlTemplate> no cambia la funcionalidad de un control, sí modifica su comportamiento visual.  Un comportamiento visual describe la apariencia del control cuando se encuentra en un estado determinado.  Para entender la diferencia entre la funcionalidad y el comportamiento visual de un control, tomemos el ejemplo del botón.  La funcionalidad del botón consiste en generar el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> cuando se hace clic en él; en cambio, el comportamiento visual del botón consiste en cambiar su apariencia al señalarlo o presionarlo.  
  
 Para especificar la apariencia de un control cuando se encuentra en un estado determinado se emplean objetos <xref:System.Windows.VisualState>.  Un objeto <xref:System.Windows.VisualState> contiene un objeto <xref:System.Windows.Media.Animation.Storyboard> que cambia la apariencia de los elementos que se encuentran en la plantilla <xref:System.Windows.Controls.ControlTemplate>.  No es necesario escribir código para que esto suceda, ya que la lógica del control cambia de estado mediante <xref:System.Windows.VisualStateManager>.  Cuando el control entra en el estado especificado por la propiedad <xref:System.Windows.VisualState.Name%2A?displayProperty=fullName>, se inicia <xref:System.Windows.Media.Animation.Storyboard>.  Cuando el control sale del estado, <xref:System.Windows.Media.Animation.Storyboard> se detiene.  
  
 En el ejemplo siguiente se muestra un objeto <xref:System.Windows.VisualState> que cambia la apariencia de un control <xref:System.Windows.Controls.Button> cuando el puntero del mouse está encima de él.  <xref:System.Windows.Media.Animation.Storyboard> cambia el color del borde del botón cambiando el color de `BorderBrush`.  Si se fija en el ejemplo de <xref:System.Windows.Controls.ControlTemplate> que se proporciona al principio de este tema, recordará que `BorderBrush` es el nombre del objeto <xref:System.Windows.Media.SolidColorBrush> asignado a la propiedad <xref:System.Windows.Controls.Border.Background%2A> del control <xref:System.Windows.Controls.Border>.  
  
 [!code-xml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 El control es responsable de definir los estados como parte de su contrato de control; esto se explica con detalle en [Personalizar otros controles entendiendo el contrato de control](#customizing_other_controls_by_understanding_the_control_contract) más adelante en este mismo tema.  En la tabla siguiente se enumeran los estados especificados para <xref:System.Windows.Controls.Button>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Pressed|CommonStates|El control está presionado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
  
 <xref:System.Windows.Controls.Button> define dos grupos de estados: el grupo `CommonStates` contiene los estados `Normal`, `MouseOver`, `Pressed` y `Disabled`.  Por su parte, el grupo `FocusStates` contiene los estados `Unfocused` y `Focused`.  Los estados contenidos en el mismo grupo de estados son mutuamente excluyentes.  El control siempre se encuentra exactamente en un estado de cada grupo.  Por ejemplo, un control <xref:System.Windows.Controls.Button> puede tener el foco incluso cuando el puntero del mouse no está encima de él, por lo que un control <xref:System.Windows.Controls.Button> en el estado `Focused` puede estar en cualquiera de los estados `MouseOver`, `Pressed` o `Normal`.  
  
 Los objetos <xref:System.Windows.VisualState> se agregan los objetos <xref:System.Windows.VisualStateGroup>.  Los objetos <xref:System.Windows.VisualStateGroup> se agregan a la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>.  En el ejemplo siguiente se definen los objetos <xref:System.Windows.VisualState> correspondientes a los estados `Normal`, `MouseOver` y `Pressed`, todos ellos pertenecientes al grupo `CommonStates`.  La propiedad <xref:System.Windows.VisualState.Name%2A> de cada <xref:System.Windows.VisualState> coincide con el nombre de la tabla anterior.  El estado `Disabled` y los estados del grupo `FocusStates` se omiten para que el ejemplo resulte breve, pero se incluyen en el ejemplo completo que encontrará al final de este tema.  
  
> [!NOTE]
>  Asegúrese de establecer la propiedad adjunta <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> del <xref:System.Windows.FrameworkElement> raíz de <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 En el ejemplo anterior se generan unos resultados similares a los mostrados en las ilustraciones siguientes.  
  
 ![Botón con una plantilla de control personalizada.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Un botón que usa una plantilla de control personalizada en el estado normal  
  
 ![Botón con un borde rojo.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Un botón que usa una plantilla de control personalizada en el estado de pasar el mouse  
  
 ![El borde es transparente en un botón presionado.](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP\_ButtonPressed")  
Un botón que usa una plantilla de control personalizada en el estado presionado  
  
 Para buscar los estados visuales de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## Especificar el comportamiento de un control cuando efectúa la transición entre dos estados  
 En el ejemplo anterior, la apariencia del botón también cambia cuando el usuario hace clic en él, pero a menos que el botón se presione durante un segundo completo, el usuario no verá el efecto.  De forma predeterminada, la animación tarda un segundo en producirse.  Puesto que es probable que los usuarios hagan clic en el botón y lo suelten en mucho menos tiempo, los comentarios visuales no serán eficientes si se deja <xref:System.Windows.Controls.ControlTemplate> en su estado predeterminado.  
  
 Puede especificar la cantidad de tiempo que tardará una animación en producirse para efectuar una transición fluida de un estado a otro en un control; para ello, agregue objetos <xref:System.Windows.VisualTransition> a la plantilla <xref:System.Windows.Controls.ControlTemplate>.  Al crear un objeto <xref:System.Windows.VisualTransition>, puede especificar uno o varios de los elementos siguientes:  
  
-   El tiempo que tarda en producirse una transición entre estados.  
  
-   Los cambios adicionales en la apariencia del control que se producen en el momento de la transición.  
  
-   A qué estados se aplica el objeto <xref:System.Windows.VisualTransition>.  
  
### Especificar la duración de una transición  
 Se puede especificar cuánto tiempo tarda una transición estableciendo la propiedad <xref:System.Windows.VisualTransition.GeneratedDuration%2A>.  El ejemplo anterior contiene un objeto <xref:System.Windows.VisualState> que especifica que el borde del botón se vuelve transparente al presionarlo, pero la animación tarda demasiado tiempo y no se aprecia cuando el botón se presiona y suelta rápidamente.  Puede usar un objeto <xref:System.Windows.VisualTransition> para especificar la cantidad de tiempo que el control tarda en hacer la transición al estado presionado.  En el ejemplo siguiente se especifica que el control tarda una centésima de segundo en entrar en el estado presionado.  
  
 [!code-xml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### Especificar cambios en la apariencia del control durante una transición  
 <xref:System.Windows.VisualTransition> contiene un objeto <xref:System.Windows.Media.Animation.Storyboard> que se inicia cuando el control hace la transición entre estados.  Por ejemplo, puede especificar que se produzca determinada animación cuando el control realice la transición del estado `MouseOver` al estado `Normal`.  En el ejemplo siguiente se crea un objeto <xref:System.Windows.VisualTransition> que especifica que cuando el usuario mueve el puntero del mouse fuera del botón, su borde cambia a azul, después a amarillo y por último a negro en 1,5 segundos.  
  
 [!code-xml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### Especificar cuándo se aplica un objeto VisualTransition  
 <xref:System.Windows.VisualTransition> se puede restringir para aplicarse solo a ciertos estados o se puede aplicar siempre que el control realice la transición entre estados.  En el ejemplo anterior, <xref:System.Windows.VisualTransition> se aplica cuando el control pasa del estado `MouseOver` al estado `Normal`; en el ejemplo anterior a este, <xref:System.Windows.VisualTransition> se aplica cuando el control entra en el estado `Pressed`.  Para restringir cuándo se aplica un objeto <xref:System.Windows.VisualTransition> hay que establecer las propiedades <xref:System.Windows.VisualTransition.From%2A> y <xref:System.Windows.VisualTransition.To%2A>.  En la tabla siguiente se describen los niveles de restricción, desde el más restrictivo al menos restrictivo.  
  
|Tipo de restricción|Valor de From|Valor de To|  
|-------------------------|-------------------|-----------------|  
|Desde un estado especificado a otro estado especificado|Nombre de un objeto <xref:System.Windows.VisualState>.|Nombre de un objeto <xref:System.Windows.VisualState>.|  
|Desde cualquier estado a un estado especificado|No establecida|Nombre de un objeto <xref:System.Windows.VisualState>.|  
|Desde un estado especificado a cualquier estado|Nombre de un objeto <xref:System.Windows.VisualState>.|No establecida|  
|Desde cualquier estado a cualquier otro estado|No establecida|No establecida|  
  
 Se pueden tener varios objetos <xref:System.Windows.VisualTransition> en un <xref:System.Windows.VisualStateGroup> que haga referencia al mismo estado, pero se usarán en el orden que se especifica en la tabla anterior.  En el ejemplo siguiente hay dos objetos <xref:System.Windows.VisualTransition>.  Cuando el control realiza la transición del estado `Pressed` al estado `MouseOver`, se usa el objeto <xref:System.Windows.VisualTransition> que tiene establecidas las dos propiedades <xref:System.Windows.VisualTransition.From%2A> y <xref:System.Windows.VisualTransition.To%2A>.  Cuando el control realiza la transición de un estado que no es `Pressed` al estado `MouseOver`, se emplea el otro estado.  
  
 [!code-xml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 El objeto <xref:System.Windows.VisualStateGroup> tiene una propiedad <xref:System.Windows.VisualStateGroup.Transitions%2A> que contiene los objetos <xref:System.Windows.VisualTransition> que se aplican a los objetos <xref:System.Windows.VisualState> de <xref:System.Windows.VisualStateGroup>.  Como autor de <xref:System.Windows.Controls.ControlTemplate>, dispone de libertad para incluir cualquier objeto <xref:System.Windows.VisualTransition> que desee.  Sin embargo, si las propiedades <xref:System.Windows.VisualTransition.From%2A> y <xref:System.Windows.VisualTransition.To%2A> se establecen en nombres de estados que no pertenecen a <xref:System.Windows.VisualStateGroup>, el objeto <xref:System.Windows.VisualTransition> se omite.  
  
 En el ejemplo siguiente se muestra el objeto <xref:System.Windows.VisualStateGroup> de `CommonStates`.  En el ejemplo se define un objeto <xref:System.Windows.VisualTransition> para cada una de las transiciones siguientes del botón.  
  
-   Al estado `Pressed`.  
  
-   Al estado `MouseOver`.  
  
-   Del estado `Pressed` al estado `MouseOver`.  
  
-   Del estado `MouseOver` al estado `Normal`.  
  
 [!code-xml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## Personalizar otros controles entendiendo el contrato de control  
 Un control que usa una plantilla <xref:System.Windows.Controls.ControlTemplate> para especificar su estructura visual \(mediante objetos <xref:System.Windows.FrameworkElement>\) y su comportamiento visual \(mediante objetos <xref:System.Windows.VisualState>\) emplea el modelo de control de elementos.  Muchos de los controles incluidos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 usan este modelo.  Los elementos que un autor de plantillas <xref:System.Windows.Controls.ControlTemplate> debe conocer se comunican mediante el contrato de control.  Si se entienden los elementos de un contrato de control, es posible personalizar la apariencia de cualquier control que use el modelo de control de elementos.  
  
 El contrato de un control tiene tres elementos:  
  
-   Los elementos visuales que usa la lógica del control.  
  
-   Los estados del control y el grupo al que pertenece cada estado.  
  
-   Las propiedades públicas que afectan visualmente al control.  
  
### Elementos visuales del contrato de control  
 A veces, la lógica de un control interactúa con un objeto <xref:System.Windows.FrameworkElement> que se encuentra en una plantilla <xref:System.Windows.Controls.ControlTemplate>.  Por ejemplo, el control podría controlar un evento de uno de sus elementos.  Cuando un control espera encontrar un objeto <xref:System.Windows.FrameworkElement> determinado en la plantilla <xref:System.Windows.Controls.ControlTemplate>, debe transmitir esa información al autor de <xref:System.Windows.Controls.ControlTemplate>.  El control usa <xref:System.Windows.TemplatePartAttribute> para transmitir el tipo de elemento que se espera y cuál debe ser el nombre del elemento.  El control <xref:System.Windows.Controls.Button> no tiene elementos del objeto <xref:System.Windows.FrameworkElement> en su contrato de control; sin embargo, otros controles, como <xref:System.Windows.Controls.ComboBox>, sí los tienen.  
  
 En el ejemplo siguiente se muestran los objetos <xref:System.Windows.TemplatePartAttribute> que se especifican en la clase <xref:System.Windows.Controls.ComboBox>.  La lógica del control <xref:System.Windows.Controls.ComboBox> espera encontrar un objeto <xref:System.Windows.Controls.TextBox> denominado `PART_EditableTextBox` y un objeto <xref:System.Windows.Controls.Primitives.Popup> denominado `PART_Popup` en la plantilla <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 En el ejemplo siguiente se muestra una plantilla <xref:System.Windows.Controls.ControlTemplate> simplificada para el control <xref:System.Windows.Controls.ComboBox> que incluye los elementos especificados por los objetos <xref:System.Windows.TemplatePartAttribute> en la clase <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### Estados del contrato de control  
 Los estados de un control también forman parte del contrato de control.  En el ejemplo de creación de una plantilla <xref:System.Windows.Controls.ControlTemplate> para un control <xref:System.Windows.Controls.Button> se muestra cómo especificar la apariencia de <xref:System.Windows.Controls.Button> según sus estados.  Cree un <xref:System.Windows.VisualState> para cada estado especificado y ponga todos los objetos <xref:System.Windows.VisualState> que comparten un <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> en un <xref:System.Windows.VisualStateGroup>, tal y como se describe en [Cambiar la apariencia de un control según su estado](#changing_the_appearance_of_a_control_depending_on_its_state) anteriormente en este tema.  Los controles de otros fabricantes deben especificar los estados mediante <xref:System.Windows.TemplateVisualStateAttribute>, que permite que las herramientas del diseñador, como expression Blend, exponer los estados del control para crear plantillas de control.  
  
 Para buscar el contrato de control de los controles que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### Propiedades del contrato de control  
 Las propiedades públicas que afectan visualmente al control también se incluyen en el contrato de control.  Puede establecer estas propiedades para cambiar la apariencia del control sin crear una nueva plantilla <xref:System.Windows.Controls.ControlTemplate>.  También puede emplear la extensión de marcado [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) para enlazar propiedades de elementos que se encuentran en la plantilla <xref:System.Windows.Controls.ControlTemplate> a propiedades públicas definidas por el control <xref:System.Windows.Controls.Button>.  
  
 En el ejemplo siguiente se muestra el contrato de control del botón.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Al crear una plantilla <xref:System.Windows.Controls.ControlTemplate>, con frecuencia resulta más fácil empezar con una plantilla <xref:System.Windows.Controls.ControlTemplate> existente y modificarla.  Para cambiar una plantilla <xref:System.Windows.Controls.ControlTemplate> existente, puede realizar uno de los procedimientos siguientes:  
  
-   Usar un diseñador, como Expression Blend, que proporciona una interfaz gráfica de usuario para crear plantillas de control.  Para obtener más información, vea [Aplicar estilo a un control que admite plantillas](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Obtener la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada y editarla.  Para buscar las plantillas de control predeterminadas que se incluyen con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Default WPF Themes](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## Ejemplo completo  
 En el ejemplo siguiente se muestra todo el control <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.ControlTemplate> que se describe en este tema.  
  
 [!code-xml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)