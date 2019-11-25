---
title: Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 7437add6795c1bb7f8a59807ebfc51dc2d0f987f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972018"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework
Al definir tipos personalizados que son objetos de negocio o que son tipos que no tienen una dependencia en marcos de trabajo específicos, se pueden seguir algunas prácticas recomendadas para XAML. Si sigue estos procedimientos, .NET Framework servicios XAML y sus lectores XAML y escritores de XAML pueden detectar las características XAML de su tipo y proporcionar una representación adecuada en un flujo de nodo XAML mediante el sistema de tipos XAML. En este tema se describen los procedimientos recomendados para definiciones de tipo, definiciones de miembro y atribución de CLR de tipos o miembros.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Patrones de constructor y definiciones de tipos para XAML  
 Para crear instancias como un elemento de objeto en XAML, una clase personalizada debe cumplir los siguientes requisitos:  
  
- La clase personalizada debe ser pública y debe exponer un constructor público sin parámetros. (Vea en la siguiente sección las notas relativas a las estructuras).  
  
- La clase personalizada no debe ser una clase anidada. El "punto" adicional de la ruta de acceso de nombre completo hace que la división de espacio de nombres de clase sea ambigua e interfiere con otras características de XAML, como las propiedades adjuntas.  
  
 Si se puede crear una instancia de un objeto como un elemento de objeto, el objeto creado puede rellenar el formulario de elemento de propiedad de las propiedades que toman el objeto como su tipo subyacente.  
  
 Todavía puede proporcionar valores de objeto para los tipos que no cumplen estos criterios, si habilita un convertidor de valores. Para obtener más información, vea [convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Estructuras  
 Las estructuras siempre se pueden construir en XAML, por definición de CLR. Esto se debe a que un compilador CLR crea implícitamente un constructor sin parámetros para una estructura. Este constructor inicializa todos los valores de propiedad a sus valores predeterminados.  
  
 En algunos casos, no es deseable el comportamiento de construcción predeterminado para una estructura. Esto puede deberse a que la estructura está pensada para rellenar los valores y funcionar conceptualmente como una Unión. Como Unión, los valores contenidos podrían tener interpretaciones mutuamente excluyentes y, por lo tanto, no se puede establecer ninguna de sus propiedades. Un ejemplo de este tipo de estructura en el vocabulario de WPF es <xref:System.Windows.GridLength>. Estas estructuras deben implementar un convertidor de tipos para que los valores se puedan expresar en forma de atributo, mediante el uso de convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura. La estructura también debe exponer un comportamiento similar para la construcción del código a través de un constructor sin parámetros.  
  
### <a name="interfaces"></a>Interfaces  
 Las interfaces se pueden usar como tipos subyacentes de miembros. El sistema de tipos XAML comprueba la lista asignable y espera que el objeto que se proporciona como valor se pueda asignar a la interfaz. No hay ningún concepto de cómo se debe presentar la interfaz como un tipo XAML siempre que un tipo asignable pertinente admita los requisitos de construcción de XAML.  
  
### <a name="factory-methods"></a>Métodos de generador  
 Los métodos de generador son una característica de XAML 2009. Modifican el principio de XAML de que los objetos deben tener constructores sin parámetros. Los métodos de generador no se documentan en este tema. Consulte [la Directiva x:FactoryMethod](x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumeraciones  
 Las enumeraciones tienen un comportamiento de conversión de tipo nativo XAML. Los nombres de constantes de enumeración especificados en XAML se resuelven con el tipo de enumeración subyacente y devuelven el valor de enumeración a un escritor de objetos XAML.  
  
 XAML admite el uso del estilo de marcas para las enumeraciones con <xref:System.FlagsAttribute> aplicado. Para obtener más información, consulte la [Sintaxis de XAML en detalle](../wpf/advanced/xaml-syntax-in-detail.md). (La[sintaxis XAML en detalle](../wpf/advanced/xaml-syntax-in-detail.md) se escribe para la audiencia de WPF, pero la mayor parte de la información de ese tema es relevante para XAML que no es específico de un marco de implementación concreto).  
  
## <a name="member-definitions"></a>Definiciones de miembro  
 Los tipos pueden definir miembros para el uso de XAML. Es posible para tipos que definen miembros que se pueden usar en XAML, aunque ese tipo específico no se pueda usar en XAML. Esto es posible debido a la herencia de CLR. Siempre que algún tipo que herede el miembro admita el uso de XAML como un tipo, y el miembro admita el uso de XAML para su tipo subyacente o tenga una sintaxis nativa de XAML disponible, ese miembro se puede usar en XAML.  
  
### <a name="properties"></a>Propiedades  
 Si define las propiedades como una propiedad CLR pública mediante los patrones de descriptor de acceso y `set` de `get` CLR típicos y las palabras clave apropiadas para el lenguaje, el sistema de tipos XAML puede informar de la propiedad como un miembro con la información adecuada proporcionada para <xref:System.Xaml.XamlMember> propiedades, como <xref:System.Xaml.XamlMember.IsReadPublic%2A> y <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Las propiedades específicas pueden habilitar una sintaxis de texto aplicando <xref:System.ComponentModel.TypeConverterAttribute>. Para obtener más información, vea [convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 En ausencia de una sintaxis de texto o de una conversión XAML nativa y, en ausencia de más direccionamiento indirecto, como un uso de la extensión de marcado, el tipo de una propiedad (<xref:System.Xaml.XamlMember.TargetType%2A> en el sistema de tipos XAML) debe ser capaz de devolver una instancia a un escritor de objetos XAML tratando el tipo de destino como un tipo CLR.  
  
 Si se usa XAML 2009, se puede usar la [extensión de marcado x:Reference](x-reference-markup-extension.md) para proporcionar valores si no se cumplen las consideraciones anteriores; sin embargo, eso es más un problema de uso que un problema de definición de tipo.  
  
### <a name="events"></a>Events  
 Si define eventos como un evento CLR público, el sistema de tipos XAML puede informar del evento como un miembro con <xref:System.Xaml.XamlMember.IsEvent%2A> como `true`. El cableado de los controladores de eventos no está dentro del ámbito de .NET Framework funcionalidades de servicios XAML; Esto se deja en marcos e implementaciones específicos.  
  
### <a name="methods"></a>Métodos  
 El código insertado para los métodos no es una funcionalidad XAML predeterminada. En la mayoría de los casos, no se hace referencia directamente a los miembros de método desde XAML, y el rol de los métodos en XAML solo es proporcionar compatibilidad con patrones específicos de XAML. [la Directiva x:FactoryMethod](x-factorymethod-directive.md) es una excepción.  
  
### <a name="fields"></a>Campos  
 Las instrucciones de diseño de CLR desaconsejan los campos no estáticos. En el caso de los campos estáticos, solo puede acceder a los valores de campo estáticos a través de la [extensión de marcado x:Static](x-static-markup-extension.md). en este caso, no está haciendo nada especial en la definición de CLR para exponer un campo para los usos de [x:Static](x-static-markup-extension.md) .  
  
## <a name="attachable-members"></a>Miembros que se van a adjuntar  
 Los miembros adjuntables se exponen a XAML a través de un patrón de método de descriptor de acceso en un tipo de definición No es necesario que el propio tipo de definición se pueda usar en XAML como un objeto. De hecho, un patrón común es declarar una clase de servicio cuyo rol sea el propietario del miembro que se va a adjuntar e implementar los comportamientos relacionados, pero no atender ninguna otra función, como la representación de la interfaz de usuario. En las secciones siguientes, el marcador de posición *PropertyName* representa el nombre del miembro que se va a adjuntar. Ese nombre debe ser válido en la [Gramática XamlName](xamlname-grammar.md).  
  
 Tenga cuidado con los conflictos de nombres entre estos patrones y otros métodos de un tipo. Si existe un miembro que coincide con uno de los patrones, un procesador XAML puede interpretarlo como una ruta de uso de miembros que se puede adjuntar, aunque no sea su intención.  
  
#### <a name="the-getpropertyname-accessor"></a>El descriptor de acceso GetPropertyName  
 La signatura del descriptor de acceso `Get`*NombreDePropiedad* debe ser:  
  
 `public static object Get` *NombreDePropiedad* `(object`  `target` `)`  
  
- El objeto `target` puede especificarse como un tipo más específico en la implementación. Puede utilizar esto para limitar el uso del miembro que se puede adjuntar; los usos fuera del ámbito previsto producirán excepciones de conversión no válidas que se mostrarán después de un error de análisis de XAML. El nombre del parámetro `target` no es un requisito, pero se denomina `target` por Convención en la mayoría de las implementaciones.  
  
- El valor devuelto puede especificarse como un tipo más específico en la implementación.  
  
 Para admitir una sintaxis de texto <xref:System.ComponentModel.TypeConverter> habilitada para el uso de atributos del miembro adjuntable, aplique <xref:System.ComponentModel.TypeConverterAttribute> al descriptor de acceso `Get`*PropertyName* . La aplicación del `get` en lugar de la `set` puede parecer no intuitiva; sin embargo, esta Convención puede admitir el concepto de miembros que se pueden asociar de solo lectura y que son serializables, lo que resulta útil en los escenarios del diseñador.  
  
#### <a name="the-setpropertyname-accessor"></a>El descriptor de acceso SetPropertyName  
 La firma para el descriptor de acceso set*PropertyName* debe ser:  
  
 `public static void Set` *NombreDePropiedad* `(object`  `target` `, object`  `value` `)`  
  
- El objeto `target` puede especificarse como un tipo más específico en la implementación, con la misma lógica y las mismas consecuencias descritas en la sección anterior.  
  
- El objeto `value` puede especificarse como un tipo más específico en la implementación.  
  
 Recuerde que el valor de este método es la entrada procedente del uso de XAML, normalmente en forma de atributo. En el formulario de atributo debe haber compatibilidad con el convertidor de valores para una sintaxis de texto y el atributo en el descriptor de acceso `Get`*PropertyName* .  
  
### <a name="attachable-member-stores"></a>Almacenes de miembros adjuntables  
 Normalmente, los métodos de descriptor de acceso no son suficientes para proporcionar un medio para colocar los valores de miembro que se pueden asociar en un gráfico de objetos, o para recuperar los valores del gráfico de objetos y serializarlos correctamente. Para proporcionar esta funcionalidad, los objetos `target` en las signaturas del descriptor de acceso anterior deben ser capaces de almacenar valores. El mecanismo de almacenamiento debe ser coherente con el principio de miembro que se puede adjuntar que el miembro se puede asociar a los destinos en los que el miembro que se puede adjuntar no está en la lista de miembros. .NET Framework servicios XAML proporciona una técnica de implementación para los almacenes de miembros que se asocian a través de las API <xref:System.Xaml.IAttachedPropertyStore> y <xref:System.Xaml.AttachablePropertyServices>. los escritores de XAML usan <xref:System.Xaml.IAttachedPropertyStore> para detectar la implementación del almacén y deben implementarse en el tipo que es el `target` de los descriptores de acceso. Las API de <xref:System.Xaml.AttachablePropertyServices> estáticas se utilizan dentro del cuerpo de los descriptores de acceso y hacen referencia al miembro adjuntable por su <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Atributos de CLR relacionados con XAML  
 Es importante atribuir correctamente sus tipos, miembros y ensamblados para informar a la información del sistema de tipos XAML a .NET Framework servicios XAML. Esto es importante si piensa usar sus tipos con sistemas XAML que se basan directamente en .NET Framework los lectores XAML de los servicios XAML y los escritores de XAML, o si define o usa un marco de trabajo de uso de XAML que se basa en esos lectores y escritores de XAML.  
  
 Para obtener una lista de cada atributo relacionado con XAML que es relevante para la compatibilidad con XAML de los tipos personalizados, vea [atributos de CLR relacionados con XAML para tipos y bibliotecas personalizados](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Uso  
 El uso de tipos personalizados requiere que el autor de marcado deba asignar un prefijo para el ensamblado y el espacio de nombres CLR que contienen el tipo personalizado. Este procedimiento no se documenta en este tema.  
  
## <a name="access-level"></a>Nivel de acceso  
 XAML proporciona un medio para cargar y crear instancias de tipos que tienen un nivel de acceso `internal`. Esta funcionalidad se proporciona para que el código de usuario pueda definir sus propios tipos y, a continuación, crear instancias de esas clases a partir del marcado que también forma parte del mismo ámbito de código de usuario.  
  
 Un ejemplo de WPF es cada vez que el código de usuario define un <xref:System.Windows.Controls.UserControl> que está pensado como una manera de refactorizar un comportamiento de la interfaz de usuario, pero no como parte de cualquier mecanismo de extensión posible que podría estar implícito al declarar la clase auxiliar con el nivel de acceso `public`. Tal <xref:System.Windows.Controls.UserControl> se puede declarar con `internal` acceso si el código de respaldo se compila en el mismo ensamblado desde el que se hace referencia a él como un tipo XAML.  
  
 Para una aplicación que carga XAML con plena confianza y usa <xref:System.Xaml.XamlObjectWriter>, la carga de clases con `internal` nivel de acceso siempre está habilitada.  
  
 Para una aplicación que carga XAML en confianza parcial, puede controlar las características del nivel de acceso mediante el uso de la API de <xref:System.Xaml.Permissions.XamlAccessLevel>. Además, los mecanismos de aplazamiento (como el sistema de plantilla de WPF) deben poder propagar los permisos de nivel de acceso y conservarlos para las evaluaciones de tiempo de ejecución eventuales; Esto se controla internamente pasando la información <xref:System.Xaml.Permissions.XamlAccessLevel>.  
  
### <a name="wpf-implementation"></a>Implementación de WPF  
 XAML de WPF usa un modelo de acceso de confianza parcial en el que si BAML se carga bajo confianza parcial, el acceso está restringido a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> para el ensamblado que es el origen BAML. Para el aplazamiento, WPF usa <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> como mecanismo para pasar la información de nivel de acceso.  
  
 En la terminología XAML de WPF, un *tipo interno* es un tipo definido por el mismo ensamblado que también incluye el XAML de referencia. Este tipo se puede asignar a través de un espacio de nombres XAML que omita deliberadamente la parte Assembly = de una asignación, por ejemplo, `xmlns:local="clr-namespace:WPFApplication1"`.  Si BAML hace referencia a un tipo interno y ese tipo tiene `internal` nivel de acceso, se genera una clase `GeneratedInternalTypeHelper` para el ensamblado. Si desea evitar `GeneratedInternalTypeHelper`, debe usar `public` nivel de acceso o debe factorizar la clase correspondiente en un ensamblado independiente y hacer que ese ensamblado dependa.  
  
## <a name="see-also"></a>Vea también

- [Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [Servicios XAML](index.md)
