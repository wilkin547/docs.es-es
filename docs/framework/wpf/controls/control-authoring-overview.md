---
title: Información general sobre la creación de controles
description: La extensibilidad de los controles Windows Presentation Foundation minimiza la necesidad de crear controles personalizados. Obtenga información sobre cómo crear un nuevo control, si es necesario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: 600eb193613846d7eeeb626a6dfd317d2592f809
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166337"
---
# <a name="control-authoring-overview"></a>Información general sobre la creación de controles

La extensibilidad del modelo de control [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] reduce enormemente la necesidad de crear un nuevo control. Sin embargo, en ciertos casos, puede que necesite crear un control personalizado. En este tema se describen las características que reducen la necesidad de crear un control personalizado y los diferentes modelos de creación de controles en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En este tema también se muestra cómo crear un nuevo control.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativas a la escritura de un nuevo control

Históricamente, si quería obtener una experiencia personalizada con un control existente, estaba limitado a cambiar las propiedades estándar del control, como el color de fondo, el ancho del borde y el tamaño de la fuente. Si se deseara extender la apariencia o el comportamiento de un control más allá de estos parámetros predefinidos, necesitaría crear un nuevo control; para ello, lo que haría es heredarlo de un control existente e invalidar el método responsable de dibujar el control.  Aunque esto sigue siendo una opción, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite personalizar los controles existentes mediante su modelo de contenido enriquecido, sus estilos, plantillas y desencadenadores. En la lista siguiente se proporcionan ejemplos de cómo se pueden usar estas características para crear experiencias personalizadas y coherentes sin tener que crear un nuevo control.

- **Contenido enriquecido.** Muchos de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estándar admiten contenido enriquecido. Por ejemplo, la propiedad de contenido de un <xref:System.Windows.Controls.Button> es de tipo <xref:System.Object> , por lo que teóricamente se puede mostrar cualquier cosa en <xref:System.Windows.Controls.Button> .  Para que un botón muestre una imagen y texto, puede Agregar una imagen y un <xref:System.Windows.Controls.TextBlock> a un <xref:System.Windows.Controls.StackPanel> y asignar el <xref:System.Windows.Controls.StackPanel> a la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad. Dado que los controles pueden mostrar elementos visuales [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y datos arbitrarios, no es tan necesario crear un nuevo control o modificar un control existente para admitir una visualización compleja. Para obtener más información sobre el modelo de contenido de <xref:System.Windows.Controls.Button> y otros modelos de contenido en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , vea [modelo de contenido de WPF](wpf-content-model.md).

- **Stil.** Una <xref:System.Windows.Style> es una colección de valores que representan las propiedades de un control. Mediante el uso de estilos, puede crear una representación reutilizable de la apariencia y el comportamiento deseados de un control sin necesidad de escribir un nuevo control. Por ejemplo, supongamos que desea que todos los <xref:System.Windows.Controls.TextBlock> controles tengan una fuente Arial roja con un tamaño de fuente de 14. Puede crear un estilo como un recurso y establecer las propiedades adecuadas según corresponda. Cada <xref:System.Windows.Controls.TextBlock> que agregue a la aplicación tendrá la misma apariencia.

- **Plantillas de datos.** <xref:System.Windows.DataTemplate>Permite personalizar el modo en que se muestran los datos en un control. Por ejemplo, <xref:System.Windows.DataTemplate> se puede usar para especificar cómo se muestran los datos en un <xref:System.Windows.Controls.ListBox> .  Para ver un ejemplo de esto, consulte [Data Templating Overview](../data/data-templating-overview.md) (Introducción a las plantillas de datos).  Además de personalizar la apariencia de los datos, <xref:System.Windows.DataTemplate> puede incluir elementos de interfaz de usuario, lo que proporciona una gran flexibilidad en las interfaces de usuario personalizadas.  Por ejemplo, con <xref:System.Windows.DataTemplate> , puede crear un <xref:System.Windows.Controls.ComboBox> en el que cada elemento contenga una casilla.

- **Plantillas de control.** Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizan <xref:System.Windows.Controls.ControlTemplate> para definir la estructura y la apariencia del control, que separa la apariencia de un control de la funcionalidad del control. Puede cambiar drásticamente la apariencia de un control redefiniendo su <xref:System.Windows.Controls.ControlTemplate> .  Por ejemplo, supongamos que desea un control que se parezca a un semáforo. Este control tiene una interfaz de usuario y una funcionalidad sencillas.  El control son tres círculos, y solo uno se puede iluminar cada vez. Después de la reflexión, puede darse cuenta de que un <xref:System.Windows.Controls.RadioButton> ofrece la funcionalidad de solo una que se selecciona a la vez, pero la apariencia predeterminada del no <xref:System.Windows.Controls.RadioButton> tiene nada como las luces de una luz.  Dado que <xref:System.Windows.Controls.RadioButton> usa una plantilla de control para definir su apariencia, es fácil volver a definir el <xref:System.Windows.Controls.ControlTemplate> para que se ajuste a los requisitos del control y usar botones de radio para crear el semáforo.

  > [!NOTE]
  > Aunque un <xref:System.Windows.Controls.RadioButton> puede utilizar <xref:System.Windows.DataTemplate> , <xref:System.Windows.DataTemplate> no es suficiente en este ejemplo.  <xref:System.Windows.DataTemplate>Define la apariencia del contenido de un control. En el caso de <xref:System.Windows.Controls.RadioButton> , el contenido es lo que aparece a la derecha del círculo que indica si <xref:System.Windows.Controls.RadioButton> está seleccionado.  En el ejemplo del semáforo, el botón de selección debe ser un círculo que pueda "encenderse". Dado que el requisito de apariencia del semáforo es tan diferente al de la apariencia predeterminada de <xref:System.Windows.Controls.RadioButton> , es necesario volver a definir <xref:System.Windows.Controls.ControlTemplate> .  En general <xref:System.Windows.DataTemplate> , se usa para definir el contenido (o los datos) de un control, y <xref:System.Windows.Controls.ControlTemplate> se utiliza para definir cómo se estructura un control.

- **Desencadenadores.** <xref:System.Windows.Trigger>Permite cambiar dinámicamente la apariencia y el comportamiento de un control sin necesidad de crear un nuevo control. Por ejemplo, supongamos que tiene varios <xref:System.Windows.Controls.ListBox> controles en la aplicación y desea que los elementos de cada uno aparezcan en <xref:System.Windows.Controls.ListBox> negrita y en rojo cuando se seleccionan. La primera instinto podría ser crear una clase que hereda de <xref:System.Windows.Controls.ListBox> e invalidar el <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> método para cambiar la apariencia del elemento seleccionado, pero un enfoque más adecuado consiste en agregar un desencadenador a un estilo de <xref:System.Windows.Controls.ListBoxItem> que cambia la apariencia del elemento seleccionado. Un desencadenador permite cambiar los valores de propiedad o realizar acciones según el valor de una propiedad. <xref:System.Windows.EventTrigger>Permite realizar acciones cuando se produce un evento.

Para más información sobre los estilos, las plantillas y los desencadenadores, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

En general, si el control refleja la funcionalidad de un control existente, pero quiere que el control tenga un aspecto diferente, primero debe considerar si puede usar cualquiera de los métodos descritos en esta sección para cambiar la apariencia del control existente.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelos para crear controles

El modelo de contenido enriquecido, los estilos, las plantillas y los desencadenadores reducen la necesidad de crear un nuevo control. Sin embargo, si necesita crear un nuevo control, es importante comprender los diferentes modelos de creación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona tres modelos generales para la creación de un control, cada uno de los cuales proporciona un conjunto de características y un nivel de flexibilidad diferentes. Las clases base para los tres modelos son <xref:System.Windows.Controls.UserControl> , <xref:System.Windows.Controls.Control> y <xref:System.Windows.FrameworkElement> .

### <a name="deriving-from-usercontrol"></a>Derivación de UserControl

La manera más sencilla de crear un control en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es derivar de <xref:System.Windows.Controls.UserControl> . Al compilar un control que hereda de <xref:System.Windows.Controls.UserControl> , agregue los componentes existentes a <xref:System.Windows.Controls.UserControl> , asigne un nombre a los componentes y haga referencia a los controladores de eventos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Luego puede hacer referencia a los elementos con nombre y definir los controladores de eventos en el código. Este modelo de desarrollo es muy similar al modelo utilizado para el desarrollo de aplicaciones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Si se compilan correctamente, <xref:System.Windows.Controls.UserControl> puede aprovechar las ventajas de los desencadenadores, los estilos y el contenido enriquecido. Sin embargo, si el control hereda de <xref:System.Windows.Controls.UserControl> , las personas que usan el control no podrán usar <xref:System.Windows.DataTemplate> o <xref:System.Windows.Controls.ControlTemplate> para personalizar su apariencia.  Es necesario derivar de la <xref:System.Windows.Controls.Control> clase o de una de sus clases derivadas (distintas de <xref:System.Windows.Controls.UserControl> ) para crear un control personalizado que admita plantillas.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Ventajas de derivar de UserControl

Considere la posibilidad de derivar de <xref:System.Windows.Controls.UserControl> si se aplica lo siguiente:

- Desea crear el control de forma similar a cómo crea una aplicación.

- El control solo consta de componentes existentes.

- No se necesita personalización compleja.

### <a name="deriving-from-control"></a>Derivación de Control

La derivación de la <xref:System.Windows.Controls.Control> clase es el modelo usado por la mayoría de los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles existentes. Cuando se crea un control que hereda de la <xref:System.Windows.Controls.Control> clase, se define su apariencia mediante el uso de plantillas. Al hacerlo, se separa la lógica de funcionamiento de la representación visual. También puede garantizar el desacoplamiento de la interfaz de usuario y la lógica mediante el uso de comandos y enlaces en lugar de eventos y evitar la referencia a elementos en el <xref:System.Windows.Controls.ControlTemplate> siempre que sea posible.  Si la interfaz de usuario y la lógica del control están desacopladas correctamente, un usuario del control puede redefinir el del control <xref:System.Windows.Controls.ControlTemplate> para personalizar su apariencia. Aunque la creación de un personalizado <xref:System.Windows.Controls.Control> no es tan simple como compilar un <xref:System.Windows.Controls.UserControl> , un personalizado <xref:System.Windows.Controls.Control> proporciona la máxima flexibilidad.

#### <a name="benefits-of-deriving-from-control"></a>Ventajas de derivar de Control

Considere la posibilidad de derivar de en <xref:System.Windows.Controls.Control> lugar de usar la <xref:System.Windows.Controls.UserControl> clase si se aplica alguna de las siguientes condiciones:

- Quiere que la apariencia del control se pueda personalizar a través de <xref:System.Windows.Controls.ControlTemplate> .

- Desea que el control admita distintos temas.

### <a name="deriving-from-frameworkelement"></a>Derivación de FrameworkElement

Los controles que derivan de o se basan en la <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control> composición de elementos existentes. En muchos escenarios, se trata de una solución aceptable, ya que cualquier objeto que herede de <xref:System.Windows.FrameworkElement> puede estar en <xref:System.Windows.Controls.ControlTemplate> . Sin embargo, en ocasiones la apariencia de un control requiere una funcionalidad que va más allá de la simple composición de elementos. En estos casos, basar un componente en <xref:System.Windows.FrameworkElement> es la opción correcta.

Existen dos métodos estándar para crear <xref:System.Windows.FrameworkElement> componentes basados en: representación directa y composición de elementos personalizada. La representación directa implica reemplazar el <xref:System.Windows.UIElement.OnRender%2A> método de <xref:System.Windows.FrameworkElement> y proporcionar <xref:System.Windows.Media.DrawingContext> operaciones que definen explícitamente los objetos visuales del componente. Este es el método utilizado por <xref:System.Windows.Controls.Image> y <xref:System.Windows.Controls.Border> . La composición de elementos personalizados implica el uso de objetos de tipo <xref:System.Windows.Media.Visual> para crear la apariencia del componente. Para ver un ejemplo, consulte [Using DrawingVisual Objects](../graphics-multimedia/using-drawingvisual-objects.md) (Uso de objetos DrawingVisual). <xref:System.Windows.Controls.Primitives.Track>es un ejemplo de un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que usa la composición de elementos personalizada. También es posible mezclar la representación directa y la composición de elementos personalizada en el mismo control.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Ventajas de derivar de FrameworkElement

Considere la posibilidad de derivar de <xref:System.Windows.FrameworkElement> si se aplica alguna de las siguientes condiciones:

- Desea tener un control preciso sobre la apariencia del control más allá de lo que proporciona la simple composición de elementos.

- Desea definir el aspecto del control definiendo una lógica de representación propia.

- Desea componer los elementos existentes de maneras novedosas que van más allá de lo que es posible con <xref:System.Windows.Controls.UserControl> y <xref:System.Windows.Controls.Control> .

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

- Defina un <xref:System.Windows.DependencyProperty> identificador denominado `ValueProperty` como un `public` `static` `readonly` campo.

- Registre el nombre de la propiedad con el sistema de propiedades, llamando <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType> a, para especificar lo siguiente:

  - El nombre de la propiedad.

  - Tipo de la propiedad.

  - El tipo al que pertenece la propiedad.

  - Los metadatos de la propiedad. Los metadatos contienen el valor predeterminado de la propiedad, <xref:System.Windows.CoerceValueCallback> y <xref:System.Windows.PropertyChangedCallback> .

- Defina una propiedad de contenedor CLR denominada `Value` , que es el mismo nombre que se usa para registrar la propiedad de dependencia, mediante la implementación de los `get` descriptores de acceso y de la propiedad `set` . Tenga en cuenta que los `get` `set` descriptores de acceso y solo llaman a <xref:System.Windows.DependencyObject.GetValue%2A> y, <xref:System.Windows.DependencyObject.SetValue%2A> respectivamente. Se recomienda que los descriptores de acceso de las propiedades de dependencia no contengan lógica adicional, ya que los clientes y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden omitir los descriptores de acceso y llamar a <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> directamente. Por ejemplo, cuando una propiedad está enlazada a un origen de datos, no se llama al descriptor de acceso `set`.  En lugar de agregar lógica adicional a los descriptores de acceso get y Set, utilice los <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.PropertyChangedCallback> delegados, y para responder o comprobar el valor cuando cambie.  Para más información sobre estas devoluciones de llamada, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](../advanced/dependency-property-callbacks-and-validation.md).

- Defina un método para el <xref:System.Windows.CoerceValueCallback> denominado `CoerceValue` . `CoerceValue` garantiza que `Value` es mayor o igual que `MinValue` y menor o igual que `MaxValue`.

- Defina un método para el <xref:System.Windows.PropertyChangedCallback> denominado `OnValueChanged` . `OnValueChanged`crea un <xref:System.Windows.RoutedPropertyChangedEventArgs%601> objeto y se prepara para generar el `ValueChanged` evento enrutado. Los eventos enrutados se abordan en la sección siguiente.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Para más información, consulte [Propiedades de dependencia personalizadas](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Uso de eventos enrutados

Del mismo modo que las propiedades de dependencia extienden la noción de propiedades CLR con funcionalidad adicional, los eventos enrutados amplían la noción de eventos CLR estándar. Cuando se crea un nuevo control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], también es conveniente implementar el evento como enrutado, porque un evento enrutado admite el comportamiento siguiente:

- Los eventos se pueden controlar en un elemento primario de varios controles. Si un evento es de propagación, puede suscribirse a él un elemento primario único del árbol de elementos. A continuación, los autores de la aplicación pueden utilizar un mismo controlador para responder al evento de varios controles. Por ejemplo, si el control forma parte de cada elemento de un <xref:System.Windows.Controls.ListBox> (porque se incluye en un <xref:System.Windows.DataTemplate> ), el desarrollador de la aplicación puede definir el controlador de eventos para el evento del control en <xref:System.Windows.Controls.ListBox> . Cada vez que se produzca el evento en cualquiera de los controles, se llamará al controlador de eventos.

- Los eventos enrutados se pueden utilizar en <xref:System.Windows.EventSetter> , lo que permite a los desarrolladores de aplicaciones especificar el controlador de un evento dentro de un estilo.

- Los eventos enrutados se pueden utilizar en un <xref:System.Windows.EventTrigger> , que es útil para animar propiedades mediante el uso de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Para obtener más información, vea [información general sobre animaciones](../graphics-multimedia/animation-overview.md).

En el ejemplo siguiente se define un evento enrutado mediante este procedimiento:

- Defina un <xref:System.Windows.RoutedEvent> identificador denominado `ValueChangedEvent` como un `public` `static` `readonly` campo.

- Registre el evento enrutado llamando al <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> método. En el ejemplo se especifica la siguiente información cuando llama a <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> :

  - El nombre del evento es `ValueChanged`.

  - La estrategia de enrutamiento es <xref:System.Windows.RoutingStrategy.Bubble> , lo que significa que se llama primero a un controlador de eventos en el origen (el objeto que genera el evento) y, a continuación, se llama a los controladores de eventos en los elementos primarios del origen, comenzando por el controlador de eventos en el elemento primario más próximo.

  - El tipo del controlador de eventos es <xref:System.Windows.RoutedPropertyChangedEventHandler%601> , construido con un <xref:System.Decimal> tipo.

  - El tipo de propiedad del evento es `NumericUpDown`.

- Declare un evento público denominado `ValueChanged` e incluya declaraciones de descriptores de acceso del evento. El ejemplo llama a <xref:System.Windows.UIElement.AddHandler%2A> en la `add` declaración del descriptor de acceso y <xref:System.Windows.UIElement.RemoveHandler%2A> en la `remove` declaración del descriptor de acceso para usar los servicios de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos.

- Cree un método virtual protegido denominado `OnValueChanged` que genere el evento `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Para más información, consulte [Routed Events Overview](../advanced/routed-events-overview.md) (Introducción a los eventos enrutados) y [Create a Custom Routed Event](../advanced/how-to-create-a-custom-routed-event.md) (Creación de un evento enrutado personalizado).

### <a name="use-binding"></a>Uso del enlace

Para desacoplar la interfaz de usuario del control de su lógica, puede ser conveniente utilizar el enlace de datos. Esto es especialmente importante si define la apariencia del control mediante <xref:System.Windows.Controls.ControlTemplate> . Al utilizar el enlace de datos, puede que consiga eliminar la necesidad de hacer referencia a partes concretas de la interfaz de usuario desde el código. Es una buena idea evitar hacer referencia a los elementos que se encuentran en <xref:System.Windows.Controls.ControlTemplate> porque cuando el código hace referencia a elementos que se encuentran en <xref:System.Windows.Controls.ControlTemplate> y <xref:System.Windows.Controls.ControlTemplate> cambia, el elemento al que se hace referencia debe incluirse en el nuevo <xref:System.Windows.Controls.ControlTemplate> .

En el ejemplo siguiente se actualiza el <xref:System.Windows.Controls.TextBlock> del `NumericUpDown` control, se le asigna un nombre y se hace referencia al cuadro de texto por su nombre en el código.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

En el ejemplo siguiente se usa el enlace para lograr lo mismo.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="design-for-designers"></a>Diseño para diseñadores

Para recibir compatibilidad con los controles personalizados de WPF en WPF Designer para Visual Studio (por ejemplo, la edición de propiedades con el ventana Propiedades), siga estas instrucciones.  Para obtener más información sobre el desarrollo de WPF Designer, consulte [diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Propiedades de dependencia

Asegúrese de implementar los `get` `set` descriptores de acceso y CLR tal y como se describió anteriormente, en "usar propiedades de dependencia". Los diseñadores pueden utilizar el contenedor para detectar la presencia de una propiedad de dependencia, pero no se les exige, al igual que a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y a los clientes del control, llamar a los descriptores de acceso al obtener o establecer la propiedad.

#### <a name="attached-properties"></a>Propiedades asociadas

Para implementar propiedades adjuntas en controles personalizados, es recomendable que utilice las siguientes instrucciones:

- Tener una con `public` `static` `readonly` <xref:System.Windows.DependencyProperty> el formato *PropertyName* `Property` que se creaba mediante el <xref:System.Windows.DependencyProperty.RegisterAttached%2A> método. El nombre de propiedad que se pasa a <xref:System.Windows.DependencyProperty.RegisterAttached%2A> debe coincidir con *PropertyName*.

- Implemente un par de métodos CLR `public` `static` denominados `Set`*NombreDePropiedad* y `Get`*NombreDePropiedad*. Ambos métodos deben aceptar una clase derivada de <xref:System.Windows.DependencyProperty> como primer argumento. El método `Set`*NombreDePropiedad* también acepta un argumento cuyo tipo coincida con el tipo de datos registrado para la propiedad. El método `Get`*NombreDePropiedad* método debe devolver un valor del mismo tipo. Si falta el método `Set`*NombreDePropiedad*, la propiedad se marca como de solo lectura.

- `Set`*PropertyName* y `Get` *PropertyName* deben enrutar directamente a los <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> métodos y en el objeto de dependencia de destino, respectivamente. Los diseñadores pueden tener acceso a la propiedad adjunta mediante una llamada a través del contenedor de método o una llamada directa al objeto de dependencia de destino.

Para más información sobre las propiedades adjuntas, consulte [Attached Properties Overview](../advanced/attached-properties-overview.md) (Introducción a las propiedades adjuntas).

### <a name="define-and-use-shared-resources"></a>Definición y uso de recursos compartidos

Puede incluir el control en el mismo ensamblado que la aplicación o bien empaquetarlo en un ensamblado independiente que se pueda utilizar en varias aplicaciones. En general, la información analizada en este tema es aplicable independientemente del método que se utilice.  Sin embargo, hay una diferencia que vale la pena tener en cuenta.  Al incluir un control en el mismo ensamblado que una aplicación, puede agregar recursos globales al archivo App.xaml. Pero un ensamblado que solo contiene controles no tiene un <xref:System.Windows.Application> objeto asociado a él, por lo que no hay disponible ningún archivo app. Xaml.

Cuando una aplicación busca un recurso, la búsqueda se realiza en tres niveles en el orden que se indica a continuación:

1. El nivel de elemento.

   El sistema empieza por el elemento que hace referencia al recurso y, a continuación, busca en los recursos del elemento primario lógico y así sucesivamente hasta que se alcanza el elemento raíz.

2. El nivel de aplicación.

   Recursos definidos por el <xref:System.Windows.Application> objeto.

3. El nivel de tema.

   Los diccionarios del nivel de tema se almacenan en una subcarpeta denominada Temas.  Los archivos de la carpeta Temas corresponden a los temas.  Por ejemplo, podría tener Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc.  También puede tener un archivo denominado generic.xaml.  Cuando el sistema busca un recurso en el nivel de temas, primero lo busca en el archivo específico del tema y, a continuación, lo busca en generic.xaml.

Cuando el control está en un ensamblado independiente de la aplicación, debe colocar los recursos globales en el nivel de elemento o en el nivel de tema. Ambos métodos tienen sus ventajas.

#### <a name="defining-resources-at-the-element-level"></a>Definición de los recursos en el nivel de elemento

Puede definir recursos compartidos en el nivel de elemento creando un diccionario de recursos personalizado y combinándolos con el Diccionario de recursos del control.  Cuando utiliza este método, puede nombrar el archivo de recursos que desee y este puede estar en la misma carpeta que los controles. Los recursos en el nivel de elemento también pueden utilizar cadenas simples como claves. En el ejemplo siguiente se crea un <xref:System.Windows.Media.LinearGradientBrush> archivo de recursos denominado Dictionary1. Xaml.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Una vez definido el diccionario, debe combinarlo con el diccionario de recursos del control.  Para ello, utilice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código.

En el ejemplo siguiente se combina un diccionario de recursos mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

El inconveniente de este enfoque es que <xref:System.Windows.ResourceDictionary> se crea un objeto cada vez que se hace referencia a él.  Por ejemplo, si tiene 10 controles personalizados en la biblioteca y combina los diccionarios de recursos compartidos de cada control mediante XAML, cree 10 objetos idénticos <xref:System.Windows.ResourceDictionary> .  Para evitar esto, cree una clase estática que combine los recursos en el código y devuelva el resultado <xref:System.Windows.ResourceDictionary> .

En el ejemplo siguiente se crea una clase que devuelve un compartido <xref:System.Windows.ResourceDictionary> .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

En el ejemplo siguiente se combina el recurso compartido con los recursos de un control personalizado en el constructor del control antes de llamar a `InitializeComponent`.  Dado que `SharedDictionaryManager.SharedDictionary` es una propiedad estática, <xref:System.Windows.ResourceDictionary> se crea solo una vez. Como el diccionario de recursos se combinó antes de llamar a `InitializeComponent`, los recursos están disponibles para el control en su archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definición de recursos en el nivel de tema

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le permite crear recursos para distintos temas de Windows.  Como autor del control, puede definir un recurso para un tema concreto con el fin de cambiar la apariencia del control en función del tema que se emplee. Por ejemplo, la apariencia de un <xref:System.Windows.Controls.Button> en el tema clásico de Windows (el tema predeterminado para windows 2000) difiere de un <xref:System.Windows.Controls.Button> en el tema luna de Windows (el tema predeterminado para Windows XP) porque <xref:System.Windows.Controls.Button> utiliza un distinto <xref:System.Windows.Controls.ControlTemplate> para cada tema.

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

El ejemplo de control personalizado NumericUpDown de [C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) o [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) con el tema y la compatibilidad con la automatización de la interfaz de usuario contiene dos diccionarios de recursos para el `NumericUpDown` control: uno está en Generic. XAML y el otro en luna. NormalColor. Xaml.

Al colocar un <xref:System.Windows.Controls.ControlTemplate> en cualquiera de los archivos de Diccionario de recursos específicos del tema, debe crear un constructor estático para el control y llamar al <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> método en <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> , como se muestra en el ejemplo siguiente.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definición de los recursos de tema y referencia a ellos

Al definir un recurso en el nivel de elemento, puede asignar una cadena como su clave y obtener acceso al recurso a través de la cadena. Al definir un recurso en el nivel de tema, debe usar <xref:System.Windows.ComponentResourceKey> como clave.  En el ejemplo siguiente se define un recurso en generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

En el ejemplo siguiente se hace referencia al recurso mediante la especificación de <xref:System.Windows.ComponentResourceKey> como la clave.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Especificación de la ubicación de los recursos de tema

Para buscar los recursos de un control, la aplicación host debe saber que el ensamblado contiene recursos específicos del control. Puede hacerlo agregando <xref:System.Windows.ThemeInfoAttribute> al ensamblado que contiene el control. <xref:System.Windows.ThemeInfoAttribute>Tiene una <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> propiedad que especifica la ubicación de los recursos genéricos y una <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> propiedad que especifica la ubicación de los recursos específicos del tema.

En el ejemplo siguiente se establecen las <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> propiedades y en <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> para <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly> especificar que los recursos genéricos y específicos del tema se encuentran en el mismo ensamblado que el control.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Vea también

- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Identificadores URI de paquete en WPF](../app-development/pack-uris-in-wpf.md)
- [Personalización de controles](control-customization.md)
