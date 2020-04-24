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
ms.openlocfilehash: e4117d7add2a34d6d989d9222e7688361cf6b379
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646351"
---
# <a name="custom-dependency-properties"></a>Propiedades de dependencia personalizadas

En este tema se describen las razones por las que los autores de componentes y los desarrolladores de aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] quieren crear la propiedad de dependencia personalizada, y se describen los pasos de implementación y algunas opciones de implementación que pueden mejorar el rendimiento, la facilidad de uso o la versatilidad de la propiedad.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Prerrequisitos

En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y saber cómo escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

<a name="whatis"></a>

## <a name="what-is-a-dependency-property"></a>¿Qué es una propiedad de dependencia?

Puede habilitar lo que de otro modo sería una propiedad de Common Language Runtime (CLR) para admitir estilos, enlace de datos, herencia, animaciones y valores predeterminados implementándolo como una propiedad de dependencia. Las propiedades de dependencia son [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades que <xref:System.Windows.DependencyProperty.Register%2A> se registran <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>con el sistema de <xref:System.Windows.DependencyProperty> propiedades llamando al método (o ) y que están respaldadas por un campo de identificador. Las propiedades de dependencia <xref:System.Windows.DependencyObject> solo <xref:System.Windows.DependencyObject> se pueden usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] por tipos, pero es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bastante alta en la jerarquía de clases, por lo que la mayoría de las clases disponibles en pueden admitir propiedades de dependencia. Para obtener más información acerca de las propiedades de dependencia y algunas de las terminologías y convenciones utilizadas para describirlas en este SDK, vea [Información general](dependency-properties-overview.md)sobre propiedades de dependencia .

<a name="example_dp"></a>

## <a name="examples-of-dependency-properties"></a>Ejemplos de propiedades de dependencia

Entre los ejemplos de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de <xref:System.Windows.Controls.Control.Background%2A> dependencia que <xref:System.Windows.FrameworkElement.Width%2A> se implementan <xref:System.Windows.Controls.TextBox.Text%2A> en las clases se incluyen la propiedad, la propiedad y la propiedad, entre muchos otros. Cada propiedad de dependencia expuesta por una clase <xref:System.Windows.DependencyProperty> tiene un campo estático público correspondiente de tipo expuesto en esa misma clase. Es el identificador de la propiedad de dependencia. El identificador se denomina mediante una convención: el nombre de la propiedad de dependencia con la cadena `Property` anexada. Por ejemplo, <xref:System.Windows.DependencyProperty> el campo <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Control.BackgroundProperty>identificador correspondiente para la propiedad es . El identificador almacena la información sobre la propiedad de dependencia tal como se registró y, <xref:System.Windows.DependencyObject.SetValue%2A>a continuación, el identificador se usa más adelante para otras operaciones que implican la propiedad de dependencia, como llamar a .

Como se mencionó en la información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] general sobre [propiedades](dependency-properties-overview.md)de dependencia , todas las propiedades de dependencia en (excepto la mayoría de las propiedades adjuntas) también son propiedades CLR debido a la implementación "envoltorio". Por lo tanto, desde el código, puede obtener o establecer propiedades de dependencia llamando a descriptores de acceso CLR que definen los contenedores de la misma manera que usaría otras propiedades de CLR. Como consumidor de propiedades de dependencia establecidas, <xref:System.Windows.DependencyObject> <xref:System.Windows.DependencyObject.GetValue%2A> normalmente no se usan los métodos y <xref:System.Windows.DependencyObject.SetValue%2A>, que son el punto de conexión al sistema de propiedades subyacente. En su lugar, la implementación existente <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> de `get` las `set` propiedades CLR ya habrá llamado y dentro de las implementaciones y contenedor de la propiedad, utilizando el campo de identificador correctamente. Si se está implementando una propiedad de dependencia personalizada, a continuación, estará definiendo el contenedor de forma similar.

<a name="backing_with_dp"></a>

## <a name="when-should-you-implement-a-dependency-property"></a>¿Cuándo se debe implementar una propiedad de dependencia?

Al implementar una propiedad en una clase, siempre <xref:System.Windows.DependencyObject>que la clase derive de , <xref:System.Windows.DependencyProperty> tiene la opción de respaldar la propiedad con un identificador y, por lo tanto, convertirla en una propiedad de dependencia. Convertir su propiedad en una propiedad de dependencia no es siempre necesario ni adecuado y dependerá de las necesidades del escenario. A veces, la técnica típica de respaldar la propiedad con un campo privado es adecuada. Sin embargo, deberá implementar la propiedad como una propiedad de dependencia cada vez que quiera que esta admita una o varias de las siguientes funcionalidades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

- Quiere que su propiedad se pueda establecer en un estilo. Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

- Quiere que su propiedad admita el enlace de datos. Para obtener más información sobre las propiedades de dependencia de enlace de datos, consulte [Enlazar las propiedades de dos controles](../data/how-to-bind-the-properties-of-two-controls.md).

- Quiere que su propiedad se pueda establecer con una referencia de recurso dinámico. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

- Quiere heredar un valor de propiedad automáticamente de un elemento primario del árbol de elementos. En este caso, <xref:System.Windows.DependencyProperty.RegisterAttached%2A> regístrese con el método, incluso si también crea un contenedor de propiedades para el acceso CLR. Para más información, vea [Herencia de valores de propiedad](property-value-inheritance.md).

- Quiere que su propiedad se pueda animar. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).

- Quiere que el sistema de propiedades notifique cualquier cambio en el valor anterior de la propiedad debido a acciones del sistema de propiedades, el entorno o el usuario, o a la lectura y el uso de estilos. Al usar los metadatos de la propiedad, la propiedad puede especificar un método de devolución de llamada que se invocará cada vez que el sistema de propiedades determine un cambio definitivo en el valor de la propiedad. Un concepto relacionado es la coerción del valor de propiedad. Para obtener más información, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](dependency-property-callbacks-and-validation.md).

- Quiere usar convenciones de metadatos establecidas que también se usan en los procesos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como notificar si un cambio en un valor de propiedad debe exigir que el sistema de diseño recomponga los elementos visuales de un elemento. O bien quiere poder usar invalidaciones de metadatos para que las clases derivadas puedan cambiar las características basadas en metadatos, como el valor predeterminado.

- Desea que las propiedades de un control personalizado reciban compatibilidad con Visual Studio WPF Designer, como la edición de **ventanas de propiedades.** Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

Al examinar estos escenarios, también debe considerar si puede obtener su escenario mediante la invalidación de los metadatos de una propiedad de dependencia existente, en lugar de hacerlo a través de la implementación de una propiedad completamente nueva. Que una invalidación de metadatos resulte práctica depende de su escenario y del parecido de ese escenario con la implementación en las clases y las propiedades de dependencia existentes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información sobre cómo invalidar los metadatos de las propiedades existentes, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).

<a name="checklist"></a>

## <a name="checklist-for-defining-a-dependency-property"></a>Lista de comprobación para definir una propiedad de dependencia

La definición de una propiedad de dependencia consta de cuatro conceptos distintos. Estos conceptos no son necesariamente procedimientos estrictos, ya que algunos de ellos acaban combinándose en una sola línea de código en la implementación:

- (Opcional) Cree los metadatos de propiedad de la propiedad de dependencia.

- Registre el nombre de propiedad con el sistema de propiedades, y especifique el tipo de propietario y el tipo de valor de propiedad. Especifique también los metadatos de la propiedad, si se usan.

- Defina <xref:System.Windows.DependencyProperty> un identificador `public` `static` `readonly` como un campo en el tipo de propietario.

- Defina una propiedad "wrapper" de CLR cuyo nombre coincida con el nombre de la propiedad de dependencia. Implemente las propiedades y `get` `set` descriptores de acceso "envoltorio" de CLR para conectarse con la propiedad de dependencia que la respalda.

<a name="registering"></a>

### <a name="registering-the-property-with-the-property-system"></a>Registro de la propiedad con el sistema de propiedades

Para que la propiedad sea una propiedad de dependencia, debe registrarla en una tabla (de cuyo mantenimiento se encargue el sistema de propiedades) y asignarle un identificador único, que se usará como calificador en operaciones posteriores del sistema de propiedades. Estas operaciones pueden ser operaciones internas o sus propias API del sistema de propiedades de llamada de código. Para registrar la propiedad, <xref:System.Windows.DependencyProperty.Register%2A> llame al método dentro del cuerpo de la clase (dentro de la clase, pero fuera de cualquier definición de miembro). El campo identificador también <xref:System.Windows.DependencyProperty.Register%2A> lo proporciona la llamada al método, como el valor devuelto. La razón <xref:System.Windows.DependencyProperty.Register%2A> por la que la llamada se realiza fuera de otras definiciones de miembro es porque se usa este valor devuelto para asignar y crear un `public` `static` `readonly` campo de tipo <xref:System.Windows.DependencyProperty> como parte de la clase. Este campo se convierte en el identificador de la propiedad de dependencia.

[!code-csharp[WPFAquariumSln#RegisterAG](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
[!code-vb[WPFAquariumSln#RegisterAG](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]

<a name="nameconventions"></a>

### <a name="dependency-property-name-conventions"></a>Convenciones de nombres de las propiedades de dependencia

Existen convenciones de nomenclatura establecidas con respecto a las propiedades de dependencia que se deben seguir en todas las circunstancias, menos en las excepcionales.

La propiedad de dependencia en sí tendrá un nombre básico, "AquariumGraphic" como <xref:System.Windows.DependencyProperty.Register%2A>en este ejemplo, que se da como el primer parámetro de . Este nombre debe ser único en cada tipo de registro. Las propiedades de dependencia heredadas a través de tipos base ya se consideran parte del tipo de registro; los nombres de las propiedades heredadas no se pueden volver a registrar. Sin embargo, existe una técnica para agregar una clase como propietaria de una propiedad de dependencia, aunque esa propiedad de dependencia no sea heredada. Para obtener más información, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).

Al crear el campo de identificador, asígnele el nombre de la propiedad tal como lo registró, seguido del sufijo `Property`. Este campo es el identificador de la propiedad de dependencia y <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyObject.GetValue%2A> se usará más adelante como entrada para las llamadas y se realizaráen en los contenedores, por cualquier otro [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] acceso de código a la propiedad por su propio código, por cualquier acceso de código externo que permita, por el sistema de propiedades y potencialmente por los procesadores.

> [!NOTE]
> La definición de la propiedad de dependencia en el cuerpo de la clase es la implementación típica, pero también es posible definir una propiedad de dependencia en el constructor estático de la clase. Este enfoque podría tener sentido si necesita más de una línea de código para inicializar la propiedad de dependencia.

<a name="wrapper1"></a>

### <a name="implementing-the-wrapper"></a>Implementación del "contenedor"

La implementación <xref:System.Windows.DependencyObject.GetValue%2A> del `get` contenedor debe <xref:System.Windows.DependencyObject.SetValue%2A> llamar `set` a la implementación y en la implementación (la llamada de registro original y el campo se muestran aquí también para mayor claridad).

En todas las circunstancias, excepto en las <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> excepcionales, las implementaciones del contenedor deben realizar solo las acciones y, respectivamente. La razón se explica en el tema [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md).

Todas las propiedades de dependencia públicas existentes que se proporcionan en las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan este modelo de implementación de contenedor simple; gran parte de la complejidad del funcionamiento de las propiedades de dependencia es de manera inherente un comportamiento del sistema de propiedades, o bien se implementa a través de otros conceptos, como la coerción o las devoluciones de llamada de cambio de propiedad a través de los metadatos de la propiedad.

[!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
[!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]

Una vez más, por convención, el nombre de la propiedad contenedora <xref:System.Windows.DependencyProperty.Register%2A> debe ser el mismo que el nombre elegido y dado como primer parámetro de la llamada que registró la propiedad. Si la propiedad no cumple esta convención, no deshabilitará necesariamente todos los usos posibles, pero encontrará varios problemas importantes:

- Determinados aspectos de los estilos y las plantillas no funcionarán.

- La mayoría de las herramientas y los diseñadores deben basarse en las convenciones de nomenclatura para serializar correctamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], o para proporcionar al entorno del diseñador asistencia para cada propiedad.

- La implementación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] actual del cargador omite los contenedores por completo y se basa en la convención de nomenclatura al procesar valores de atributo. Para obtener más información, consulte [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md).

<a name="metadata"></a>

### <a name="property-metadata-for-a-new-dependency-property"></a>Metadatos de propiedad de una nueva propiedad de dependencia

Al registrar una propiedad de dependencia, el registro a través del sistema de propiedades crea un objeto de metadatos que almacena las características de la propiedad. Muchas de estas características tienen valores predeterminados que se establecen <xref:System.Windows.DependencyProperty.Register%2A>si la propiedad está registrada con las firmas simples de . Otras firmas <xref:System.Windows.DependencyProperty.Register%2A> de le permiten especificar los metadatos que desea al registrar la propiedad. La asignación de metadatos más común para las propiedades de dependencia consiste en asignarles un valor predeterminado, que se aplicará a las nuevas instancias que usen la propiedad.

Si va a crear una propiedad de dependencia <xref:System.Windows.FrameworkElement>que existe en una clase <xref:System.Windows.FrameworkPropertyMetadata> derivada de <xref:System.Windows.PropertyMetadata> , puede usar la clase de metadatos más especializada en lugar de la clase base. El constructor <xref:System.Windows.FrameworkPropertyMetadata> de la clase tiene varias firmas donde puede especificar varias características de metadatos en combinación. Si solo desea especificar el valor predeterminado, utilice la firma <xref:System.Object>que toma un único parámetro de tipo . Pase ese parámetro de objeto como un valor predeterminado específico del tipo para su `propertyType` propiedad <xref:System.Windows.DependencyProperty.Register%2A> (el valor predeterminado proporcionado debe ser el tipo que proporcionó como parámetro en la llamada).

Para <xref:System.Windows.FrameworkPropertyMetadata>, también puede especificar marcas de opción de metadatos para su propiedad. Estas marcas se convierten en propiedades discretas en los metadatos de propiedad después del registro y se usan para comunicar ciertos determinantes a otros procesos, como el motor de diseño.

#### <a name="setting-appropriate-metadata-flags"></a>Establecimiento de marcas de metadatos adecuadas

- Si su propiedad (o cambios [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]en su valor) afecta a la , y en particular afecta a cómo el <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>sistema <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>de diseño debe ajustar el tamaño o representar el elemento en una página, establezca uno o varios de los siguientes indicadores: , , .

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>indica que un cambio en esta propiedad [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requiere un cambio en la representación donde el objeto contenedor puede requerir más o menos espacio dentro del elemento primario. Por ejemplo, una propiedad "Width" debe tener establecida esta marca.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>indica que un cambio en esta propiedad [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requiere un cambio en la representación que normalmente no requiere un cambio en el espacio dedicado, pero indica que el posicionamiento dentro del espacio ha cambiado. Por ejemplo, una propiedad "Alignment" debe tener establecida esta marca.

  - <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>indica que se ha producido algún otro cambio que no afectará al diseño y la medida, pero requiere otro procesamiento. Un ejemplo sería una propiedad que cambia un color de un elemento existente, como "Background".

  - Estas marcas se usan a menudo como un protocolo en los metadatos para sus propias implementaciones de invalidación de las devoluciones de llamada de diseño o del sistema propiedades. Por ejemplo, puede <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> tener una <xref:System.Windows.UIElement.InvalidateArrange%2A> devolución de llamada que llamará si <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> alguna `true` propiedad de la instancia notifica un cambio de valor y tiene como metadatos.

- Algunas propiedades pueden afectar a la representación de características del elemento primario contenedor, más allá de los cambios en el tamaño necesario mencionados anteriormente. Un ejemplo <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> es la propiedad utilizada en el modelo de documento de flujo, donde los cambios en esa propiedad pueden cambiar la representación general del documento de flujo que contiene el párrafo. Utilice <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> o para identificar casos similares en sus propias propiedades.

- De forma predeterminada, las propiedades de dependencia admiten el enlace de datos. Puede deshabilitar deliberadamente el enlace de datos en aquellos casos en que no exista ningún escenario realista para el enlace de datos, o en que el rendimiento del enlace de datos de un objeto de gran tamaño se reconozca como un problema.

- De forma predeterminada, el enlace <xref:System.Windows.Data.Binding.Mode%2A> <xref:System.Windows.Data.BindingMode.OneWay>de datos para las propiedades de dependencia tiene como valor predeterminado . Siempre puede cambiar el <xref:System.Windows.Data.BindingMode.TwoWay> enlace para que sea por instancia de enlace; para obtener más información, vea [Especificar la dirección del enlace](../data/how-to-specify-the-direction-of-the-binding.md). Pero como autor de la propiedad de dependencia, puede elegir hacer que la propiedad use <xref:System.Windows.Data.BindingMode.TwoWay> el modo de enlace de forma predeterminada. Un ejemplo de una <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>propiedad de dependencia existente es ; el escenario de esta <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> propiedad es que la <xref:System.Windows.Controls.MenuItem> lógica de configuración y la composición de interactuar con el estilo de tema predeterminado. La <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> lógica de propiedad utiliza el enlace de datos de forma nativa para mantener el estado de la propiedad de acuerdo con otras propiedades de estado y llamadas a métodos. Otra propiedad de <xref:System.Windows.Data.BindingMode.TwoWay> ejemplo que <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>se enlaza de forma predeterminada es .

- También puede habilitar la herencia de propiedades <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> en una propiedad de dependencia personalizada estableciendo la marca. La herencia de propiedades resulta útil para un escenario en que los elementos primarios y secundarios tienen una propiedad en común, y tiene sentido para los elementos secundarios que tienen ese valor de propiedad concreto establecido en el mismo valor que el elemento primario. Una propiedad heredable de ejemplo es <xref:System.Windows.FrameworkElement.DataContext%2A>, que se utiliza para las operaciones de enlace para habilitar el escenario maestro-detalle importante para la presentación de datos. Al <xref:System.Windows.FrameworkElement.DataContext%2A> hacer heredable, los elementos secundarios también heredan ese contexto de datos. Debido a la herencia de valores de propiedad, puede especificar un contexto de datos en la raíz de la aplicación o la página y no es necesario volver a especificarlo para los enlaces de todos los elementos secundarios posibles. <xref:System.Windows.FrameworkElement.DataContext%2A>también es un buen ejemplo para ilustrar que la herencia invalida el valor predeterminado, pero siempre se puede establecer localmente en cualquier elemento secundario determinado; Para obtener más información, consulte [Usar el patrón de detalle maestro con datos jerárquicos](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). La herencia de valores de propiedad puede presentar un costo de rendimiento y, por tanto, debe usarse con moderación. Para obtener más información, consulte [Herencia de valores de propiedad](property-value-inheritance.md).

- Establezca <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> la marca para indicar si los servicios de registro en diario de navegación deben detectar o usar la propiedad de dependencia. Un ejemplo <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> es la propiedad; cualquier elemento seleccionado en un control de selección debe conservarse cuando se navega por el historial de registro en diario.

<a name="RODP"></a>

## <a name="read-only-dependency-properties"></a>Propiedades de dependencia de sólo lectura

Es posible definir una propiedad de dependencia que sea de solo lectura. Sin embargo, los escenarios para los que podría definir la propiedad como de solo lectura son algo diferentes, del mismo modo que lo es el procedimiento para registrarlos con el sistema de propiedades y exponer el identificador. Para obtener más información, consulte [Propiedades de dependencia de solo lectura](read-only-dependency-properties.md).

<a name="CTDP"></a>

## <a name="collection-type-dependency-properties"></a>Propiedades de dependencia de tipo de colección

Las propiedades de dependencia de tipo de colección presentan algunos problemas de implementación adicionales que se deben tener en cuenta. Para obtener más información, consulte [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md).

<a name="SecurityC"></a>

## <a name="dependency-property-security-considerations"></a>Consideraciones de seguridad de las propiedades de dependencia

Las propiedades de dependencia deben declararse como propiedades públicas. Los campos de identificador de las propiedades de dependencia deben declararse como campos estáticos públicos. Incluso si intenta declarar otros niveles de acceso (como protected), siempre se puede tener acceso a una propiedad de dependencia a través del identificador en combinación con las API del sistema de propiedades. Incluso un campo de identificador protegido es potencialmente accesible debido a informes de <xref:System.Windows.LocalValueEnumerator>metadatos o API de determinación de valores que forman parte del sistema de propiedades, como . Para obtener más información, consulte [Seguridad de las propiedades de dependencia](dependency-property-security.md).

<a name="DPCtor"></a>

## <a name="dependency-properties-and-class-constructors"></a>Propiedades de dependencia y constructores de clase

Existe un principio general en la programación de código administrado (que suelen aplicar las herramientas de análisis de código, como FxCop), según el cual los constructores de clase no deben llamar a métodos virtuales. Esto es debe a que los constructores se pueden llamar como inicialización base de un constructor de clase derivada y la especificación del método virtual a través del constructor puede producirse en un estado de inicialización incompleto de la instancia del objeto que se está construyendo. Al derivar de cualquier clase que <xref:System.Windows.DependencyObject>ya se deriva de , debe tener en cuenta que el propio sistema de propiedades llama y expone métodos virtuales internamente. Estos métodos virtuales forman parte de los servicios del sistema de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La invalidación de los métodos permite que las clases derivadas participen en la determinación del valor. Para evitar posibles problemas con la inicialización en tiempo de ejecución, no debe establecer valores de propiedades de dependencia dentro de los constructores de clase, a menos que siga un patrón de constructor muy específico. Para obtener más información, consulte [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
- [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md)
- [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
