---
title: "Informaci&#243;n general sobre propiedades asociadas | Microsoft Docs"
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
  - "propiedades asociadas [WPF Designer]"
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Informaci&#243;n general sobre propiedades asociadas
Una propiedad adjunta es un concepto definido por XAML.  Las propiedades asociadas están destinadas a utilizarse como un tipo de propiedad global configurable en cualquier objeto.  En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], las propiedades asociadas son normalmente definido como una forma especializada de propiedad de dependencia que no tiene el “contenedor” de propiedad convencional.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se asume que entiende las propiedades de dependencia desde la perspectiva de un consumidor de las propiedades de dependencia existentes en las clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para seguir los ejemplos de este tema, también debería entender XAML y saber escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  
  
<a name="attached_properties_usage"></a>   
## Por qué usar propiedades asociadas  
 Uno de los propósitos de una propiedad asociada es permitir que los diferentes elementos secundarios especifiquen valores únicos para una propiedad que en realidad está definida en un elemento primario.  Una aplicación concreta de este escenario es hacer que los elementos secundarios informen al elemento primario de cómo se presentarán en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Un ejemplo es la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>.  La propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> se crea como una propiedad adjunta porque se ha diseñado para establecerse en elementos contenidos dentro de un objeto <xref:System.Windows.Controls.DockPanel>, en lugar de en el propio objeto <xref:System.Windows.Controls.DockPanel>.  La clase <xref:System.Windows.Controls.DockPanel> define el campo estático <xref:System.Windows.DependencyProperty> denominado <xref:System.Windows.Controls.DockPanel.DockProperty> y, a continuación, proporciona los métodos <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> como descriptores de acceso públicos para la [propiedad asociada](GTMT).  
  
<a name="attached_properties_xaml"></a>   
## Propiedades asociadas en XAML  
 En XAML, las propiedades adjuntas se establecen usando la sintaxis *ProveedorDePropiedadAdjunta*.*PropertyName*.  
  
 A continuación, se muestra un ejemplo de cómo se puede establecer <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> en XAML:  
  
 [!code-xml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 Observe que el uso es similar a una propiedad estática; siempre se hace referencia al tipo <xref:System.Windows.Controls.DockPanel> que posee y registra la [propiedad asociada](GTMT), en lugar de hacer referencia a ninguna instancia especificada por nombre.  
  
 Además, dado que una propiedad asociada en XAML es un atributo que se establece en el marcado, solamente la operación Set tiene alguna relevancia.  No puede obtener directamente una propiedad en XAML, aunque hay algunos mecanismos indirectos para comparar valores, como desencadenadores en estilos \(para ver más detalles, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)\).  
  
### Implementación de propiedad asociada en WPF  
 En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la mayoría de las propiedades asociadas que existen en los tipos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] relacionados con la presentación de la interfaz de usuario se implementan como propiedades de dependencia.  Las propiedades adjuntas son un concepto de XAML, mientras que las propiedades de dependencia son un concepto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  Dado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] adjunta propiedades son propiedades de dependencia, admiten conceptos de la propiedad de dependencia como metadatos de propiedad, y los valores predeterminados de metadatos de propiedad.  
  
<a name="howused"></a>   
## Cómo el tipo propietario utiliza las propiedades asociadas  
 Aunque las propiedades asociadas son configurables en cualquier objeto, eso no significa automáticamente que la configuración de la propiedad vaya a producir un resultado tangible, o ni que el valor vaya a ser usado alguna vez por otro objeto.  Generalmente, las propiedades adjuntas se conciben de modo que objetos procedentes de una amplia variedad de posibles jerarquías de clases o relaciones lógicas puedan proporcionar información común, cada uno de ellos, al tipo que define la propiedad adjunta.  El tipo que define la propiedad asociada sigue normalmente uno de estos modelos:  
  
-   El tipo que define la propiedad asociada se ha diseñado de modo que pueda ser el elemento primario de los elementos que establecerán los valores de la propiedad asociada.  El tipo recorre a continuación en iteración sus objetos secundarios mediante lógica interna respecto de alguna estructura de árbol de objetos, obtiene los valores y actúa sobre esos valores de alguna manera.  
  
-   El tipo que define la propiedad asociada se utilizará como elemento secundario para una variedad de posibles elementos principales y modelos de contenido.  
  
-   El tipo que define la propiedad asociada representa un servicio.  Otros tipos establecen valores para la propiedad asociada.  A continuación, cuando el elemento que estableció la propiedad se evalúa en el contexto del servicio, los valores de propiedad asociados se obtienen a través de lógica interna de la clase de servicio.  
  
### Ejemplo de una propiedad asociada definida por el elemento primario  
 El escenario más típico donde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define una propiedad asociada es cuando un elemento primario admite una colección de elementos secundarios, y también implementa un comportamiento donde los características del comportamiento se indican individualmente para cada elemento secundario.  
  
 <xref:System.Windows.Controls.DockPanel> define la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> propiedad asociada y <xref:System.Windows.Controls.DockPanel> tiene código del nivel de clase como parte de su lógica de representación \(específicamente, <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> y <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>\).  Una instancia de <xref:System.Windows.Controls.DockPanel> siempre comprobará si cualquiera de sus elementos secundarios inmediatos ha establecido un valor para <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>.  En ese caso, esos valores se convierten en la entrada para la lógica de representación que se aplica a ese elemento secundario en particular.  Cada una de las instancias <xref:System.Windows.Controls.DockPanel> anidadas se ocupa de sus colecciones de elementos secundarios inmediatos, pero ese comportamiento es específico de la manera en que la implementación de <xref:System.Windows.Controls.DockPanel> procesa los valores de <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>.  Es teóricamente posible tener propiedades asociadas que influyan sobre elementos más allá del elemento primario inmediato.  Si la propiedad asociada de <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> se establece en un elemento que no tiene ningún elemento primario <xref:System.Windows.Controls.DockPanel> sobre el que actuar, no se produce ningún error ni ninguna excepción.  Esto significa simplemente que se estableció un valor de propiedad global, pero que no hay ningún elemento primario <xref:System.Windows.Controls.DockPanel> que pueda utilizar la información.  
  
<a name="attached_properties_code"></a>   
## Propiedades asociadas en código  
 Las propiedades asociadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no tienen los métodos "contenedores" típicos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para facilitar el acceso se lectura o escritura.  Esto se debe a que la propiedad asociada no forma parte necesariamente del espacio de nombres [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para las instancias donde se establece la propiedad.  Sin embargo, un procesador XAML debe poder establecer esos valores cuando se analiza XAML.  Para admitir su uso adjunto efectivo de una propiedad, el tipo propietario de la propiedad asociada debe implementar métodos de descriptor de acceso dedicados en el formulario `Get`*PropertyName* y `Set`*PropertyName*.  Estos métodos de descriptor de acceso dedicados también resultan útiles para obtener o establecer la propiedad adjunta en el código.  Desde la perspectiva del código, una propiedad asociada es similar a un campo de apoyo que tiene descriptores de acceso de método en lugar de descriptores de acceso de propiedad; ese campo de apoyo puede existir en cualquier objeto, en lugar de tener que definirse específicamente.  
  
 El ejemplo siguiente muestra cómo puede establecer una propiedad asociada en código.  En este siguiente ejemplo, `myCheckBox` es una instancia de la clase <xref:System.Windows.Controls.CheckBox>.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 Similar al caso de XAML, si `myCheckBox` no se hubiera agregado aún como un elemento secundario de `myDockPanel` por la tercera línea de código, la cuarta línea de código no produciría una excepción, pero el valor de propiedad no interactuaría con <xref:System.Windows.Controls.DockPanel> primario y no haría lo nada.  Solamente un valor <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> establecido en un elemento secundario, combinado con la presencia de un elemento primario <xref:System.Windows.Controls.DockPanel>, producirá un comportamiento efectivo en la aplicación representada.  \(En este caso, se podría establecer la propiedad adjunta y, a continuación, adjuntar al árbol.  O bien, se podría adjuntar al árbol y, a continuación, establecer la propiedad adjunta.  En ambos casos el resultado es el mismo.\)  
  
<a name="attached_properties_metadata"></a>   
## Metadatos de propiedad asociados  
 Al registrar la propiedad, <xref:System.Windows.FrameworkPropertyMetadata> se establece para especificar características de la propiedad como, por ejemplo, si la propiedad afecta a la representación, a la medición, etc.  Los metadatos para una [propiedad asociada](GTMT) no son diferentes, en general, en una [propiedad de dependencia](GTMT).  Si se especifica un valor predeterminado en una invalidación para metadatos de propiedad asociada, ese valor se convierte en el valor predeterminado de la propiedad asociada implícita en instancias de la clase de reemplazo.  El valor predeterminado se indica, específicamente, si algún proceso consulta el valor de una propiedad asociada a través del descriptor de acceso de método `Get` para esa propiedad, especificando una instancia de la clase donde se especificaron los metadatos, y no se ha establecido de ninguna otra manera el valor de esa propiedad asociada.  
  
 Si desea habilitar la herencia del valor de propiedad en una propiedad, es recomendable que utilice propiedades asociadas en lugar de propiedades de dependencia no asociadas.  Para obtener información detallada, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="custom"></a>   
## Propiedades asociadas personalizadas  
  
<a name="create_attached_properties"></a>   
### Cuándo crear una propiedad asociada  
 Se puede crear una [propiedad asociada](GTMT) cuando haya una razón para tener un mecanismo de configuración de propiedad disponible para clases distintas de la clase de la definición.  El escenario más común para ello es el diseño.  Ejemplos de propiedades de diseño existentes son <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> y <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>.  El escenario habilitado aquí es que los elementos que existen como elementos secundarios para los elementos que controlan el diseño pueden expresar individualmente los requisitos de diseño para sus elementos principales de diseño, cada uno de los cuales establece un valor de propiedad que el elemento primario ha definido como una propiedad asociada.  
  
 Otro escenario para utilizar una propiedad asociada es cuando la clase representa un servicio y se desea que las clases puedan integrar el servicio de forma más transparente.  
  
 Hay otro escenario más compatible con [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)][!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], tal como la edición de ventana **Propiedades**.  Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Como ya se ha mencionado, se debe registrar como una propiedad asociada si se desea utilizar la herencia del valor de propiedad.  
  
<a name="how_do_i_create_attached_properties"></a>   
### Cómo crear una propiedad asociada  
 Si la clase está definiendo la [propiedad asociada](GTMT) estrictamente para el uso en otros tipos, no es necesario que la clase derive de <xref:System.Windows.DependencyObject>.  Pero debe derivar de <xref:System.Windows.DependencyObject> si sigue el modelo total de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de tener la propiedad asociada sea también una propiedad de dependencia.  
  
 Defina la propiedad adjunta como una propiedad de dependencia mediante la declaración de un campo `public` `static` `readonly` de tipo <xref:System.Windows.DependencyProperty>.  Para definir este campo, utilice el valor devuelto del método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>.  El nombre de campo debe coincidir con el nombre de propiedad asociado, al que se anexa la cadena `Property`, para seguir el modelo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] establecido de denominar los campos identificadores según las propiedades que representan.  El proveedor de la propiedad asociada también debe proporcionar los métodos estáticos `Get`de*PropertyName* y `Set`de*PropertyName* como descriptores de acceso para la propiedad asociada; el si no lo hace el sistema de propiedades que no puede usar la propiedad asociada.  
  
> [!NOTE]
>  Si omite el descriptor de acceso get de la propiedad adjunta, el enlace de datos en la propiedad no funcionará en las herramientas de diseño, como [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] y Expression Blend.  
  
#### El descriptor de acceso Get  
 La firma para `Get`el descriptor de*PropertyName* debe ser:  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   El objeto `target` se puede especificar como un tipo más específico en la implementación.  Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=fullName> establece el tipo del parámetro como <xref:System.Windows.UIElement>, porque la propiedad asociada solamente está destinada a establecerse en instancias de <xref:System.Windows.UIElement>.  
  
-   El valor devuelto se puede especificar como un tipo más específico en la implementación.  Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.GetDock%2A> define el tipo como <xref:System.Windows.Controls.Dock>, porque el valor solamente se puede establecer en esa enumeración.  
  
#### El descriptor de acceso Set  
 La firma para `Set`el descriptor de*PropertyName* debe ser:  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   El objeto `target` se puede especificar como un tipo más específico en la implementación.  Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.SetDock%2A> establece el tipo como <xref:System.Windows.UIElement>, porque la propiedad asociada solamente está destinada a establecerse en instancias de <xref:System.Windows.UIElement>.  
  
-   El objeto `value` se puede especificar como un tipo más específico en la implementación.  Por ejemplo, el método <xref:System.Windows.Controls.DockPanel.SetDock%2A> define el tipo como <xref:System.Windows.Controls.Dock>, porque el valor solamente se puede establecer en esa enumeración.  Recuerde que el valor para este método es la entrada procedente de cargador de XAML cuando encuentra la propiedad asociada en un uso de propiedad asociada en el marcado.  Esa entrada es el valor especificado como valor de atributo de XAML en el marcado.  Por consiguiente, debe haber compatibilidad con conversión de tipos, serializador de valor o extensión de marcado para el tipo que se utilice, de modo que se pueda crear el tipo adecuado a partir del valor del atributo \(que, en última instancia, no es nada más que una cadena\).  
  
 El ejemplo siguiente se muestra el registro de propiedades de dependencia \(mediante el método de <xref:System.Windows.DependencyProperty.RegisterAttached%2A> \), así `Get`como a los descriptores de*PropertyName* y `Set`de*PropertyName* .  En el ejemplo, el nombre de la propiedad asociada es `IsBubbleSource`.  Por consiguiente, los descriptores de acceso se deben denominar `GetIsBubbleSource` y `SetIsBubbleSource`.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### Atributos de propiedad asociada  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define varios [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] destinados a proporcionar información sobre las propiedades asociadas a los procesos de la reflexión, así como a usuarios típicos de reflexión e información de propiedad tales como los diseñadores.  Dado que las propiedades adjuntas tienen un tipo de ámbito ilimitado, los diseñadores necesitan una manera de evitar abrumar a los usuarios con una lista global de todas las propiedades asociadas que se definen en una implementación concreta de la tecnología que utiliza XAML.  Los [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] que define [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para las propiedades asociadas se pueden utilizar para definir el ámbito en aquellas situaciones en las que una propiedad asociada dada deba mostrarse en una ventana de propiedades.  También se puede considerar la aplicación de estos atributos para propiedades asociadas propias.  El propósito y la sintaxis de los [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] se describen en las páginas de referencia adecuadas:  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## Obtener más información sobre propiedades asociadas  
  
-   Para obtener más información sobre cómo crear una propiedad asociada, vea [Registrar una propiedad asociada](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   Para ver escenarios de uso más avanzado para las propiedades de dependencia y las propiedades asociadas, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   También es posible registrar una propiedad como una propiedad asociada y como una propiedad de dependencia, pero continuar exponiendo las implementaciones "contenedoras".  En este caso, la propiedad se puede establecer en ese elemento, o en cualquier otro con el XAML adjunta sintaxis de propiedad.  Un ejemplo de una propiedad con un escenario adecuado para usos estándar y asociados es <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.DependencyProperty>   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Registrar una propiedad asociada](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)