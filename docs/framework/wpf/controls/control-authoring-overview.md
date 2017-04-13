---
title: "Informaci&#243;n general sobre la creaci&#243;n de controles | Microsoft Docs"
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
  - "información general sobre la creación de controles"
  - "controles, información general sobre la creación"
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Informaci&#243;n general sobre la creaci&#243;n de controles
La extensibilidad del modelo de control [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] reduce en gran medida la necesidad de crear un nuevo control.  Sin embargo, en ciertos casos es posible que aún necesite crear un control personalizado.  En este tema se explican las características que minimizan la necesidad de crear un control personalizado y los diferentes modelos de creación de controles de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En este tema también se muestra cómo crear un nuevo control.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="when_to_write_a_new_control"></a>   
## Alternativas a la escritura de un nuevo control  
 Históricamente, si se deseaba obtener una experiencia personalizada de un control existente, las posibilidades estaban limitadas a cambiar las propiedades estándar del control, tales como el color de fondo, el ancho del borde y el tamaño de fuente.  Si se deseaba extender la apariencia o comportamiento de un control más allá de estos parámetros predefinidos, necesitaba crear un nuevo control, normalmente heredado de uno existente, e invalidar el método responsable de dibujarlo.  Aunque esto sigue siendo posible, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite personalizar los controles existentes gracias a su modelo de contenido enriquecido, así como estilos, plantillas y desencadenadores.  La lista siguiente proporciona ejemplos de cómo utilizar estas características para crear experiencias personalizadas y coherentes sin tener que crear un nuevo control.  
  
-   **Contenido enriquecido.** Muchos de los controles estándar de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son compatibles con contenido enriquecido.  Por ejemplo, la propiedad de contenido de un control <xref:System.Windows.Controls.Button> es del tipo <xref:System.Object>, de modo que, en teoría, en un control <xref:System.Windows.Controls.Button> se puede mostrar cualquier elemento.  Para que un botón muestre una imagen y texto, puede agregar una imagen y un control <xref:System.Windows.Controls.TextBlock> a <xref:System.Windows.Controls.StackPanel> y asignar <xref:System.Windows.Controls.StackPanel> a la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>.  Debido a que estos controles permiten mostrar elementos visuales de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y datos arbitrarios, se reduce la necesidad de crear un nuevo control o modificar un control existente para permitir una visualización compleja.  Para obtener más información sobre el modelo de contenido de <xref:System.Windows.Controls.Button> y otros modelos de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
-   **Estilos.** Un objeto <xref:System.Windows.Style> es una colección de valores que representan propiedades para un control.  Utilizando estilos, puede crear una representación reutilizable del aspecto y el comportamiento deseados para un control sin necesidad de escribir un nuevo control.  Por ejemplo, suponga que desea que todos los controles <xref:System.Windows.Controls.TextBlock> tengan la fuente Arial de color rojo con un tamaño de fuente de 14.  Puede crear un estilo como un recurso y establecer las propiedades adecuadas correspondientes.  A continuación, todos los controles <xref:System.Windows.Controls.TextBlock> que agregue a la aplicación tendrán la misma apariencia.  
  
-   **Plantillas de datos.** <xref:System.Windows.DataTemplate> permite personalizar cómo se muestran los datos en un control.  Por ejemplo, <xref:System.Windows.DataTemplate> se puede utilizar para especificar cómo se muestran los datos en <xref:System.Windows.Controls.ListBox>.  Se puede ver un ejemplo en [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  Además de personalizar la apariencia de los datos, un objeto <xref:System.Windows.DataTemplate> puede incluir elementos de interfaz de usuario, lo que aporta gran flexibilidad en las interfaces de usuario personalizadas.  Por ejemplo, con <xref:System.Windows.DataTemplate> se puede crear un control <xref:System.Windows.Controls.ComboBox> en el que cada elemento contenga una casilla.  
  
-   **Plantillas de control.** Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizan una <xref:System.Windows.Controls.ControlTemplate> para definir la estructura y apariencia del control, a fin de independizar su apariencia de su funcionalidad. Es posible cambiar drásticamente la apariencia de un control si se redefine su <xref:System.Windows.Controls.ControlTemplate>.  Por ejemplo, supongamos que desea un control semejante a un semáforo.  La interfaz de usuario y la funcionalidad de este control son sencillas.  El control está compuesto de tres círculos y sólo uno de ellos puede estar encendido en un momento dado.  Después de reflexionar, puede que se dé cuenta de que <xref:System.Windows.Controls.RadioButton> proporciona la funcionalidad de permitir la selección de una sola opción a la vez, aunque la apariencia predeterminada de <xref:System.Windows.Controls.RadioButton> no se parece nada a un semáforo.  Dado que <xref:System.Windows.Controls.RadioButton> utiliza una plantilla de control para definir su apariencia, resulta fácil redefinir <xref:System.Windows.Controls.ControlTemplate> para adaptarlo a los requisitos del control y utilizar los botones de radio para crear el semáforo.  
  
    > [!NOTE]
    >  Aunque <xref:System.Windows.Controls.RadioButton> puede utilizar un objeto <xref:System.Windows.DataTemplate>, en este ejemplo no basta con <xref:System.Windows.DataTemplate>.  <xref:System.Windows.DataTemplate> define la apariencia del contenido de un control.  En el caso de un botón de radio \(<xref:System.Windows.Controls.RadioButton>\), su contenido es aquello que aparece a la derecha del círculo, que indica si <xref:System.Windows.Controls.RadioButton> está seleccionado.  En el ejemplo del semáforo, el botón de radio tiene que ser sólo un círculo capaz de "encenderse". Dado que el requisito de apariencia del semáforo es tan distinto de la apariencia predeterminada de <xref:System.Windows.Controls.RadioButton>, es necesario redefinir <xref:System.Windows.Controls.ControlTemplate>.  En general, <xref:System.Windows.DataTemplate> se utiliza para definir el contenido \(o los datos\) de un control y <xref:System.Windows.Controls.ControlTemplate> se utiliza para definir la estructura del control.  
  
-   **Desencadenadores.** <xref:System.Windows.Trigger> permite cambiar dinámicamente la apariencia y el comportamiento de un control sin crear uno nuevo.  Por ejemplo, suponga que tiene varios controles <xref:System.Windows.Controls.ListBox> en una aplicación y desea que todos los elementos de <xref:System.Windows.Controls.ListBox> se muestren en negrita y en rojo cuando están seleccionados.  Su primer impulso podría ser crear una clase que herede de <xref:System.Windows.Controls.ListBox> e invalidar el método <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> para cambiar la apariencia del elemento seleccionado; sin embargo, sería más apropiado agregar a un estilo de <xref:System.Windows.Controls.ListBoxItem> un desencadenador que cambie la apariencia del elemento seleccionado.  Un desencadenador permite cambiar los valores de las propiedades o realizar acciones basadas en el valor de una propiedad.  Un objeto <xref:System.Windows.EventTrigger> permite realizar acciones cuando se produce un evento.  
  
 Para obtener más información sobre los estilos, plantillas y desencadenadores, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 En general, si el control tiene la misma funcionalidad que un control existente, pero desea modificar su apariencia, antes de nada debe estudiar si puede utilizar cualquiera de los métodos descritos en esta sección a fin de cambiar la apariencia del control existente.  
  
<a name="models_for_control_authoring"></a>   
## Modelos para la creación de controles  
 El modelo de contenido enriquecido, los estilos, las plantillas y los desencadenadores minimizan la necesidad de crear controles nuevos.  Sin embargo, si se ve obligado a crear uno nuevo, es importante comprender los distintos modelos de creación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona tres modelos generales para crear controles, cada uno de los cuales ofrece un conjunto diferente de características y un nivel de flexibilidad distinto.  Las clases base de los tres modelos son <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control> y <xref:System.Windows.FrameworkElement>.  
  
### Derivar de UserControl  
 La manera más sencilla de crear un control en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es derivar de <xref:System.Windows.Controls.UserControl>.  Cuando se compila un control que hereda de <xref:System.Windows.Controls.UserControl>, se agregan los componentes existentes a <xref:System.Windows.Controls.UserControl>, se les da un nombre y se hace referencia los controladores de eventos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  A continuación, puede hacer referencia a los elementos con nombre y definir los controladores de eventos en el código.  Este modelo de desarrollo es muy similar al utilizado para el desarrollo de aplicaciones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Si está compilado correctamente, un control <xref:System.Windows.Controls.UserControl> puede aprovechar las ventajas del contenido enriquecido, los estilos y los desencadenadores.  Sin embargo, si el control hereda de <xref:System.Windows.Controls.UserControl>, las personas que lo utilicen no podrán usar <xref:System.Windows.DataTemplate> o <xref:System.Windows.Controls.ControlTemplate> para personalizar su apariencia.  Es necesario derivar de la clase <xref:System.Windows.Controls.Control> o de una de sus clases derivadas \(excepto <xref:System.Windows.Controls.UserControl>\) para crear un control personalizado que admita plantillas.  
  
#### Ventajas de derivar de UserControl  
 Considere la posibilidad de derivar de <xref:System.Windows.Controls.UserControl> si se cumplen todas las condiciones siguientes:  
  
-   Desea compilar un control de forma similar a como se compila una aplicación.  
  
-   El control está compuesto solamente de componentes existentes.  
  
-   No necesita permitir una personalización compleja.  
  
### Derivar de Control  
 Derivar de la clase <xref:System.Windows.Controls.Control> es el modelo utilizado por la mayoría de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes.  Cuando se crea un control que hereda de la clase <xref:System.Windows.Controls.Control>, su apariencia se define mediante plantillas.  Al hacerlo, se independiza la lógica de funcionamiento de la representación visual.  También se puede garantizar la independencia entre la interfaz de usuario y la lógica si se usan comandos y enlaces en lugar de eventos, y se evita en lo posible hacer referencia a los elementos de <xref:System.Windows.Controls.ControlTemplate>. Si la interfaz de usuario y la lógica del control están debidamente desconectadas, un usuario del control podrá redefinir la <xref:System.Windows.Controls.ControlTemplate> del control para personalizar su apariencia. Aunque compilar un <xref:System.Windows.Controls.Control> personalizado no es tan sencillo como compilar un <xref:System.Windows.Controls.UserControl>, un <xref:System.Windows.Controls.Control> personalizado proporciona mayor flexibilidad.  
  
#### Ventajas de derivar de Control  
 Considere la posibilidad de derivar de <xref:System.Windows.Controls.Control> en lugar de utilizar la clase <xref:System.Windows.Controls.UserControl> si se cumple cualquiera de las condiciones siguientes:  
  
-   Desea que la apariencia del control sea personalizable a través del objeto <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Desea que el control admita temas diferentes.  
  
### Derivar de FrameworkElement  
 Los controles derivados de <xref:System.Windows.Controls.UserControl> o <xref:System.Windows.Controls.Control> se basan en la composición de elementos existentes.  Para muchos escenarios, ésta es una solución aceptable, porque cualquier objeto que hereda de <xref:System.Windows.FrameworkElement> puede estar en un objeto <xref:System.Windows.Controls.ControlTemplate>.  Sin embargo, en ocasiones la apariencia de un control requiere una funcionalidad que va más allá de la simple composición de elementos.  Para estos escenarios, basar un componente en <xref:System.Windows.FrameworkElement> es la opción correcta.  
  
 Hay dos métodos estándar para generar componentes basados en <xref:System.Windows.FrameworkElement>: la representación directa y la composición de elementos personalizada.  La representación directa implica invalidar el método <xref:System.Windows.UIElement.OnRender%2A> de <xref:System.Windows.FrameworkElement> y proporcionar operaciones <xref:System.Windows.Media.DrawingContext> que definan explícitamente el aspecto visual del componente.  Éste es el método utilizado por <xref:System.Windows.Controls.Image> y <xref:System.Windows.Controls.Border>.  La composición de elementos personalizada implica utilizar objetos de tipo <xref:System.Windows.Media.Visual> para crear la apariencia del componente.  Para obtener un ejemplo, vea [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  <xref:System.Windows.Controls.Primitives.Track> es un ejemplo de un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que usa la composición de elementos personalizada.  También es posible mezclar la representación directa y la composición de elementos personalizada en el mismo control.  
  
#### Ventajas de derivar de FrameworkElement  
 Considere la posibilidad de derivar de <xref:System.Windows.FrameworkElement> si se cumple cualquiera de las condiciones siguientes:  
  
-   Desea tener un control preciso sobre la apariencia del control más allá de lo que proporciona la simple composición de elementos.  
  
-   Desea definir el aspecto del control definiendo una lógica de representación propia.  
  
-   Desea componer elementos existentes de maneras nuevas que excedan lo posible con <xref:System.Windows.Controls.UserControl> y <xref:System.Windows.Controls.Control>.  
  
<a name="control_authoring_basics"></a>   
## Fundamentos de creación de controles  
 Como se comentó anteriormente, una de las características más eficaces de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es la posibilidad de no tener que limitarse a establecer las propiedades básicas de un control para modificar su apariencia y comportamiento, sin estar obligado a crear un control personalizado. Las características de estilo, enlace de datos y desencadenadores son posibles gracias al sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y al sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En las próximas secciones se describen algunos procedimientos que debe seguir, independientemente del modelo que emplee para crear el control personalizado, de modo que los usuarios de su control personalizado puedan usar estas características como lo harían para un control incluido con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Utilizar propiedades de dependencia  
 Cuando una propiedad es de dependencia, es posible realizar las acciones siguientes:  
  
-   Establecer la propiedad en un estilo.  
  
-   Enlazar la propiedad a un origen de datos.  
  
-   Utilizar un recurso dinámico como valor de la propiedad.  
  
-   Animar la propiedad.  
  
 Si desea que una propiedad del control admita cualquiera de estas funcionalidades, debe implementarla como propiedad de dependencia.  En el ejemplo siguiente se define una propiedad de dependencia denominada `Value` mediante este procedimiento:  
  
-   Defina un identificador de <xref:System.Windows.DependencyProperty> denominado `ValueProperty` como un campo `public` `static` `readonly`.  
  
-   Registre el nombre de la propiedad en el sistema de propiedades, mediante una llamada a <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=fullName>, para especificar lo siguiente:  
  
    -   El nombre de la propiedad.  
  
    -   Tipo de la propiedad.  
  
    -   El tipo que posee la propiedad.  
  
    -   Los metadatos de la propiedad.  Los metadatos contienen el valor predeterminado de la propiedad, <xref:System.Windows.CoerceValueCallback> y <xref:System.Windows.PropertyChangedCallback>.  
  
-   Defina una propiedad de "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] denominada `Value` \(que es el mismo nombre que se emplea para registrar la propiedad de dependencia\) mediante la implementación de los descriptores de acceso `get` y `set` de la propiedad.  Observe que los descriptores de acceso `get` y `set` llaman únicamente a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, respectivamente.  Se recomienda que los descriptores de acceso de las propiedades de dependencia no contengan lógica adicional, porque los clientes y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden omitir dichos descriptores y llamar a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> directamente.  Por ejemplo, cuando una propiedad está enlazada a un origen de datos, no se llama al descriptor de acceso `set` de la propiedad.  En lugar de agregar lógica adicional a los descriptores de acceso get y set, utilice los delegados <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback> y <xref:System.Windows.CoerceValueCallback> para responder a los cambios del valor o comprobar si el valor ha cambiado.  Para obtener más información acerca de estas devoluciones de llamada, vea [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Defina un método para el delegado <xref:System.Windows.CoerceValueCallback> denominado `CoerceValue`.  `CoerceValue` garantiza que `Value` es mayor o igual que `MinValue` y menor o igual que `MaxValue`.  
  
-   Defina un método para el delegado <xref:System.Windows.PropertyChangedCallback> denominado `OnValueChanged`.  `OnValueChanged` crea un objeto <xref:System.Windows.RoutedPropertyChangedEventArgs%601> y se prepara para generar el evento enrutado `ValueChanged`.  Los eventos enrutados se abordan en la sección siguiente.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 Para obtener más información, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### Utilizar eventos enrutados  
 Al igual que las [propiedades de dependencia](GTMT) extienden la noción de propiedades [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con funciones adicionales, los [eventos enrutados](GTMT) extienden la noción de eventos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] estándar.  Al crear un nuevo control de[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], también es conveniente implementar el evento como enrutado, porque un evento enrutado admite el comportamiento siguiente:  
  
-   Los eventos se pueden controlar en un elemento primario de varios controles.  Si un evento es de propagación, puede suscribirse a él un elemento primario único del árbol de elementos.  A continuación, los autores de la aplicación pueden utilizar un mismo controlador para responder al evento de varios controles.  Por ejemplo, si el control forma parte de cada uno de los elementos de un control <xref:System.Windows.Controls.ListBox> \(por estar incluido en <xref:System.Windows.DataTemplate>\), el programador de la aplicación puede definir el controlador del evento del control en <xref:System.Windows.Controls.ListBox>.  Cada vez que se produzca el evento en cualquiera de los controles, se llamará al controlador.  
  
-   Los eventos enrutados se pueden utilizar en <xref:System.Windows.EventSetter>, lo que permite a los programadores de aplicaciones especificar el controlador de un evento en un estilo.  
  
-   Los eventos enrutados se pueden utilizar en <xref:System.Windows.EventTrigger>, lo que resulta útil para animar propiedades mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 En el ejemplo siguiente se define un evento enrutado mediante este procedimiento:  
  
-   Defina un identificador de <xref:System.Windows.RoutedEvent> denominado `ValueChangedEvent` como un campo `public` `static` `readonly`.  
  
-   Registre el evento enrutado mediante una llamada al método <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=fullName>.  En el ejemplo se especifica la información siguiente al llamar a <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>:  
  
    -   El nombre del evento es `ValueChanged`.  
  
    -   La estrategia del enrutamiento es <xref:System.Windows.RoutingStrategy>. Esto significa que primero se llama a un controlador de eventos en el origen \(el objeto que provoca el evento\) y, a continuación, se llama sucesivamente a los controladores de eventos en los elementos primarios del origen, empezando por el controlador de eventos del elemento primario más cercano.  
  
    -   El tipo del controlador de eventos es <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, construido con un tipo <xref:System.Decimal>.  
  
    -   El tipo propietario del evento es `NumericUpDown`.  
  
-   Declare un evento público denominado `ValueChanged` e incluya declaraciones de descriptores de acceso del evento.  En el ejemplo se llama a <xref:System.Windows.UIElement.AddHandler%2A> en la declaración del descriptor de acceso `add` y a <xref:System.Windows.UIElement.RemoveHandler%2A> en la declaración del descriptor de acceso `remove` a fin de utilizar los servicios de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Cree un método virtual protegido denominado `OnValueChanged` que genere el evento `ValueChanged`.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 Para obtener más información, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md) y [Crear un evento enrutado personalizado](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md).  
  
### Utilizar el enlace  
 Para desacoplar la interfaz de usuario del control de su lógica, puede ser conveniente utilizar el enlace de datos.  Esto resulta particularmente importante si la apariencia del control se define mediante <xref:System.Windows.Controls.ControlTemplate>.  Al utilizar el enlace de datos, puede que consiga eliminar la necesidad de hacer referencia a partes concretas de la interfaz de usuario desde el código.  Es conveniente evitar hacer referencia a elementos incluidos en <xref:System.Windows.Controls.ControlTemplate>, ya que cuando el código hace referencia a elementos incluidos en <xref:System.Windows.Controls.ControlTemplate> y se modifica <xref:System.Windows.Controls.ControlTemplate>, el elemento al que se hace referencia debe incluirse en el nuevo objeto <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se actualiza el control <xref:System.Windows.Controls.TextBlock> del control `NumericUpDown`, para ello se le asigna un nombre y se hace referencia al cuadro de texto por su nombre en el código.  
  
 [!code-xml[UserControlNumericUpDownSimple#UIRefMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 En el ejemplo siguiente se utiliza el enlace para lograr lo mismo.  
  
 [!code-xml[UserControlNumericUpDown#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 Para obtener más información sobre el enlace de datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
### Diseñar para diseñadores  
 Para recibir soporte técnico para controles personalizados de WPF en [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] \(por ejemplo, la edición de propiedades con la ventana Propiedades\), siga estas instrucciones.  Para obtener más información sobre la programación para [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], vea [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26).  
  
#### Propiedades de dependencia  
 Es importante implementar los descriptores de acceso [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` y `set` como se describió anteriormente en "Utilizar propiedades de dependencia". Los diseñadores pueden utilizar el contenedor para detectar la presencia de una propiedad de dependencia, pero no se les exige, al igual que a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y a los clientes del control, llamar a los descriptores de acceso al obtener o establecer la propiedad.  
  
#### Propiedades adjuntas  
 Para implementar propiedades adjuntas en controles personalizados, es recomendable que utilice las siguientes instrucciones:  
  
-   Consideremos una clase `public` `static` `readonly` <xref:System.Windows.DependencyProperty> con el formato *NombreDePropiedad*`Property` creada mediante el método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>.  El nombre de propiedad que se pasa a <xref:System.Windows.DependencyProperty.RegisterAttached%2A> debe coincidir con *NombreDePropiedad*.  
  
-   Implemente un par de métodos `public``static` CLR denominados `Set`*NombreDePropiedad* y `Get`*NombreDePropiedad*.  Ambos métodos deben aceptar una clase derivada de <xref:System.Windows.DependencyProperty> como su primer argumento.  El método `Set`*NombreDePropiedad* también acepta un argumento cuyo tipo coincida con el tipo de datos registrado para la propiedad.  El método `Get`*método NombreDePropiedad* debe devolver un valor del mismo tipo.  Si falta el método `Set`*NombreDePropiedad*, la propiedad se marca como de sólo lectura.  
  
-   `Set` *NombreDePropiedad* y `Get`*NombreDePropiedad* deben enrutar directamente a los métodos <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> del objeto de dependencia de destino, respectivamente.  Los diseñadores pueden tener acceso a la propiedad adjunta mediante una llamada a través del contenedor de método o una llamada directa al objeto de dependencia de destino.  
  
 Para obtener más información sobre las propiedades adjuntas, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
### Definir y usar recursos compartidos  
 Puede incluir el control en el mismo ensamblado que la aplicación o bien empaquetarlo en un ensamblado independiente que se pueda utilizar en varias aplicaciones.  En general, la información analizada en este tema es aplicable independientemente del método que se utilice.  Sin embargo, es necesario destacar una diferencia.  Al incluir un control en el mismo ensamblado que una aplicación, puede agregar recursos globales al archivo app.xaml libremente.  Sin embargo, un ensamblado que solo contiene controles no tiene asociado ningún objeto <xref:System.Windows.Application>, por lo que no hay disponible ningún archivo App.xaml.  
  
 Cuando una aplicación busca un recurso, la búsqueda se realiza en tres niveles en el orden que se indica a continuación:  
  
1.  Nivel de elemento.  
  
     El sistema empieza por el elemento que hace referencia al recurso y, a continuación, busca en los recursos del elemento primario lógico y así sucesivamente hasta que se alcanza el elemento raíz.  
  
2.  Nivel de aplicación.  
  
     Recursos definidos por el objeto <xref:System.Windows.Application>.  
  
3.  Nivel de tema.  
  
     Los diccionarios del nivel de tema se almacenan en una subcarpeta denominada Temas.  Los archivos de la carpeta Temas corresponden a los temas.  Por ejemplo, puede tener Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc.  También puede tener un archivo denominado generic.xaml.  Cuando el sistema busca un recurso en el nivel de temas, primero busca en el archivo específico del tema y, después, en generic.xaml.  
  
 Cuando el control se encuentra en un ensamblado independiente de la aplicación, debe colocar los recursos globales en el nivel de elemento o el nivel de tema.  Ambos métodos tienen sus ventajas.  
  
#### Definir recursos en el nivel de elemento  
 Para definir recursos compartidos en el nivel de elemento, cree un diccionario de recursos personalizado y combínelo con el diccionario de recursos del control.  Cuando usa este método, puede asignar al archivo de recursos el nombre que desee e incluir dicho archivo en la misma carpeta que los controles.  Los recursos del nivel de elemento también pueden utilizar cadenas simples como claves.  En el ejemplo siguiente se crea un archivo de recursos de <xref:System.Windows.Media.LinearGradientBrush> denominado Dictionary1.xaml.  
  
 [!code-xml[SharedResources#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 Una vez definido el diccionario, deberá combinarlo con el diccionario de recursos del control.  Para ello, use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o el código.  
  
 En el ejemplo siguiente se combina un diccionario de recursos mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[SharedResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 El inconveniente de este enfoque es que se crea un objeto <xref:System.Windows.ResourceDictionary> cada vez que se hace referencia a él.  Por ejemplo, si tiene 10 controles personalizados en la biblioteca y se combinan los diccionarios de recursos compartidos de cada control mediante XAML, se crean 10 objetos <xref:System.Windows.ResourceDictionary> idénticos.  Para evitarlo, cree una clase estática que combine los recursos del código y devuelva el elemento <xref:System.Windows.ResourceDictionary> resultante.  
  
 En el ejemplo siguiente se crea una clase que devuelve un elemento <xref:System.Windows.ResourceDictionary> compartido.  
  
 [!code-csharp[SharedResources#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 En el ejemplo siguiente se combina el recurso compartido con los recursos de un control personalizado en el constructor del control antes de llamar a `InitilizeComponent`.  Dado que `SharedDictionaryManager.SharedDictionary` es una propiedad estática, <xref:System.Windows.ResourceDictionary> sólo se crea una vez.  Dado que el diccionario de recursos se combinó antes de llamar a `InitializeComponent`, los recursos están disponibles para el control en su archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[SharedResources#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### Definir recursos en el nivel de tema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite crear recursos para distintos temas de Windows.  Como autor del control, puede definir un recurso para un tema concreto con el fin de cambiar la apariencia del control en función del tema que se emplee.  Por ejemplo, la apariencia de un elemento <xref:System.Windows.Controls.Button> en el tema de Windows clásico \(el tema predeterminado de Windows 2000\) es distinta de la de un elemento <xref:System.Windows.Controls.Button> en el tema Luna de Windows \(el tema predeterminado de Windows XP\) porque <xref:System.Windows.Controls.Button> usa un elemento <xref:System.Windows.Controls.ControlTemplate> distinto para cada tema.  
  
 Los recursos específicos de un tema se mantienen en un diccionario de recursos con un nombre de archivo concreto.  Estos archivos deben estar en una carpeta denominada `Temas`, que es una subcarpeta de la carpeta que contiene el control.  En la tabla siguiente se enumeran los archivos de diccionario de recursos y el tema asociado a cada archivo:  
  
|Nombre del archivo de diccionario de recursos|Tema de Windows|  
|---------------------------------------------------|---------------------|  
|`Classic.xaml`|Apariencia clásica de Windows 9x\/2000 en Windows XP|  
|`Luna.NormalColor.xaml`|Tema azul predeterminado en Windows XP|  
|`Luna.Homestead.xaml`|Tema verde olivo en Windows XP|  
|`Luna.Metallic.xaml`|Tema plateado en Windows XP|  
|`Royale.NormalColor.xaml`|Tema predeterminado en Windows XP Media Center Edition|  
|`Aero.NormalColor.xaml`|Tema predeterminado en Windows Vista|  
  
 No es necesario definir un recurso para cada tema.  Si no se ha definido un recurso para un tema concreto, el control comprueba `Classic.xaml` para el recurso.  Si no se ha definido el recurso en el archivo correspondiente al tema actual o en `Classic.xaml`, el control utiliza el recurso genérico, que está en un archivo de diccionario de recursos denominado `generic.xaml`.  El archivo `generic.xaml` se encuentra en la misma carpeta que los archivos de diccionario de recursos específicos de un tema.  Aunque `generic.xaml` no corresponde a un tema concreto de Windows, no deja de ser un diccionario del nivel de tema.  
  
 [NumericUpDown Custom Control with Theme and UI Automation Support Sample](http://go.microsoft.com/fwlink/?LinkID=160025) contiene dos diccionarios de recursos para el control `NumericUpDown`: uno está en generic.xaml y el otro en Luna.NormalColor.xaml.  Puede ejecutar la aplicación y cambiar entre el tema plateado de Windows XP y otro tema a fin de ver la diferencia entre las dos plantillas de control.  \(Si está ejecutandoWindows Vista, puede cambiar el nombre de Luna.NormalColor.xaml a Aero.NormalColor.xaml y cambiar entre dos temas, como el de Windows clásico y el tema predeterminado de Windows Vista.\)  
  
 Al colocar un elemento <xref:System.Windows.Controls.ControlTemplate> en cualquiera de los archivos de diccionario de recursos específicos de un tema, debe crear un constructor estático para el control y llamar al método <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> en <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### Definir y hacer referencia a claves para los recursos de tema  
 Al definir un recurso en el nivel de elemento, puede asignar una cadena como clave de éste y obtener acceso al recurso a través de la cadena.  Al definir un recurso en el nivel de tema, debe utilizar un elemento <xref:System.Windows.ComponentResourceKey> como clave.  En el ejemplo siguiente se define un recurso en generic.xaml.  
  
  
  
 En el ejemplo siguiente se hace referencia al recurso mediante la especificación de <xref:System.Windows.ComponentResourceKey> como clave.  
  
  
  
##### Especificar la ubicación de los recursos de tema  
 Para buscar los recursos de un control, la aplicación host debe saber que el ensamblado contiene recursos específicos del control.  Para ello, agregue <xref:System.Windows.ThemeInfoAttribute> al ensamblado que contiene el control.  <xref:System.Windows.ThemeInfoAttribute> tiene una propiedad <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> que especifica la ubicación de los recursos genéricos y una propiedad <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> que especifica la ubicación de los recursos específicos de tema.  
  
 En el ejemplo siguiente se establecen las propiedades <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> y <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> en <xref:System.Windows.ResourceDictionaryLocation>, para especificar que los recursos genéricos y específicos de tema están en el mismo ensamblado que el control.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## Vea también  
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)