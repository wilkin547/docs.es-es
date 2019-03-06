---
title: Información general sobre propiedades asociadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: de17fb30358bdf1a8e2a1d6cfc4f5f80fefa1268
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370129"
---
# <a name="attached-properties-overview"></a>Información general sobre propiedades asociadas

Una propiedad adjunta es un concepto definido por XAML. Una propiedad adjunta está destinada a usarse como un tipo de propiedad global que se puede establecer en cualquier objeto. En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], las propiedades adjuntas se definen normalmente como una forma especializada de propiedad de dependencia que no tiene el "contenedor" de propiedades convencional.

## Requisitos previos <a name="prerequisites"></a>

En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe entender XAML y saber cómo escribir aplicaciones de WPF.

## ¿Por qué usar las propiedades adjuntas <a name="attached_properties_usage"></a>

Un objetivo de una propiedad adjunta es permitir que distintos elementos secundarios especifiquen valores únicos para una propiedad que, en realidad, está definida en un elemento primario. Una aplicación concreta de este escenario es hacer que los elementos secundarios notifiquen al elemento primario cómo se presentarán en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un ejemplo es el <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad. El <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad se crea como una propiedad adjunta porque está diseñado para establecerse en elementos que están dentro de un <xref:System.Windows.Controls.DockPanel>, en lugar de en <xref:System.Windows.Controls.DockPanel> propio. El <xref:System.Windows.Controls.DockPanel> clase define estático <xref:System.Windows.DependencyProperty> campo denominado <xref:System.Windows.Controls.DockPanel.DockProperty>y, a continuación, se proporciona el <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> métodos como descriptores de acceso públicos para la propiedad adjunta.

## Propiedades adjuntas en XAML <a name="attached_properties_xaml"></a>

En XAML, las propiedades adjuntas se establecen mediante la sintaxis *ProveedorDePropiedadAdjunta*.*NombreDePropiedad*

El siguiente es un ejemplo de cómo se puede establecer <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> en XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Tenga en cuenta que el uso es algo similar a una propiedad estática; siempre se hace referencia el tipo <xref:System.Windows.Controls.DockPanel> que posee y registra la propiedad adjunta, en lugar de hacer referencia a cualquier instancia especificada por nombre.

Además, dado que una propiedad adjunta en XAML es un atributo que se establece en el marcado, solamente la operación set tiene alguna relevancia. No se puede obtener directamente una propiedad en XAML, aunque hay algunos mecanismos indirectos para comparar valores, como los desencadenadores en estilos (para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md)).

### <a name="attached-property-implementation-in-wpf"></a>Implementación de propiedades adjuntas en WPF

En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la mayoría de las propiedades adjuntas que existen en los tipos WPF que están relacionadas con la presentación de la interfaz de usuario se implementan como propiedades de dependencia. Las propiedades adjuntas son un concepto XAML, mientras que las propiedades de dependencia son un concepto WPF. Dado que las propiedades de WPF conectado son las propiedades de dependencia, admiten los conceptos de propiedad de dependencia como metadatos de las propiedades y los valores predeterminados de los metadatos de esa propiedad.

## Cómo las propiedades adjuntas se utilizan el tipo de propietario <a name="howused"></a>

Aunque las propiedades adjuntas se pueden establecer en cualquier objeto, eso no significa automáticamente que establecer la propiedad vaya a producir un resultado tangible ni que otro objeto no pueda usar nunca el valor. Por lo general, las propiedades adjuntas están diseñadas para que los objetos procedentes de una amplia variedad de posibles jerarquías de clases o relaciones lógicas puedan, individualmente, notificar información común del tipo que define la propiedad adjunta. El tipo que define la propiedad adjunta suele seguir uno de estos modelos:

-   El tipo que define la propiedad adjunta está diseñado para poder ser el elemento primario de los elementos que establecerán los valores de la propiedad adjunta. A continuación, el tipo itera sus objetos secundarios a través de la lógica interna en alguna estructura de árbol de objetos, obtiene los valores y actúa sobre esos valores de algún modo.

-   El tipo que define la propiedad adjunta se usará como el elemento secundario de una variedad de posibles elementos primarios y modelos de contenido.

-   El tipo que define la propiedad adjunta representa un servicio. Otros tipos establecen los valores de la propiedad adjunta. A continuación, cuando el elemento que establece la propiedad se evalúa en el contexto del servicio, los valores de la propiedad adjunta se obtienen a través de la lógica interna de la clase de servicio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Ejemplo de una propiedad adjunta definida por el elemento primario

El escenario más típico donde WPF define una propiedad adjunta es cuando un elemento primario es compatible con una colección de elementos secundarios y también implementa un comportamiento donde se notifican individualmente los detalles del comportamiento de cada elemento secundario.

<xref:System.Windows.Controls.DockPanel> define el <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta, y <xref:System.Windows.Controls.DockPanel> tiene código de nivel de clase como parte de su lógica de representación (específicamente, <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> y <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Un <xref:System.Windows.Controls.DockPanel> instancia siempre comprobará si alguno de sus elementos secundarios inmediatos tiene establecido un valor para <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Si es así, esos valores se convierten en la entrada de la lógica de representación que se aplica a ese elemento secundario determinado. Anidar <xref:System.Windows.Controls.DockPanel> instancias cada tratan sus propias colecciones de elementos secundarios inmediatos, pero ese comportamiento es específico de la implementación a la forma <xref:System.Windows.Controls.DockPanel> procesos <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valores. Teóricamente, es posible tener propiedades adjuntas que influyan en los elementos, más allá del elemento primario inmediato. Si el <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta se establece en un elemento que no tiene ningún <xref:System.Windows.Controls.DockPanel> se genera el elemento primario va a actuar, ningún error o excepción. Esto significa simplemente que se estableció un valor de propiedad global, pero no tiene ningún actual <xref:System.Windows.Controls.DockPanel> primario que podría consumir la información.

## Propiedades adjuntas en código <a name="attached_properties_code"></a>

Las propiedades adjuntas en WPF no tiene el típico [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] métodos "contenedor" para el acceso fácil de obtener o establecer. Esto se debe a que la propiedad adjunta no forma parte necesariamente del espacio de nombres de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para las instancias con la propiedad establecida. No obstante, un procesador de XAML debe poder establecer esos valores durante el análisis de XAML. Para admitir el uso de una propiedad adjunta efectivo, el tipo de propietario de la propiedad adjunta debe implementar métodos de descriptor de acceso dedicados en el formulario **Get_PropertyName_** y **Set_PropertyName_**. Estos métodos de descriptor de acceso dedicados también resultan útiles para obtener o establecer la propiedad adjunta en el código. Desde una perspectiva del código, una propiedad adjunta se parece a un campo de respaldo, que presenta descriptores de acceso de métodos en lugar de descriptores de acceso de propiedades. Ese campo de respaldo puede existir en cualquier objeto, en lugar de tener que definirse específicamente.

En el ejemplo siguiente se muestra cómo establecer una propiedad adjunta en el código. En este ejemplo, `myCheckBox` es una instancia de la <xref:System.Windows.Controls.CheckBox> clase.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Caso de forma similar del XAML, si `myCheckBox` tenía no ya se ha agregado como un elemento secundario de `myDockPanel` mediante la tercera línea de código, la cuarta línea de código no generaría una excepción, pero el valor de propiedad no interactuaría con un <xref:System.Windows.Controls.DockPanel> primario y, por tanto, no funcionará. Solo un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valor establecido en un elemento secundario combinado con la presencia de un <xref:System.Windows.Controls.DockPanel> elemento primario provocará un comportamiento eficaz en la aplicación representada. (En este caso, podría establecer la propiedad adjunta y, luego, adjuntarla al árbol. O bien podría establecer la propiedad adjunta después de adjuntarla al árbol. En ambos casos, el resultado es el mismo).

## Metadatos de propiedad adjunta <a name="attached_properties_metadata"></a>

Al registrar la propiedad, <xref:System.Windows.FrameworkPropertyMetadata> se establece para especificar características de la propiedad, por ejemplo, si la propiedad afecta a la representación, medida y así sucesivamente. Los metadatos de una propiedad adjunta no suelen ser diferentes de los de una propiedad de dependencia. Si especifica un valor predeterminado de una invalidación en los metadatos de la propiedad adjunta, ese valor se convierte en el valor predeterminado de la propiedad adjunta implícita en las instancias de la clase de invalidación. En concreto, su valor predeterminado se notifica si algún proceso consulta el valor de una propiedad adjunta a través del descriptor de acceso del método `Get` de esa propiedad y especifica una instancia de la clase donde se especificaron los metadatos, y el valor de esa propiedad asociada no estaba establecido.

Si quiere habilitar la herencia de valores de propiedad en una propiedad, debe utilizar las propiedades adjuntas en lugar de propiedades de dependencia no adjuntas. Para obtener información detallada, consulte [Herencia de valores de propiedad](property-value-inheritance.md).

## Propiedades adjuntas personalizadas <a name="custom"></a>

### Cuándo crear una propiedad adjunta <a name="create_attached_properties"></a>

Puede crear una propiedad adjunta cuando existe una razón para tener una mecanismo de definición de propiedades disponible para clases distintas de la clase que se define. El escenario más común es el diseño. Ejemplos de propiedades de diseño existentes son <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, y <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. El escenario habilitado aquí es que los elementos que existen como elementos secundarios de los elementos que controlan el diseño pueden expresar los requisitos de diseño para sus elementos primarios de diseño individualmente, cada uno de los cuales define un valor de propiedad para el elemento primario definido como una propiedad adjunta.

Otro escenario para usar una propiedad adjunta es cuando la clase representa un servicio y quiere que las clases puedan integrar el servicio de manera más transparente.

Otro escenario es recibir soporte técnico de Visual Studio WPF Designer, como **propiedades** edición de la ventana. Para obtener más información, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).

Como mencionamos anteriormente, debe realizar el registro como una propiedad adjunta si quiere usar la herencia de valores de propiedad.

### Cómo crear una propiedad adjunta <a name="how_do_i_create_attached_properties"></a>

Si la clase está definiendo la propiedad adjunta estrictamente para su uso en otros tipos, la clase no tiene que derivar <xref:System.Windows.DependencyObject>. Pero debe derivar de <xref:System.Windows.DependencyObject> si sigue el modelo general de WPF de tener la propiedad adjunta también ser una propiedad de dependencia.

Defina la propiedad adjunta como una propiedad de dependencia declarando un `public static readonly` campo de tipo <xref:System.Windows.DependencyProperty>. Este campo se define mediante el valor devuelto de la <xref:System.Windows.DependencyProperty.RegisterAttached%2A> método. El nombre del campo debe coincidir con el nombre de propiedad adjunta, anexado la cadena `Property`, seguir el patrón establecido de WPF de asignación de nombres de los campos que identifican frente a las propiedades que representan. El proveedor de propiedades adjuntas debe proporcionar también estático **Get_PropertyName_** y **Set_PropertyName_** métodos como descriptores de acceso para la propiedad adjunta; si no lo hace esto dará como resultado de la propiedad sistema no podrá usar la propiedad adjunta.

> [!NOTE]
> Si se omite el descriptor de acceso de la propiedad adjunta get, enlace de datos en la propiedad no funcionará en las herramientas de diseño, como Visual Studio y Expression Blend.

#### <a name="the-get-accessor"></a>Descriptor de acceso get

La firma para el **Get_PropertyName_** descriptor de acceso debe ser:

`public static object GetPropertyName(object target)`

-   El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> método el tipo del parámetro como <xref:System.Windows.UIElement>, porque la propiedad adjunta solo debe establecerse en <xref:System.Windows.UIElement> instancias.

-   El valor devuelto puede especificarse como un tipo más específico en la implementación. Por ejemplo, el <xref:System.Windows.Controls.DockPanel.GetDock%2A> tipos de método como <xref:System.Windows.Controls.Dock>, porque el valor solo puede establecerse en esa enumeración.

#### <a name="the-set-accessor"></a>Descriptor de acceso set

La firma para el **Set_PropertyName_** descriptor de acceso debe ser:

`public static void SetPropertyName(object target, object value)`

-   El objeto `target` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el <xref:System.Windows.Controls.DockPanel.SetDock%2A> tipos de método como <xref:System.Windows.UIElement>, porque la propiedad adjunta solo debe establecerse en <xref:System.Windows.UIElement> instancias.

-   El objeto `value` puede especificarse como un tipo más específico en la implementación. Por ejemplo, el <xref:System.Windows.Controls.DockPanel.SetDock%2A> tipos de método como <xref:System.Windows.Controls.Dock>, porque el valor solo puede establecerse en esa enumeración. Recuerde que el valor de este método es la entrada procedente del cargador de XAML cuando encuentra la propiedad adjunta en el uso de propiedades adjuntas en un marcado. Esa entrada es el valor especificado como un valor de atributo XAML en el marcado. Por lo tanto, debe existir compatibilidad con la conversión de tipos, el serializador de valores o la extensión de marcado para el tipo que usa, de modo que el tipo adecuado se pueda crear desde el valor del atributo (que, básicamente, es una cadena).

El ejemplo siguiente muestra el registro de la propiedad de dependencia (mediante el <xref:System.Windows.DependencyProperty.RegisterAttached%2A> método), así como el **Get_PropertyName_** y **Set_PropertyName_** descriptores de acceso. En el ejemplo, el nombre de la propiedad adjunta es `IsBubbleSource`. Por consiguiente, los descriptores de acceso deben denominarse `GetIsBubbleSource` y `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Atributos de propiedades adjuntas

WPF define varios [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] que están diseñadas para proporcionar información sobre las propiedades adjuntas a los procesos de reflexión y a los usuarios típicos de reflexión y la propiedad de información, tales como diseñadores. Dado que las propiedades adjuntas tienen un tipo de ámbito ilimitado, los diseñadores necesitan una manera de evitar abrumar a los usuarios con una lista global de todas las propiedades adjuntas que se definen en una implementación de tecnología específica que utiliza XAML. El [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] que WPF define para las propiedades adjuntas se pueden usar para delimitar las situaciones donde una determinada propiedad adjunta debe mostrarse en una ventana de propiedades. También puede aplicar estos atributos para sus propias propiedades adjuntas personalizadas. El propósito y la sintaxis de [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] se describe en las páginas de referencia correspondientes:

-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Obtener más información sobre las propiedades adjuntas <a name="more"></a>

-   Para obtener más información acerca de cómo crear una propiedad adjunta, consulte [Registrar una propiedad asociada](how-to-register-an-attached-property.md).

-   Para obtener escenarios de uso más avanzados sobre las propiedades de dependencia y las propiedades adjuntas, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).

-   Puede registrar una propiedad como una propiedad adjunta y también como una propiedad de dependencia, pero continuar exponiendo las implementaciones de "contenedor". En este caso, la propiedad puede establecerse en ese elemento o en cualquier elemento a través de la sintaxis XAML de la propiedad adjunta. Un ejemplo de una propiedad con un escenario adecuado para usos estándar y adjuntos es <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Registrar una propiedad asociada](how-to-register-an-attached-property.md)