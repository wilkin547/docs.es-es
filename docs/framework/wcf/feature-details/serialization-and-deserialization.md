---
title: Serialización y deserialización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3d71814c-bda7-424b-85b7-15084ff9377a
ms.openlocfilehash: 8d62fe1cb646bfa00f3fd2e694f08d9fed297bc2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600430"
---
# <a name="serialization-and-deserialization"></a>Serialización y deserialización
Windows Communication Foundation (WCF) incluye un nuevo motor de serialización, el <xref:System.Runtime.Serialization.DataContractSerializer> . <xref:System.Runtime.Serialization.DataContractSerializer>Traduce entre .NET Framework objetos y XML, en ambas direcciones. En este tema se explica cómo funciona el serializador.  
  
 Al serializar .NET Framework objetos, el serializador entiende diversos modelos de programación de la serialización, incluido el nuevo modelo de *contrato de datos* . Para obtener una lista completa de los tipos admitidos, consulte [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md). Para obtener una introducción a los contratos de datos, consulte [Using Data Contracts](using-data-contracts.md).  
  
 Al deserializar XML, el serializador utiliza las clases <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter> . También admite las <xref:System.Xml.XmlDictionaryReader> clases y <xref:System.Xml.XmlDictionaryWriter> para permitirle generar XML optimizado en algunos casos, como cuando se usa el formato XML binario WCF.  
  
 WCF también incluye un serializador complementario, el <xref:System.Runtime.Serialization.NetDataContractSerializer> . <xref:System.Runtime.Serialization.NetDataContractSerializer>Es similar a los <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> serializadores y porque también emite .NET Framework nombres de tipo como parte de los datos serializados. Se utiliza cuando se comparten los mismos tipos en los extremos de serialización y deserialización. <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer> derivan de una clase base común, <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
> [!WARNING]
> <xref:System.Runtime.Serialization.DataContractSerializer> serializa cadenas que contienen caracteres de control con un valor hexadecimal inferior a 20 como entidades XML. Esto puede producir un problema con un cliente que no sea de WCF al enviar estos datos a un servicio WCF.  
  
## <a name="creating-a-datacontractserializer-instance"></a>Creación de una instancia de DataContractSerializer  
 Construir una instancia de <xref:System.Runtime.Serialization.DataContractSerializer> es un paso importante. Después de la construcción no puede cambiar ninguno de los valores.  
  
### <a name="specifying-the-root-type"></a>Especificación del tipo de raíz  
 El *tipo de raíz* es el tipo en el que las instancias se serializan o deserializan. <xref:System.Runtime.Serialization.DataContractSerializer> tiene muchas sobrecarga del constructor, pero, como mínimo, se debe proporcionar un tipo de raíz utilizando el parámetro `type` .  
  
 Un serializador creado para un tipo de raíz determinado no se puede utilizar para serializar (o deserializar) otro tipo, a menos que el tipo se derive del tipo de raíz. En el ejemplo siguiente se muestran dos clases.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#1)]
 [!code-vb[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#1)]  
  
 Este código construye una instancia del `DataContractSerializer` que solo se puede utilizar para serializar o deserializar instancias de la clase `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#2)]
 [!code-vb[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#2)]  
  
### <a name="specifying-known-types"></a>Especificación de los tipos conocidos  
 Si el polimorfismo está implicado en los tipos que se están serializando que aún no se administran usando el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> o algún otro mecanismo, se ha de pasar una lista de posibles tipos conocidos al constructor del serializador usando el parámetro `knownTypes` . Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).  
  
 El siguiente ejemplo muestra una clase, `LibraryPatron`, que incluye una colección de un tipo específico, `LibraryItem`. La segunda clase define el tipo `LibraryItem` . Las clases tercera y cuarta`Book` y `Newspaper`heredan de la clase `LibraryItem` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#3)]  
 [!code-vb[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#3)]  
  
 El siguiente código construye una instancia del serializador utilizando el parámetro `knownTypes` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#4)]
 [!code-vb[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#4)]  
  
### <a name="specifying-the-default-root-name-and-namespace"></a>Especificación del espacio de nombres y el nombre de raíz predeterminados  
 Normalmente, cuando se serializa un objeto, el nombre y espacio de nombres predeterminados del elemento XML extremo se determinan según el nombre y el espacio de nombres del contrato de datos. Los nombres de todos los elementos internos se determinan a partir de los nombres de los miembros de datos y su espacio de nombres es el espacio de nombres del contrato de datos. El siguiente ejemplo establece los valores de `Name` y `Namespace` en los constructores de las clases <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#5)]
 [!code-vb[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#5)]  
  
 Al serializar una instancia de la clase `Person` , se genera código XML similar al siguiente.  
  
```xml  
<PersonContract xmlns="http://schemas.contoso.com">  
  <AddressMember>  
    <StreetMember>123 Main Street</StreetMember>  
   </AddressMember>  
</PersonContract>  
```  
  
 Sin embargo, puede personalizar el nombre y espacio de nombres predeterminado del elemento raíz pasando los valores de los parámetros `rootName` y `rootNamespace` al constructor <xref:System.Runtime.Serialization.DataContractSerializer> . Observe que el `rootNamespace` no afecta al espacio de nombres de los elementos contenidos que corresponden a miembros de datos. Solo afecta al espacio de nombres del elemento extremo.  
  
 Estos valores se pueden pasar como cadenas o instancias de la clase <xref:System.Xml.XmlDictionaryString> para permitir su optimización mediante el formato XML binario.  
  
### <a name="setting-the-maximum-objects-quota"></a>Establecimiento de la cuota de objetos máximos  
 Algunas sobrecargas del constructor de `DataContractSerializer` tienen un parámetro `maxItemsInObjectGraph` . Este parámetro determina el número máximo de objetos que el serializador serializa o deserializa en una única llamada al método <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . (El método siempre lee un objeto raíz, pero este objeto puede tener otros objetos en sus miembros de datos. Esos objetos pueden tener otros objetos, etc.) El valor predeterminado es 65536. Tenga en cuenta que al serializar o deserializar las matrices, cada entrada de matriz cuenta como un objeto independiente. Observe también que algunos objetos pueden tener una representación de memoria grande, por lo que esta cuota por sí sola puede no ser suficiente para evitar ataques por denegación de servicio. Para obtener más información, vea [consideraciones de seguridad para los datos](security-considerations-for-data.md). Si necesita aumentar esta cuota por encima del valor predeterminado, es importante hacerlo en los lados de envío (serialización) y recepción (deserialización), porque se aplica a ambos al leer y escribir datos.  
  
### <a name="round-trips"></a>Acciones de ida y vuelta  
 Una *acción de ida y vuelta (round trip)* se produce cuando un objeto se deserializa y se vuelve a serializar en una operación. De este modo, va de XML a una instancia de objeto y de vuelta a una secuencia XML.  
  
 Algunas sobrecargas del constructor del `DataContractSerializer` tienen un parámetro `ignoreExtensionDataObject` , que está establecido de forma predeterminada en `false` . En este modo predeterminado, los datos se pueden enviar en un viaje de ida y vuelta (round trip) desde una versión más reciente de un contrato de datos a través de una versión anterior y de vuelta a la versión más reciente sin pérdidas, siempre que el contrato de datos implemente la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject> . Por ejemplo, suponga que la versión 1 del contrato de datos de la `Person` contiene los miembros de datos `Name` y `PhoneNumber` , y la versión 2 agrega un miembro `Nickname` . Si se implementa `IExtensibleDataObject` al enviar información de la versión 2 a la versión 1, los datos `Nickname` se almacenan y, a continuación, se vuelven a emitir cuando se vuelven a serializar los datos; por tanto, no se pierden datos en el viaje de ida y vuelta. Para obtener más información, consulte los [contratos de datos compatibles con el avance y el control de versiones del](forward-compatible-data-contracts.md) contrato de [datos](data-contract-versioning.md).  
  
#### <a name="security-and-schema-validity-concerns-with-round-trips"></a>Aspectos a tener en cuenta sobre seguridad y validez del esquema en relación con los viajes de ida y vuelta (round trip)  
 Los viajes de ida y vuelta pueden tener implicaciones en cuanto a la seguridad. Por ejemplo, deserializar y almacenar grandes cantidades de datos extraños puede constituir un riesgo para la seguridad. Puede haber problemas de seguridad al reemitir estos datos que no se pueden comprobar, sobre todo si hay firmas digitales implicadas. Por ejemplo, en el escenario anterior, el extremo de versión 1 podría estar firmando un valor `Nickname` que contuviese datos malintencionados. Por último, puede haber problemas de validez del esquema: un extremo puede desear emitir siempre datos que cumplan de manera estricta el contrato indicado y no valores adicionales. En el ejemplo anterior, el contrato del extremo de versión 1 dice que solo emite `Name` y `PhoneNumber`, y si se utiliza la validación de esquema, se produciría un error de validación al emitir el valor `Nickname` adicional.  
  
#### <a name="enabling-and-disabling-round-trips"></a>Habilitar y deshabilitar los viajes de ida y vuelta  
 Para desactivar los viajes de ida y vuelta, no implemente la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject> . Si no tiene ningún control sobre los tipos, establezca el parámetro `ignoreExtensionDataObject` en `true` para lograr el mismo efecto.  
  
### <a name="object-graph-preservation"></a>Preservación de gráfico de objeto  
 Normalmente, el serializador no se preocupa de la identidad del objeto, como en el código siguiente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#6)]
 [!code-vb[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#6)]  
  
 El siguiente código crea un pedido de compra.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#7)]
 [!code-vb[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#7)]  
  
 Observe que los campos `billTo` y `shipTo` están establecidos en la misma instancia de objeto. Sin embargo, el XML generado duplica la información duplicada y parece similar al siguiente XML.  
  
```xml  
<PurchaseOrder>  
  <billTo><street>123 Main St.</street></billTo>  
  <shipTo><street>123 Main St.</street></shipTo>  
</PurchaseOrder>  
```  
  
 Sin embargo, este enfoque tiene las siguientes características, que puede que no se deseen:  
  
- Rendimiento. La replicación de datos es ineficaz.  
  
- Referencias circulares. Si los objetos hacen referencia a ellos mismos, incluso a través de otros objetos, la serialización mediante resultados de replicación resulta en un bucle infinito. (Si esto sucede, el serializador inicia una <xref:System.Runtime.Serialization.SerializationException> .)  
  
- Semántica. A veces es importante conservar el hecho de que se realicen dos referencias al mismo objeto, y no a dos objetos idénticos.  
  
 Por estas razones, algunas sobrecargas del constructor de `DataContractSerializer` tienen un parámetro `preserveObjectReferences` (el valor predeterminado es `false`). Cuando este parámetro se establece en `true` , se usa un método especial de codificación de referencias de objeto, que solo es compatible con WCF. Cuando se establece en `true`, el ejemplo de código XML tiene ahora el siguiente aspecto.  
  
```xml  
<PurchaseOrder ser:id="1">  
  <billTo ser:id="2"><street ser:id="3">123 Main St.</street></billTo>  
  <shipTo ser:ref="2"/>  
</PurchaseOrder>  
```  
  
 El espacio de nombres "ser" hace referencia al espacio de nombres de serialización estándar, `http://schemas.microsoft.com/2003/10/Serialization/` . Cada parte de datos se serializa solo una vez y se proporciona un número de identificador a cada una de esas partes de datos, y los posteriores usos resultan en una referencia a los datos ya serializados.  
  
> [!IMPORTANT]
> Si los atributos "id" y "ref" están presentes en el elemento `XMLElement`del contrato de datos, se observa el atributo "ref" y se omite "id".  
  
 Es importante conocer las limitaciones de este modo:  
  
- El XML que produce el `DataContractSerializer` con `preserveObjectReferences` establecido en `true` no es interoperable con ninguna otra tecnología y solo puede obtenerse acceso a él mediante otra instancia del `DataContractSerializer` , también con `preserveObjectReferences` establecido en `true`.  
  
- No hay compatibilidad con metadatos (esquema) para esta característica. El esquema que se genera solo es válido para el caso en que `preserveObjectReferences` está establecido en `false`.  
  
- Esta característica puede hacer que el proceso de serialización y deserialización se ejecuten más lentamente. Aunque los datos no tienen que replicarse, las comparaciones con objetos adicionales se deben realizar en este modo.  
  
> [!CAUTION]
> Cuando se habilita el modo `preserveObjectReferences` , es especialmente importante establecer el valor `maxItemsInObjectGraph` en la cuota correcta. Debido a la manera en la que se administran las matrices en este modo, es fácil que un atacante construya un pequeño mensaje malintencionado que provoque un uso de memoria grande limitado únicamente por la cuota `maxItemsInObjectGraph` .  
  
### <a name="specifying-a-data-contract-surrogate"></a>Especificación de un contrato de datos suplente  
 Algunas sobrecargas del constructor del `DataContractSerializer` tienen un parámetro `dataContractSurrogate` , que se puede establecer en `null`. De lo contrario, puede utilizarlo para especificar un *contrato de datos suplente*, que es un tipo que implementa la interfaz <xref:System.Runtime.Serialization.IDataContractSurrogate> . Puede utilizar a continuación la interfaz para personalizar el proceso de serialización y deserialización. Para obtener más información, vea [suplentes del contrato de datos](../extending/data-contract-surrogates.md).  
  
## <a name="serialization"></a>Serialización  
 La siguiente información se aplica a cualquier clase que herede del <xref:System.Runtime.Serialization.XmlObjectSerializer>,incluido las clases <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer> .  
  
### <a name="simple-serialization"></a>Serialización simple  
 La manera más básica de serializar un objeto es pasarlo al método <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> . Hay tres sobrecargas, que permiten escribir en una <xref:System.IO.Stream>, un <xref:System.Xml.XmlWriter>o un <xref:System.Xml.XmlDictionaryWriter>. Con la sobrecarga <xref:System.IO.Stream> , el resultado es XML en la codificación UTF-8. Con la sobrecarga <xref:System.Xml.XmlDictionaryWriter> , el serializador optimiza su resultado para XML binario.  
  
 Cuando se usa el <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> método, el serializador utiliza el nombre y espacio de nombres predeterminados para el elemento contenedor y lo escribe junto con el contenido (vea la sección anterior "Especificación del nombre y espacio de nombres raíz predeterminados").  
  
 En el ejemplo siguiente se muestra la escritura con <xref:System.Xml.XmlDictionaryWriter>.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#8)]
 [!code-vb[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#8)]  
  
 Esto produce un XML similar al siguiente.  
  
```xml  
<Person>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
### <a name="step-by-step-serialization"></a>Serialización paso a paso  
 Utilice los métodos <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A>, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A>y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> para escribir el elemento de fin, escribir el contenido del objeto y cerrar el elemento contenedor, respectivamente.  
  
> [!NOTE]
> No hay ninguna sobrecarga <xref:System.IO.Stream> de estos métodos.  
  
 Esta serialización paso a paso tiene dos usos extendidos. Uno consiste en insertar contenido como atributos o comentarios entre `WriteStartObject` y `WriteObjectContent`, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#9)]
 [!code-vb[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#9)]  
  
 Esto produce un XML similar al siguiente.  
  
```xml  
<Person serializedBy="myCode">  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
 Otro uso común consiste en evitar utilizar <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> por completo, y escribir su propio elemento contenedor personalizado (o incluso pasar por alto totalmente la escritura de un contenedor), tal y como se muestra en el siguiente código.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#10)]
 [!code-vb[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#10)]  
  
 Esto produce un XML similar al siguiente.  
  
```xml  
<MyCustomWrapper>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</MyCustomWrapper>  
```  
  
> [!NOTE]
> El uso de la serialización paso a paso puede producir un XML de esquema no válido.  
  
## <a name="deserialization"></a>Deserialización  
 La siguiente información se aplica a cualquier clase que herede del <xref:System.Runtime.Serialization.XmlObjectSerializer>,incluido las clases <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer> .  
  
 La manera más básica de deserializar un objeto consiste en llamar a una de las sobrecargas del método <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Hay tres sobrecargas, que permiten leer con un <xref:System.Xml.XmlDictionaryReader>, un `XmlReader`o una `Stream`. Observe que la sobrecarga `Stream` crea un <xref:System.Xml.XmlDictionaryReader> textual que no está protegido por ninguna cuota, por lo que solo debería utilizarse para leer datos de confianza.  
  
 También tenga en cuenta que el objeto que devuelve el método `ReadObject` debe convertirse al tipo adecuado.  
  
 El siguiente código construye una instancia de <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.XmlDictionaryReader>, a continuación, deserializa una instancia de `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#11)]
 [!code-vb[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#11)]  
  
 Antes de llamar al método <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> , coloque el lector XML en el elemento contenedor o en un nodo de no contenido que preceda al elemento contenedor. Puede realizar esto llamando al método <xref:System.Xml.XmlReader.Read%2A> del <xref:System.Xml.XmlReader> o su derivación y probando <xref:System.Xml.XmlReader.NodeType%2A>, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#12)]
 [!code-vb[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#12)]  
  
 Observe que puede leer atributos en este elemento contenedor antes de entregar el lector a `ReadObject`.  
  
 Al utilizar una de las `ReadObject` sobrecargas simples, el deserializador busca el nombre y espacio de nombres predeterminados en el elemento contenedor (vea la sección anterior, "especificar el nombre de raíz y el espacio de nombres predeterminados") e inicia una excepción si encuentra un elemento desconocido. En el ejemplo anterior se espera el elemento contenedor `<Person>` . Se llama al método <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> para comprobar que el lector está ubicado en un elemento que se denomina como esperado.  
  
 Hay una manera de deshabilitar esta comprobación de nombre del elemento contenedor; algunas sobrecargas del método `ReadObject` toman el parámetro booleano `verifyObjectName`, que está establecido de forma predeterminada en `true` . Cuando se establece en `false`, se ignoran el nombre y el espacio de nombres del elemento contenedor. Esto es útil para leer XML escrito mediante el mecanismo de serialización paso a paso descrito previamente.  
  
## <a name="using-the-netdatacontractserializer"></a>Uso del NetDataContractSerializer  
 La principal diferencia entre `DataContractSerializer` y <xref:System.Runtime.Serialization.NetDataContractSerializer> es que `DataContractSerializer` utiliza los nombres de contrato de datos, mientras que las `NetDataContractSerializer` salidas se completan .NET Framework nombre de ensamblado y tipo en el XML serializado. Esto significa que se han de compartir exactamente los mismos tipos entre los extremos de serialización y deserialización. Esto significa que el mecanismo de tipos conocidos no se requiere con el `NetDataContractSerializer` , porque siempre se conocen los tipos exactos que se van a deserializar.  
  
 Sin embargo, pueden producirse varios problemas:  
  
- Securidad. Se carga cualquier tipo en el XML que se esté deserializando. Esto se puede explotar para forzar la carga de tipos malintencionados. El uso del `NetDataContractSerializer` con datos que no son de confianza solo se debería realizar si se utiliza un *Enlazador de Serialización* (mediante el parámetro del constructor o la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> ). El enlazador solo permite cargar tipos seguros. El mecanismo del enlazador es idéntico al que utilizan los tipos en el espacio de nombres de <xref:System.Runtime.Serialization> .  
  
- Control de versiones El uso de nombres de ensamblado y tipos completos en el XML restringe en gran medida el control de versión de los tipos. No se pueden cambiar lo siguientes elementos: nombres de tipos, espacios de nombres, nombres de ensamblados y versiones de ensamblados. Establecer la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> o el parámetro de constructor en <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple> en lugar del valor predeterminado de <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Full> permite los cambios de versión de ensamblado, pero no para tipos de parámetros genéricos.  
  
- Interoperabilidad. Dado que .NET Framework nombres de tipo y de ensamblado se incluyen en el XML, las plataformas distintas de la .NET Framework no pueden tener acceso a los datos resultantes.  
  
- Rendimiento. Escribir los nombres del ensamblado y el tipo aumenta significativamente el tamaño del XML resultante.  
  
 Este mecanismo es similar a la serialización binaria o SOAP utilizada por .NET Framework remoto (concretamente, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ).  
  
 El uso del `NetDataContractSerializer` es similar al uso del `DataContractSerializer`, con las siguientes diferencias:  
  
- Los constructores no le exigen que especifique un tipo de raíz. Puede serializar cualquier tipo con la misma instancia del `NetDataContractSerializer`.  
  
- Los constructores no aceptan ninguna lista de tipos conocidos. El mecanismo de tipos conocidos no es necesario si los nombres de tipos se serializan en el XML.  
  
- Los constructores no aceptan un contrato de datos suplente. En su lugar, aceptan un parámetro <xref:System.Runtime.Serialization.ISurrogateSelector> llamado `surrogateSelector` (que asigna a la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.SurrogateSelector%2A> ). Éste es un mecanismo suplente de herencia.  
  
- Los constructores aceptan un parámetro denominado `assemblyFormat` del <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> que asigna a la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> . Tal y como se comentó previamente, esto se puede utilizar para mejorar las capacidades del control de versiones del serializador. Esto es idéntico al mecanismo <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> en la serialización binaria o de SOAP.  
  
- Los constructores aceptan un parámetro <xref:System.Runtime.Serialization.StreamingContext> denominado `context` que asigna a la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.Context%2A> . Puede utilizar esto para pasar información en los tipos que se serializan. Este uso es idéntico al del mecanismo <xref:System.Runtime.Serialization.StreamingContext> utilizado en otras clases <xref:System.Runtime.Serialization> .  
  
- Los métodos <xref:System.Runtime.Serialization.NetDataContractSerializer.Serialize%2A> y <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize%2A> son alias de los métodos <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> y <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Éstos existen para proporcionar un modelo de programación con serialización binaria o de SOAP más coherente.  
  
 Para obtener más información sobre estas características, vea [serialización binaria](../../../standard/serialization/binary-serialization.md).  
  
 Generalmente, los formatos XML que usan el `NetDataContractSerializer` y el `DataContractSerializer` no son compatibles. Es decir, intentar serializar con uno de estos serializadores y deserializar con el otro no es un escenario admitido.  
  
 Además, tenga en cuenta que el no `NetDataContractSerializer` genera el tipo de .NET Framework completo y el nombre de ensamblado para cada nodo del gráfico de objetos. Solo genera esa información cuando hay ambigüedad. Es decir, produce el resultado en el nivel del objeto raíz y para cualquier caso polimórfico.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.NetDataContractSerializer>
- <xref:System.Runtime.Serialization.XmlObjectSerializer>
- [Serialización binaria](../../../standard/serialization/binary-serialization.md)
- [Tipos admitidos por el serializador de contratos de datos](types-supported-by-the-data-contract-serializer.md)
