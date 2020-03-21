---
title: Información general sobre la creación de controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: d5dd2d962c554b860fb6f68110945d56c4ee03ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401032"
---
# <a name="control-authoring-overview"></a>Información general sobre la creación de controles

La extensibilidad del modelo de control [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] reduce enormemente la necesidad de crear un nuevo control. Sin embargo, en ciertos casos, puede que necesite crear un control personalizado. En este tema se describen las características que reducen la necesidad de crear un control personalizado y los diferentes modelos de creación de controles en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En este tema también se muestra cómo crear un nuevo control.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativas a la escritura de un nuevo control

Históricamente, si quería obtener una experiencia personalizada con un control existente, estaba limitado a cambiar las propiedades estándar del control, como el color de fondo, el ancho del borde y el tamaño de la fuente. Si se deseara extender la apariencia o el comportamiento de un control más allá de estos parámetros predefinidos, necesitaría crear un nuevo control; para ello, lo que haría es heredarlo de un control existente e invalidar el método responsable de dibujar el control.  Aunque esto sigue siendo una opción, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite personalizar los controles existentes mediante su modelo de contenido enriquecido, sus estilos, plantillas y desencadenadores. En la lista siguiente se proporcionan ejemplos de cómo se pueden usar estas características para crear experiencias personalizadas y coherentes sin tener que crear un nuevo control.

- **Contenido enriquecido.** Muchos de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estándar admiten contenido enriquecido. Por ejemplo, la propiedad <xref:System.Windows.Controls.Button> content <xref:System.Object>de a es de tipo , <xref:System.Windows.Controls.Button>por lo que teóricamente cualquier cosa se puede mostrar en un archivo .  Para que un botón muestre una imagen y <xref:System.Windows.Controls.TextBlock> un <xref:System.Windows.Controls.StackPanel> texto, <xref:System.Windows.Controls.StackPanel> puede <xref:System.Windows.Controls.ContentControl.Content%2A> agregar una imagen y una a y asignarla a la propiedad. Dado que los controles pueden mostrar elementos visuales [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y datos arbitrarios, no es tan necesario crear un nuevo control o modificar un control existente para admitir una visualización compleja. Para obtener más información <xref:System.Windows.Controls.Button> sobre el modelo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]de contenido y otros modelos de contenido en , vea [WPF Content Model](wpf-content-model.md).

- **Estilos.** A <xref:System.Windows.Style> es una colección de valores que representan propiedades para un control. Mediante el uso de estilos, puede crear una representación reutilizable de la apariencia y el comportamiento deseados de un control sin necesidad de escribir un nuevo control. Por ejemplo, supongamos que <xref:System.Windows.Controls.TextBlock> desea que todos los controles tengan una fuente Arial roja con un tamaño de fuente de 14. Puede crear un estilo como un recurso y establecer las propiedades adecuadas según corresponda. A <xref:System.Windows.Controls.TextBlock> continuación, cada uno de los que agregue a la aplicación tendrá la misma apariencia.

- **Plantillas de datos.** A <xref:System.Windows.DataTemplate> le permite personalizar cómo se muestran los datos en un control. Por ejemplo, <xref:System.Windows.DataTemplate> se puede utilizar a para especificar <xref:System.Windows.Controls.ListBox>cómo se muestran los datos en un archivo .  Para ver un ejemplo de esto, consulte [Data Templating Overview](../data/data-templating-overview.md) (Introducción a las plantillas de datos).  Además de personalizar la <xref:System.Windows.DataTemplate> apariencia de los datos, puede incluir elementos de interfaz de usuario, lo que proporciona mucha flexibilidad en las configuraciones de usuario personalizadas.  Por ejemplo, mediante <xref:System.Windows.DataTemplate>un , <xref:System.Windows.Controls.ComboBox> puede crear un , en el que cada elemento contiene una casilla de verificación.

- **Plantillas de control.** Muchos controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en <xref:System.Windows.Controls.ControlTemplate> uso a para definir la estructura y apariencia del control, que separa la apariencia de un control de la funcionalidad del control. Puede cambiar drásticamente la apariencia de un control <xref:System.Windows.Controls.ControlTemplate>redefiniendo su archivo .  Por ejemplo, supongamos que desea un control que se parezca a un semáforo. Este control tiene una interfaz de usuario y una funcionalidad sencillas.  El control son tres círculos, y solo uno se puede iluminar cada vez. Después de un poco <xref:System.Windows.Controls.RadioButton> de reflexión, es posible que se dé cuenta de <xref:System.Windows.Controls.RadioButton> que una ofrece la funcionalidad de uno solo que se selecciona a la vez, pero la apariencia predeterminada de la no se parece en nada a las luces en un semáforo.  Dado <xref:System.Windows.Controls.RadioButton> que utiliza una plantilla de control para definir <xref:System.Windows.Controls.ControlTemplate> su apariencia, es fácil redefinir el para ajustarse a los requisitos del control y utilizar botones de opción para hacer el semáforo.

  > [!NOTE]
  > Aunque <xref:System.Windows.Controls.RadioButton> a puede <xref:System.Windows.DataTemplate>utilizar <xref:System.Windows.DataTemplate> un , a no es suficiente en este ejemplo.  Define <xref:System.Windows.DataTemplate> la apariencia del contenido de un control. En el caso <xref:System.Windows.Controls.RadioButton>de un , el contenido es lo que <xref:System.Windows.Controls.RadioButton> aparece a la derecha del círculo que indica si está seleccionado.  En el ejemplo del semáforo, el botón de selección debe ser un círculo que pueda "encenderse". Dado que el requisito de apariencia para el semáforo <xref:System.Windows.Controls.RadioButton>es tan diferente de <xref:System.Windows.Controls.ControlTemplate>la apariencia predeterminada de la , es necesario redefinir el archivo .  En general, <xref:System.Windows.DataTemplate> a se utiliza para definir el contenido (o datos) de un control y <xref:System.Windows.Controls.ControlTemplate> a se utiliza para definir cómo se estructura un control.

- **desencadenantes.** A <xref:System.Windows.Trigger> le permite cambiar dinámicamente la apariencia y el comportamiento de un control sin crear un nuevo control. Por ejemplo, supongamos <xref:System.Windows.Controls.ListBox> que tiene varios controles en <xref:System.Windows.Controls.ListBox> la aplicación y desea que los elementos de cada uno estén en negrita y rojo cuando se seleccionan. El primer instinto podría ser crear una <xref:System.Windows.Controls.ListBox> clase <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> que herede y reemplace el método para cambiar la apariencia del elemento <xref:System.Windows.Controls.ListBoxItem> seleccionado, pero un mejor enfoque es agregar un desencadenador a un estilo de un que cambia la apariencia del elemento seleccionado. Un desencadenador permite cambiar los valores de propiedad o realizar acciones según el valor de una propiedad. Un <xref:System.Windows.EventTrigger> le permite realizar acciones cuando se produce un evento.

Para más información sobre los estilos, las plantillas y los desencadenadores, consulte [Aplicar estilos y plantillas](styling-and-templating.md).

En general, si el control refleja la funcionalidad de un control existente, pero quiere que el control tenga un aspecto diferente, primero debe considerar si puede usar cualquiera de los métodos descritos en esta sección para cambiar la apariencia del control existente.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelos para crear controles

El modelo de contenido enriquecido, los estilos, las plantillas y los desencadenadores reducen la necesidad de crear un nuevo control. Sin embargo, si necesita crear un nuevo control, es importante comprender los diferentes modelos de creación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona tres modelos generales para la creación de un control, cada uno de los cuales proporciona un conjunto de características y un nivel de flexibilidad diferentes. Las clases base para <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control>los <xref:System.Windows.FrameworkElement>tres modelos son , , y .

### <a name="deriving-from-usercontrol"></a>Derivación de UserControl

La forma más sencilla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de crear <xref:System.Windows.Controls.UserControl>un control en es derivar de . Cuando se crea un control <xref:System.Windows.Controls.UserControl>que hereda de <xref:System.Windows.Controls.UserControl>, se agregan componentes existentes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]a los controladores de eventos , nombre los componentes y referencia en . Luego puede hacer referencia a los elementos con nombre y definir los controladores de eventos en el código. Este modelo de desarrollo es muy similar al modelo utilizado para el desarrollo de aplicaciones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Si se crea <xref:System.Windows.Controls.UserControl> correctamente, a puede aprovechar las ventajas de contenido enriquecido, estilos y desencadenadores. Sin embargo, si <xref:System.Windows.Controls.UserControl>el control hereda de , las <xref:System.Windows.DataTemplate> personas <xref:System.Windows.Controls.ControlTemplate> que usan el control no podrán usar a o personalizar su apariencia.  Es necesario derivar de <xref:System.Windows.Controls.Control> la clase o de una <xref:System.Windows.Controls.UserControl>de sus clases derivadas (distintas de ) para crear un control personalizado que admita plantillas.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Ventajas de derivar de UserControl

Considere la <xref:System.Windows.Controls.UserControl> posibilidad de derivar de si se aplican todas las condiciones siguientes:

- Desea crear el control de forma similar a cómo crea una aplicación.

- El control solo consta de componentes existentes.

- No se necesita personalización compleja.

### <a name="deriving-from-control"></a>Derivación de Control

Derivado de <xref:System.Windows.Controls.Control> la clase es el modelo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizado por la mayoría de los controles existentes. Cuando se crea un control <xref:System.Windows.Controls.Control> que hereda de la clase, se define su apariencia mediante plantillas. Al hacerlo, se separa la lógica de funcionamiento de la representación visual. También puede garantizar el desacoplamiento de la interfaz de usuario y la lógica <xref:System.Windows.Controls.ControlTemplate> mediante comandos y enlaces en lugar de eventos y evitar hacer referencia a elementos en el siempre que sea posible.  Si la interfaz de usuario y la lógica del control se desacoplan correctamente, un usuario del control puede redefinir el control <xref:System.Windows.Controls.ControlTemplate> para personalizar su apariencia. Aunque crear <xref:System.Windows.Controls.Control> una costumbre no es <xref:System.Windows.Controls.UserControl>tan <xref:System.Windows.Controls.Control> simple como crear un , una personalizada proporciona la mayor flexibilidad.

#### <a name="benefits-of-deriving-from-control"></a>Ventajas de derivar de Control

Considere la <xref:System.Windows.Controls.Control> posibilidad de <xref:System.Windows.Controls.UserControl> derivar de en lugar de usar la clase si se aplica alguna de las siguientes condiciones:

- Desea que la apariencia de su <xref:System.Windows.Controls.ControlTemplate>control sea personalizable a través de la .

- Desea que el control admita distintos temas.

### <a name="deriving-from-frameworkelement"></a>Derivación de FrameworkElement

Controles que <xref:System.Windows.Controls.UserControl> derivan <xref:System.Windows.Controls.Control> o se basan en la composición de elementos existentes. Para muchos escenarios, esta es una solución aceptable, <xref:System.Windows.FrameworkElement> porque cualquier <xref:System.Windows.Controls.ControlTemplate>objeto que herede de puede estar en un archivo . Sin embargo, en ocasiones la apariencia de un control requiere una funcionalidad que va más allá de la simple composición de elementos. Para estos escenarios, basar <xref:System.Windows.FrameworkElement> un componente en es la opción correcta.

Existen dos métodos <xref:System.Windows.FrameworkElement>estándar para crear componentes basados en la creación: representación directa y composición de elementos personalizados. La representación directa <xref:System.Windows.UIElement.OnRender%2A> implica <xref:System.Windows.FrameworkElement> reemplazar <xref:System.Windows.Media.DrawingContext> el método de proporcionar y proporcionar operaciones que definen explícitamente los objetos visuales del componente. Este es el <xref:System.Windows.Controls.Image> método <xref:System.Windows.Controls.Border>utilizado por y . La composición de elementos <xref:System.Windows.Media.Visual> personalizados implica el uso de objetos de tipo para componer la apariencia del componente. Para ver un ejemplo, consulte [Using DrawingVisual Objects](../graphics-multimedia/using-drawingvisual-objects.md) (Uso de objetos DrawingVisual). <xref:System.Windows.Controls.Primitives.Track>es un ejemplo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un control en el que utiliza la composición de elementos personalizados. También es posible mezclar la representación directa y la composición de elementos personalizada en el mismo control.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Ventajas de derivar de FrameworkElement

Considere la <xref:System.Windows.FrameworkElement> posibilidad de derivar de si se aplica alguna de las siguientes condiciones:

- Desea tener un control preciso sobre la apariencia del control más allá de lo que proporciona la simple composición de elementos.

- Desea definir el aspecto del control definiendo una lógica de representación propia.

- Desea componer elementos existentes de formas novedosas que van más allá de lo posible con <xref:System.Windows.Controls.UserControl> y <xref:System.Windows.Controls.Control>.

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>Conceptos básicos de creación de controles

Como se comentó anteriormente, una de las características más eficaces de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es la posibilidad de no tener que limitarse a establecer las propiedades básicas de un control para modificar su apariencia y comportamiento, sin estar obligado a crear un control personalizado. Las características de estilo, enlace de datos y desencadenadores son posibles gracias al sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el sistema de eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En las próximas secciones se describen algunos procedimientos que debe seguir, independientemente del modelo que emplee para crear el control personalizado, de modo que los usuarios de su control personalizado puedan usar estas características como lo harían para un control incluido con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="use-dependency-properties"></a>Uso de propiedades de dependencia

Cuando una propiedad es de dependencia, es posible realizar las acciones siguientes:

- Establecer la propiedad en un estilo.

- Enlazar la propiedad a un origen de datos.

- Utilizar un recurso dinámico como valor de la propiedad.

- Animar la propiedad.

Si desea que una propiedad del control admita esta funcionalidad, debe implementarla como una propiedad de dependencia. En el ejemplo siguiente se define una propiedad de dependencia denominada `Value` mediante este procedimiento:

- Defina <xref:System.Windows.DependencyProperty> un `ValueProperty` identificador `public` `static` `readonly` denominado como campo.

- Registre el nombre de propiedad con <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>el sistema de propiedades, llamando a , para especificar lo siguiente:

  - El nombre de la propiedad.

  - Tipo de la propiedad.

  - El tipo al que pertenece la propiedad.

  - Los metadatos de la propiedad. Los metadatos contienen el valor <xref:System.Windows.CoerceValueCallback> predeterminado <xref:System.Windows.PropertyChangedCallback>de la propiedad, a y a .

- Defina una propiedad `Value`contenedora CLR denominada , que es el mismo nombre que `get` se `set` usa para registrar la propiedad de dependencia, implementando la propiedad y los descriptores de acceso. Tenga en `get` `set` cuenta que <xref:System.Windows.DependencyObject.GetValue%2A> los <xref:System.Windows.DependencyObject.SetValue%2A> descriptores de acceso y solo llaman y, respectivamente. Se recomienda que los descriptores de acceso de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las propiedades de dependencia <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> no contengan lógica adicional porque los clientes pueden omitir los descriptores de acceso y la llamada y directamente. Por ejemplo, cuando una propiedad está enlazada a un origen de datos, no se llama al descriptor de acceso `set`.  En lugar de agregar lógica adicional a los <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback>descriptores <xref:System.Windows.PropertyChangedCallback> de acceso get y set, use los delegados , y para responder o comprobar el valor cuando cambie.  Para más información sobre estas devoluciones de llamada, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](../advanced/dependency-property-callbacks-and-validation.md).

- Defina un método <xref:System.Windows.CoerceValueCallback> `CoerceValue`para el nombre . `CoerceValue` garantiza que `Value` es mayor o igual que `MinValue` y menor o igual que `MaxValue`.

- Defina un método <xref:System.Windows.PropertyChangedCallback>para `OnValueChanged`el archivo , denominado . `OnValueChanged`crea <xref:System.Windows.RoutedPropertyChangedEventArgs%601> un objeto y se `ValueChanged` prepara para generar el evento enrutado. Los eventos enrutados se abordan en la sección siguiente.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Para más información, consulte [Propiedades de dependencia personalizadas](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Uso de eventos enrutados

Del mismo modo que las propiedades de dependencia extienden la noción de propiedades CLR con funcionalidad adicional, los eventos enrutados amplían la noción de eventos CLR estándar. Cuando se crea un nuevo control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], también es conveniente implementar el evento como enrutado, porque un evento enrutado admite el comportamiento siguiente:

- Los eventos se pueden controlar en un elemento primario de varios controles. Si un evento es de propagación, puede suscribirse a él un elemento primario único del árbol de elementos. A continuación, los autores de la aplicación pueden utilizar un mismo controlador para responder al evento de varios controles. Por ejemplo, si el control forma parte <xref:System.Windows.Controls.ListBox> de cada elemento <xref:System.Windows.DataTemplate>de un (porque se incluye en un ), <xref:System.Windows.Controls.ListBox>el desarrollador de la aplicación puede definir el controlador de eventos para el evento del control en el archivo . Cada vez que se produzca el evento en cualquiera de los controles, se llamará al controlador de eventos.

- Los eventos enrutados <xref:System.Windows.EventSetter>se pueden usar en un , lo que permite a los desarrolladores de aplicaciones especificar el controlador de un evento dentro de un estilo.

- Los eventos enrutados <xref:System.Windows.EventTrigger>se pueden usar en un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]archivo , lo que resulta útil para animar propiedades mediante . Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).

En el ejemplo siguiente se define un evento enrutado mediante este procedimiento:

- Defina <xref:System.Windows.RoutedEvent> un `ValueChangedEvent` identificador `public` `static` `readonly` denominado como campo.

- Registre el evento enrutado llamando al <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> método. En el ejemplo se especifica <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>la siguiente información cuando se llama a:

  - El nombre del evento es `ValueChanged`.

  - La estrategia <xref:System.Windows.RoutingStrategy.Bubble>de enrutamiento es , lo que significa que se llama primero a un controlador de eventos en el origen (el objeto que provoca el evento) y, a continuación, se llama sucesivamente a los controladores de eventos de los elementos primarios del origen, empezando por el controlador de eventos en el elemento primario más cercano.

  - El tipo del controlador <xref:System.Windows.RoutedPropertyChangedEventHandler%601>de eventos <xref:System.Decimal> es , construido con un tipo.

  - El tipo de propiedad del evento es `NumericUpDown`.

- Declare un evento público denominado `ValueChanged` e incluya declaraciones de descriptores de acceso del evento. El ejemplo <xref:System.Windows.UIElement.AddHandler%2A> llama `add` a <xref:System.Windows.UIElement.RemoveHandler%2A> la `remove` declaración de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descriptor de acceso y a la declaración de descriptor de acceso para usar los servicios de eventos.

- Cree un método virtual protegido denominado `OnValueChanged` que genere el evento `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Para más información, consulte [Routed Events Overview](../advanced/routed-events-overview.md) (Introducción a los eventos enrutados) y [Create a Custom Routed Event](../advanced/how-to-create-a-custom-routed-event.md) (Creación de un evento enrutado personalizado).

### <a name="use-binding"></a>Uso del enlace

Para desacoplar la interfaz de usuario del control de su lógica, puede ser conveniente utilizar el enlace de datos. Esto es especialmente importante si define la apariencia <xref:System.Windows.Controls.ControlTemplate>del control mediante un archivo . Al utilizar el enlace de datos, puede que consiga eliminar la necesidad de hacer referencia a partes concretas de la interfaz de usuario desde el código. Es una buena idea evitar hacer referencia a <xref:System.Windows.Controls.ControlTemplate> elementos que se encuentran <xref:System.Windows.Controls.ControlTemplate> en <xref:System.Windows.Controls.ControlTemplate> el porque cuando el código hace referencia <xref:System.Windows.Controls.ControlTemplate>a los elementos que se encuentran en el y se cambia, el elemento al que se hace referencia debe incluirse en el nuevo .

En el ejemplo <xref:System.Windows.Controls.TextBlock> siguiente `NumericUpDown` se actualiza el control, asignándole un nombre y haciendo referencia al cuadro de texto por su nombre en el código.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

En el ejemplo siguiente se usa el enlace para lograr lo mismo.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="design-for-designers"></a>Diseño para diseñadores

Para recibir compatibilidad con controles WPF personalizados en WPF Designer para Visual Studio (por ejemplo, edición de propiedades con la ventana Propiedades), siga estas instrucciones.  Para obtener más información sobre el desarrollo para WPF Designer, vea [Diseñar XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Propiedades de dependencia

Asegúrese de `get` implementar `set` CLR y descriptores de acceso como se describió anteriormente, en "Usar propiedades de dependencia." Los diseñadores pueden utilizar el contenedor para detectar la presencia de una propiedad de dependencia, pero no se les exige, al igual que a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y a los clientes del control, llamar a los descriptores de acceso al obtener o establecer la propiedad.

#### <a name="attached-properties"></a>Propiedades asociadas

Para implementar propiedades adjuntas en controles personalizados, es recomendable que utilice las siguientes instrucciones:

- Tener `public` `static` `readonly` <xref:System.Windows.DependencyProperty> un formulario *PropertyName* `Property` que se <xref:System.Windows.DependencyProperty.RegisterAttached%2A> estaba creando mediante el método. El nombre de propiedad <xref:System.Windows.DependencyProperty.RegisterAttached%2A> al que se pasa debe coincidir con *PropertyName*.

- Implemente un par de métodos CLR `public` `static` denominados `Set`*NombreDePropiedad* y `Get`*NombreDePropiedad*. Ambos métodos deben aceptar <xref:System.Windows.DependencyProperty> una clase derivada de como su primer argumento. El método `Set`*NombreDePropiedad* también acepta un argumento cuyo tipo coincida con el tipo de datos registrado para la propiedad. El método `Get`*NombreDePropiedad* método debe devolver un valor del mismo tipo. Si falta el método `Set`*NombreDePropiedad*, la propiedad se marca como de solo lectura.

- `Set`*PropertyName* `Get`y *PropertyName* deben <xref:System.Windows.DependencyObject.GetValue%2A> enrutar <xref:System.Windows.DependencyObject.SetValue%2A> directamente a los métodos y del objeto de dependencia de destino, respectivamente. Los diseñadores pueden tener acceso a la propiedad adjunta mediante una llamada a través del contenedor de método o una llamada directa al objeto de dependencia de destino.

Para más información sobre las propiedades adjuntas, consulte [Attached Properties Overview](../advanced/attached-properties-overview.md) (Introducción a las propiedades adjuntas).

### <a name="define-and-use-shared-resources"></a>Definición y uso de recursos compartidos

Puede incluir el control en el mismo ensamblado que la aplicación o bien empaquetarlo en un ensamblado independiente que se pueda utilizar en varias aplicaciones. En general, la información analizada en este tema es aplicable independientemente del método que se utilice.  Sin embargo, hay una diferencia que vale la pena tener en cuenta.  Al incluir un control en el mismo ensamblado que una aplicación, puede agregar recursos globales al archivo App.xaml. Pero un ensamblado que contiene solo <xref:System.Windows.Application> controles no tiene un objeto asociado, por lo que un archivo App.xaml no está disponible.

Cuando una aplicación busca un recurso, la búsqueda se realiza en tres niveles en el orden que se indica a continuación:

1. El nivel de elemento.

   El sistema empieza por el elemento que hace referencia al recurso y, a continuación, busca en los recursos del elemento primario lógico y así sucesivamente hasta que se alcanza el elemento raíz.

2. El nivel de aplicación.

   Recursos definidos <xref:System.Windows.Application> por el objeto.

3. El nivel de tema.

   Los diccionarios del nivel de tema se almacenan en una subcarpeta denominada Temas.  Los archivos de la carpeta Temas corresponden a los temas.  Por ejemplo, podría tener Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc.  También puede tener un archivo denominado generic.xaml.  Cuando el sistema busca un recurso en el nivel de temas, primero lo busca en el archivo específico del tema y, a continuación, lo busca en generic.xaml.

Cuando el control está en un ensamblado independiente de la aplicación, debe colocar los recursos globales en el nivel de elemento o en el nivel de tema. Ambos métodos tienen sus ventajas.

#### <a name="defining-resources-at-the-element-level"></a>Definición de los recursos en el nivel de elemento

Puede definir los recursos compartidos en el nivel de elemento mediante la creación de un diccionario de recursos personalizado y combinarlo con el diccionario de recursos del control.  Cuando utiliza este método, puede nombrar el archivo de recursos que desee y este puede estar en la misma carpeta que los controles. Los recursos en el nivel de elemento también pueden utilizar cadenas simples como claves. En el ejemplo <xref:System.Windows.Media.LinearGradientBrush> siguiente se crea un archivo de recursos denominado Dictionary1.xaml.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Una vez definido el diccionario, debe combinarlo con el diccionario de recursos del control.  Para ello, utilice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código.

En el ejemplo siguiente se combina un diccionario de recursos mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

La desventaja de este <xref:System.Windows.ResourceDictionary> enfoque es que se crea un objeto cada vez que se hace referencia a él.  Por ejemplo, si tienes 10 controles personalizados en la biblioteca y combinas los diccionarios de recursos compartidos para cada control mediante XAML, creas 10 objetos idénticos. <xref:System.Windows.ResourceDictionary>  Puede evitar esto mediante la creación de una clase estática <xref:System.Windows.ResourceDictionary>que combina los recursos en el código y devuelve el resultado .

En el ejemplo siguiente se <xref:System.Windows.ResourceDictionary>crea una clase que devuelve un archivo .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

En el ejemplo siguiente se combina el recurso compartido con los recursos de un control personalizado en el constructor del control antes de llamar a `InitializeComponent`.  Dado `SharedDictionaryManager.SharedDictionary` que es una <xref:System.Windows.ResourceDictionary> propiedad estática, se crea solo una vez. Como el diccionario de recursos se combinó antes de llamar a `InitializeComponent`, los recursos están disponibles para el control en su archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definición de recursos en el nivel de tema

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le permite crear recursos para distintos temas de Windows.  Como autor del control, puede definir un recurso para un tema concreto con el fin de cambiar la apariencia del control en función del tema que se emplee. Por ejemplo, la <xref:System.Windows.Controls.Button> apariencia de a en el tema clásico de Windows (el tema <xref:System.Windows.Controls.Button> predeterminado para Windows 2000) difiere de <xref:System.Windows.Controls.Button> un en <xref:System.Windows.Controls.ControlTemplate> el tema de Windows Luna (el tema predeterminado para Windows XP) porque usa un tema diferente para cada tema.

Los recursos específicos de un tema se mantienen en un diccionario de recursos con un nombre de archivo concreto. Estos archivos deben estar en una carpeta denominada `Themes` que es una subcarpeta de la carpeta que contiene el control. En la tabla siguiente se enumeran los archivos de diccionario de recursos y el tema que está asociado a cada archivo:

|Nombre de archivo de diccionario de recursos|Tema de Windows|
|-----------------------------------|-------------------|
|`Classic.xaml`|Apariencia clásica de Windows 9x/2000 en Windows XP|
|`Luna.NormalColor.xaml`|Tema azul predeterminado en Windows XP|
|`Luna.Homestead.xaml`|Tema verde olivo en Windows XP|
|`Luna.Metallic.xaml`|Tema plateado en Windows XP|
|`Royale.NormalColor.xaml`|Tema predeterminado en Windows XP Media Center Edition|
|`Aero.NormalColor.xaml`|Tema predeterminado en Windows Vista|

No es necesario definir un recurso para cada tema. Si no se ha definido un recurso para un tema concreto, el control comprueba `Classic.xaml` para el recurso. Si no se ha definido el recurso en el archivo correspondiente al tema actual o en `Classic.xaml`, el control utiliza el recurso genérico, que está en un archivo de diccionario de recursos denominado `generic.xaml`.  El archivo `generic.xaml` se encuentra en la misma carpeta que los archivos de diccionario de recursos específicos del tema. Aunque `generic.xaml` no corresponde a un tema específico de Windows, sigue siendo un diccionario de nivel de tema.

El control personalizado NumericUpDown de [Visual](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) Basic o de [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) con `NumericUpDown` el tema y el ejemplo de compatibilidad con la automatización de la interfaz de usuario contiene dos diccionarios de recursos para el control: uno está en generic.xaml y el otro en Luna.NormalColor.xaml.

Al colocar <xref:System.Windows.Controls.ControlTemplate> un en cualquiera de los archivos de diccionario de recursos específicos del <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> tema, <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>debe crear un constructor estático para el control y llamar al método en el , como se muestra en el ejemplo siguiente.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definición de los recursos de tema y referencia a ellos

Al definir un recurso en el nivel de elemento, puede asignar una cadena como su clave y obtener acceso al recurso a través de la cadena. Al definir un recurso en el nivel de <xref:System.Windows.ComponentResourceKey> tema, debe usar a como clave.  En el ejemplo siguiente se define un recurso en generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

En el ejemplo siguiente se <xref:System.Windows.ComponentResourceKey> hace referencia al recurso especificando la clave como.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Especificación de la ubicación de los recursos de tema

Para buscar los recursos de un control, la aplicación host debe saber que el ensamblado contiene recursos específicos del control. Puede lograrlo agregando <xref:System.Windows.ThemeInfoAttribute> el ensamblado que contiene el control. Tiene <xref:System.Windows.ThemeInfoAttribute> una <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> propiedad que especifica la ubicación de <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> los recursos genéricos y una propiedad que especifica la ubicación de los recursos específicos del tema.

En el ejemplo <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> siguiente <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>se establece n.o y propiedades en , para especificar que los recursos genéricos y específicos del tema están en el mismo ensamblado que el control.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Consulte también

- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Empaquetar URI en WPF](../app-development/pack-uris-in-wpf.md)
- [Control Customization](control-customization.md) (Personalización de controles)
