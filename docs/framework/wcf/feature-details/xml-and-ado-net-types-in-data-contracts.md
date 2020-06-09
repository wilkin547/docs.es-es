---
title: Clases de XML y ADO.NET en contratos de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2ce8461-3c15-4c41-8c81-1cb78f5b59a6
ms.openlocfilehash: 975d4f4f37bbbd895cab4e87686f15017e90f382
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600080"
---
# <a name="xml-and-adonet-types-in-data-contracts"></a>Clases de XML y ADO.NET en contratos de datos
El modelo de contrato de datos Windows Communication Foundation (WCF) admite ciertos tipos que representan directamente XML. Cuando estos tipos se serializan a XML, el serializador escribe el contenido de XML de estos tipos sin procesar la instrucción. Los tipos admitidos son <xref:System.Xml.XmlElement>, matrices de <xref:System.Xml.XmlNode> (pero no el propio tipo `XmlNode` ), así como los tipos que implementan <xref:System.Xml.Serialization.IXmlSerializable>. <xref:System.Data.DataSet> y el tipo <xref:System.Data.DataTable>, así como los conjuntos de datos con tipo, se utilizan normalmente en programación de base de datos. Estos tipos implementan la interfaz `IXmlSerializable` y son, por lo tanto, serializables en el modelo del contrato de datos. Al final de este tema, se describen algunas consideraciones especiales para estos tipos.  
  
## <a name="xml-types"></a>Tipos XML  
  
### <a name="xml-element"></a>Elemento Xml  
 El tipo `XmlElement` se serializa utilizando sus contenidos de XML. Por ejemplo, utilizando el siguiente tipo.  
  
 [!code-csharp[DataContractAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#4)]
 [!code-vb[DataContractAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#4)]  
  
 Esto se serializará a XML del modo siguiente:  
  
```xml  
<MyDataContract xmlns="http://schemas.contoso.com">  
    <myDataMember>  
        <myElement xmlns="" myAttribute="myValue">  
            myContents  
        </myElement>  
    </myDataMember>  
</MyDataContract>  
```  
  
 Fíjese en que un elemento contenedor de miembro de datos `<myDataMember>` todavía está presente. No hay ninguna manera de quitar este elemento en el modelo del contrato de datos. Los serializadores que administran este modelo ( <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer>) pueden emitir atributos especiales en este elemento contenedor. Estos atributos incluyen el atributo "nil" de la instancia del estándar Esquema XML (que permite que `XmlElement` sea `null`) y el atributo "type" (que permite que `XmlElement` se utilice polimórficamente)." Además, los siguientes atributos XML son específicos de WCF: "ID", "ref", "type" y "Assembly". Estos atributos se pueden emitir para permitir utilizar `XmlElement` con el modo de preservación de gráfico de objetos habilitado o con <xref:System.Runtime.Serialization.NetDataContractSerializer>. (Para obtener más información sobre el modo de preservación del gráfico de objetos, vea [serialización y deserialización](serialization-and-deserialization.md)).  
  
 Las matrices o colecciones de `XmlElement` se permiten y administran como cualquier otra matriz o colección. Es decir, existe un elemento contenedor para la colección completa y un elemento contenedor independiente (similar a  en el ejemplo anterior) para cada  de la matriz.  
  
 En la deserialización, el deserializador crea un `XmlElement` a partir del XML de entrada. El deserializador proporciona un <xref:System.Xml.XmlDocument> primario válido.  
  
 Asegúrese de que el fragmento XML que se deserializará a un `XmlElement` define todos los prefijos que utiliza y que no está basado en ninguna definición de prefijo de elementos antecesores. Esto solo resulta preocupante si se utiliza el `DataContractSerializer` para tener acceso a XML desde un origen diferente (no -`DataContractSerializer`).  
  
 Cuando se usa con `DataContractSerializer` , `XmlElement` se puede asignar polimórficamente, pero solo a un miembro de datos de tipo <xref:System.Object> . Aunque implementa <xref:System.Collections.IEnumerable>, un `XmlElement` no se puede utilizar como un tipo de colección y no se puede asignar a un miembro de datos <xref:System.Collections.IEnumerable>. Como ocurre con todas las asignaciones polimórficas, el `DataContractSerializer` emite el nombre del contrato de datos en el XML resultante; en este caso, es "XmlElement" en el http://schemas.datacontract.org/2004/07/System.Xml espacio de nombres "".  
  
 Con `NetDataContractSerializer`, cualquier trabajo polimórfico válido de `XmlElement` (a `Object` o `IEnumerable`) se admite.  
  
 No intente utilizar cualquiera de los serializadores con tipos derivados de `XmlElement`, estén asignados polimórficamente o no.  
  
### <a name="array-of-xmlnode"></a>Matriz de XMLNode  
 Utilizar matrices de <xref:System.Xml.XmlNode> es muy similar a utilizar `XmlElement`. Utilizar matrices de `XmlNode` le proporciona más flexibilidad que utilizar `XmlElement`. Puede escribir varios elementos dentro del elemento de ajuste de miembro de datos. También puede insertar contenido que no sean elementos dentro del elemento de ajuste de miembro de datos, como comentarios XML. Por último, puede poner atributos en el elemento de miembro de datos de ajuste. Todos esto puede lograrse rellenando la matriz de `XmlNode` con clases derivadas específicas de `XmlNode`, como <xref:System.Xml.XmlAttribute>, `XmlElement` o <xref:System.Xml.XmlComment>. Por ejemplo, utilizando el siguiente tipo.  
  
 [!code-csharp[DataContractAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#5)]
 [!code-vb[DataContractAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#5)]  
  
 Al serializar, el XML resultante es similar al siguiente código.  
  
```xml  
<MyDataContract xmlns="http://schemas.contoso.com">  
  <myDataMember myAttribute="myValue">  
     <!--myComment-->  
     <myElement xmlns="" myAttribute="myValue">  
 myContents  
     </myElement>  
     <myElement xmlns="" myAttribute="myValue">  
       myContents  
     </myElement>  
  </myDataMember>  
</MyDataContract>  
```  
  
 Tenga en cuenta que `<myDataMember>` del elemento contenedor de miembro de datos contiene un atributo, un comentario y dos elementos. Éstas son las cuatro instancias `XmlNode` serializadas.  
  
 No se puede serializar una matriz de `XmlNode` que produciría un XML no válido. Por ejemplo, una matriz de dos instancias `XmlNode` donde la primera es `XmlElement` y la segunda es <xref:System.Xml.XmlAttribute> no es válida, porque esta secuencia no corresponde a ninguna instancia XML válida (no hay ningún lugar para adjuntar el atributo).  
  
 En la deserialización de una matriz de `XmlNode`, los nodos se crean y rellenan con información del XML de entrada. El deserializador proporciona un <xref:System.Xml.XmlDocument> primario válido. Se deserializan todos los nodos, incluidos los atributos del elemento de miembro de datos del contenedor, pero excluyendo los atributos colocados ahí por los serializadores de WCF (como los atributos utilizados para indicar la asignación polimórfica). La advertencia sobre cómo definir todos los prefijos de espacio de nombres en el fragmento XML se aplica a la deserialización de matrices de `XmlNode` simplemente como se hace al deserializar `XmlElement`.  
  
 Al utilizar los serializadores con preservación del gráfico de objetos activada, la igualdad de los objeto solo se conserva en el nivel de matrices `XmlNode`, no instancias `XmlNode` individuales.  
  
 No intente serializar una matriz de `XmlNode` en la que uno o varios nodos están establecidos en `null`. Se permite que todo el miembro de la matriz sea `null`, pero no los `XmlNode` individuales incluidos en la matriz. Si todo el miembro de la matriz es null, el elemento contenedor de miembro de datos incluirá un atributo especial que indica que es null. En la deserialización, todo el miembro de la matriz también se convertirá en null.  
  
 El serializador trata especialmente solo las matrices normales de `XmlNode`. Los miembros de datos declarados como otros tipos de colección que contienen `XmlNode`, o los miembros de datos declarados como matrices de tipos derivadas de `XmlNode`, no se tratan de manera especial. Por esta razón, normalmente, no son serializables a menos que también cumplan uno de los otros criterios de serialización.  
  
 Se permiten matrices o colecciones de matrices de `XmlNode`. Existe un elemento contenedor para toda la colección, y un elemento contenedor independiente (similar a  en el ejemplo anterior) para cada matriz de  en la matriz o colección externa.  
  
 Rellenar un miembro de datos de tipo <xref:System.Array> de `Object`, o `Array` de `IEnumerable`, con instancias `XmlNode` no produce el miembro de datos tratado como una `Array` de instancias `XmlNode`. Cada miembro de matriz se serializa de manera independiente.  
  
 Cuando se utiliza con el `DataContractSerializer`, las matrices de `XmlNode`pueden estar asignadas polimórficamente pero solo a un miembro de datos de tipo `Object`. Aunque implementa `IEnumerable`, una matriz de `XmlNode` no se puede utilizar como un tipo de colección y no se puede asignar a un miembro de datos `IEnumerable`. Como ocurre con todas las asignaciones polimórficas, el `DataContractSerializer` emite el nombre del contrato de datos en el XML resultante; en este caso, es "ArrayOfXmlNode" en el http://schemas.datacontract.org/2004/07/System.Xml espacio de nombres "". Cuando se usa con `NetDataContractSerializer` , se admite cualquier asignación válida de una `XmlNode` matriz.  
  
### <a name="schema-considerations"></a>Consideraciones del esquema  
 Para obtener más información sobre la asignación de esquemas de tipos XML, vea [referencia de esquema de contrato de datos](data-contract-schema-reference.md). En esta sección se proporciona un resumen de los puntos importantes.  
  
 Un miembro de datos de tipo `XmlElement` está asignado a un elemento definido mediante el siguiente tipo anónimo.  
  
```xml  
<xsd:complexType>  
   <xsd:sequence>  
      <xsd:any minOccurs="0" processContents="lax" />  
   </xsd:sequence>  
</xsd:complexType>  
```  
  
 Un miembro de datos de tipo Matriz de `XmlNode` está asignado a un elemento definido mediante el siguiente tipo anónimo.  
  
```xml  
<xsd:complexType mixed="true">  
   <xsd:sequence>  
      <xsd:any minOccurs="0" maxOccurs="unbounded" processContents="lax" />  
   </xsd:sequence>  
   <xsd:anyAttribute/>  
</xsd:complexType>  
```  
  
## <a name="types-implementing-the-ixmlserializable-interface"></a>Tipos que implementan la interfaz IXmlSerializable   
 `IXmlSerializable`admite totalmente los tipos que implementan la interfaz `DataContractSerializer`. El atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> siempre se debería aplicar a estos tipos para controlar su esquema.  
  
 Existen tres variedades de tipos que implementan `IXmlSerializable`: tipos que representan el contenido arbitrario, tipos que representan un elemento único, y los tipos <xref:System.Data.DataSet> heredados.  
  
- Los tipos de contenido utilizan un método de proveedor de esquema especificado por el atributo `XmlSchemaProviderAttribute`. El método no devuelve `null`y la propiedad <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A> en el atributo se deja como su valor predeterminado de `false`. Éste es el uso más común de los tipos `IXmlSerializable`.  
  
- Se utilizan los tipos de elemento cuando un tipo `IXmlSerializable` debe controlar su propio nombre del elemento raíz. Para marcar un tipo como un tipo de elemento, establezca la propiedad <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A> del atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> en `true` o devuelva null a partir del método de proveedor de esquema. Tener un método de proveedor de esquema es opcional para los tipos de elemento. Puede especificar null en lugar del nombre del método en `XmlSchemaProviderAttribute`. Sin embargo, si `IsAny` es `true` y se especifica un método de proveedor de esquema, el método debe devolver null.  
  
- Los tipos <xref:System.Data.DataSet> heredados son `IXmlSerializable` escribe que no se marca con el atributo `XmlSchemaProviderAttribute`. En su lugar, confían en el método <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> para la generación del esquema. Este patrón se utiliza para el tipo `DataSet` y su conjunto de datos con tipo deriva una clase en versiones anteriores de .NET Framework, pero ahora es obsoleto y sólo se admite por razones heredadas. No confíe en este patrón y aplique siempre `XmlSchemaProviderAttribute` a sus tipos `IXmlSerializable`.  
  
### <a name="ixmlserializable-content-types"></a>Tipos de contenido de IXmlSerializable  
 Al serializar un miembro de datos de un tipo que implementa `IXmlSerializable`, y es un tipo de contenido como el que se ha definido previamente, el serializador escribe el elemento contenedor para el miembro de datos y pasará el control al método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>. La implementación <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> puede escribir cualquier XML, incluso agregar los atributos al elemento contenedor. Una vez realizado `WriteXml`, el serializador cierra el elemento.  
  
 Al deserializar un miembro de datos de un tipo que implementa `IXmlSerializable`, y es un tipo de contenido como el que se ha definido previamente, el deserializador sitúa el lector de XML en el elemento contenedor para el miembro de datos y pasa el control al método <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>. El método debe leer todo el elemento, también las etiquetas de cierre e inicio. Asegúrese de que su código `ReadXml` controla el caso donde el elemento está vacío. Además, su implementación `ReadXml` no debería confiar en el elemento contenedor denominado de una manera determinada. El serializador elige el nombre y este puede variar.  
  
 Se permite asignar polimórficamente tipos de contenido `IXmlSerializable`, por ejemplo, a los miembros de datos de tipo <xref:System.Object>. También se permite que las instancias de tipo sean nulo. Finalmente, es posible utilizar los tipos `IXmlSerializable` con preservación de gráfico de objetos habilitado y con <xref:System.Runtime.Serialization.NetDataContractSerializer>. Todas estas características requieren que el serializador de WCF adjunte determinados atributos en el elemento contenedor ("nil" y "tipo" en el espacio de nombres de la instancia del esquema XML y "ID", "ref", "type" y "Assembly" en un espacio de nombres específico de WCF).  
  
#### <a name="attributes-to-ignore-when-implementing-readxml"></a>Atributos que hay que omitir al Implementar ReadXml  
 Antes de pasar el control al código `ReadXml`, el deserializador examina el elemento XML, detecta estos atributos XML especiales y actúa sobre ellos. Por ejemplo, si "nil" es `true`, se deserializa un valor null y no se llama a `ReadXml`. Si se detecta polimorfismo, el contenido del elemento se deserializa como si fuera un tipo diferente. Se llama a la implementación del tipo asignado polimórficamente `ReadXml`. En cualquier caso, una implementación de `ReadXml` debería omitir estos atributos especiales ya que están controlados por el deserializador.  
  
### <a name="schema-considerations-for-ixmlserializable-content-types"></a>Consideraciones del esquema para los tipos de contenido de IXmlSerializable  
 Al exportar el esquema un tipo de contenido `IXmlSerializable`, se llama al método del proveedor de esquema. <xref:System.Xml.Schema.XmlSchemaSet> se pasa al método de proveedor de esquema. El método puede agregar cualquier esquema válido al conjunto de esquemas. El conjunto de esquemas contiene el esquema conocido en el momento de la exportación del esquema. Cuando el método de proveedor de esquemas debe agregar un elemento al conjunto de esquemas, debe determinar si en el esquema ya existe un <xref:System.Xml.Schema.XmlSchema> con el espacio de nombres adecuado. Si ya existe, el método de proveedor de esquema debe agregar el nuevo elemento al `XmlSchema` existente. De lo contrario, debe crear una nueva instancia `XmlSchema`. Esto es importante si se utilizan las matrices de los tipos `IXmlSerializable`. Por ejemplo, si tiene un tipo `IXmlSerializable` que se exporta como tipo "A" en el espacio de nombres "B", es posible que cuando al llamar al método de proveedor de esquema, el conjunto de esquemas ya contenga el esquema para que "B" incluya el tipo "ArrayOfA."  
  
 Además de agregar los tipos a <xref:System.Xml.Schema.XmlSchemaSet>, el método de proveedor de esquema para los tipos de contenido debe devolver un valor no nulo. Puede devolver un <xref:System.Xml.XmlQualifiedName> que especifique el nombre del tipo de esquema que se utilizará para el tipo `IXmlSerializable` concreto. Este nombre completo también actúa como el nombre de contrato de datos y el espacio de nombres del tipo. Se permite devolver un tipo que no existe en el esquema establecido inmediatamente cuando vuelve el método del proveedor de esquema. No obstante, se espera que en el momento de exportar todos los tipos relacionados (se llama al método <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A> para todos los tipos relevantes en el <xref:System.Runtime.Serialization.XsdDataContractExporter>, y se tiene acceso a la propiedad <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A>), el tipo existirá en el conjunto de esquemas. Teniendo acceso a la propiedad `Schemas` antes de que se hayan realizado todas las llamadas `Export` pertinentes puede producir <xref:System.Xml.Schema.XmlSchemaException>. Para obtener más información sobre el proceso de exportación, vea [exportar esquemas de clases](exporting-schemas-from-classes.md).  
  
 El método de proveedor de esquema también puede devolver el <xref:System.Xml.Schema.XmlSchemaType> que se va a utilizar. El tipo puede o no ser anónimo. Si es anónimo, el esquema para el tipo `IXmlSerializable` se exporta como tipo anónimo cada vez que el tipo `IXmlSerializable` se utiliza como un miembro de datos. El tipo `IXmlSerializable` aún tiene un nombre de contrato de datos y un espacio de nombres. (Esto se determina como se describe en [nombres de contrato de datos](data-contract-names.md) , salvo que el <xref:System.Runtime.Serialization.DataContractAttribute> atributo no se puede usar para personalizar el nombre). Si no es anónimo, debe ser uno de los tipos de `XmlSchemaSet` . Este caso es equivalente a la devolución del `XmlQualifiedName` del tipo.  
  
 Además, se exporta una declaración de elemento global para el tipo. Si el tipo no tiene el atributo <xref:System.Xml.Serialization.XmlRootAttribute> aplicado, el elemento tiene el mismo nombre y espacio de nombres que el contrato de datos, y su propiedad "nillable" será verdadera. La única excepción a esto es el espacio de nombres del esquema (" http://www.w3.org/2001/XMLSchema "): Si el contrato de datos del tipo está en este espacio de nombres, el elemento global correspondiente se encuentra en el espacio de nombres en blanco porque está prohibido agregar nuevos elementos al espacio de nombres del esquema. Si el tipo tiene el atributo `XmlRootAttribute` aplicado, la declaración del elemento global se exporta mediante las siguientes propiedades: <xref:System.Xml.Serialization.XmlRootAttribute.ElementName%2A>, <xref:System.Xml.Serialization.XmlRootAttribute.Namespace%2A> y <xref:System.Xml.Serialization.XmlRootAttribute.IsNullable%2A>. Los valores predeterminados con `XmlRootAttribute` aplicados son el nombre de contrato de datos, un espacio de nombres en blanco y "nillable" verdadero.  
  
 Las mismas reglas de la declaración de elemento globales se aplican a los tipos de conjunto de datos heredados. Tenga en cuenta que `XmlRootAttribute` no puede invalidar declaraciones de elemento globales agregadas a través de código personalizado, o agregadas a `XmlSchemaSet` mediante el método de proveedor de esquema o a través de `GetSchema` para los tipos de conjunto de datos heredados.  
  
### <a name="ixmlserializable-element-types"></a>Tipos de elemento de IXmlSerializable  
 Los tipos de elemento `IXmlSerializable` hacen que la propiedad `IsAny` se establezca en `true` o hacen que su método de proveedor de esquema se vuelva `null`.  
  
 Serializar y deserializar un tipo de elemento es muy similar a serializar y deserializar un tipo de contenido. Sin embargo, hay algunas diferencias importantes:  
  
- Se espera que la implementación `WriteXml` escriba exactamente un elemento (qué podría contener, por supuesto, varios elementos secundarios). No debería estar escribiendo los atributos fuera de este elemento único, varios elementos del mismo nivel o contenido mixto. El elemento puede estar vacío.  
  
- La implementación `ReadXml` no debería leer el elemento contenedor. Se espera que lea el un elemento que `WriteXml` genera.  
  
- Al serializar de manera regular un tipo de elemento (por ejemplo, como un miembro de datos en un contrato de datos), el serializador producirá un elemento contenedor antes de llamar a `WriteXml`, como en los tipos de contenido. No obstante, al serializar un tipo de elemento en el nivel superior, normalmente, el serializador no produce un elemento contenedor alrededor del elemento que `WriteXml` escribe, salvo que se especifiquen explícitamente un nombre de raíz y un espacio de nombres al construir el serializador en el `DataContractSerializer`, o los constructores `NetDataContractSerializer`. Para obtener más información, vea [serialización y deserialización](serialization-and-deserialization.md).  
  
- Cuando se serializa un tipo de elemento en el nivel superior sin especificar el nombre de raíz y el espacio de nombres en el momento de la construcción, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> no hace prácticamente nada, y <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A> llama a `WriteXml`. En este modo, el objeto que se serializa no puede ser nulo y no se puede asignar polimórficamente. Además, la preservación del gráfico de objetos puede se puede habilitar y no se puede utilizar `NetDataContractSerializer`.  
  
- Al deserializar un tipo de elemento en el nivel superior sin especificar el nombre y el espacio de nombres raíz en el momento de la construcción, <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> devuelve `true` si encuentra el inicio de cualquier elemento. <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> con el parámetro `verifyObjectName` establecido en `true` se comporta igual que `IsStartObject` antes realmente de leer el objeto realmente. `ReadObject` después pasa el control al método `ReadXml`.  
  
 El esquema exportado para los tipos de elemento es igual que para el tipo `XmlElement` tal y como se ha descrito en una sección anterior, excepto que el método de proveedor de esquema puede agregar un esquema adicional a <xref:System.Xml.Schema.XmlSchemaSet> como con los tipos de contenido. No se permite utilizar el atributo `XmlRootAttribute` con tipos de elemento y las declaraciones de elemento globales nunca se emiten para estos tipos.  
  
### <a name="differences-from-the-xmlserializer"></a>Diferencias respecto a XmlSerializer  
 `IXmlSerializable` entiende también la interfaz `XmlSchemaProviderAttribute` y `XmlRootAttribute` y los atributos <xref:System.Xml.Serialization.XmlSerializer>. Sin embargo, hay algunas diferencias en cómo se tratan estos en el modelo del contrato de datos. A continuación se resumen las principales diferencias:  
  
- El método de proveedor de esquema debe ser público para ser utilizable en `XmlSerializer`, pero no tiene que ser público para ser utilizable en el modelo del contrato de datos.  
  
- Se llama al método de proveedor de esquema cuando `IsAny` es verdadero en el modelo del contrato de datos pero no con `XmlSerializer`.  
  
- Cuando el atributo `XmlRootAttribute` no está presente para contenido o tipos de conjunto de datos heredados, `XmlSerializer` exporta una declaración de elemento global en el espacio de nombres en blanco. En el modelo del contrato de datos, el espacio de nombres utilizado es normalmente el espacio de nombres de contrato de datos, tal y como se ha descrito anteriormente.  
  
 Tenga en cuenta estas diferencias cuando cree tipos que se utilizan con ambas tecnologías de serialización.  
  
### <a name="importing-ixmlserializable-schema"></a>Importar el esquema de IXmlSerializable  
 Al importar un esquema generado a partir de los tipos `IXmlSerializable`, existen pocas posibilidades:  
  
- El esquema generado puede ser un esquema de contrato de datos válido, tal como se describe en [referencia de esquema de contrato de datos](data-contract-schema-reference.md). En este caso, el esquema puede importarse como de costumbre y se generarán los tipos de contrato de datos normales.  
  
- El esquema generado no puede ser un esquema de contrato de datos válido. Por ejemplo, su método de proveedor de esquemas puede generar un esquema que incluye atributos XML que no se admiten en el modelo de contrato de datos. En este caso, puede importar el esquema como tipos `IXmlSerializable`. Este modo de importación no está activado de forma predeterminada, pero se puede habilitar fácilmente; por ejemplo, con el `/importXmlTypes` modificador de la línea de comandos para la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Esto se describe en detalle en el [esquema de importación para generar clases](importing-schema-to-generate-classes.md). Tenga en cuenta que debe trabajar directamente con XML para sus instancias de tipo. También puede considerar la utilización de una tecnología de serialización diferente que admita una gama más amplia de esquemas. Vea el tema acerca de la utilización del `XmlSerializer`.  
  
- Puede desear volver a usar sus tipos `IXmlSerializable` existentes en el proxy en lugar de generar nuevos. En este caso, la característica de tipos a la cual s se hace referencia descrita en el tema Esquema de Importación para generar Tipos se puede utilizar para indicar el tipo que se reutilizará. Esto se corresponde con el uso del modificador `/reference` en svcutil.exe, que especifica el ensamblado que contiene los tipos que se van a volver a usar.  
  
## <a name="representing-arbitrary-xml-in-data-contracts"></a>Representar XML arbitrario en contratos de datos  
 `XmlElement`, Matriz de `XmlNode` y los tipos `IXmlSerializable` le permite insertar XML arbitrario en el modelo del contrato de datos. `DataContractSerializer` y `NetDataContractSerializer` pasan este contenido XML al sistema de escritura XML en uso, sin interferir en el proceso. Sin embargo, los sistemas de escritura XML pueden exigir ciertas restricciones en el XML que escriben. Específicamente, aquí se describen algunos ejemplos importantes:  
  
- Los sistemas de escritura XML normalmente no permiten una declaración de documento XML (por ejemplo, \<?xml version=’1.0’ ?> ) en medio de la escritura de otro documento. No puede tomar un documento XML completo y serializarlo como un `Array` de un miembro de datos de `XmlNode`. Para hacerlo, tiene que quitar la declaración del documento o utilizar su propio esquema de codificación para representarlo.  
  
- Todos los sistemas de escritura XML que se proporcionan con WCF rechazan las instrucciones de procesamiento XML ( \<? … ?> ) y las definiciones de tipo de documento ( \<! … > ), ya que no se permiten en los mensajes SOAP. En este caso, también puede utilizar su propio mecanismo de codificación para evitar esta restricción. Si debe incluirlos en el XML resultante, puede escribir un codificador personalizado que utilice sistemas de escritura XML que los admitan.  
  
- Al implementar `WriteXml`, evite llamar al método <xref:System.Xml.XmlWriter.WriteRaw%2A> en el sistema de escritura XML. WCF usa una variedad de codificaciones XML (incluido el binario), es muy difícil o imposible de usar de `WriteRaw` tal forma que el resultado se pueda utilizar en cualquier codificación.  
  
- Al implementar `WriteXml` , evite usar los <xref:System.Xml.XmlWriter.WriteEntityRef%2A> <xref:System.Xml.XmlWriter.WriteNmToken%2A> métodos y que no se admiten en los sistemas de escritura XML suministrados con WCF.  
  
## <a name="using-dataset-typed-dataset-and-datatable"></a>Utilizar DataSet, DataSet con tipo y DataTable  
 El uso de estos tipos está totalmente admitido en el modelo del contrato de datos. Al utilizar estos tipos, considere los puntos siguientes:  
  
- El esquema de estos tipos (especialmente <xref:System.Data.DataSet> y sus clases derivadas con tipo) puede no ser interoperable con algunas plataformas que no son de WCF, o puede dar lugar a un uso deficiente cuando se usa con estas plataformas. Además, utilizar el tipo `DataSet` puede tener implicaciones de rendimiento. Finalmente, puede hacer más difícil su control sobre las versiones de su aplicación en el futuro. Considere utilizar explícitamente los tipos de contrato de datos definidos en lugar de los tipos `DataSet` en sus contratos.  
  
- Al importar `DataSet` o esquema `DataTable`, es importante hacer referencia a estos tipos. Con la herramienta de línea de comandos SvcUtil. exe, esto se puede lograr pasando el nombre de ensamblado System. Data. dll al `/reference` modificador. Si importa el esquema del conjunto de datos con tipo, debe hacer referencia al tipo del conjunto de datos con tipo. Con SvcUtil. exe, pase la ubicación del ensamblado del conjunto de los tipos al `/reference` conmutador. Para obtener más información sobre los tipos de referencia, vea el [esquema de importación para generar clases](importing-schema-to-generate-classes.md).  
  
 La compatibilidad de los conjuntos de datos con tipo del modelo de contrato de datos es limitada. Los conjuntos de datos con tipos pueden serializarse y deserializarse, y pueden exportar su esquema. No obstante, la importación del esquema de contrato de datos no puede generar nuevos tipos de conjunto de datos con tipo desde el esquema, ya que solo puede reutilizar los existentes. Puede señalar a un conjunto de datos con tipo existente mediante el modificador `/r` en Svcutil.exe. Si intenta usar una Svcutil.exe sin el modificador `/r` en un servicio que usa un conjunto de datos con tipo, se selecciona automáticamente un serializador alternativo (XmlSerializer). Si necesita usar DataContractSerializer y generar conjuntos de datos a partir del esquema, puede usar el procedimiento siguiente: genere los tipos DataSet con tipo (mediante la herramienta Xsd.exe con el modificador `/d` en el servicio), compile los tipos y, a continuación, señale a ellos mediante el uso del modificador `/r` en Svcutil.exe.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
- [Utilización de contratos de datos](using-data-contracts.md)
- [Tipos admitidos por el serializador de contratos de datos](types-supported-by-the-data-contract-serializer.md)
