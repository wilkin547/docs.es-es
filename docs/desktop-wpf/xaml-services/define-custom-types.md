---
title: Definición de tipos personalizados para usarlos con los servicios XAML de .NET
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: ff7e4229450e801a6d618c5141efde8cdcbef03d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433077"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>Definir tipos personalizados para su uso con los servicios XAML de .NET

Al definir tipos personalizados que son objetos de negocio o son tipos que no tienen una dependencia en marcos específicos, hay ciertos procedimientos recomendados para XAML que puede seguir. Si sigues estas prácticas, los servicios XAML de .NET y sus lectores XAML y escritores XAML pueden detectar las características XAML del tipo y darle la representación adecuada en un flujo de nodo XAML mediante el sistema de tipos XAML. En este tema se describen los procedimientos recomendados para las definiciones de tipos, las definiciones de miembro y la atribución de CLR de tipos o miembros.

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Patrones de constructor y definiciones de tipo para XAML

Para crear instancias como un elemento de objeto en XAML, una clase personalizada debe cumplir los siguientes requisitos:

- La clase personalizada debe ser pública y debe exponer un constructor público sin parámetros. (Vea en la siguiente sección las notas relativas a las estructuras).

- La clase personalizada no debe ser una clase anidada. El "punto" adicional en la ruta de acceso de nombre completo hace que la división de espacio de nombres de clase sea ambigua e interfiere con otras características XAML, como las propiedades adjuntas.
Si se puede crear una instancia de un objeto como un elemento de objeto, el objeto creado puede rellenar el formulario de elemento de propiedad de cualquier propiedad que tome el objeto como su tipo subyacente.

Todavía puede proporcionar valores de objeto para tipos que no cumplen estos criterios, si habilita un convertidor de valores. Para obtener más información, vea Convertidores de tipos [y extensiones](type-converters-and-markup-extensions.md)de marcado para XAML .

### <a name="structures"></a>Estructuras

Las estructuras siempre se pueden construir en XAML, por definición de CLR. Esto se debe a que un compilador CLR crea implícitamente un constructor sin parámetros para una estructura. Este constructor inicializa todos los valores de propiedad en sus valores predeterminados.

En algunos casos, el comportamiento de construcción predeterminado para una estructura no es deseable. Esto puede deberse a que la estructura está diseñada para rellenar valores y funcionar conceptualmente como una unión. Como unión, los valores contenidos pueden tener interpretaciones mutuamente excluyentes y, por lo tanto, ninguna de sus propiedades se puede establecer. Un ejemplo de tal estructura en <xref:System.Windows.GridLength>el vocabulario WPFWPF es . Estas estructuras deben implementar un convertidor de tipos para que los valores se puedan expresar en forma de atributo, mediante convenciones de cadena que creen las diferentes interpretaciones o modos de los valores de estructura. La estructura también debe exponer un comportamiento similar para la construcción de código a través de un constructor sin parámetros.

### <a name="interfaces"></a>Interfaces

Las interfaces se pueden utilizar como tipos subyacentes de miembros. El sistema de tipos XAML comprueba la lista asignable y espera que el objeto que se proporciona como valor se puede asignar a la interfaz. No hay ningún concepto de cómo se debe presentar la interfaz como un tipo XAML, siempre y cuando un tipo asignable relevante admita los requisitos de construcción XAML.

### <a name="factory-methods"></a>Métodos de fábrica

Los métodos de fábrica son una característica DE XAML 2009. Modifican el principio XAML de que los objetos deben tener constructores sin parámetros. Los métodos de fábrica no se documentan en este artículo. Consulte [x:Directiva FactoryMethod](xfactorymethod-directive.md).

## <a name="enumerations"></a>Enumeraciones

Las enumeraciones tienen un comportamiento de conversión de tipos nativoXAML. Los nombres de constantes de enumeración especificados en XAML se resuelven con el tipo de enumeración subyacente y devuelven el valor de enumeración a un escritor de objetos XAML.

XAML admite un uso de estilo <xref:System.FlagsAttribute> de marcas para enumeraciones con aplicado. Para obtener más información, vea Detalle de [sintaxis XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md). ([Sintaxis XAML en detalle](../../framework/wpf/advanced/xaml-syntax-in-detail.md) se escribe para la audiencia de WPFWPF, pero la mayor parte de la información de ese tema es relevante para XAML que no es específica de un marco de implementación determinado.)

## <a name="member-definitions"></a>Definiciones de miembros

Los tipos pueden definir miembros para el uso de XAML. Es posible que los tipos definan miembros que se pueden usar XAML incluso si ese tipo específico no se puede usar XAML. Esto es posible debido a la herencia de CLR. Siempre que algún tipo que herede el miembro admita el uso XAML como tipo y el miembro admita el uso xaml para su tipo subyacente o tenga una sintaxis XAML nativa disponible, ese miembro se puede usar mediante XAML.

### <a name="properties"></a>Propiedades

Si define propiedades como una propiedad CLR `get` `set` pública mediante los patrones clr y descriptor de acceso típicos y las palabras clave apropiadas para el lenguaje, el sistema de tipos XAML puede notificar la propiedad como un miembro con la información adecuada proporcionada para <xref:System.Xaml.XamlMember> las propiedades, como <xref:System.Xaml.XamlMember.IsReadPublic%2A> y <xref:System.Xaml.XamlMember.IsWritePublic%2A>.

Las propiedades específicas pueden habilitar <xref:System.ComponentModel.TypeConverterAttribute>una sintaxis de texto aplicando . Para obtener más información, vea Convertidores de tipos [y extensiones](type-converters-and-markup-extensions.md)de marcado para XAML .

En ausencia de una sintaxis de texto o conversión XAML nativa y en ausencia de más<xref:System.Xaml.XamlMember.TargetType%2A> direccionamiento indirecto, como un uso de extensión de marcado, el tipo de una propiedad (en el sistema de tipos XAML) debe ser capaz de devolver una instancia a un escritor de objetos XAML tratando el tipo de destino como un tipo CLR.

Si usa XAML 2009, [x:Reference Markup Extension](xreference-markup-extension.md) se puede usar para proporcionar valores si no se cumplen las consideraciones anteriores; sin embargo, eso es más un problema de uso que un problema de definición de tipo.

### <a name="events"></a>Eventos

Si define eventos como un evento CLR público, el sistema de <xref:System.Xaml.XamlMember.IsEvent%2A> `true`tipos XAML puede notificar el evento como miembro con como . El cableado de los controladores de eventos no está dentro del ámbito de las capacidades de servicios XAML de .NET; el cableado se deja a marcos e implementaciones específicos.

### <a name="methods"></a>Métodos

El código en línea para los métodos no es una capacidad XAML predeterminada. En la mayoría de los casos, no hace referencia directamente a los miembros del método desde XAML y el rol de los métodos en XAML es solo para proporcionar compatibilidad con patrones XAML específicos. [x:FactoryMethod Directive](xfactorymethod-directive.md) es una excepción.

### <a name="fields"></a>Fields

Las directrices de diseño de CLR desalientan los campos no estáticos. Para los campos estáticos, solo puede tener acceso a los valores de campo estático a través de [x:Static Markup Extension](xstatic-markup-extension.md); en este caso, no está haciendo nada especial en la definición de CLR para exponer un campo para [x:Usos estáticos.](xstatic-markup-extension.md)

## <a name="attachable-members"></a>Miembros adjuntables

Los miembros adjuntables se exponen a XAML a través de un patrón de método de descriptor de acceso en un tipo de definición. El propio tipo de definición no necesita ser XAML-utilizable como un objeto. De hecho, un patrón común es declarar una clase de servicio cuyo rol es poseer el miembro adjuntable e implementar los comportamientos relacionados, pero no servir ninguna otra función como una representación de interfaz de usuario. Para las secciones siguientes, el marcador de posición *PropertyName* representa el nombre del miembro adjuntable. Ese nombre debe ser válido en [la gramática XamlName](xamlname-grammar.md).

Tenga cuidado con las colisiones de nombres entre estos patrones y otros métodos de un tipo. Si existe un miembro que coincide con uno de los patrones, puede interpretarse como una ruta de uso de miembro adjuntable por un procesador XAML, incluso si esa no era su intención.

#### <a name="the-getpropertyname-accessor"></a>El descriptor de acceso GetPropertyName

La firma `GetPropertyName` del descriptor de acceso debe ser:

`public static object GetPropertyName(object target)`

- El objeto `target` puede especificarse como un tipo más específico en la implementación. Puede usar esto para establecer el ámbito del uso de su miembro adjuntable; los usos fuera del ámbito previsto producirán excepciones de conversión no válidas que, a continuación, se exponen mediante un error de análisis XAML. El nombre `target` del parámetro no es `target` un requisito, pero se nombra por convención en la mayoría de las implementaciones.

- El valor devuelto puede especificarse como un tipo más específico en la implementación.

Para admitir <xref:System.ComponentModel.TypeConverter> una sintaxis de texto habilitada para <xref:System.ComponentModel.TypeConverterAttribute> el `GetPropertyName` uso de atributos del miembro adjuntable, aplique al descriptor de acceso. Aplicar a `get` la en `set` lugar de la puede parecer no intuitiva; sin embargo, esta convención puede admitir el concepto de miembros adjuntables de solo lectura que son serializables, lo que resulta útil en escenarios de diseñador.

#### <a name="the-setpropertyname-accessor"></a>El descriptor de acceso SetPropertyName

La firma `SetPropertyName` del descriptor de acceso debe ser:

`public static void SetPropertyName(object target, object value)`

- El `target` objeto se puede especificar como un tipo más específico en la implementación, con la misma lógica y consecuencias que se describe en la sección anterior.

- El objeto `value` puede especificarse como un tipo más específico en la implementación.

Recuerde que el valor de este método es la entrada procedente del uso XAML, normalmente en forma de atributo. Desde formulario de atributo debe haber compatibilidad con el convertidor `GetPropertyName`de valores para una sintaxis de texto y se atribuye en el descriptor de acceso s.

### <a name="attachable-member-stores"></a>Tiendas de miembros adjuntas

Los métodos de descriptor de acceso normalmente no son suficientes para proporcionar un medio para colocar valores de miembro adjuntables en un gráfico de objetos, o para recuperar valores fuera del gráfico de objetos y serializarlos correctamente. Para proporcionar esta funcionalidad, los `target` objetos de las firmas de descriptor de acceso anteriores deben ser capaces de almacenar valores. El mecanismo de almacenamiento debe ser coherente con el principio de miembro adjuntable de que el miembro es adjuntable a destinos donde el miembro adjuntable no está en la lista de miembros. Servicios XAML de .NET proporciona una técnica de <xref:System.Xaml.IAttachedPropertyStore> implementación para los almacenes de miembros adjuntables a través de las API y <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore>los escritores XAML lo usan para detectar la implementación del almacén `target` y deben implementarse en el tipo que es el de los descriptores de acceso. Las <xref:System.Xaml.AttachablePropertyServices> API estáticas se utilizan dentro del cuerpo de los descriptores <xref:System.Xaml.AttachableMemberIdentifier>de acceso y hacen referencia al miembro adjuntable por su .

## <a name="xaml-related-clr-attributes"></a>Atributos CLR relacionados con XAML

Atribuir correctamente los tipos, miembros y ensamblados es importante para notificar información del sistema de tipos XAML a los servicios XAML de .NET. La información del sistema de tipos XAML de informes es relevante si se aplica alguna de las situaciones siguientes:

- Tiene según los tipos para su uso con sistemas XAML que se basan directamente en lectores XAML de servicios XAML de .NET y escritores XAML.
- Definir o usar un marco de uso XAML que se basa en esos lectores XAML y escritores XAML.

Para obtener una lista de cada atributo relacionado con XAML que es relevante para la compatibilidad con XAML de los tipos personalizados, vea [Atributos CLR relacionados con XAML para tipos personalizados y bibliotecas](clr-attributes-with-custom-types-and-libraries.md).

## <a name="usage"></a>Uso

El uso de tipos personalizados requiere que el autor del marcado asigne un prefijo para el ensamblado y el espacio de nombres CLR que contienen el tipo personalizado. Este procedimiento no se documenta en este tema.

## <a name="access-level"></a>Nivel de acceso

XAML proporciona un medio para cargar `internal` y crear instancias de tipos que tienen un nivel de acceso. Esta capacidad se proporciona para que el código de usuario pueda definir sus propios tipos y, a continuación, crear instancias de las clases de marcado que también forma parte del mismo ámbito de código de usuario.

Un ejemplo de WPFWPF siempre <xref:System.Windows.Controls.UserControl> que el código de usuario define un que está pensado como una forma de refactorizar un `public` comportamiento de interfaz de usuario, pero no como parte de cualquier mecanismo de extensión posible que podría estar implícito declarando la clase auxiliar con nivel de acceso. Este <xref:System.Windows.Controls.UserControl> tipo se `internal` puede declarar con acceso si el código de respaldo se compila en el mismo ensamblado desde el que se hace referencia como un tipo XAML.

Para una aplicación que carga XAML <xref:System.Xaml.XamlObjectWriter>con plena `internal` confianza y usa , la carga de clases con nivel de acceso siempre está habilitada.

Para una aplicación que carga XAML en confianza parcial, puede <xref:System.Xaml.Permissions.XamlAccessLevel> controlar las características del nivel de acceso mediante la API. Además, los mecanismos de aplazamiento (como el sistema de plantillas WPF) deben poder propagar los permisos de nivel de acceso y conservarlos para las evaluaciones de tiempo de ejecución finales; esto se maneja internamente <xref:System.Xaml.Permissions.XamlAccessLevel> pasando la información.

### <a name="wpf-implementation"></a>Implementación de WPF

XAML de WPF usa un modelo de acceso de confianza parcial donde <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> si BAML se carga en confianza parcial, el acceso está restringido para el ensamblado que es el origen de BAML. Para el aplazamiento, <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> WPFWPF usa como mecanismo para pasar la información de nivel de acceso.

En la terminología XAML de WPF, un *tipo interno* es un tipo definido por el mismo ensamblado que también incluye el XAML de referencia. Este tipo se puede asignar a través de un espacio de nombres `xmlns:local="clr-namespace:WPFApplication1"`XAML que omite deliberadamente la parte del ensamblado de una asignación, por ejemplo, . Si BAML hace referencia a `internal` un tipo interno `GeneratedInternalTypeHelper` y ese tipo tiene nivel de acceso, esto genera una clase para el ensamblado. Si desea evitar `GeneratedInternalTypeHelper`, debe `public` utilizar el nivel de acceso o debe tener en cuenta la clase relevante en un ensamblado independiente y hacer que ese ensamblado sea dependiente.

## <a name="see-also"></a>Consulte también

- [Atributos de CLR relacionados con XAML para los tipos y bibliotecas personalizados](clr-attributes-with-custom-types-and-libraries.md)
- [Servicios XAML](../../../api/index.md)
