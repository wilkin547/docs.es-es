---
title: Propiedades de dependencia personalizadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
ms.openlocfilehash: 659497543d40c8eda18b55b4d98feac976c5abf5
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860243"
---
# <a name="custom-dependency-properties"></a>Propiedades de dependencia personalizadas

En este tema se describen las razones por las que los autores de componentes y los desarrolladores de aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] quieren crear la propiedad de dependencia personalizada, y se describen los pasos de implementación y algunas opciones de implementación que pueden mejorar el rendimiento, la facilidad de uso o la versatilidad de la propiedad.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Requisitos previos

En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y saber cómo escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>¿Qué es una propiedad de dependencia?

Puede habilitar lo que, de lo contrario, sería una propiedad [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] para que admita la aplicación de estilos, el enlace de datos, la herencia, las animaciones y los valores predeterminados. Para ello, impleméntela como una propiedad de dependencia. Las propiedades de dependencia son propiedades que están registradas con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de propiedades mediante una llamada a la <xref:System.Windows.DependencyProperty.Register%2A> método (o <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>), y están respaldadas por un <xref:System.Windows.DependencyProperty> campo identificador. Solo se pueden usar las propiedades de dependencia <xref:System.Windows.DependencyObject> tipos, pero <xref:System.Windows.DependencyObject> es bastante elevado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jerarquía de clases, por lo que la mayoría de las clases disponibles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede admitir propiedades de dependencia. Para obtener más información acerca de las propiedades de dependencia, y algunos de los términos y convenciones que se usan para describirlas en este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)], consulte [Información general sobre las propiedades de dependencia](dependency-properties-overview.md).

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Ejemplos de propiedades de dependencia

Ejemplos de propiedades de dependencia que se implementan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clases incluyen el <xref:System.Windows.Controls.Control.Background%2A> propiedad, el <xref:System.Windows.FrameworkElement.Width%2A> propiedad y el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad, entre muchas otras. Cada propiedad de dependencia expuesta por una clase tiene un campo estático público correspondiente de tipo <xref:System.Windows.DependencyProperty> expuesto en esa misma clase. Es el identificador de la propiedad de dependencia. El identificador se denomina mediante una convención: el nombre de la propiedad de dependencia con la cadena `Property` anexada. Por ejemplo, la correspondiente <xref:System.Windows.DependencyProperty> campo de identificador de la <xref:System.Windows.Controls.Control.Background%2A> propiedad es <xref:System.Windows.Controls.Control.BackgroundProperty>. El identificador almacena la información sobre la propiedad de dependencia tal como se ha registrado y el identificador se usa posteriormente para otras operaciones relacionadas con la propiedad de dependencia, como la llamada a <xref:System.Windows.DependencyObject.SetValue%2A>.

Como se mencionó en la [Información general sobre las propiedades de dependencia](dependency-properties-overview.md), todas las propiedades de dependencia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (excepto la mayoría de las propiedades adjuntas) también son propiedades de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] debido a la implementación del "contenedor". Por lo tanto, a partir del código, puede obtener o establecer propiedades de dependencia mediante una llamada a los descriptores de acceso de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que definen los contenedores de la misma manera que usaría otras propiedades de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Como consumidor de propiedades de dependencia establecidas, no utiliza normalmente el <xref:System.Windows.DependencyObject> métodos <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, que son el punto de conexión al sistema de propiedades subyacente. En su lugar, la implementación existente de la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] propiedades ya habrá llamado a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> dentro de la `get` y `set` implementaciones de contenedores de la propiedad mediante el campo de identificador adecuadamente . Si se está implementando una propiedad de dependencia personalizada, a continuación, estará definiendo el contenedor de forma similar.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>¿Cuándo se debe implementar una propiedad de dependencia?

Cuando implementa una propiedad en una clase, siempre y cuando la clase se deriva de <xref:System.Windows.DependencyObject>, tiene la opción de respaldar su propiedad con un <xref:System.Windows.DependencyProperty> identificador y, por tanto, para que sea una propiedad de dependencia. Convertir su propiedad en una propiedad de dependencia no es siempre necesario ni adecuado y dependerá de las necesidades del escenario. A veces, la técnica típica de respaldar la propiedad con un campo privado es adecuada. Sin embargo, deberá implementar la propiedad como una propiedad de dependencia cada vez que quiera que esta admita una o varias de las siguientes funcionalidades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

- Quiere que su propiedad se pueda establecer en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md).

- Quiere que su propiedad admita el enlace de datos. Para obtener más información sobre las propiedades de dependencia de enlace de datos, consulte [Enlazar las propiedades de dos controles](../data/how-to-bind-the-properties-of-two-controls.md).

- Quiere que su propiedad se pueda establecer con una referencia de recurso dinámico. Para obtener más información, consulte [Recursos XAML](xaml-resources.md).

- Quiere heredar un valor de propiedad automáticamente de un elemento primario del árbol de elementos. En este caso, se registre con el <xref:System.Windows.DependencyProperty.RegisterAttached%2A> método, aunque también crea un contenedor de propiedad para [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] acceso. Para más información, vea [Herencia de valores de propiedad](property-value-inheritance.md).

- Quiere que su propiedad se pueda animar. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).

- Quiere que el sistema de propiedades notifique cualquier cambio en el valor anterior de la propiedad debido a acciones del sistema de propiedades, el entorno o el usuario, o a la lectura y el uso de estilos. Al usar los metadatos de la propiedad, la propiedad puede especificar un método de devolución de llamada que se invocará cada vez que el sistema de propiedades determine un cambio definitivo en el valor de la propiedad. Un concepto relacionado es la coerción del valor de propiedad. Para obtener más información, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](dependency-property-callbacks-and-validation.md).

- Quiere usar convenciones de metadatos establecidas que también se usan en los procesos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como notificar si un cambio en un valor de propiedad debe exigir que el sistema de diseño recomponga los elementos visuales de un elemento. O bien quiere poder usar invalidaciones de metadatos para que las clases derivadas puedan cambiar las características basadas en metadatos, como el valor predeterminado.

- Desea admiten las propiedades de un control personalizado para recibir el Diseñador de WPF de Visual Studio, como **propiedades** edición de la ventana. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

Al examinar estos escenarios, también debe considerar si puede obtener su escenario mediante la invalidación de los metadatos de una propiedad de dependencia existente, en lugar de hacerlo a través de la implementación de una propiedad completamente nueva. Que una invalidación de metadatos resulte práctica depende de su escenario y del parecido de ese escenario con la implementación en las clases y las propiedades de dependencia existentes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información sobre cómo invalidar los metadatos de las propiedades existentes, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Lista de comprobación para definir una propiedad de dependencia

La definición de una propiedad de dependencia consta de cuatro conceptos distintos. Estos conceptos no son necesariamente procedimientos estrictos, ya que algunos de ellos acaban combinándose en una sola línea de código en la implementación:

- (Opcional) Cree los metadatos de propiedad de la propiedad de dependencia.

- Registre el nombre de propiedad con el sistema de propiedades, y especifique el tipo de propietario y el tipo de valor de propiedad. Especifique también los metadatos de la propiedad, si se usan.

- Definir un <xref:System.Windows.DependencyProperty> identificador como un `public` `static` `readonly` campo en el tipo de propietario.

- Defina una propiedad de "contenedor" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] cuyo nombre coincida con el nombre de la propiedad de dependencia. Implemente los descriptores de acceso `get` y `set` de la propiedad de "contenedor" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para establecer la conexión con la propiedad de dependencia que la respalda.

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registro de la propiedad con el sistema de propiedades

Para que la propiedad sea una propiedad de dependencia, debe registrarla en una tabla (de cuyo mantenimiento se encargue el sistema de propiedades) y asignarle un identificador único, que se usará como calificador en operaciones posteriores del sistema de propiedades. Estas operaciones podrían ser operaciones internas o su propio código que llama a las API del sistema de propiedades. Para registrar la propiedad, llame a la <xref:System.Windows.DependencyProperty.Register%2A> método dentro del cuerpo de la clase (dentro de la clase, pero fuera de las definiciones de miembros). El campo de identificador también lo proporciona el <xref:System.Windows.DependencyProperty.Register%2A> llamada al método, como el valor devuelto. La razón por la que el <xref:System.Windows.DependencyProperty.Register%2A> llamada se realiza fuera de otro miembro definiciones es porque este valor devuelto se utiliza para asignar y crear un `public` `static` `readonly` campo de tipo <xref:System.Windows.DependencyProperty> como parte de la clase. Este campo se convierte en el identificador de la propiedad de dependencia.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Convenciones de nombres de las propiedades de dependencia

Existen convenciones de nomenclatura establecidas con respecto a las propiedades de dependencia que se deben seguir en todas las circunstancias, menos en las excepcionales.

La propiedad de dependencia tendrá un nombre básico, "AquariumGraphic" en este ejemplo, que se proporciona como el primer parámetro de <xref:System.Windows.DependencyProperty.Register%2A>. Este nombre debe ser único en cada tipo de registro. Las propiedades de dependencia heredadas a través de tipos base ya se consideran parte del tipo de registro; los nombres de las propiedades heredadas no se pueden volver a registrar. Sin embargo, existe una técnica para agregar una clase como propietaria de una propiedad de dependencia, aunque esa propiedad de dependencia no sea heredada. Para obtener más información, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).

Al crear el campo de identificador, asígnele el nombre de la propiedad tal como lo registró, seguido del sufijo `Property`. Este campo es el identificador de la propiedad de dependencia, y se usará más adelante como entrada para el <xref:System.Windows.DependencyObject.SetValue%2A> y <xref:System.Windows.DependencyObject.GetValue%2A> permiten las llamadas que le permitirán en los contenedores, por cualquier otro código acceso a la propiedad por su propio código, mediante cualquier acceso de código externo , el sistema de propiedades y, posiblemente, los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesadores.

> [!NOTE]
> La definición de la propiedad de dependencia en el cuerpo de la clase es la implementación típica, pero también es posible definir una propiedad de dependencia en el constructor estático de la clase. Este enfoque podría tener sentido si necesita más de una línea de código para inicializar la propiedad de dependencia.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementación del "contenedor"

Debe llamar la implementación del contenedor <xref:System.Windows.DependencyObject.GetValue%2A> en el `get` implementación, y <xref:System.Windows.DependencyObject.SetValue%2A> en el `set` implementación (la llamada de registro original y el campo se muestran aquí demasiado para mayor claridad).

En circunstancias excepcionales, las implementaciones de contenedores se deben realizar sólo el <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> acciones, respectivamente. La razón se explica en el tema [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md).

Todas las propiedades de dependencia públicas existentes que se proporcionan en las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan este modelo de implementación de contenedor simple; gran parte de la complejidad del funcionamiento de las propiedades de dependencia es de manera inherente un comportamiento del sistema de propiedades, o bien se implementa a través de otros conceptos, como la coerción o las devoluciones de llamada de cambio de propiedad a través de los metadatos de la propiedad.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

De nuevo, por convención, el nombre de la propiedad de contenedor debe ser el mismo que el nombre elegido y asignado como primer parámetro de la <xref:System.Windows.DependencyProperty.Register%2A> llamada que registró la propiedad. Si la propiedad no cumple esta convención, no deshabilitará necesariamente todos los usos posibles, pero encontrará varios problemas importantes:

- Determinados aspectos de los estilos y las plantillas no funcionarán.

- La mayoría de las herramientas y los diseñadores deben basarse en las convenciones de nomenclatura para serializar correctamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], o para proporcionar al entorno del diseñador asistencia para cada propiedad.

- La implementación actual del cargador de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omite completamente los contenedores y se basa en la convención de nomenclatura al procesar los valores de atributo. Para obtener más información, consulte [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Metadatos de propiedad de una nueva propiedad de dependencia

Al registrar una propiedad de dependencia, el registro a través del sistema de propiedades crea un objeto de metadatos que almacena las características de la propiedad. Muchas de estas características tienen valores predeterminados que se establecen si la propiedad se registra con las signaturas simples de <xref:System.Windows.DependencyProperty.Register%2A>. Otras signaturas de <xref:System.Windows.DependencyProperty.Register%2A> le permiten especificar los metadatos que desee al registrar la propiedad. La asignación de metadatos más común para las propiedades de dependencia consiste en asignarles un valor predeterminado, que se aplicará a las nuevas instancias que usen la propiedad.

Si va a crear una propiedad de dependencia que existe en una clase derivada de <xref:System.Windows.FrameworkElement>, puede usar la clase de metadatos más especializada <xref:System.Windows.FrameworkPropertyMetadata> en lugar de la base de <xref:System.Windows.PropertyMetadata> clase. El constructor para la <xref:System.Windows.FrameworkPropertyMetadata> clase tiene varias signaturas, donde puede especificar diversas características de los metadatos en combinación. Si desea especificar solo el valor predeterminado, utilice la firma que toma un único parámetro de tipo <xref:System.Object>. Pase dicho parámetro de objeto como un valor predeterminado específico del tipo para la propiedad (el valor predeterminado proporcionado debe ser el tipo que se proporcionó como el `propertyType` parámetro en el <xref:System.Windows.DependencyProperty.Register%2A> llamar).

Para <xref:System.Windows.FrameworkPropertyMetadata>, también puede especificar marcas de opción de metadatos para la propiedad. Estas marcas se convierten en propiedades discretas en los metadatos de propiedad después del registro y se usan para comunicar ciertos determinantes a otros procesos, como el motor de diseño.

#### <a name="setting-appropriate-metadata-flags"></a>Establecimiento de marcas de metadatos adecuadas

- Si su propiedad (o los cambios en su valor) afecta a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], y en particular afecta a cómo el sistema de diseño debe dimensionar o representar su elemento en una página, conjunto de uno o varios de los siguientes indicadores: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure> indica que un cambio a esta propiedad requiere un cambio en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] representación donde el objeto contenedor puede necesitar más o menos espacio dentro del elemento primario. Por ejemplo, una propiedad "Width" debe tener establecida esta marca.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange> indica que un cambio a esta propiedad requiere un cambio en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de representación que normalmente no requiere un cambio en el espacio dedicado, pero indica que la posición dentro del espacio ha cambiado. Por ejemplo, una propiedad "Alignment" debe tener establecida esta marca.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender> indica que ha habido algún otro cambio que no afectará al diseño y la medida, pero se requiere ninguna otra representación. Un ejemplo sería una propiedad que cambia un color de un elemento existente, como "Background".

  - Estas marcas se usan a menudo como un protocolo en los metadatos para sus propias implementaciones de invalidación de las devoluciones de llamada de diseño o del sistema propiedades. Por ejemplo, es posible que tenga un <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> devolución de llamada que se llamará <xref:System.Windows.UIElement.InvalidateArrange%2A> si cualquier propiedad de la instancia notifica un cambio de valor y tiene <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> como `true` en sus metadatos.

- Algunas propiedades pueden afectar a la representación de características del elemento primario contenedor, más allá de los cambios en el tamaño necesario mencionados anteriormente. Un ejemplo es el <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> propiedad utilizada en el modelo de documentos dinámicos, donde los cambios en esa propiedad pueden cambiar la representación global del documento dinámico que contiene el párrafo. Use <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> o <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> para identificar casos similares en sus propias propiedades.

- De forma predeterminada, las propiedades de dependencia admiten el enlace de datos. Puede deshabilitar deliberadamente el enlace de datos en aquellos casos en que no exista ningún escenario realista para el enlace de datos, o en que el rendimiento del enlace de datos de un objeto de gran tamaño se reconozca como un problema.

- De forma predeterminada, el enlace de datos <xref:System.Windows.Data.Binding.Mode%2A> predeterminado de las propiedades de dependencia para <xref:System.Windows.Data.BindingMode.OneWay>. Siempre puede cambiar el enlace se <xref:System.Windows.Data.BindingMode.TwoWay> por instancia de enlace; para obtener más información, consulte [especificar la dirección del enlace](../data/how-to-specify-the-direction-of-the-binding.md). Pero como autor de la propiedad de dependencia, puede elegir convertir la propiedad use <xref:System.Windows.Data.BindingMode.TwoWay> modo de enlace predeterminada. Un ejemplo de una propiedad de dependencia existente es <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>; el escenario de esta propiedad es el <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> configuración lógica y la composición de <xref:System.Windows.Controls.MenuItem> interactuar con el estilo de tema predeterminado. El <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> lógica de la propiedad utiliza enlace de datos de forma nativa para mantener el estado de la propiedad de acuerdo con otras propiedades de estado y las llamadas a métodos. Otro ejemplo de propiedad que se enlaza <xref:System.Windows.Data.BindingMode.TwoWay> de forma predeterminada es <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>.

- También puede habilitar la herencia de propiedades en una propiedad de dependencia personalizada estableciendo el <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> marca. La herencia de propiedades resulta útil para un escenario en que los elementos primarios y secundarios tienen una propiedad en común, y tiene sentido para los elementos secundarios que tienen ese valor de propiedad concreto establecido en el mismo valor que el elemento primario. Es un ejemplo de propiedad heredable <xref:System.Windows.FrameworkElement.DataContext%2A>, que se usa para las operaciones para habilitar el escenario de maestro y detalles importante para la presentación de los datos de enlace. Mediante la realización de <xref:System.Windows.FrameworkElement.DataContext%2A> heredable, todos los elementos secundarios heredan ese contexto de datos también. Debido a la herencia de valores de propiedad, puede especificar un contexto de datos en la raíz de la aplicación o la página y no es necesario volver a especificarlo para los enlaces de todos los elementos secundarios posibles. <xref:System.Windows.FrameworkElement.DataContext%2A> También es un buen ejemplo para ilustrar que la herencia invalida el valor predeterminado, pero siempre se puede establecer localmente en cualquier elemento secundario determinado; Para obtener más información, consulte [usar el patrón principal-detalle con datos jerárquicos](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). La herencia de valores de propiedad puede presentar un costo de rendimiento y, por tanto, debe usarse con moderación. Para obtener más información, consulte [Herencia de valores de propiedad](property-value-inheritance.md).

- Establecer el <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> marca para indicar si la propiedad de dependencia debe ser detectada o utilizada por los servicios de registro en diario de navegación. Un ejemplo es el <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> propiedad; los elementos seleccionados en una selección de control se debe conservar cuando se navega el historial de registro en diario.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Propiedades de dependencia de sólo lectura

Es posible definir una propiedad de dependencia que sea de solo lectura. Sin embargo, los escenarios para los que podría definir la propiedad como de solo lectura son algo diferentes, del mismo modo que lo es el procedimiento para registrarlos con el sistema de propiedades y exponer el identificador. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Propiedades de dependencia de tipo de colección

Las propiedades de dependencia de tipo de colección presentan algunos problemas de implementación adicionales que se deben tener en cuenta. Para obtener más información, consulte [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Consideraciones de seguridad de las propiedades de dependencia

Las propiedades de dependencia deben declararse como propiedades públicas. Los campos de identificador de las propiedades de dependencia deben declararse como campos estáticos públicos. Aunque intente declarar otros niveles de acceso (como protegidos), una propiedad de dependencia siempre se puede acceder a través del identificador en combinación con las API del sistema de propiedad. Incluso un campo de identificador protegido es potencialmente accesible debido a la determinación de elaboración de informes o el valor de metadatos API que forman parte del sistema de propiedades, como <xref:System.Windows.LocalValueEnumerator>. Para obtener más información, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Propiedades de dependencia y constructores de clase

Existe un principio general en la programación de código administrado (que suelen aplicar las herramientas de análisis de código, como FxCop), según el cual los constructores de clase no deben llamar a métodos virtuales. Esto es debe a que los constructores se pueden llamar como inicialización base de un constructor de clase derivada y la especificación del método virtual a través del constructor puede producirse en un estado de inicialización incompleto de la instancia del objeto que se está construyendo. Al derivar de cualquier clase que ya se deriva de <xref:System.Windows.DependencyObject>, debe tener en cuenta que el propio sistema de propiedades llama y expone internamente los métodos virtuales. Estos métodos virtuales forman parte de los servicios del sistema de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La invalidación de los métodos permite que las clases derivadas participen en la determinación del valor. Para evitar posibles problemas con la inicialización en tiempo de ejecución, no debe establecer valores de propiedades de dependencia dentro de los constructores de clase, a menos que siga un patrón de constructor muy específico. Para obtener más información, consulte [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
- [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md)
- [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
