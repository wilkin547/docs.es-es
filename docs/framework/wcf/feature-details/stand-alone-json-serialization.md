---
title: "Serializaci&#243;n independiente de JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 312bd7b2-1300-4b12-801e-ebe742bd2287
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Serializaci&#243;n independiente de JSON
JSON \(JavaScript Object Notation\) es un formato de datos diseñado específicamente para usarse por código JavaScript que se ejecute en páginas web dentro del explorador.Es el formato de datos predeterminado usado por servicios de AJAX de ASP.NET creados en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 Este formato también puede usarse al crear servicios de AJAX sin integrar con ASP.NET, en este caso, XML es el valor predeterminado pero se puede elegir JSON.  
  
 Finalmente, si necesita compatibilidad JSON pero no está creando un servicio de AJAX, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> permite serializar directamente los objetos .NET en datos JSON y volver a deserializar estos datos en instancias de tipos .NET.Para obtener una descripción sobre cómo hacerlo, vea [Cómo serializar y deserializar datos JSON](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 Al trabajar con JSON, se admiten los mismos tipos .NET, con una pocas excepciones, como las compatibles con <xref:System.Runtime.Serialization.DataContractSerializer>.Para obtener una lista de tipos admitidos, vea [Tipos admitidos por el serializador de contrato de datos](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).Entre éstos se incluyen los tipos más primitivos, la mayoría de tipos de colección y matriz, y también tipos complejos que usan <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
## Asignación de tipos .NET a tipos JSON  
 En la siguiente tabla se muestra la correspondencia entre los tipos .NET y los tipos JSON\/JavaScript cuando se asignan mediante procedimientos de serialización y deserialización.  
  
|Tipos .NET|JSON\/JavaScript|Notas|  
|----------------|----------------------|-----------|  
|Todos los tipos numéricos, por ejemplo <xref:System.Int32>, <xref:System.Decimal> o <xref:System.Double>|Número|Los valores especiales como `Double.NaN`, `Double.PositiveInfinity` y `Double.NegativeInfinity` no son compatibles y dan como resultado una JSON no válida.|  
|<xref:System.Enum>|Número|Vea "Enumeraciones y JSON" más adelante en este tema.|  
|<xref:System.Boolean>|Boolean|\-\-|  
|<xref:System.String>, <xref:System.Char>|Cadena|\-\-|  
|<xref:System.Timespan>, <xref:System.Guid>, <xref:System.Uri>|Cadena|El formato de estos tipos en JSON es el mismo que en XML \(básicamente, TimeSpan en el formato de duración de ISO 8601, GUID en el formato "12345678\-ABCD\-ABCD\-ABCD\-1234567890AB" y URI en su forma de cadena natural, como "http:\/\/www.example.com"\).Para obtener información exacta, consulte [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).|  
|<xref:System.Xml.XmlQualifiedName>|String|El formato es "nombre:espaciodenombres" \(cualquier cosa antes de los primeros dos puntos es el nombre\).Puede que falte el nombre o el espacio de nombres.Si no hay ningún espacio de nombres, también se pueden omitir los dos puntos.|  
|<xref:System.Array> de tipo <xref:System.Byte>|Matriz de números|Cada número representa el valor de un byte.|  
|<xref:System.Datetime>|DateTime \(fecha y hora\) o cadena|Vea Fechas\/horas y JSON más adelante en este tema.|  
|<xref:System.DatetimeOffset>|Tipo complejo|Vea Fechas\/horas y JSON más adelante en este tema.|  
|Tipos XML y ADO.NET \(<xref:System.Xml.XmlElement>,<br /><br /> <xref:System.Xml.Linq.XElement>.Matrices de <xref:System.Xml.XmlNode>,<br /><br /> <xref:System.Runtime.Serialization.ISerializable>,<br /><br /> <xref:System.Data.DataSet>\).|Cadena|Consulte la sección Tipos XML y JSON en este tema.|  
|<xref:System.DBNull>|Tipo complejo vacío|\-\-|  
|Colecciones, diccionarios y matrices|Matriz|Consulte la sección Colecciones, diccionarios y matrices en este tema.|  
|Tipos complejos \(con el <xref:System.Runtime.Serialization.DataContractAttribute> o <xref:System.SerializableAttribute> aplicado\)|Tipo complejo|Los miembros de datos se convierten en miembros del tipo complejo de JavaScript.|  
|Tipos complejos que implementan la interfaz <xref:System.Runtime.Serialization.ISerializable>\)|Tipo complejo|Igual que otros tipos complejos, pero algunos tipos <xref:System.Runtime.Serialization.ISerializable> no se admiten; vea la nota sobre la compatibilidad de ISerializable en la sección de Información avanzada de este tema.|  
|Valor `Null` para cualquier tipo|Null|Los tipos que aceptan valores null también se admiten y asignan a JSON de la misma manera que los tipos que no aceptan valores null.|  
  
### Enumeraciones y JSON  
 Los valores del miembro de enumeración se tratan como números en JSON, que es diferente de cómo se tratan en contratos de datos, donde se incluyen como nombres de miembros.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] el tratamiento de contratos de datos, vea [Tipos de enumeración en contratos de datos](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).  
  
-   Por ejemplo, si tiene `public enum Color {red, green, blue, yellow, pink}`, al serializar `yellow`, se genera el número 3 y no la cadena "amarillo".  
  
-   Todos los miembros `enum` son serializables.Se omiten los atributos <xref:System.Runtime.Serialization.EnumMemberAttribute> y <xref:System.NonSerializedAttribute> si se utilizan.  
  
-   Es posible deserializar un valor `enum` no existente, por ejemplo, el valor 87 se puede deserializar en la enumeración de color anterior aunque no esté definido un nombre de color correspondiente.  
  
-   Una `enum` de marcas no es especial y se trata igual que otra `enum`.  
  
### Fechas\/horas y JSON  
 El formato JSON no admite directamente fechas y horas.No obstante, se usan correctamente y AJAX de ASP.NET proporciona compatibilidad especial para estos tipos.Al usar proxies AJAX de ASP.NET, el tipo <xref:System.DateTime> de .NET se corresponde completamente con el tipo `DateTime` de JavaScript.  
  
-   Cuando no se utiliza ASP.NET, se representa un tipo <xref:System.DateTime> en JSON como una cadena con un formato especial que se describe en la sección de Información avanzada en este tema.  
  
-   <xref:System.DateTimeOffset> se representa en JSON como un tipo complejo: {"DateTime":dateTime,"OffsetMinutes":offsetMinutes}.El miembro `offsetMinutes` es el desplazamiento de la hora local respecto a la hora del meridiano de Greenwich \(GMT\), también conocida como hora universal coordinada \(UTC\), que está asociado a la ubicación del evento de interés.El miembro `dateTime` representa la instancia temporal en la que se produce el evento de interés \(de nuevo, se convierte en un `DateTime` en JavaScript cuando se usa AJAX de ASP.NET y en una cadena cuando no se usa\).En la serialización, el miembro `dateTime` siempre se serializa en GMT.Por lo tanto, si se describen las 3:00 a.m. hora de Nueva York, `dateTime` tiene un componente horario de 8:00 a.m. y `offsetMinutes` son 300 \(menos 300 minutos o 5 horas con respecto a GMT\).  
  
    > [!NOTE]
    >  Los objetos <xref:System.DateTime> y <xref:System.DateTimeOffset>, cuando se serializan en JSON, solo conservan información de precisión de milisegundos.Los valores de submilisegundos \(micro y nanosegundos\) se pierden durante la serialización.  
  
### Tipos XML y JSON  
 Los tipos XML se convierten en cadenas JSON.  
  
-   Por ejemplo, si un miembro de datos "q" de tipo XElement contiene \<abc\/\>, JSON es {"q":"\<abc\/\>"}.  
  
-   Hay algunas reglas especiales que especifican el ajuste de XML; para obtener más información, consulte la sección Información avanzada más adelante en este tema.  
  
-   Si está usando AJAX de ASP.NET y no desea emplear cadenas en JavaScript, pero quiere XML DOM en su lugar, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> en XML en <xref:System.ServiceModel.Web.WebGetAttribute> o la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> en XML en <xref:System.ServiceModel.Web.WebInvokeAttribute>.  
  
### Colecciones, diccionarios y matrices  
 Todas las colecciones, diccionarios y matrices se representan en JSON como matrices.  
  
-   Cualquier personalización que utilice <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se omite en la representación de JSON.  
  
-   Los diccionarios no son una forma para trabajar directamente con JSON.Diccionario\<cadena,objeto\> puede no ser compatible de la misma manera en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como se espera que funcione con otras tecnologías de JSON.Por ejemplo, si "abc" está asignado a "xyz" y "def" está asignado a 42 en un diccionario, la representación de JSON no es {"abc":"xyz","def":42} si no que en su lugar es \[{"Clave":"abc","Valor":"xyz"},{"Clave":"def","Valor":42}\].  
  
-   Si desea trabajar con JSON directamente \(obteniendo acceso dinámicamente a claves y valores, sin predefinir una restricción rígida\), tiene varias opciones:  
  
    -   Considere utilizar el ejemplo [Ejemplo de serialización JSON débilmente tipada \(AJAX\)](../../../../docs/framework/wcf/samples/weakly-typed-json-serialization-sample.md) siguiente:  
  
    -   Considere usar la interfaz <xref:System.Runtime.Serialization.ISerializable> y los constructores de deserialización; estos dos mecanismos le permiten obtener acceso a parejas de valores y claves de JSON en serialización y deserialización respectivamente, pero no funcionan en escenarios de confianza parcial.  
  
    -   Considere trabajar con [Asignación entre JSON y XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md) en vez de utilizar un serializador.  
  
    -   *Polimorfismo* en el contexto de serialización hace referencia a la capacidad de serializar un tipo derivado donde se espera su tipo base.Hay reglas específicas de JSON especiales al utilizar las colecciones de manera polimórfica, por ejemplo, al asignar una colección a un <xref:System.Object>.Este problema se trata con todo detalle en la sección de Información avanzada más adelante en este tema.  
  
## Detalles adicionales  
  
### Orden de los miembros de datos  
 El orden de miembros de datos no es importante al utilizar JSON.Específicamente, incluso cuando se establece <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>, los datos de JSON aún se pueden deserializar en cualquier orden.  
  
### Tipos JSON  
 El tipo JSON no tiene que coincidir con la tabla precedente en la deserialización.Por ejemplo, un `Int` normalmente asigna a un número JSON, pero también se puede deserializar correctamente de una cadena JSON siempre que esa cadena contenga un número válido.Es decir, ambos {"q": 42} y {"q": "42"} son válidos si hay un miembro de datos `Int` denominado "q".  
  
### Polimorfismo  
 La serialización polimórfica es la capacidad de serializar un tipo derivado donde se espera su tipo base.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite la serialización JSON de la misma forma que admite la serialización XML.Por ejemplo, puede serializar `MyDerivedType` donde se espera `MyBaseType` o serializar `Int` donde se espera `Object`.  
  
 La información de tipo puede perderse al deserializar un tipo derivado si se espera el tipo base, a menos que esté deserializando un tipo complejo.Por ejemplo, si se serializa <xref:System.Uri> donde se espera un <xref:System.Object>, resulta en una cadena de JSON.Si esta cadena se vuelve a deserializar en <xref:System.Object>, se devuelve un <xref:System.String> .NET.El deserializador no conoce el tipo <xref:System.Uri> inicial de la cadena.Generalmente, cuando se espera <xref:System.Object>, todas las cadenas JSON se deserializan como cadenas .NET y todas las matrices JSON usadas para serializar colecciones, diccionarios y matrices .NET se deserializan como <xref:System.Array> .NET de tipo <xref:System.Object>, independientemente de cual haya sido el tipo original real.Un booleano JSON se asigna a un <xref:System.Boolean> .NET.No obstante, al esperar un <xref:System.Object>, los números de JSON se deserializan como <xref:System.Int32>, <xref:System.Decimal> o <xref:System.Double> .NET, donde se escoge automáticamente el tipo más adecuado.  
  
 Al deserializar en un tipo de interfaz, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> deserializa como si el tipo declarado fuese un objeto.  
  
 Al trabajar con sus tipos base y derivados propios, normalmente se requiere utilizar <xref:System.Runtime.Serialization.KnownTypeAttribute>, <xref:System.ServiceModel.ServiceKnownTypeAttribute> o un mecanismo equivalente.Por ejemplo, si tiene una operación con un valor devuelto `Animal` y realmente devuelve una instancia de `Gato` \(derivada de `Animal`\), debe aplicar <xref:System.Runtime.Serialization.KnownTypeAttribute> al tipo `Animal` o <xref:System.ServiceModel.ServiceKnownTypeAttribute> a la operación y especificar el tipo `Gato` en estos atributos.Para obtener más información, consulte [Tipos conocidos de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 Para obtener detalles sobre cómo funciona la serialización polimórfica y una explicación sobre algunas limitaciones que se deben respetar al usarla, consulte el sección Información avanzada más adelante en este tema.  
  
### Control de versiones  
 Las características de versiones de contratos de datos, incluida la interfaz de <xref:System.Runtime.Serialization.IExtensibleDataObject>, con completamente compatible en JSON.Además, en la mayoría de los casos es posible deserializar un tipo en un formato \(por ejemplo, XML\) y, a continuación, serializarlo en otro formato \(por ejemplo, JSON\) y conservar los datos en <xref:System.Runtime.Serialization.IExtensibleDataObject>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Contratos de datos compatibles con el reenvío](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).Recuerde que JSON no está ordenado por lo que se pierde la información de orden.Además, JSON no admite múltiples parejas de claves y valores con el mismo nombre de clave.Finalmente, todas las operaciones en <xref:System.Runtime.Serialization.IExtensibleDataObject> son inherentemente polimórficas, es decir, que su tipo derivado se asigna a <xref:System.Object>, el tipo base para todos los tipos.  
  
## JSON en direcciones URL  
 Al utilizar extremos AJAX de ASP.NET con el verbo HTTP GET \(usando el atributo <xref:System.ServiceModel.Web.WebGetAttribute>\), los parámetros de entrada aparecen en la dirección URL de solicitud en lugar del cuerpo del mensaje.JSON incluso se admite en la URL de la solicitud, por lo que si tiene una operación que tome un `Int` llamada "número" y un tipo complejo de `Person`, llamado "p", la dirección URL pueda parecerse a la dirección URL siguiente.  
  
```  
http://example.com/myservice.svc/MyOperation?number=7&p={"name":"John","age":42}  
```  
  
 Si está utilizando un control Script Manager de AJAX de ASP.NET y proxy para llamar al servicio, el proxy genera automáticamente esta dirección URL y no se ve.JSON no se puede utilizar en direcciones URL ni en extremos AJAX de no ASP.NET.  
  
## Información avanzada  
  
### Compatible con ISerializable  
  
#### Tipos compatibles y no compatibles con ISerializable  
 En general, los tipos que implementan la interfaz <xref:System.Runtime.Serialization.ISerializable> son completamente compatibles al serializar o deserializar JSON.No obstante, algunos de estos tipos \(incluidos algunos tipos .NET Framework\) se implementan de tal forma que los aspectos de serialización específicos de JSON hacen que no se deserialicen correctamente:  
  
-   Con <xref:System.Runtime.Serialization.ISerializable>, el tipo de los miembros de datos individuales nunca se conocen por anticipado.Esto lleva a una situación polimórfica similar a deserializar tipos en un objeto.Como se mencionó anteriormente, esto puede llevar a perder la información de tipo en JSON.Por ejemplo, un tipo que serializa un `enum` en su implementación de <xref:System.Runtime.Serialization.ISerializable> e intenta volver a deserializar correctamente en un `enum` \(sin las conversiones adecuadas\) tiene errores, porque una `enum` se serializa usando números en JSON y los números JSON se deserializan en tipos numéricos .NET integrados \(Int32, decimal o doble\).Por tanto, el hecho de que el número usado sea un valor `enum` se pierde.  
  
-   Un tipo <xref:System.Runtime.Serialization.ISerializable> que depende de un orden particular de deserialización en su constructor de deserialización también puede tener errores al deserializar algunos datos JSON, porque la mayoría de serializadores JSON no garantizan ningún orden específico.  
  
#### Tipos de fábrica  
 Mientras que, en general, la interfaz <xref:System.Runtime.Serialization.IObjectReference> se admite en JSON, no se admiten los atributos que requieren la característica "tipo de fábrica" \(que devuelven una instancia de un tipo diferente de <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%28System.Runtime.Serialization.StreamingContext%29> del tipo que implementa la interfaz\).  
  
### Formato de conexión DateTime  
 Los valores <xref:System.DateTime> aparecen como cadenas JSON con el formato "\/Date\(700000\+0500\)\/", donde el primer número \(en el ejemplo proporcionado, 700000\) es el número de milisegundos en la zona horaria GMT, hora normal \(sin horario de verano\) desde la medianoche del 1 de enero de 1970.El número puede ser negativo para representar horas anteriores.La parte del ejemplo que contiene "\+0500" es opcional e indica que la hora es de tipo <xref:System.DateTimeKind>, es decir, debe convertirse a la zona horaria local en la deserialización.Si no está presente, la hora se deserializa como <xref:System.DateTimeKind>.El número real \(en el ejemplo, "0500"\) y su signo \(\+ o \-\) se omiten.  
  
 Al serializar las horas <xref:System.DateTime>, <xref:System.DateTimeKind> y <xref:System.DateTimeKind> se escriben con un desplazamiento y <xref:System.DateTimeKind> se escribe sin él.  
  
 El código JavaScript del cliente de AJAX de ASP.NET convierte automáticamente estas cadenas en instancias `DateTime` de JavaScript.Si existen otras cadenas con un formato similar que son sean de tipo <xref:System.DateTime> en .NET, también se convierten.  
  
 La conversión solo se realiza si los caracteres "\/" tienen escape \(es decir, JSON se parece a "\\\/Date\(700000\+0500\)\\\/"\) y, por este motivo, del codificador JSON de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(habilitado por <xref:System.ServiceModel.WebHttpBinding>\) siempre tiene escape en el carácter "\/".  
  
### Cadenas XML en JSON  
  
#### XmlElement  
 <xref:System.Xml.XmlElement> se serializa como tal, sin ajustes.Por ejemplo, el miembro de datos "x" de tipo <xref:System.Xml.XmlElement> que contiene \<abc\/\> se representa de la forma siguiente.  
  
```  
{"x":"<abc/>"}  
```  
  
#### Matrices de XmlNode  
 Los objetos de <xref:System.Array> de tipo <xref:System.Xml.XmlNode> se ajustan en un elemento denominado ArrayOfXmlNode en el espacio de nombres del contrato de datos estándar del tipo.Si "x" es una matriz que contiene el nodo de atributo "N" en el espacio de nombres "ns" que contiene "valor" y un nodo del elemento "M" vacío, la representación es la siguiente.  
  
```  
{"x":"<ArrayOfXmlNode xmlns=\"http://schemas.datacontract.org/2004/07/System.Xml\" a:N=\"value\" xmlns:a=\"ns\"><M/></ArrayOfXmlNode>"}  
```  
  
 No se admiten atributos en el espacio de nombres vacío al principio de matrices XmlNode \(antes de otros elementos\).  
  
#### Tipos IXmlSerializable incluidos XElement y DataSet  
 Los tipos <xref:System.Runtime.Serialization.ISerializable> se subdividen en "tipos Content", "tipos DataSet" y "tipos Element".Para obtener definiciones de estos tipos, consulte [Clases de XML y ADO.NET en contratos de datos](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).  
  
 Los tipos "Content" y "DataSet" se serializan de forma similar a los objetos <xref:System.Array> de <xref:System.Xml.XmlNode> explicados en la sección anterior.Se ajustan en un elemento cuyo nombre y espacio de nombres se corresponde al nombre y espacio de nombres del contrato de datos del tipo en cuestión.  
  
 Los tipos "Element" como <xref:System.Xml.Linq.XElement> are se serializan como tales, similar a <xref:System.Xml.XmlElement> explicado anteriormente en este tema.  
  
### Polimorfismo  
  
#### Conservación de la información de tipo  
 Como se indicó anteriormente, se admite el polimorfismo en JSON con algunas limitaciones.JavaScript es un lenguaje débilmente tipado y la identidad de tipos normalmente no es un problema.No obstante, al usar JSON para comunicarse entre un sistema fuertemente tipado \(.NET\) y un sistema débilmente tipado \(JavaScript\), es útil conservar la identidad de tipos.Por ejemplo, los tipos con nombres de contrato de datos "Cuadrado" y "Círculo" derivan de un tipo con un nombre de contrato de datos "Forma".Si "Círculo" se envía de .NET a JavaScript y después se devuelve a un método .NET que espera "Forma", es útil en el lado de .NET saber que el objeto en cuestión originalmente era un "Círculo", en otro caso, cualquier información específica del tipo derivado \(por ejemplo, el miembro de datos "radio" en "Círculo"\) se puede perder.  
  
 Para conservar la identidad de tipos, al serializar tipos complejos a JSON se puede agregar una "sugerencia de tipo" y deserializador reconoce la sugerencia y actúa correctamente.La "sugerencia de tipo" es una pareja de clave y valor de JSON con el nombre de clave de "\_\_type" \(dos caracteres de subrayado seguidos de la palabra "type"\).El valor es una cadena JSON de formato "DataContractName:DataContractNamespace" \(lo que va antes de los dos puntos es el nombre\).Con el ejemplo anterior, "Círculo" se puede serializar de la forma siguiente.  
  
```  
{"__type":"Circle:http://example.com/myNamespace","x":50,"y":70,"radius":10}  
```  
  
 La sugerencia de tipo es muy similar al atributo `xsi:type` definido por la instancia de esquema XML estándar y se usa al serializar y deserializar XML.  
  
 Están prohibidos los miembros de datos con el nombre "\_\_type" debido a posibles conflictos con la sugerencia de tipo.  
  
#### Reducción del tamaño de sugerencias de tipo  
 Para reducir el tamaño de mensajes JSON, el prefijo del espacio de nombres del contrato de datos predeterminado \(http:\/\/schemas.datacontract.org\/2004\/07\/\) se reemplaza con el carácter "\#".\(Para hacer reversible este reemplazo, se usa una regla de escape: si el espacio de nombres empieza con los caracteres "\#" o "\\", se agregan con un carácter extra "\\"\).Por tanto, si "Círculo" es un tipo del espacio de nombres de .NET "MyApp.Shapes", su espacio de nombres del contrato de datos predeterminado es http:\/\/schemas.datacontract.org\/2004\/07\/MyApp.Las formas y la representación  JSON son las siguientes.  
  
```  
{"__type":"Circle:#MyApp.Shapes","x":50,"y":70,"radius":10}  
```  
  
 En la deserialización se entienden los nombres \(\#MyApp.Shapes\) truncado y \(http:\/\/schemas.datacontract.org\/2004\/07\/MyApp.Shapes\) completo.  
  
#### Posición de la sugerencia de tipo en objetos JSON  
 Observe que la sugerencia de tipo debe aparecer primero en la representación JSON.Éste es el único caso donde el orden de las parejas de clave y valor es importante en el procesamiento JSON.Por ejemplo, lo siguiente no es una forma válida de especificar una sugerencia de tipo.  
  
```  
{"x":50,"y":70,"radius":10,"__type":"Circle:#MyApp.Shapes"}  
```  
  
 Los <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> usados por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y as páginas del cliente AJAX de ASP.NET siempre emiten primero la sugerencia de tipo.  
  
#### Las sugerencias de tipo solo se aplican a tipos complejos.  
 No hay ninguna manera de emitir una sugerencia de tipo para tipos no complejos.Por ejemplo, si una operación tiene un valor de devolución de <xref:System.Object> pero devuelve un Círculo, la representación JSON se puede mostrar antes y la información de tipo se conserva.No obstante, si se devuelve el identificador URI, la representación JSON es una cadena y se pierde el hecho de la cadena usada para representar un URI.Esto se aplica no solo a tipos primitivos, si no también a colecciones y matrices.  
  
#### Cuando se emiten sugerencias de tipo  
 Las sugerencias de tipo pueden aumentar de forma significativa el tamaño del mensaje \(una forma de mitigarlo es usar espacios de nombres de contratos de datos más cortos si es posible\).Por consiguiente, rigen las siguientes reglas si se emiten sugerencias de tipo:  
  
-   Al usar ASP.NET AJAX, las sugerencias de tipo siempre se emiten cuando es posible, incluso si no existe una asignación base\/derivada, por ejemplo, incluso si un Círculo se asigna a Círculo.\(Esto es necesario para habilitar completamente el proceso de llamada del entorno JSON de tipo flexible en el entorno .NET de tipo inflexible sin sorpresas de pérdidas de información\).  
  
-   Al usar servicios de AJAX sin integración de ASP.NET, las sugerencias de tipo solo se emiten cuando existe una asignación base\/derivada, es decir, se emiten cuando un Círculo se asigna a Forma o <xref:System.Object>, pero no cuando se asigna a Círculo.Esto proporciona la información mínima necesaria para implementar correctamente un cliente JavaScript, mejorando por tanto el rendimiento, pero no protege contra la pérdida de información de tipos en clientes diseñados de forma incorrecta.Evite asignaciones base\/derivadas juntas en el servidor si desea evitar este problema en el cliente.  
  
-   Al utilizar el tipo <xref:System.Runtime.Serialization.DataContractSerializer>, el parámetro de constructor `alwaysEmitTypeInformation` le permite elegir entre los dos modos anteriores, con el valor predeterminado de "`false`" \(solo se emiten sugerencias de tipo cuando son necesarias\).  
  
#### Nombres de miembros de datos duplicados  
 La información de tipo derivado se presenta en el mismo objeto JSON que la información de tipo base y puede producirse en cualquier orden.Por ejemplo, `Forma` puede representarse de la manera siguiente.  
  
```  
{"__type":"Shape:#MyApp.Shapes","x":50,"y":70}  
```  
  
 Mientras que Círculo puede representarse de la manera siguiente.  
  
```  
{"__type":"Circle:#MyApp.Shapes","x":50, "radius":10,"y":70}  
```  
  
 Si el tipo base `Forma` también tenía un miembro de datos denominado "`radio`", esto lleva a una colisión en la serialización \(porque los objetos JSON no pueden tener nombres clave repetidos\) y la deserialización \(porque no está claro si "radio" hace referencia a `Forma.radio` o a `Círculo.radio`\).Por tanto, mientras que generalmente no se recomienda el concepto de "ocultamiento de propiedad" \(miembros de datos con el mismo nombre en clases base y derivadas\) en clases de contratos de datos, realmente está prohibido en el caso de JSON.  
  
#### Polimorfismo y tipos IXmlSerializable  
 Los tipos <xref:System.Xml.Serialization.IXmlSerializable> pueden asignarse de forma polimórfica a otro como se hace habitualmente siempre que se cumplan los requisitos de Tipos conocidos, según las reglas de contrato de datos normal.No obstante, serializar un tipo <xref:System.Xml.Serialization.IXmlSerializable> en vez de <xref:System.Object> produce una pérdida de información de tipo como resultado en una cadena JSON.  
  
#### Polimorfismo y determinados tipos de interfaz  
 Se prohíbe serializar un tipo de colección o un tipo que implemente <xref:System.Xml.Serialization.IXmlSerializable> donde no se espera un tipo de no colección <xref:System.Xml.Serialization.IXmlSerializable> \(excepto para <xref:System.Object>\).Por ejemplo, una interfaz personalizada denominada `IMyInterface` y un tipo `MyType` que implementan <xref:System.Collections.Generic.IEnumerable%601> de tipo `int` y `IMyInterface`.Se prohíbe devolver `MyType` desde una operación cuyo tipo devuelto es `IMyInterface`.Esto es porque `MyType` debe serializarse como una matriz JSON y requiere una sugerencia de tipo y, como se indicó antes, no se puede incluir una sugerencia de tipo con matrices, solo con tipos complejos.  
  
#### Tipos conocidos y configuración  
 Todos los mecanismos de tipos conocidos usados por <xref:System.Runtime.Serialization.DataContractSerializer> también se admiten de la misma manera en <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.Los dos serializadores leen el mismo elemento de configuración, [\<dataContractSerializer\>](../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)[\<system.runtime.serialization\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md), para descubrir tipos conocidos agregados a través de un archivo de configuración.  
  
#### Colecciones asignadas a objetos  
 Las colecciones asignadas a objetos se serializan como si fueran colecciones que implementan  <xref:System.Collections.Generic.IEnumerable%601>: una matriz JSON donde cada entrada tiene una sugerencia de tipo si es un tipo complejo.Por ejemplo, una <xref:System.Collections.Generic.List%601> de tipo `Forma` asignada a <xref:System.Object> se parece a lo siguiente.  
  
```  
[{"__type":"Shape:#MyApp.Shapes","x":50,"y":70},  
{"__type":"Shape:#MyApp.Shapes","x":58,"y":73},  
{"__type":"Shape:#MyApp.Shapes","x":41,"y":32}]  
```  
  
 Al volver a deserializar en <xref:System.Object>:  
  
-   `Forma` debe estar en la lista de tipos conocidos.Tener <xref:System.Collections.Generic.List%601> de tipo `Forma` en tipos conocidos no tiene ningún efecto.Observe que no tiene que agregar `Forma` a los tipos conocidos en la serialización, en este caso se hace automáticamente.  
  
-   La colección se deserializa como una <xref:System.Array> de tipo <xref:System.Object> que contiene instancias de `Forma`.  
  
#### Colecciones derivadas asignadas a colecciones base  
 Cuando una colección derivada se asigna a una colección base, la colección normalmente se serializa como si fuera una colección del tipo base.No obstante, si el tipo de elemento de la colección derivada no se puede asignar al tipo de elemento de la colección base, se inicia una excepción.  
  
#### Sugerencias de tipo y diccionarios  
 Cuando se asigna un diccionario a un <xref:System.Object>, cada entrada Clave y Valor del diccionario se trata como si se asignara a <xref:System.Object> y se obtiene una sugerencia de tipo.  
  
 Al serializar tipos de diccionario, el objeto JSON que contiene los miembros "Clave" y "Valor" no se ven afectados por el parámetro `alwaysEmitTypeInformation` y solo contiene una sugerencia de tipo cuando las reglas de la colección precedente lo requieren.  
  
### Nombres de claves JSON válidos  
 El serializador XML codifica nombres de claves que no son nombres XML válidos.Por ejemplo, un miembro de datos con el nombre "123" tendría un nombre codificado como "\_x0031\_\_x0032\_\_x0033\_" porque "123" no es un nombre de elemento XML válido \(empieza con un dígito\).Se puede producir una situación similar con algunos juegos de caracteres internacionales no válidos en nombres de XML.Para obtener una explicación de este efecto de XML en procesamiento JSON, consulte [Asignación entre JSON y XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
## Vea también  
 [Compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)