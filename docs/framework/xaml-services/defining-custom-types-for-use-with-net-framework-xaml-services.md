---
title: Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: be9c0e26574a15279ce89af2c7862abaa8713360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164442"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
Al definir tipos personalizados que son objetos de negocios o son tipos que no tiene una dependencia en marcos de trabajo específicos, hay algunas prácticas recomendadas para XAML que puede seguir. Si sigue estas prácticas, los servicios XAML de .NET Framework y sus lectores XAML y escritores XAML pueden detectar las características XAML de su tipo y asígnele una representación adecuada en un flujo de nodo XAML mediante el sistema de tipos XAML. Este tema describe los procedimientos recomendados para las definiciones de tipo, definiciones de miembros y atribución de CLR de tipos o miembros.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Patrones de constructor y definiciones de tipos para XAML  
 Para la creación de instancias como un elemento de objeto en XAML, una clase personalizada debe cumplir los siguientes requisitos:  
  
-   La clase personalizada debe ser pública y debe exponer un constructor público (sin parámetros) de forma predeterminada. (Vea en la siguiente sección las notas relativas a las estructuras).  
  
-   La clase personalizada no debe ser una clase anidada. El extra "punto" en la ruta de acceso del nombre completo hace que la división del espacio de nombres de clase ambiguo e interfiere con otras características XAML, como las propiedades adjuntas.  
  
 Si un objeto se puede crear instancias como un elemento de objeto, el objeto creado puede rellenar el formulario de elemento de propiedad de las propiedades que toman el objeto como su tipo subyacente.  
  
 Todavía puede proporcionar los valores de objeto para los tipos que no cumplen estos criterios, si habilita un convertidor de valores. Para obtener más información, consulte [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Estructuras  
 Las estructuras son siempre pueden construirse en XAML, por definición de CLR. Esto es porque un compilador CLR crea implícitamente un constructor predeterminado para una estructura. Este constructor inicializa todos los valores de propiedad en sus valores predeterminados.  
  
 En algunos casos, el comportamiento predeterminado de construcción de una estructura no es deseable. Esto puede deberse a la estructura está pensada para rellenar valores y funcionar conceptualmente como una unión. Como una unión, los valores contenidos pueden tener interpretaciones mutuamente excluyentes y, por lo tanto, ninguna de sus propiedades son configurable. Un ejemplo de este tipo de estructura en el vocabulario de WPF es <xref:System.Windows.GridLength>. Tales estructuras deberían implementar un convertidor de tipos para que los valores que pueden expresarse en forma de atributo, utilizando las convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura. La estructura también debería exponer un comportamiento similar por la construcción del código a través de un constructor no predeterminado.  
  
### <a name="interfaces"></a>Interfaces  
 Interfaces se pueden utilizar como tipos subyacentes de miembros. El sistema de tipos XAML comprueba la lista asignable y espera que el objeto que se proporciona como el valor puede asignarse a la interfaz. No hay ningún concepto de cómo la interfaz debe presentarse como un tipo XAML como un tipo asignable pertinente es compatible con los requisitos de la construcción de XAML.  
  
### <a name="factory-methods"></a>Métodos de fábrica  
 Métodos de generador son una característica de XAML 2009. Modifican el principio XAML que los objetos deben tener constructores predeterminados. Métodos de generador no se documentan en este tema. Consulte [x: FactoryMethod (directiva)](x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumeraciones  
 Las enumeraciones tienen el comportamiento de conversión de tipo nativo de XAML. Los nombres de constantes de enumeración especificados en XAML se resuelven en el tipo de enumeración subyacente y devuelven el valor de enumeración a un escritor de objetos XAML.  
  
 XAML admite el uso de marcas de estilo para las enumeraciones con <xref:System.FlagsAttribute> aplicado. Para obtener más información, consulte [XAML detalles de la sintaxis](../wpf/advanced/xaml-syntax-in-detail.md). ([XAML detalles de la sintaxis](../wpf/advanced/xaml-syntax-in-detail.md) está escrito para la audiencia WPF, pero la mayoría de la información de ese tema es pertinente para XAML que no es específico de un marco de trabajo de implementación concreto.)  
  
## <a name="member-definitions"></a>Definiciones de miembros  
 Los tipos pueden definir a miembros para el uso XAML. Es posible que los tipos que definen a los miembros que puede usar XAML incluso si ese tipo específico no es que pueda usar de XAML. Esto es posible debido a la herencia de CLR. Siempre y cuando algún tipo que hereda al miembro es compatible con el uso XAML como un tipo y el miembro admite el uso XAML para su tipo subyacente o tiene una sintaxis XAML nativa disponible, ese miembro es que pueda usar de XAML.  
  
### <a name="properties"></a>Propiedades  
 Si define las propiedades como una propiedad pública de CLR mediante CLR típico `get` y `set` patrones de descriptor de acceso y el idioma apropiado, las palabras clave, el sistema de tipos XAML puede notificar la propiedad como un miembro con la información adecuada se proporciona para <xref:System.Xaml.XamlMember> propiedades, como <xref:System.Xaml.XamlMember.IsReadPublic%2A> y <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Pueden permitir que las propiedades específicas de una sintaxis de texto aplicando <xref:System.ComponentModel.TypeConverterAttribute>. Para obtener más información, consulte [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 En ausencia de una sintaxis de texto o conversión de XAML nativa y en ausencia de más direccionamiento indirecto, como el uso de una extensión de marcado, el tipo de una propiedad (<xref:System.Xaml.XamlMember.TargetType%2A> sistema de tipos en el XAML) debe ser capaz de devolver una instancia a un escritor de objetos XAML tratando el t tipo de destino como un tipo CLR.  
  
 Si utiliza XAML 2009, [x: Reference Markup Extension](x-reference-markup-extension.md) puede usarse para proporcionar valores si no se cumplen las consideraciones anteriores; sin embargo, que es más un problema de uso que un problema de la definición de tipo.  
  
### <a name="events"></a>Eventos  
 Si define los eventos como un evento CLR público, el sistema de tipos XAML puede notificar el evento como un miembro con <xref:System.Xaml.XamlMember.IsEvent%2A> como `true`. Conectar los controladores de eventos no está dentro del ámbito de las capacidades de servicios XAML de .NET Framework; Esto queda en las implementaciones y marcos de trabajo específicos.  
  
### <a name="methods"></a>Métodos  
 Código en línea para los métodos no es una funcionalidad XAML predeterminado. En la mayoría de los casos no referencia directamente a los miembros de método desde XAML y el rol de los métodos en XAML es solo proporcionar compatibilidad con patrones específicos de XAML. [x: FactoryMethod Directive](x-factorymethod-directive.md) es una excepción.  
  
### <a name="fields"></a>Campos  
 Instrucciones de diseño de CLR desaconseja campos no estáticos. Para los campos estáticos, puede tener acceso a los valores de campo estáticos solo [x: Static Markup Extension](x-static-markup-extension.md); en este caso, no realiza ninguna acción especial en la definición de CLR para exponer un campo para [x: Static](x-static-markup-extension.md) usos.  
  
## <a name="attachable-members"></a>Miembros adjuntables  
 Los miembros adjuntables se exponen a XAML a través de un patrón de método de descriptor de acceso en un tipo de definición. El tipo de definición no es necesario que se pueda usar XAML como un objeto. De hecho, es un patrón común declarar una clase de servicio cuya función es el propietario del miembro adjuntable e implementan los comportamientos relacionados, sino también no sirven de ninguna otra función como una representación de la interfaz de usuario. Las secciones siguientes, el marcador de posición *PropertyName* representa el nombre del miembro adjuntable. Ese nombre debe ser válido en el [gramática de XamlName](xamlname-grammar.md).  
  
 Tenga cuidado de conflictos de nombres entre estos modelos y otros métodos de un tipo. Si existe un miembro que coincide con uno de los patrones, se puede interpretar como una ruta de uso de miembro adjuntable con un procesador XAML incluso si no era su intención.  
  
#### <a name="the-getpropertyname-accessor"></a>El descriptor de acceso GetPropertyName  
 La signatura del descriptor de acceso `Get`*NombreDePropiedad* debe ser:  
  
 `public static object Get` *NombreDePropiedad* `(object`  `target` `)`  
  
-   El objeto `target` puede especificarse como un tipo más específico en la implementación. Puede usar para definir el ámbito del uso del miembro adjuntable; los usos fuera del ámbito deseado producirán excepciones de conversión no válida que se exponen a través de un error de análisis XAML. El nombre del parámetro `target` no es un requisito, pero se denomina `target` por convención en la mayoría de las implementaciones.  
  
-   El valor devuelto puede especificarse como un tipo más específico en la implementación.  
  
 Para admitir un <xref:System.ComponentModel.TypeConverter> sintaxis de texto habilitado para el uso de atributos del miembro adjuntable, aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la `Get` *PropertyName* descriptor de acceso. Aplicar a la `get` en lugar de la `set` puede no parecer intuitivo; sin embargo, esta convención puede admitir el concepto de solo lectura que se puede asociar los miembros que son serializables, lo que resulta útil en escenarios del diseñador.  
  
#### <a name="the-setpropertyname-accessor"></a>El descriptor de acceso SetPropertyName  
 La firma para el conjunto de*PropertyName* descriptor de acceso debe ser:  
  
 `public static void Set` *NombreDePropiedad* `(object`  `target` `, object`  `value` `)`  
  
-   La `target` objeto puede especificarse como un tipo más específico en su implementación, con la misma lógica y consecuencias tal como se describe en la sección anterior.  
  
-   El objeto `value` puede especificarse como un tipo más específico en la implementación.  
  
 Recuerde que el valor de este método es la entrada procedente del uso XAML, normalmente en forma de atributo. De forma de atributo debe ser compatibles con la conversión de valor para una sintaxis de texto y el atributo en el `Get` *PropertyName* descriptor de acceso.  
  
### <a name="attachable-member-stores"></a>Los almacenes de miembros adjuntables  
 Los métodos de descriptor de acceso normalmente no son suficientes para proporcionar un medio para colocar los valores del miembro adjuntable en un gráfico de objetos, o para recuperar los valores del gráfico de objetos y serializarlos correctamente. Para proporcionar esta funcionalidad, el `target` objetos en las firmas anteriores del descriptor de acceso deben ser capaces de almacenar los valores. El mecanismo de almacenamiento debe ser coherente con el principio del miembro adjuntable que el miembro es que se puede asociar a los destinos donde el miembro adjuntable no está en la lista de miembros. Servicios XAML de .NET framework proporciona una técnica de implementación para el miembro adjuntable que se almacena mediante las API de <xref:System.Xaml.IAttachedPropertyStore> y <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore> los escritores XAML se usan para detectar la implementación del almacén y deben implementarse en el tipo que es el `target` de los descriptores de acceso. Estático <xref:System.Xaml.AttachablePropertyServices> API se utilizan dentro del cuerpo de los descriptores de acceso y hacer referencia al miembro adjuntable por su <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Atributos CLR relacionados con XAML  
 Es importante para notificar información de sistema de tipos XAML para los servicios XAML de .NET Framework atribución correctamente sus tipos, miembros y ensamblados. Esto es importante si piensa que sus tipos para su uso con sistemas XAML que se basa directamente en los lectores de XAML de los servicios XAML de .NET Framework y escritores XAML, o si se define o usar un marco de uso de XAML que se basa en los lectores XAML y escritores XAML.  
  
 Para obtener una lista de cada atributo relacionado con el XAML que es relevante para la compatibilidad con XAML de los tipos personalizados, vea [Related atributos de CLR para tipos y bibliotecas personalizados](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Uso  
 Uso de tipos personalizados requiere que el autor de marcado debe asignar un prefijo para el ensamblado y el espacio de nombres CLR que contienen el tipo personalizado. Este procedimiento no se documenta en este tema.  
  
## <a name="access-level"></a>Nivel de acceso  
 XAML proporciona un medio para cargar y crear instancias de tipos que tienen un `internal` nivel de acceso. Esta funcionalidad se proporciona para que el código de usuario puede definir sus propios tipos y, a continuación, crear instancias de esas clases desde el marcado que también forma parte del mismo ámbito de código de usuario.  
  
 Un ejemplo de WPF es cada vez que el código de usuario define un <xref:System.Windows.Controls.UserControl> que está pensado como una manera de refactorizar un comportamiento de la interfaz de usuario, pero no como parte de cualquier mecanismo de extensión posibles que podría estar implícita por declarar la clase auxiliar con `public` nivel de acceso. Este tipo una <xref:System.Windows.Controls.UserControl> se pueden declarar con `internal` acceso si se compila el código de respaldo en el mismo ensamblado del que se hace referencia como un tipo XAML.  
  
 Para una aplicación que carga el XAML con plena confianza y utiliza <xref:System.Xaml.XamlObjectWriter>, cargando clases con `internal` siempre está habilitado el nivel de acceso.  
  
 Para una aplicación XAML de la carga bajo confianza parcial, puede controlar las características de nivel de acceso mediante la <xref:System.Xaml.Permissions.XamlAccessLevel> API. Además, los mecanismos de aplazamiento (por ejemplo, el sistema de plantillas de WPF) deben poder propagar los permisos de nivel de acceso y mantenerlos para las evaluaciones de tiempo de ejecución eventual; Esto se controla internamente pasando el <xref:System.Xaml.Permissions.XamlAccessLevel> información.  
  
### <a name="wpf-implementation"></a>Implementación de WPF  
 WPF XAML usa un modelo de acceso de confianza parcial, donde si BAML se carga bajo confianza parcial, el acceso está restringido a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> para el ensamblado que es el origen BAML. Para el aplazamiento, WPF usa <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> como un mecanismo para pasar la información de nivel de acceso.  
  
 En la terminología de WPF XAML, un *tipo interno* es un tipo definido por el mismo ensamblado que también incluye el XAML que hace referencia. Este tipo puede asignarse a través de un espacio de nombres XAML que omite deliberadamente el ensamblado = parte de una asignación, por ejemplo, `xmlns:local="clr-namespace:WPFApplication1"`.  Si BAML hace referencia a un tipo interno y que tiene tipo `internal` tener acceso a nivel, esto genera un `GeneratedInternalTypeHelper` clase del ensamblado. Si desea evitar `GeneratedInternalTypeHelper`, ya sea debe usar `public` nivel, de acceso o debe incluir la clase relevante en un ensamblado independiente y hacer que ese ensamblado dependiente.  
  
## <a name="see-also"></a>Vea también

- [Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [Servicios XAML](index.md)
