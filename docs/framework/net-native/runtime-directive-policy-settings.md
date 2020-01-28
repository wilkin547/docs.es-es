---
title: Configuración de directiva de la directiva en tiempo de ejecución
ms.date: 03/30/2017
ms.assetid: cb52b1ef-47fd-4609-b69d-0586c818ac9e
ms.openlocfilehash: 7a8933decaec45e8000f3f3d1717847f333deddd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738497"
---
# <a name="runtime-directive-policy-settings"></a>Configuración de directiva de la directiva en tiempo de ejecución

> [!NOTE]
> En este tema se hace referencia a .NET Native Developer Preview, que es una versión preliminar del software. Puede descargar esta versión preliminar desde el [sitio web de Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (es necesario registrarse).

La configuración de directiva de la directiva en tiempo de ejecución de .NET Native determina la disponibilidad de los metadatos de los tipos y miembros de tipo en tiempo de ejecución. Sin los metadatos necesarios, las operaciones que se basan en la reflexión, la serialización y la deserialización o el cálculo de referencias de tipos de .NET Framework a COM o Windows en tiempo de ejecución pueden producir errores y generar una excepción. Las excepciones más comunes son [MissingMetadataException](missingmetadataexception-class-net-native.md) y, en el caso de la interoperabilidad, [MissingInteropDataException](missinginteropdataexception-class-net-native.md).

La configuración de la directiva en tiempo de ejecución se controla mediante un archivo de directivas en tiempo de ejecución (.rd.xml). Cada directiva en tiempo de ejecución define la directiva de un elemento del programa determinado, como un ensamblado (elemento [\<Assembly>](assembly-element-net-native.md)), un tipo (elemento [\<Type>](type-element-net-native.md)) o un método (elemento [\<Method>](method-element-net-native.md)). La directiva incluye uno o más atributos que definen los tipos de directivas de reflexión, los tipos de directivas de serialización y los tipos de directiva de interoperabilidad descritos en la siguiente sección. El valor del atributo define la configuración de directiva.

## <a name="policy-types"></a>Tipos de directiva

Los archivos de directivas en tiempo de ejecución reconocen tres categorías de tipos de directivas: reflexión, serialización e interoperabilidad.

- Los tipos de directiva de reflexión determinan los metadatos que van a estar disponibles en tiempo de ejecución para la reflexión:

  - `Activate` controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.

  - `Browse` controla la consulta para obtener información sobre los elementos del programa.

  - `Dynamic` controla el acceso en tiempo de ejecución a todos los tipos y miembros para permitir la programación dinámica.

  En la siguiente tabla se recogen los tipos de directivas de reflexión y los elementos de programa con los que se pueden usar.

  |Elemento|Activar|Explorar|Dinámico|
  |-------------|--------------|------------|-------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||✔️|✔️|
  |[\<Field>](field-element-net-native.md)||✔️|✔️|
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||✔️|✔️|
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||✔️|✔️|
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||✔️|✔️|
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

- Los tipos de directivas de serialización determinan los metadatos que van a estar disponibles en tiempo de ejecución para la serialización y deserialización:

  - `Serialize` controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas de terceros como el serializador JSON Newtonsoft puedan serializar instancias de tipo.

  - `DataContractSerializer` controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que la clase <xref:System.Runtime.Serialization.DataContractSerializer> pueda serializar instancias de tipo.

  - `DataContractJsonSerializer` controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> pueda serializar instancias de tipo.

  - `XmlSerializer` controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que la clase <xref:System.Xml.Serialization.XmlSerializer> pueda serializar instancias de tipo.

  En la siguiente tabla se muestran los tipos de directivas de serialización y los elementos de programa con los que se pueden usar.

  |Elemento|Serializar|DataContractSerializer|DataContractJsonSerializer|XmlSerializer|
  |-------------|---------------|----------------------------|--------------------------------|-------------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)|||||
  |[\<Field>](field-element-net-native.md)|✔️||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)|||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)|✔️||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|✔️|

- Los tipos de directivas de interoperabilidad determinan los metadatos que van a estar disponibles en tiempo de ejecución para pasar punteros de función, tipos de valor y tipos de referencias a COM y a Windows en tiempo de ejecución:

  - `MarshalObject` controla el cálculo de referencias nativo a COM y a Windows en tiempo de ejecución para los tipos de referencia.

  - `MarshalDelegate` controla el cálculo de referencias nativo de tipos de delegado como punteros de función.

  - `MarshalStructure` controla el cálculo de referencias nativo a COM y a Windows en tiempo de ejecución para los tipos de valor.

  En la siguiente tabla se enumeran los tipos de directivas de interoperabilidad y los elementos de programa con los que se pueden usar.

  |Elemento|MarshalObject|MarshalDelegate|MarshalStructure|
  |-------------|-------------------|---------------------|----------------------|
  |[\<Application>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||||
  |[\<Field>](field-element-net-native.md)||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

## <a name="policy-settings"></a>Configuración de directiva

Cada tipo de directiva se puede establecer en uno de los valores incluidos en la siguiente tabla. Tenga en cuenta que los elementos que representan miembros de tipo admiten un conjunto diferente de opciones de directiva que otros elementos.

|Configuración de directiva|Descripción|Elementos `Assembly`, `Namespace`, `Type` y `TypeInstantiation`|Elementos `Event`, `Field`, `Method`, `MethodInstantiation` y `Property`|
|--------------------|-----------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|
|`All`|Habilita la directiva para todos los tipos y miembros que la cadena de herramientas de .NET Native no elimina.|✔️||
|`Auto`|Especifica que se debe usar la directiva predeterminada para el tipo de directiva de ese elemento de programa. Esto es exactamente lo mismo que omitir una directiva para ese tipo de directiva. `Auto` se suele usar para indicar que la directiva se hereda de un elemento primario.|✔️|✔️|
|`Excluded`|Especifica que la directiva está deshabilitada para un determinado elemento del programa. Por ejemplo, la directiva en tiempo de ejecución:<br /><br /> `<Type Name="BusinessClasses.Person" Browse="Excluded" Dynamic="Excluded" />`<br /><br /> especifica que no hay metadatos de la clase `BusinessClasses.Person` disponibles para examinarlos o para crear una instancia de objetos `Person` y modificarlos dinámicamente.|✔️|✔️|
|`Included`|Habilita una directiva si hay metadatos disponibles para el tipo primario.||✔️|
|`Public`|Habilita la directiva para miembros o tipos públicos, a menos que la cadena de herramientas determine que el tipo o miembro no es necesario y, por tanto, lo quite. Esta configuración difiere de `Required Public`, lo que garantiza que siempre va a haber metadatos disponibles para miembros y tipos públicos, aun cuando la cadena de herramientas determine que no son necesarios.|✔️||
|`PublicAndInternal`|Habilita la directiva para miembros o tipos públicos e internos, a menos que la cadena de herramientas determine que el tipo o miembro no es necesario y, por tanto, lo quite. Este parámetro difiere de `Required PublicAndInternal`, lo que garantiza que siempre va a haber metadatos disponibles para miembros y tipos públicos e internos, aun cuando la cadena de herramientas determine que no son necesarios.|✔️||
|`Required`|Especifica que la directiva para un miembro está habilitada y que va a haber metadatos disponibles incluso cuando parezca que el miembro está en uso.||✔️|
|`Required Public`|Habilita la directiva para los miembros y tipos públicos y garantiza que siempre va a haber metadatos disponibles para los miembros y tipos públicos. Este parámetro difiere de `Public`, lo que hace que solo haya metadatos disponibles para miembros y tipos públicos cuando la cadena de herramientas determine que son necesarios.|✔️||
|`Required PublicAndInternal`|Habilita la directiva para miembros o tipos públicos e internos y garantiza que siempre va a haber metadatos disponibles para los miembros y tipos públicos e internos. Este parámetro difiere de `PublicAndInternal`, lo que hace que solo haya metadatos disponibles para miembros y tipos públicos e internos cuando la cadena de herramientas determine que son necesarios.|✔️||
|`Required All`|Requiere que la cadena de herramientas conserve todos los tipos y miembros (se usen o no) y habilita la directiva para estos.|✔️||

## <a name="see-also"></a>Vea también

- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](runtime-directive-elements.md)
