---
description: 'Más información sobre: Stand-Alone la serialización de JSON mediante DataContractJsonSerializer'
title: Stand-Alone la serialización de JSON mediante DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 312bd7b2-1300-4b12-801e-ebe742bd2287
ms.openlocfilehash: c88a996eeac7e9e62caa7797bc0bf7cd68dfd67b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793420"
---
# <a name="stand-alone-json-serialization-using-datacontractjsonserializer"></a>Stand-Alone la serialización de JSON mediante DataContractJsonSerializer

> [!NOTE]
> Este artículo trata acerca de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> . Para la mayoría de los escenarios que implican la serialización y deserialización de JSON, se recomiendan las API del [System.Text.Jsen el espacio de nombres](../../../standard/serialization/system-text-json-overview.md).

JSON (JavaScript Object Notation) es un formato de datos diseñado específicamente para usarse por código JavaScript que se ejecute en páginas web dentro del explorador. Es el formato de datos predeterminado que usan los servicios de ASP.NET AJAX creados en Windows Communication Foundation (WCF).

Este formato también puede usarse al crear servicios de AJAX sin integrar con ASP.NET, en este caso, XML es el valor predeterminado pero se puede elegir JSON.

Finalmente, si necesita compatibilidad JSON pero no está creando un servicio de AJAX, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> permite serializar directamente los objetos .NET en datos JSON y volver a deserializar estos datos en instancias de tipos .NET. Para obtener una descripción de cómo hacerlo, consulte [Cómo: serializar y deserializar datos JSON](how-to-serialize-and-deserialize-json-data.md).

Al trabajar con JSON, se admiten los mismos tipos .NET, con una pocas excepciones, como las compatibles con <xref:System.Runtime.Serialization.DataContractSerializer>. Para obtener una lista de los tipos admitidos, consulte [tipos admitidos por el serializador de contrato de datos](types-supported-by-the-data-contract-serializer.md). Entre éstos se incluyen los tipos más primitivos, la mayoría de tipos de colección y matriz, y también tipos complejos que usan <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>.

## <a name="mapping-net-types-to-json-types"></a>Asignación de tipos .NET a tipos JSON

En la siguiente tabla se muestra la correspondencia entre los tipos .NET y los tipos JSON/JavaScript cuando se asignan mediante procedimientos de serialización y deserialización.

|Tipos .NET|JSON/JavaScript|Notas|
|----------------|----------------------|-----------|
|Todos los tipos numéricos, por ejemplo <xref:System.Int32>, <xref:System.Decimal> o <xref:System.Double>|Número|Los valores especiales como `Double.NaN`, `Double.PositiveInfinity` y `Double.NegativeInfinity` no son compatibles y dan como resultado una JSON no válida.|
|<xref:System.Enum>|Número|Vea "Enumeraciones y JSON" más adelante en este tema.|
|<xref:System.Boolean>|Boolean|--|
|<xref:System.String>, <xref:System.Char>|String|--|
|<xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>|String|El formato de estos tipos en JSON es el mismo que en XML (esencialmente, TimeSpan en el formato de duración ISO 8601, GUID en el formato "12345678-ABCD-ABCD-ABCD-1234567890AB" y el URI en su forma de cadena natural como " http://www.example.com "). Para obtener información precisa, vea [referencia de esquema de contrato de datos](data-contract-schema-reference.md).|
|<xref:System.Xml.XmlQualifiedName>|String|El formato es "nombre:espaciodenombres" (cualquier cosa antes de los primeros dos puntos es el nombre). Puede que falte el nombre o el espacio de nombres. Si no hay ningún espacio de nombres, también se pueden omitir los dos puntos.|
|<xref:System.Array> de tipo <xref:System.Byte>|Matriz de números|Cada número representa el valor de un byte.|
|<xref:System.DateTime>|DateTime (fecha y hora) o cadena|Vea Fechas/horas y JSON más adelante en este tema.|
|<xref:System.DateTimeOffset>|Tipo complejo|Vea Fechas/horas y JSON más adelante en este tema.|
|Tipos XML y ADO.NET (<xref:System.Xml.XmlElement>,<br /><br /> <xref:System.Xml.Linq.XElement>. Matrices de <xref:System.Xml.XmlNode>,<br /><br /> <xref:System.Runtime.Serialization.ISerializable>,<br /><br /> <xref:System.Data.DataSet>).|String|Consulte la sección Tipos XML y JSON en este tema.|
|<xref:System.DBNull>|Tipo complejo vacío|--|
|Colecciones, diccionarios y matrices|Array|Consulte la sección Colecciones, diccionarios y matrices en este tema.|
|Tipos complejos (con el <xref:System.Runtime.Serialization.DataContractAttribute> o <xref:System.SerializableAttribute> aplicado)|Tipo complejo|Los miembros de datos se convierten en miembros del tipo complejo de Javascript.|
|Tipos complejos que implementan la interfaz <xref:System.Runtime.Serialization.ISerializable>)|Tipo complejo|Igual que otros tipos complejos, pero algunos tipos <xref:System.Runtime.Serialization.ISerializable> no se admiten; vea la nota sobre la compatibilidad de ISerializable en la sección de Información avanzada de este tema.|
|Valor `Null` para cualquier tipo|Null|Los tipos de valor que aceptan valores null también se admiten y se asignan a JSON de la misma manera que los tipos de valor que no aceptan valores NULL.|

### <a name="enumerations-and-json"></a>Enumeraciones y JSON

Los valores del miembro de enumeración se tratan como números en JSON, que es diferente de cómo se tratan en contratos de datos, donde se incluyen como nombres de miembros. Para obtener más información sobre el tratamiento del contrato de datos, vea [tipos de enumeración en contratos de datos](enumeration-types-in-data-contracts.md).

- Por ejemplo, si tiene `public enum Color {red, green, blue, yellow, pink}`, al serializar `yellow`, se genera el número 3 y no la cadena "amarillo".

- Todos los miembros `enum` son serializables. Se omiten los atributos <xref:System.Runtime.Serialization.EnumMemberAttribute> y <xref:System.NonSerializedAttribute> si se utilizan.

- Es posible deserializar un valor `enum` no existente, por ejemplo, el valor 87 se puede deserializar en la enumeración de color anterior aunque no esté definido un nombre de color correspondiente.

- Una `enum` de marcas no es especial y se trata igual que otra `enum`.

### <a name="datestimes-and-json"></a>Fechas/horas y JSON

El formato JSON no admite directamente fechas y horas. No obstante, se usan correctamente y AJAX de ASP.NET proporciona compatibilidad especial para estos tipos. Al usar proxies AJAX de ASP.NET, el tipo <xref:System.DateTime> de .NET se corresponde completamente con el tipo `DateTime` de JavaScript.

- Cuando no se utiliza ASP.NET, se representa un tipo <xref:System.DateTime> en JSON como una cadena con un formato especial que se describe en la sección de Información avanzada en este tema.

- <xref:System.DateTimeOffset> se representa en JSON como un tipo complejo: {"DateTime":dateTime,"OffsetMinutes":offsetMinutes}. El miembro `offsetMinutes` es el desplazamiento de la hora local respecto a la hora del meridiano de Greenwich (GMT), también conocida como hora universal coordinada (UTC), que está asociado a la ubicación del evento de interés. El miembro `dateTime` representa la instancia temporal en la que se produce el evento de interés (de nuevo, se convierte en un `DateTime` en JavaScript cuando se usa AJAX de ASP.NET y en una cadena cuando no se usa). En la serialización, el miembro `dateTime` siempre se serializa en GMT. Por lo tanto, si se describen las 3:00 a.m. hora de Nueva York, `dateTime` tiene un componente horario de 8:00 a.m. y `offsetMinutes` son 300 (menos 300 minutos o 5 horas con respecto a GMT).

  > [!NOTE]
  > Los objetos <xref:System.DateTime> y <xref:System.DateTimeOffset>, cuando se serializan en JSON, solo conservan información de precisión de milisegundos. Los valores de submilisegundos (micro y nanosegundos) se pierden durante la serialización.

### <a name="xml-types-and-json"></a>Tipos XML y JSON

Los tipos XML se convierten en cadenas JSON.

- Por ejemplo, si un miembro de datos "q" de tipo XElement contiene \<abc/> , el JSON es {"q": " \<abc/> "}.

- Hay algunas reglas especiales que especifican el ajuste de XML; para obtener más información, consulte la sección Información avanzada más adelante en este tema.

- Si está utilizando AJAX de ASP.NET y no desea usar cadenas en JavaScript, pero quiere XML DOM en su lugar, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> en XML en <xref:System.ServiceModel.Web.WebGetAttribute> o la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> en XML en <xref:System.ServiceModel.Web.WebInvokeAttribute>.

### <a name="collections-dictionaries-and-arrays"></a>Colecciones, diccionarios y matrices

Todas las colecciones, diccionarios y matrices se representan en JSON como matrices.

- Cualquier personalización que utilice <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se omite en la representación de JSON.

- Los diccionarios no son una forma para trabajar directamente con JSON. \<string,object>Es posible que el diccionario no se admita de la misma manera en WCF, como se esperaba, al trabajar con otras tecnologías JSON. Por ejemplo, si "abc" está asignado a "xyz" y "def" está asignado a 42 en un diccionario, la representación de JSON no es {"abc":"xyz","def":42} si no que en su lugar es [{"Clave":"abc","Valor":"xyz"},{"Clave":"def","Valor":42}].

- Si desea trabajar con JSON directamente (obteniendo acceso dinámicamente a claves y valores, sin predefinir una restricción rígida), tiene varias opciones:

  - Considere la posibilidad de usar el ejemplo de [serialización JSON (AJAX) de tipo débil](../samples/weakly-typed-json-serialization-sample.md) .

  - Considere usar la interfaz <xref:System.Runtime.Serialization.ISerializable> y los constructores de deserialización; estos dos mecanismos le permiten obtener acceso a parejas de valores y claves de JSON en serialización y deserialización respectivamente, pero no funcionan en escenarios de confianza parcial.

  - Considere la posibilidad de trabajar con la [asignación entre JSON y XML](mapping-between-json-and-xml.md) en lugar de usar un serializador.

  - El *polimorfismo* en el contexto de serialización hace referencia a la capacidad de serializar un tipo derivado donde se espera su tipo base. Hay reglas específicas de JSON especiales al utilizar las colecciones de manera polimórfica, por ejemplo, al asignar una colección a un <xref:System.Object>. Este problema se trata con todo detalle en la sección de Información avanzada más adelante en este tema.

## <a name="additional-details"></a>Detalles adicionales

### <a name="order-of-data-members"></a>Orden de los miembros de datos

El orden de miembros de datos no es importante al utilizar JSON. Específicamente, incluso cuando se establece <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>, los datos de JSON aún se pueden deserializar en cualquier orden.

### <a name="json-types"></a>Tipos JSON

El tipo JSON no tiene que coincidir con la tabla precedente en la deserialización. Por ejemplo, un `Int` normalmente asigna a un número JSON, pero también se puede deserializar correctamente de una cadena JSON siempre que esa cadena contenga un número válido. Es decir, ambos {"q": 42} y {"q": "42"} son válidos si hay un miembro de datos `Int` denominado "q".

### <a name="polymorphism"></a>Polimorfismo

La serialización polimórfica es la capacidad de serializar un tipo derivado donde se espera su tipo base. Esto se admite para la serialización de JSON con WCF comparable a la manera en que se admite la serialización XML. Por ejemplo, puede serializar `MyDerivedType` donde `MyBaseType` se espera o serializar `Int` donde `Object` se espera.

La información de tipo puede perderse al deserializar un tipo derivado si se espera el tipo base, a menos que esté deserializando un tipo complejo. Por ejemplo, si se serializa <xref:System.Uri> donde se espera un <xref:System.Object>, resulta en una cadena de JSON. Si esta cadena se vuelve a deserializar en <xref:System.Object>, se devuelve un <xref:System.String> .NET. El deserializador no conoce el tipo <xref:System.Uri> inicial de la cadena. Generalmente, cuando se espera <xref:System.Object>, todas las cadenas JSON se deserializan como cadenas .NET y todas las matrices JSON usadas para serializar colecciones, diccionarios y matrices .NET se deserializan como <xref:System.Array> .NET de tipo <xref:System.Object>, independientemente de cual haya sido el tipo original real. Un booleano JSON se asigna a un <xref:System.Boolean> .NET. No obstante, al esperar un <xref:System.Object>, los números de JSON se deserializan como <xref:System.Int32>, <xref:System.Decimal> o <xref:System.Double> .NET, donde se escoge automáticamente el tipo más adecuado.

Al deserializar en un tipo de interfaz, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> deserializa como si el tipo declarado fuese un objeto.

Al trabajar con sus tipos base y derivados propios, normalmente se requiere utilizar <xref:System.Runtime.Serialization.KnownTypeAttribute>, <xref:System.ServiceModel.ServiceKnownTypeAttribute> o un mecanismo equivalente. Por ejemplo, si tiene una operación que tiene un `Animal` valor devuelto y realmente devuelve una instancia de `Cat` (derivada de `Animal` ), debe aplicar <xref:System.Runtime.Serialization.KnownTypeAttribute> , al `Animal` tipo o <xref:System.ServiceModel.ServiceKnownTypeAttribute> a la operación y especificar el `Cat` tipo en estos atributos. Para obtener más información, vea [tipos conocidos de contratos de datos](data-contract-known-types.md).

Para obtener detalles sobre cómo funciona la serialización polimórfica y una explicación sobre algunas limitaciones que se deben respetar al usarla, consulte el sección Información avanzada más adelante en este tema.

### <a name="versioning"></a>Control de versiones

Las características de versiones de contratos de datos, incluida la interfaz de <xref:System.Runtime.Serialization.IExtensibleDataObject>, con completamente compatible en JSON. Además, en la mayoría de los casos es posible deserializar un tipo en un formato (por ejemplo, XML) y, a continuación, serializarlo en otro formato (por ejemplo, JSON) y conservar los datos en <xref:System.Runtime.Serialization.IExtensibleDataObject>. Para obtener más información, vea [Forward-Compatible Data Contracts](forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío). Recuerde que JSON no está ordenado por lo que se pierde la información de orden. Además, JSON no admite múltiples parejas de claves y valores con el mismo nombre de clave. Finalmente, todas las operaciones en <xref:System.Runtime.Serialization.IExtensibleDataObject> son inherentemente polimórficas, es decir, que su tipo derivado se asigna a <xref:System.Object>, el tipo base para todos los tipos.

## <a name="json-in-urls"></a>JSON en direcciones URL

Al utilizar puntos de conexión AJAX de ASP.NET con el verbo HTTP GET (usando el atributo <xref:System.ServiceModel.Web.WebGetAttribute>), los parámetros de entrada aparecen en la dirección URL de solicitud en lugar del cuerpo del mensaje. JSON se admite incluso en la dirección URL de la solicitud, por lo que si tiene una operación que toma un `Int` llamado "número" y un `Person` tipo complejo denominado "p", la dirección URL puede ser similar a la siguiente dirección URL.

```html
http://example.com/myservice.svc/MyOperation?number=7&p={"name":"John","age":42}
```

Si está utilizando un control Script Manager de AJAX de ASP.NET y proxy para llamar al servicio, el proxy genera automáticamente esta dirección URL y no se ve. JSON no se puede utilizar en direcciones URL ni en puntos de conexión AJAX de no ASP.NET.

## <a name="advanced-information"></a>Información avanzada

### <a name="iserializable-support"></a>Compatible con ISerializable

#### <a name="supported-and-unsupported-iserializable-types"></a>Tipos compatibles y no compatibles con ISerializable

En general, los tipos que implementan la interfaz <xref:System.Runtime.Serialization.ISerializable> son completamente compatibles al serializar o deserializar JSON. No obstante, algunos de estos tipos (incluidos algunos tipos .NET Framework) se implementan de tal forma que los aspectos de serialización específicos de JSON hacen que no se deserialicen correctamente:

- Con <xref:System.Runtime.Serialization.ISerializable>, el tipo de los miembros de datos individuales nunca se conocen por anticipado. Esto lleva a una situación polimórfica similar a deserializar tipos en un objeto. Como se mencionó anteriormente, esto puede llevar a perder la información de tipo en JSON. Por ejemplo, un tipo que serializa un `enum` en su implementación de <xref:System.Runtime.Serialization.ISerializable> e intenta volver a deserializar correctamente en un `enum` (sin las conversiones adecuadas) tiene errores, porque una `enum` se serializa usando números en JSON y los números JSON se deserializan en tipos numéricos .NET integrados (Int32, decimal o doble). Por tanto, el hecho de que el número usado sea un valor `enum` se pierde.

- Un tipo <xref:System.Runtime.Serialization.ISerializable> que depende de un orden particular de deserialización en su constructor de deserialización también puede tener errores al deserializar algunos datos JSON, porque la mayoría de serializadores JSON no garantizan ningún orden específico.

#### <a name="factory-types"></a>Tipos de fábrica

Mientras que, en general, la interfaz <xref:System.Runtime.Serialization.IObjectReference> se admite en JSON, no se admiten los atributos que requieren la característica "tipo de fábrica" (que devuelven una instancia de un tipo diferente de <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%28System.Runtime.Serialization.StreamingContext%29> del tipo que implementa la interfaz).

### <a name="datetime-wire-format"></a>Formato de conexión DateTime

Los valores <xref:System.DateTime> aparecen como cadenas JSON con el formato "/Date(700000+0500)/", donde el primer número (en el ejemplo proporcionado, 700000) es el número de milisegundos en la zona horaria GMT, hora normal (sin horario de verano) desde la medianoche del 1 de enero de 1970. El número puede ser negativo para representar horas anteriores. La parte del ejemplo que contiene "+0500" es opcional e indica que la hora es de tipo <xref:System.DateTimeKind.Local>, es decir, debe convertirse a la zona horaria local en la deserialización. Si no está presente, la hora se deserializa como <xref:System.DateTimeKind.Utc>. El número real (en el ejemplo, "0500") y su signo (+ o -) se omiten.

Al serializar las horas <xref:System.DateTime>, <xref:System.DateTimeKind.Local> y <xref:System.DateTimeKind.Unspecified> se escriben con un desplazamiento y <xref:System.DateTimeKind.Utc> se escribe sin él.

El código JavaScript del cliente de AJAX de ASP.NET convierte automáticamente estas cadenas en instancias `DateTime` de JavaScript. Si existen otras cadenas con un formato similar que son sean de tipo <xref:System.DateTime> en .NET, también se convierten.

La conversión solo tiene lugar si los caracteres "/" son caracteres de escape (es decir, el JSON es similar a " \\ /Date (700000 + 0500) \\ /") y, por este motivo, el codificador JSON de WCF (habilitado por <xref:System.ServiceModel.WebHttpBinding> ) siempre escapa del carácter "/".

### <a name="xml-in-json-strings"></a>Cadenas XML en JSON

#### <a name="xmlelement"></a>XmlElement

<xref:System.Xml.XmlElement> se serializa como tal, sin ajustes. Por ejemplo, el miembro de datos "x" de tipo <xref:System.Xml.XmlElement> que contiene \<abc/> se representa de la manera siguiente:

```json
{"x":"<abc/>"}
```

#### <a name="arrays-of-xmlnode"></a>Matrices de XmlNode

Los objetos de <xref:System.Array> de tipo <xref:System.Xml.XmlNode> se ajustan en un elemento denominado ArrayOfXmlNode en el espacio de nombres del contrato de datos estándar del tipo. Si "x" es una matriz que contiene el nodo de atributo "N" en el espacio de nombres "ns" que contiene "valor" y un nodo del elemento "M" vacío, la representación es la siguiente.

```json
{"x":"<ArrayOfXmlNode xmlns=\"http://schemas.datacontract.org/2004/07/System.Xml\" a:N=\"value\" xmlns:a=\"ns\"><M/></ArrayOfXmlNode>"}
```

 No se admiten atributos en el espacio de nombres vacío al principio de matrices XmlNode (antes de otros elementos).

#### <a name="ixmlserializable-types-including-xelement-and-dataset"></a>Tipos IXmlSerializable incluidos XElement y DataSet

Los tipos <xref:System.Runtime.Serialization.ISerializable> se subdividen en "tipos Content", "tipos DataSet" y "tipos Element". Para obtener definiciones de estos tipos, consulte [tipos XML y ADO.net en los contratos de datos](xml-and-ado-net-types-in-data-contracts.md).

Los tipos "Content" y "DataSet" se serializan de forma similar a los objetos <xref:System.Array> de <xref:System.Xml.XmlNode> explicados en la sección anterior. Se ajustan en un elemento cuyo nombre y espacio de nombres se corresponde al nombre y espacio de nombres del contrato de datos del tipo en cuestión.

Los tipos "Element" como <xref:System.Xml.Linq.XElement> are se serializan como tales, similar a <xref:System.Xml.XmlElement> explicado anteriormente en este tema.

### <a name="polymorphism"></a>Polimorfismo

#### <a name="preserving-type-information"></a>Conservación de la información de tipo

Como se indicó anteriormente, se admite el polimorfismo en JSON con algunas limitaciones. JavaScript es un lenguaje débilmente tipado y la identidad de tipos normalmente no es un problema. Sin embargo, al usar JSON para comunicarse entre un sistema fuertemente tipado (.NET) y un sistema de tipo débil (JavaScript), es útil conservar la identidad de tipo. Por ejemplo, los tipos con nombres de contrato de datos "Cuadrado" y "Círculo" derivan de un tipo con un nombre de contrato de datos "Forma". Si "Círculo" se envía de .NET a JavaScript y después se devuelve a un método .NET que espera "Forma", es útil en el lado de .NET saber que el objeto en cuestión originalmente era un "Círculo", en otro caso, cualquier información específica al tipo derivado (por ejemplo, el miembro de datos "radio" en "Círculo") se puede perder.

Para conservar la identidad de tipos, al serializar tipos complejos a JSON se puede agregar una "sugerencia de tipo" y deserializador reconoce la sugerencia y actúa correctamente. La "sugerencia de tipo" es un par clave-valor de JSON con el nombre de clave " \_ \_ tipo" (dos subrayados seguidos de la palabra "tipo"). El valor es una cadena JSON de formato "DataContractName:DataContractNamespace" (lo que va antes de los dos puntos es el nombre). Con el ejemplo anterior, "Círculo" se puede serializar de la forma siguiente.

```json
{"__type":"Circle:http://example.com/myNamespace","x":50,"y":70,"radius":10}
```

La sugerencia de tipo es muy similar al atributo `xsi:type` definido por la instancia de esquema XML estándar y se usa al serializar y deserializar XML.

Los miembros de datos denominados " \_ \_ type" están prohibidos debido a un posible conflicto con la sugerencia de tipo.

#### <a name="reducing-the-size-of-type-hints"></a>Reducción del tamaño de sugerencias de tipo

Para reducir el tamaño de los mensajes JSON, el prefijo de espacio de nombres del contrato de datos predeterminado ( `http://schemas.datacontract.org/2004/07/` ) se reemplaza por el carácter "#". (Para que este reemplazo sea reversible, se usa una regla de escape: Si el espacio de nombres comienza con los caracteres "#" o " \\ ", se anexan con un \\ carácter "" adicional). Por lo tanto, si "Circle" es un tipo del espacio de nombres de .NET "MyApp. Shapes", su espacio de nombres de contrato de datos predeterminado es `http://schemas.datacontract.org/2004/07/MyApp` . Las formas y la representación  JSON son las siguientes.

```json
{"__type":"Circle:#MyApp.Shapes","x":50,"y":70,"radius":10}
```

Tanto el nombre truncado (#MyApp. Shapes) como los <http://schemas.datacontract.org/2004/07/MyApp.Shapes> nombres completos () se entienden en la deserialización.

#### <a name="type-hint-position-in-json-objects"></a>Posición de la sugerencia de tipo en objetos JSON

Observe que la sugerencia de tipo debe aparecer primero en la representación JSON. Éste es el único caso donde el orden de las parejas de clave y valor es importante en el procesamiento JSON. Por ejemplo, lo siguiente no es una forma válida de especificar una sugerencia de tipo.

```json
{"x":50,"y":70,"radius":10,"__type":"Circle:#MyApp.Shapes"}
```

Tanto las <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> páginas de cliente de WCF como las usadas por las páginas de cliente de ASP.NET AJAX siempre emiten primero la sugerencia de tipo.

#### <a name="type-hints-apply-only-to-complex-types"></a>Las sugerencias de tipo solo se aplican a tipos complejos.

No hay ninguna manera de emitir una sugerencia de tipo para tipos no complejos. Por ejemplo, si una operación tiene un valor de devolución de <xref:System.Object> pero devuelve un Círculo, la representación JSON se puede mostrar antes y la información de tipo se conserva. No obstante, si se devuelve el identificador URI, la representación JSON es una cadena y se pierde el hecho de la cadena usada para representar un URI. Esto se aplica no solo a tipos primitivos, si no también a colecciones y matrices.

#### <a name="when-are-type-hints-emitted"></a>Cuando se emiten sugerencias de tipo

Las sugerencias de tipo pueden aumentar de forma significativa el tamaño del mensaje (una forma de mitigarlo es usar espacios de nombres de contratos de datos más cortos si es posible). Por consiguiente, rigen las siguientes reglas si se emiten sugerencias de tipo:

- Al usar ASP.NET AJAX, las sugerencias de tipo siempre se emiten cuando es posible, incluso si no existe una asignación base/derivada, por ejemplo, incluso si un Círculo se asigna a Círculo. (Esto es necesario para habilitar completamente el proceso de llamada desde el entorno JSON fuertemente tipado en el entorno de .NET fuertemente tipado sin pérdida de información.)

- Al usar servicios de AJAX sin integración de ASP.NET, las sugerencias de tipo solo se emiten cuando existe una asignación base/derivada, es decir, se emiten cuando un Círculo se asigna a Forma o <xref:System.Object>, pero no cuando se asigna a Círculo. Esto proporciona la información mínima necesaria para implementar correctamente un cliente JavaScript, por tanto para mejorar el rendimiento, pero no protege contra la pérdida de información en clientes designado de forma incorrecta. Evite asignaciones base/derivadas juntas en el servidor si desea evitar este problema en el cliente.

- Al utilizar el tipo <xref:System.Runtime.Serialization.DataContractSerializer>, el parámetro de constructor `alwaysEmitTypeInformation` le permite elegir entre los dos modos anteriores, con el valor predeterminado de "`false`" (solo se emiten sugerencias de tipo cuando son necesarias).

#### <a name="duplicate-data-member-names"></a>Nombres de miembros de datos duplicados

La información de tipo derivado se presenta en el mismo objeto JSON que la información de tipo base y puede producirse en cualquier orden. Por ejemplo, `Shape` se puede representar como se indica a continuación.

```json
{"__type":"Shape:#MyApp.Shapes","x":50,"y":70}
```

Mientras que Círculo puede representarse de la manera siguiente.

```json
{"__type":"Circle:#MyApp.Shapes","x":50, "radius":10,"y":70}
```

Si el `Shape` tipo base también contenía un miembro de datos denominado " `radius` ", esto conduce a una colisión en la serialización (porque los objetos JSON no pueden tener nombres de clave repetidos) y la deserialización (porque no está claro si "RADIUS" hace referencia a `Shape.radius` o `Circle.radius` ). Por tanto, mientras que generalmente no se recomienda el concepto de "ocultamiento de propiedad" (miembros de datos con el mismo nombre en clases base y derivadas) en clases de contratos de datos, realmente está prohibido en el caso de JSON.

#### <a name="polymorphism-and-ixmlserializable-types"></a>Polimorfismo y tipos IXmlSerializable

Los tipos <xref:System.Xml.Serialization.IXmlSerializable> pueden asignarse de forma polimórfica a otro como se hace habitualmente siempre que se cumplan los requisitos de Tipos conocidos, según las reglas de contrato de datos normal. No obstante, serializar un tipo <xref:System.Xml.Serialization.IXmlSerializable> en vez de <xref:System.Object> produce una pérdida de información de tipo como resultado en una cadena JSON.

#### <a name="polymorphism-and-certain-interface-types"></a>Polimorfismo y determinados tipos de interfaz

Se prohíbe serializar un tipo de colección o un tipo que implemente <xref:System.Xml.Serialization.IXmlSerializable> donde no se espera un tipo de no colección <xref:System.Xml.Serialization.IXmlSerializable> (excepto para <xref:System.Object>). Por ejemplo, una interfaz personalizada denominada `IMyInterface` y un tipo `MyType` que implementan ambos <xref:System.Collections.Generic.IEnumerable%601> tipos `int` y `IMyInterface` . Está prohibido devolver `MyType` desde una operación cuyo tipo de valor devuelto sea `IMyInterface` . Esto se debe a que se `MyType` debe serializar como una matriz JSON y requiere una sugerencia de tipo y, como se indicó antes, no se puede incluir una sugerencia de tipo con matrices, solo con tipos complejos.

#### <a name="known-types-and-configuration"></a>Tipos conocidos y configuración

Todos los mecanismos de tipos conocidos usados por <xref:System.Runtime.Serialization.DataContractSerializer> también se admiten de la misma manera en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. Ambos serializadores leen el mismo elemento de configuración, [\<dataContractSerializer>](../../configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md) en [\<system.runtime.serialization>](../../configure-apps/file-schema/wcf/system-runtime-serialization.md) , para detectar los tipos conocidos agregados a través de un archivo de configuración.

#### <a name="collections-assigned-to-object"></a>Colecciones asignadas a objetos

Las colecciones asignadas a objetos se serializan como si fueran colecciones que implementan  <xref:System.Collections.Generic.IEnumerable%601>: una matriz JSON donde cada entrada tiene una sugerencia de tipo si es un tipo complejo. Por ejemplo, un <xref:System.Collections.Generic.List%601> de tipo `Shape` asignado a <xref:System.Object> tiene un aspecto similar al siguiente.

```json
[{"__type":"Shape:#MyApp.Shapes","x":50,"y":70},
{"__type":"Shape:#MyApp.Shapes","x":58,"y":73},
{"__type":"Shape:#MyApp.Shapes","x":41,"y":32}]
```

Al volver a deserializar en <xref:System.Object>:

- `Shape` debe estar en la lista de tipos conocidos. Tener <xref:System.Collections.Generic.List%601> un tipo `Shape` en tipos conocidos no tiene ningún efecto. Tenga en cuenta que, en este caso, no tiene que agregar `Shape` a tipos conocidos en la serialización; esto se hace automáticamente.

- La colección se deserializa como un <xref:System.Array> de tipo <xref:System.Object> que contiene `Shape` instancias de.

#### <a name="derived-collections-assigned-to-base-collections"></a>Colecciones derivadas asignadas a colecciones base

Cuando una colección derivada se asigna a una colección base, la colección normalmente se serializa como si fuera una colección del tipo base. No obstante, si el tipo de elemento de la colección derivada no se puede asignar al tipo de elemento de la colección base, se inicia una excepción.

#### <a name="type-hints-and-dictionaries"></a>Sugerencias de tipo y diccionarios

Cuando se asigna un diccionario a un <xref:System.Object>, cada entrada Clave y Valor del diccionario se trata como si se asignara a <xref:System.Object> y se obtiene una sugerencia de tipo.

Al serializar tipos de diccionario, el objeto JSON que contiene los miembros "Clave" y "Valor" no se ven afectados por el parámetro `alwaysEmitTypeInformation` y solo contiene una sugerencia de tipo cuando las reglas de la colección precedente lo requieren.

### <a name="valid-json-key-names"></a>Nombres de claves JSON válidos

El serializador XML codifica nombres de claves que no son nombres XML válidos. Por ejemplo, un miembro de datos con el nombre "123" tendría un nombre codificado como " \_ x0031 \_ \_ x0032 \_ \_ x0033 \_ " porque "123" es un nombre de elemento XML no válido (empieza con un dígito). Se puede producir una situación similar con algunos juegos de caracteres internacionales no válidos en nombres de XML. Para obtener una explicación de este efecto de XML en el procesamiento de JSON, consulte [asignación entre JSON y XML](mapping-between-json-and-xml.md).

## <a name="see-also"></a>Vea también

- [Compatibilidad con JSON y otros formatos de transferencia de datos](support-for-json-and-other-data-transfer-formats.md)
