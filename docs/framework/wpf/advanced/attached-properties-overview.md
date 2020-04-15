---
title: Información general sobre propiedades asociadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 5086401f4616074d364c1d387b751116120d5969
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81388999"
---
# <a name="attached-properties-overview"></a>Información general sobre propiedades asociadas

Una propiedad adjunta es un concepto definido por XAML. Una propiedad adjunta está destinada a usarse como un tipo de propiedad global que se puede establecer en cualquier objeto. En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], las propiedades adjuntas se definen normalmente como una forma especializada de propiedad de dependencia que no tiene el "contenedor" de propiedades convencional.

## <a name="prerequisites"></a>Requisitos previos<a name="prerequisites"></a>

En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender XAML y saber cómo escribir aplicaciones WPFWPF.

## <a name="why-use-attached-properties"></a>Por qué usar propiedades adjuntas<a name="attached_properties_usage"></a>

Un objetivo de una propiedad adjunta es permitir que distintos elementos secundarios especifiquen valores únicos para una propiedad que, en realidad, está definida en un elemento primario. Una aplicación concreta de este escenario es hacer que los elementos secundarios notifiquen al elemento primario cómo se presentarán en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un ejemplo <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> es la propiedad. La <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad se crea como una propiedad adjunta porque está diseñada para <xref:System.Windows.Controls.DockPanel>establecerse <xref:System.Windows.Controls.DockPanel> en elementos que se encuentran dentro de un , en lugar de en sí mismo. La <xref:System.Windows.Controls.DockPanel> clase define <xref:System.Windows.DependencyProperty> el <xref:System.Windows.Controls.DockPanel.DockProperty>campo estático <xref:System.Windows.Controls.DockPanel.GetDock%2A> denominado <xref:System.Windows.Controls.DockPanel.SetDock%2A> y, a continuación, proporciona los métodos y como descriptores de acceso públicos para la propiedad adjunta.

## <a name="attached-properties-in-xaml"></a>Propiedades adjuntas en XAML<a name="attached_properties_xaml"></a>

En XAML, las propiedades adjuntas se establecen mediante la sintaxis *ProveedorDePropiedadAdjunta*.*NombreDePropiedad*

A continuación se muestra un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> ejemplo de cómo se puede establecer en XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Tenga en cuenta que el uso es algo similar a una propiedad estática; Siempre hace referencia <xref:System.Windows.Controls.DockPanel> al tipo que posee y registra la propiedad adjunta, en lugar de hacer referencia a cualquier instancia especificada por name.

Además, dado que una propiedad adjunta en XAML es un atributo que se establece en el marcado, solamente la operación set tiene alguna relevancia. No se puede obtener directamente una propiedad en XAML, aunque hay algunos mecanismos indirectos para comparar valores, como los desencadenadores en estilos (para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementación de propiedades adjuntas en WPF

En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la mayoría de las propiedades adjuntas que existen en WPFWPF tipos que están relacionados con la presentación de la interfaz de usuario se implementan como propiedades de dependencia. Las propiedades adjuntas son un concepto XAML, mientras que las propiedades de dependencia son un concepto DE WPFWPF. Dado que las propiedades adjuntas de WPFWPF son propiedades de dependencia, admiten conceptos de propiedad de dependencia como metadatos de propiedad y valores predeterminados de los metadatos de esa propiedad.

## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Cómo se utilizan las propiedades adjuntas por el tipo de propiedad<a name="howused"></a>

Aunque las propiedades adjuntas se pueden establecer en cualquier objeto, eso no significa automáticamente que establecer la propiedad vaya a producir un resultado tangible ni que otro objeto no pueda usar nunca el valor. Por lo general, las propiedades adjuntas están diseñadas para que los objetos procedentes de una amplia variedad de posibles jerarquías de clases o relaciones lógicas puedan, individualmente, notificar información común del tipo que define la propiedad adjunta. El tipo que define la propiedad adjunta suele seguir uno de estos modelos:

- El tipo que define la propiedad adjunta está diseñado para poder ser el elemento primario de los elementos que establecerán los valores de la propiedad adjunta. A continuación, el tipo itera sus objetos secundarios a través de la lógica interna en alguna estructura de árbol de objetos, obtiene los valores y actúa sobre esos valores de algún modo.

- El tipo que define la propiedad adjunta se usará como el elemento secundario de una variedad de posibles elementos primarios y modelos de contenido.

- El tipo que define la propiedad adjunta representa un servicio. Otros tipos establecen los valores de la propiedad adjunta. A continuación, cuando el elemento que establece la propiedad se evalúa en el contexto del servicio, los valores de la propiedad adjunta se obtienen a través de la lógica interna de la clase de servicio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ejemplo de una propiedad adjunta definida por el elemento primario

El escenario más típico donde WPFWPF define una propiedad adjunta es cuando un elemento primario admite una colección de elementos secundarios y también implementa un comportamiento donde los detalles del comportamiento se notifican individualmente para cada elemento secundario.

<xref:System.Windows.Controls.DockPanel>define <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la propiedad <xref:System.Windows.Controls.DockPanel> adjunta y tiene código de nivel de clase <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>como parte de su lógica de representación (específicamente, y ). Una <xref:System.Windows.Controls.DockPanel> instancia siempre comprobará si alguno de sus elementos <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>secundarios inmediatos ha establecido un valor para . Si es así, esos valores se convierten en la entrada de la lógica de representación que se aplica a ese elemento secundario determinado. Las <xref:System.Windows.Controls.DockPanel> instancias anidadas tratan cada una de sus propias <xref:System.Windows.Controls.DockPanel> colecciones de elementos secundarios inmediatas, pero ese comportamiento es específico de la implementación de cómo procesa <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> los valores. Teóricamente, es posible tener propiedades adjuntas que influyan en los elementos, más allá del elemento primario inmediato. Si <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la propiedad adjunta se establece <xref:System.Windows.Controls.DockPanel> en un elemento que no tiene ningún elemento primario para actuar sobre él, no se produce ningún error o excepción. Esto simplemente significa que se estableció un valor <xref:System.Windows.Controls.DockPanel> de propiedad global, pero no tiene ningún elemento primario actual que pueda consumir la información.

## <a name="attached-properties-in-code"></a>Propiedades adjuntas en código<a name="attached_properties_code"></a>

Las propiedades adjuntas en WPFWPF no tienen los métodos típicos de "envoltorio" de CLR para obtener o establecer fácilmente el acceso. Esto se debe a que la propiedad adjunta no forma necesariamente parte del espacio de nombres CLR para las instancias en las que se establece la propiedad. No obstante, un procesador de XAML debe poder establecer esos valores durante el análisis de XAML. Para admitir un uso efectivo de la propiedad adjunta, el tipo de propietario de la propiedad adjunta debe implementar métodos de descriptor de acceso dedicados en el formulario **Get_PropertyName_** y **Set_PropertyName_**. Estos métodos de descriptor de acceso dedicados también resultan útiles para obtener o establecer la propiedad adjunta en el código. Desde una perspectiva del código, una propiedad adjunta se parece a un campo de respaldo, que presenta descriptores de acceso de métodos en lugar de descriptores de acceso de propiedades. Ese campo de respaldo puede existir en cualquier objeto, en lugar de tener que definirse específicamente.

En el ejemplo siguiente se muestra cómo establecer una propiedad adjunta en el código. En este `myCheckBox` ejemplo, es <xref:System.Windows.Controls.CheckBox> una instancia de la clase.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Similar al caso XAML, si `myCheckBox` no se hubiera `myDockPanel` agregado ya como un elemento secundario de la cuarta línea de código, la <xref:System.Windows.Controls.DockPanel> quinta línea de código no generaría una excepción, pero el valor de propiedad no interactuaría con un elemento primario y, por lo tanto, no haría nada. Solo <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> un valor establecido en un elemento <xref:System.Windows.Controls.DockPanel> secundario combinado con la presencia de un elemento primario provocará un comportamiento eficaz en la aplicación representada. (En este caso, podría establecer la propiedad adjunta y, luego, adjuntarla al árbol. O bien podría establecer la propiedad adjunta después de adjuntarla al árbol. En ambos casos, el resultado es el mismo).

## <a name="attached-property-metadata"></a>Metadatos de propiedad adjunta<a name="attached_properties_metadata"></a>

Al registrar la <xref:System.Windows.FrameworkPropertyMetadata> propiedad, se establece para especificar las características de la propiedad, como si la propiedad afecta a la representación, la medición, etc. Los metadatos de una propiedad adjunta no suelen ser diferentes de los de una propiedad de dependencia. Si especifica un valor predeterminado de una invalidación en los metadatos de la propiedad adjunta, ese valor se convierte en el valor predeterminado de la propiedad adjunta implícita en las instancias de la clase de invalidación. En concreto, su valor predeterminado se notifica si algún proceso consulta el valor de una propiedad adjunta a través del descriptor de acceso del método `Get` de esa propiedad y especifica una instancia de la clase donde se especificaron los metadatos, y el valor de esa propiedad asociada no estaba establecido.

Si quiere habilitar la herencia de valores de propiedad en una propiedad, debe utilizar las propiedades adjuntas en lugar de propiedades de dependencia no adjuntas. Para obtener más información, vea Herencia de valor de [propiedad](property-value-inheritance.md).

## <a name="custom-attached-properties"></a>Propiedades personalizadas adjuntas<a name="custom"></a>

### <a name="when-to-create-an-attached-property"></a>Cuándo crear una propiedad adjunta<a name="create_attached_properties"></a>

Puede crear una propiedad adjunta cuando existe una razón para tener una mecanismo de definición de propiedades disponible para clases distintas de la clase que se define. El escenario más común es el diseño. Ejemplos de propiedades <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>de <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>diseño <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>existentes son , , y . El escenario habilitado aquí es que los elementos que existen como elementos secundarios de los elementos que controlan el diseño pueden expresar los requisitos de diseño para sus elementos primarios de diseño individualmente, cada uno de los cuales define un valor de propiedad para el elemento primario definido como una propiedad adjunta.

Otro escenario para usar una propiedad adjunta es cuando la clase representa un servicio y quiere que las clases puedan integrar el servicio de manera más transparente.

Otro escenario es recibir compatibilidad con Visual Studio WPF Designer, como la edición de **ventanas de propiedades.** Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

Como mencionamos anteriormente, debe realizar el registro como una propiedad adjunta si quiere usar la herencia de valores de propiedad.

### <a name="how-to-create-an-attached-property"></a>Cómo crear una propiedad adjunta<a name="how_do_i_create_attached_properties"></a>

Si la clase está definiendo la propiedad adjunta estrictamente para su uso <xref:System.Windows.DependencyObject>en otros tipos, la clase no tiene que derivar de . Pero es necesario derivar <xref:System.Windows.DependencyObject> de si sigue el modelo general de WPFWPF de tener la propiedad adjunta también ser una propiedad de dependencia.

Defina la propiedad adjunta como una `public static readonly` propiedad de <xref:System.Windows.DependencyProperty>dependencia declarando un campo de tipo . Este campo se define mediante el <xref:System.Windows.DependencyProperty.RegisterAttached%2A> valor devuelto del método. El nombre del campo debe coincidir con el `Property`nombre de la propiedad adjunta, anexado con la cadena , para seguir el patrón WPF establecido de nombrar los campos de identificación frente a las propiedades que representan. El proveedor de propiedades adjunta también debe proporcionar **Get_PropertyName_** estáticos y **métodos de Set_PropertyName_** como descriptores de acceso para la propiedad adjunta; si no lo hace, el sistema de propiedades no podrá utilizar la propiedad adjunta.

> [!NOTE]
> Si omite el descriptor de acceso get de la propiedad adjunta, el enlace de datos de la propiedad no funcionará en herramientas de diseño, como Visual Studio y Blend para Visual Studio.

#### <a name="the-get-accessor"></a>Descriptor de acceso get

La firma del descriptor **de acceso Get_PropertyName_** debe ser:

`public static object GetPropertyName(object target)`

- El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> el método <xref:System.Windows.UIElement>escribe el parámetro como , porque <xref:System.Windows.UIElement> la propiedad adjunta solo está diseñada para establecerse en instancias.

- El valor devuelto puede especificarse como un tipo más específico en la implementación. Por ejemplo, <xref:System.Windows.Controls.DockPanel.GetDock%2A> el método <xref:System.Windows.Controls.Dock>lo escribe como , porque el valor solo se puede establecer en esa enumeración.

#### <a name="the-set-accessor"></a>Descriptor de acceso set

La firma del descriptor de acceso **Set_PropertyName_** debe ser:

`public static void SetPropertyName(object target, object value)`

- El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, <xref:System.Windows.Controls.DockPanel.SetDock%2A> el método <xref:System.Windows.UIElement>lo escribe como , porque la <xref:System.Windows.UIElement> propiedad adjunta solo está diseñada para establecerse en instancias.

- El objeto `value` puede especificarse como un tipo más específico en la implementación. Por ejemplo, <xref:System.Windows.Controls.DockPanel.SetDock%2A> el método <xref:System.Windows.Controls.Dock>lo escribe como , porque el valor solo se puede establecer en esa enumeración. Recuerde que el valor de este método es la entrada procedente del cargador de XAML cuando encuentra la propiedad adjunta en el uso de propiedades adjuntas en un marcado. Esa entrada es el valor especificado como un valor de atributo XAML en el marcado. Por lo tanto, debe existir compatibilidad con la conversión de tipos, el serializador de valores o la extensión de marcado para el tipo que usa, de modo que el tipo adecuado se pueda crear desde el valor del atributo (que, básicamente, es una cadena).

En el ejemplo siguiente se muestra <xref:System.Windows.DependencyProperty.RegisterAttached%2A> el registro de la propiedad de dependencia (mediante el método), así como los descriptores de acceso **Get_PropertyName_** y **Set_PropertyName_.** En el ejemplo, el nombre de la propiedad adjunta es `IsBubbleSource`. Por consiguiente, los descriptores de acceso deben denominarse `GetIsBubbleSource` y `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Atributos de propiedades adjuntas

WPFWPF define varios atributos de .NET que están diseñados para proporcionar información sobre las propiedades adjuntas a los procesos de reflexión y a los usuarios típicos de información de reflexión y propiedad, como los diseñadores. Dado que las propiedades adjuntas tienen un tipo de ámbito ilimitado, los diseñadores necesitan una manera de evitar abrumar a los usuarios con una lista global de todas las propiedades adjuntas que se definen en una implementación de tecnología específica que utiliza XAML. Los atributos de .NET que WPFWPF define para las propiedades adjuntas se pueden usar para definir el ámbito de las situaciones en las que una propiedad adjunta determinada debe mostrarse en una ventana de propiedades. También puede aplicar estos atributos para sus propias propiedades adjuntas personalizadas. El propósito y la sintaxis de los atributos de .NET se describen en las páginas de referencia adecuadas:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## <a name="learning-more-about-attached-properties"></a>Aprender más sobre las propiedades adjuntas<a name="more"></a>

- Para obtener más información acerca de cómo crear una propiedad adjunta, consulte [Registrar una propiedad asociada](how-to-register-an-attached-property.md).

- Para obtener escenarios de uso más avanzados sobre las propiedades de dependencia y las propiedades adjuntas, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).

- Puede registrar una propiedad como una propiedad adjunta y también como una propiedad de dependencia, pero continuar exponiendo las implementaciones de "contenedor". En este caso, la propiedad puede establecerse en ese elemento o en cualquier elemento a través de la sintaxis XAML de la propiedad adjunta. Un ejemplo de una propiedad con un escenario adecuado <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>para los usos estándar y adjunto es .

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.DependencyProperty>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Registrar una propiedad adjunta](how-to-register-an-attached-property.md)
