---
title: Información general sobre propiedades asociadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: cee80ca0880e046870f699f45624df61ee507a47
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919857"
---
# <a name="attached-properties-overview"></a>Información general sobre propiedades asociadas

Una propiedad adjunta es un concepto definido por XAML. Una propiedad adjunta está destinada a usarse como un tipo de propiedad global que se puede establecer en cualquier objeto. En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], las propiedades adjuntas se definen normalmente como una forma especializada de propiedad de dependencia que no tiene el "contenedor" de propiedades convencional.

## Requisitos previos<a name="prerequisites"></a>

En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender XAML y saber cómo escribir aplicaciones de WPF.

## Por qué usar las propiedades adjuntas<a name="attached_properties_usage"></a>

Un objetivo de una propiedad adjunta es permitir que distintos elementos secundarios especifiquen valores únicos para una propiedad que, en realidad, está definida en un elemento primario. Una aplicación concreta de este escenario es hacer que los elementos secundarios notifiquen al elemento primario cómo se presentarán en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un ejemplo es la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. La propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> se crea como una propiedad adjunta porque está diseñada para establecerse en elementos contenidos dentro de un <xref:System.Windows.Controls.DockPanel>, en lugar de en <xref:System.Windows.Controls.DockPanel> mismo. La clase <xref:System.Windows.Controls.DockPanel> define el campo de <xref:System.Windows.DependencyProperty> estático denominado <xref:System.Windows.Controls.DockPanel.DockProperty>y, a continuación, proporciona los métodos <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> como descriptores de acceso públicos para la propiedad adjunta.

## Propiedades adjuntas en XAML<a name="attached_properties_xaml"></a>

En XAML, las propiedades adjuntas se establecen mediante la sintaxis *ProveedorDePropiedadAdjunta*.*NombreDePropiedad*

El siguiente es un ejemplo de cómo puede establecer <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> en XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Tenga en cuenta que el uso es algo similar a una propiedad estática; siempre se hace referencia al tipo <xref:System.Windows.Controls.DockPanel> que posee y registra la propiedad adjunta, en lugar de hacer referencia a cualquier instancia especificada por el nombre.

Además, dado que una propiedad adjunta en XAML es un atributo que se establece en el marcado, solamente la operación set tiene alguna relevancia. No se puede obtener directamente una propiedad en XAML, aunque hay algunos mecanismos indirectos para comparar valores, como los desencadenadores en estilos (para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementación de propiedades adjuntas en WPF

En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la mayoría de las propiedades adjuntas que existen en los tipos de WPF que están relacionados con la presentación de la interfaz de usuario se implementan como propiedades de dependencia. Las propiedades adjuntas son un concepto de XAML, mientras que las propiedades de dependencia son un concepto de WPF. Dado que las propiedades adjuntas de WPF son propiedades de dependencia, admiten conceptos de propiedades de dependencia como metadatos de propiedad y valores predeterminados de esos metadatos de propiedad.

## Cómo usa el tipo propietario las propiedades adjuntas<a name="howused"></a>

Aunque las propiedades adjuntas se pueden establecer en cualquier objeto, eso no significa automáticamente que establecer la propiedad vaya a producir un resultado tangible ni que otro objeto no pueda usar nunca el valor. Por lo general, las propiedades adjuntas están diseñadas para que los objetos procedentes de una amplia variedad de posibles jerarquías de clases o relaciones lógicas puedan, individualmente, notificar información común del tipo que define la propiedad adjunta. El tipo que define la propiedad adjunta suele seguir uno de estos modelos:

- El tipo que define la propiedad adjunta está diseñado para poder ser el elemento primario de los elementos que establecerán los valores de la propiedad adjunta. A continuación, el tipo itera sus objetos secundarios a través de la lógica interna en alguna estructura de árbol de objetos, obtiene los valores y actúa sobre esos valores de algún modo.

- El tipo que define la propiedad adjunta se usará como el elemento secundario de una variedad de posibles elementos primarios y modelos de contenido.

- El tipo que define la propiedad adjunta representa un servicio. Otros tipos establecen los valores de la propiedad adjunta. A continuación, cuando el elemento que establece la propiedad se evalúa en el contexto del servicio, los valores de la propiedad adjunta se obtienen a través de la lógica interna de la clase de servicio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ejemplo de una propiedad adjunta definida por el elemento primario

El escenario más típico en el que WPF define una propiedad adjunta es cuando un elemento primario admite una colección de elementos secundarios, y también implementa un comportamiento en el que los detalles del comportamiento se informan individualmente para cada elemento secundario.

<xref:System.Windows.Controls.DockPanel> define el <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta y <xref:System.Windows.Controls.DockPanel> tiene código de nivel de clase como parte de su lógica de representación (concretamente, <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> y <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Una instancia de <xref:System.Windows.Controls.DockPanel> siempre comprobará si alguno de sus elementos secundarios inmediatos tiene establecido un valor para <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Si es así, esos valores se convierten en la entrada de la lógica de representación que se aplica a ese elemento secundario determinado. Las instancias de <xref:System.Windows.Controls.DockPanel> anidadas tratan sus propias colecciones de elementos secundarios inmediatas, pero ese comportamiento es específico de la implementación de cómo <xref:System.Windows.Controls.DockPanel> procesa los valores <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Teóricamente, es posible tener propiedades adjuntas que influyan en los elementos, más allá del elemento primario inmediato. Si el <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta se establece en un elemento que no tiene <xref:System.Windows.Controls.DockPanel> elemento primario que actúe sobre él, no se produce ningún error o excepción. Esto significa simplemente que se ha establecido un valor de propiedad global, pero no tiene <xref:System.Windows.Controls.DockPanel> primario actual que pueda consumir la información.

## Propiedades adjuntas en el código<a name="attached_properties_code"></a>

Las propiedades adjuntas en WPF no tienen los métodos de "contenedor" de CLR típicos para facilitar el acceso get/set. Esto se debe a que la propiedad adjunta no es necesariamente parte del espacio de nombres CLR para las instancias en las que se establece la propiedad. No obstante, un procesador de XAML debe poder establecer esos valores durante el análisis de XAML. Para admitir el uso de una propiedad adjunta efectiva, el tipo de propietario de la propiedad adjunta debe implementar métodos de descriptor de acceso dedicados en la forma **Get_PropertyName_** y **Set_PropertyName_** . Estos métodos de descriptor de acceso dedicados también resultan útiles para obtener o establecer la propiedad adjunta en el código. Desde una perspectiva del código, una propiedad adjunta se parece a un campo de respaldo, que presenta descriptores de acceso de métodos en lugar de descriptores de acceso de propiedades. Ese campo de respaldo puede existir en cualquier objeto, en lugar de tener que definirse específicamente.

En el ejemplo siguiente se muestra cómo establecer una propiedad adjunta en el código. En este ejemplo, `myCheckBox` es una instancia de la clase <xref:System.Windows.Controls.CheckBox>.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

De forma similar al caso de XAML, si no se ha agregado todavía `myCheckBox` como un elemento secundario de `myDockPanel` por la tercera línea de código, la cuarta línea de código no produciría una excepción, pero el valor de propiedad no interactuaría con un <xref:System.Windows.Controls.DockPanel> primario y, por lo tanto, lo haría relación. Solo un valor <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> establecido en un elemento secundario combinado con la presencia de un elemento primario <xref:System.Windows.Controls.DockPanel> producirá un comportamiento efectivo en la aplicación representada. (En este caso, podría establecer la propiedad adjunta y, luego, adjuntarla al árbol. O bien podría establecer la propiedad adjunta después de adjuntarla al árbol. En ambos casos, el resultado es el mismo).

## Metadatos de propiedad adjunta<a name="attached_properties_metadata"></a>

Al registrar la propiedad, <xref:System.Windows.FrameworkPropertyMetadata> se establece para especificar las características de la propiedad, por ejemplo, si la propiedad afecta a la representación, medida, etc. Los metadatos de una propiedad adjunta no suelen ser diferentes de los de una propiedad de dependencia. Si especifica un valor predeterminado de una invalidación en los metadatos de la propiedad adjunta, ese valor se convierte en el valor predeterminado de la propiedad adjunta implícita en las instancias de la clase de invalidación. En concreto, su valor predeterminado se notifica si algún proceso consulta el valor de una propiedad adjunta a través del descriptor de acceso del método `Get` de esa propiedad y especifica una instancia de la clase donde se especificaron los metadatos, y el valor de esa propiedad asociada no estaba establecido.

Si quiere habilitar la herencia de valores de propiedad en una propiedad, debe utilizar las propiedades adjuntas en lugar de propiedades de dependencia no adjuntas. Para obtener información detallada, consulte [Herencia de valores de propiedad](property-value-inheritance.md).

## Propiedades adjuntas personalizadas<a name="custom"></a>

### Cuándo crear una propiedad adjunta<a name="create_attached_properties"></a>

Puede crear una propiedad adjunta cuando existe una razón para tener una mecanismo de definición de propiedades disponible para clases distintas de la clase que se define. El escenario más común es el diseño. Los ejemplos de propiedades de diseño existentes son <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>y <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. El escenario habilitado aquí es que los elementos que existen como elementos secundarios de los elementos que controlan el diseño pueden expresar los requisitos de diseño para sus elementos primarios de diseño individualmente, cada uno de los cuales define un valor de propiedad para el elemento primario definido como una propiedad adjunta.

Otro escenario para usar una propiedad adjunta es cuando la clase representa un servicio y quiere que las clases puedan integrar el servicio de manera más transparente.

Otro escenario es recibir compatibilidad con Visual Studio WPF Designer, como la edición de la ventana **propiedades** . Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

Como mencionamos anteriormente, debe realizar el registro como una propiedad adjunta si quiere usar la herencia de valores de propiedad.

### Cómo crear una propiedad adjunta<a name="how_do_i_create_attached_properties"></a>

Si la clase está definiendo la propiedad adjunta estrictamente para su uso en otros tipos, la clase no tiene que derivar de <xref:System.Windows.DependencyObject>. Pero debe derivar de <xref:System.Windows.DependencyObject> si sigue el modelo de WPF general de tener la propiedad adjunta también una propiedad de dependencia.

Defina la propiedad adjunta como una propiedad de dependencia declarando un `public static readonly` campo de tipo <xref:System.Windows.DependencyProperty>. Este campo se define con el valor devuelto del método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>. El nombre del campo debe coincidir con el nombre de la propiedad adjunta, anexado con la cadena `Property`, para seguir el modelo de WPF establecido para asignar nombres a los campos de identificación frente a las propiedades que representan. El proveedor de propiedades adjunta también debe proporcionar métodos estáticos **Get_PropertyName_** y **Set_PropertyName_** como descriptores de acceso para la propiedad adjunta. Si no lo hace, el sistema de propiedades no podrá utilizar la propiedad adjunta.

> [!NOTE]
> Si omite el descriptor de acceso get de la propiedad adjunta, el enlace de datos de la propiedad no funcionará en las herramientas de diseño, como Visual Studio y Blend para Visual Studio.

#### <a name="the-get-accessor"></a>Descriptor de acceso get

La firma para el descriptor de acceso **Get_PropertyName_** debe ser:

`public static object GetPropertyName(object target)`

- El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> escribe el parámetro como <xref:System.Windows.UIElement>, porque la propiedad adjunta solo está pensada para establecerse en instancias de <xref:System.Windows.UIElement>.

- El valor devuelto puede especificarse como un tipo más específico en la implementación. Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.GetDock%2A> escribe como <xref:System.Windows.Controls.Dock>, porque el valor solo se puede establecer en esa enumeración.

#### <a name="the-set-accessor"></a>Descriptor de acceso set

La firma para el descriptor de acceso **Set_PropertyName_** debe ser:

`public static void SetPropertyName(object target, object value)`

- El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.SetDock%2A> lo escribe como <xref:System.Windows.UIElement>, porque la propiedad adjunta solo está pensada para establecerse en instancias de <xref:System.Windows.UIElement>.

- El objeto `value` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.SetDock%2A> escribe como <xref:System.Windows.Controls.Dock>, porque el valor solo se puede establecer en esa enumeración. Recuerde que el valor de este método es la entrada procedente del cargador de XAML cuando encuentra la propiedad adjunta en el uso de propiedades adjuntas en un marcado. Esa entrada es el valor especificado como un valor de atributo XAML en el marcado. Por lo tanto, debe existir compatibilidad con la conversión de tipos, el serializador de valores o la extensión de marcado para el tipo que usa, de modo que el tipo adecuado se pueda crear desde el valor del atributo (que, básicamente, es una cadena).

En el ejemplo siguiente se muestra el registro de la propiedad de dependencia (mediante el método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>), así como los descriptores de acceso **Get_PropertyName_** y **Set_PropertyName_** . En el ejemplo, el nombre de la propiedad adjunta es `IsBubbleSource`. Por consiguiente, los descriptores de acceso deben denominarse `GetIsBubbleSource` y `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Atributos de propiedades adjuntas

WPF define varias [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] que están diseñadas para proporcionar información sobre las propiedades adjuntas a los procesos de reflexión y para los usuarios típicos de reflexión e información de propiedades, como los diseñadores. Dado que las propiedades adjuntas tienen un tipo de ámbito ilimitado, los diseñadores necesitan una manera de evitar abrumar a los usuarios con una lista global de todas las propiedades adjuntas que se definen en una implementación de tecnología específica que utiliza XAML. Los [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] que WPF define para las propiedades adjuntas se pueden usar para definir el ámbito de las situaciones en las que se debe mostrar una propiedad adjunta determinada en una ventana Propiedades. También puede aplicar estos atributos para sus propias propiedades adjuntas personalizadas. El propósito y la sintaxis de [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] se describe en las páginas de referencia correspondientes:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Obtener más información sobre las propiedades adjuntas<a name="more"></a>

- Para obtener más información acerca de cómo crear una propiedad adjunta, consulte [Registrar una propiedad asociada](how-to-register-an-attached-property.md).

- Para obtener escenarios de uso más avanzados sobre las propiedades de dependencia y las propiedades adjuntas, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).

- Puede registrar una propiedad como una propiedad adjunta y también como una propiedad de dependencia, pero continuar exponiendo las implementaciones de "contenedor". En este caso, la propiedad puede establecerse en ese elemento o en cualquier elemento a través de la sintaxis XAML de la propiedad adjunta. Un ejemplo de una propiedad con un escenario adecuado para los usos estándar y asociados es <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Registrar una propiedad asociada](how-to-register-an-attached-property.md)
