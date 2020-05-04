---
title: Directrices de serialización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serialization, guidelines
- binary serialization, guidelines
ms.assetid: ebbeddff-179d-443f-bf08-9c373199a73a
ms.openlocfilehash: 067f32a026e3354e6c4256602ed17fd7d7bde0b8
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159798"
---
# <a name="serialization-guidelines"></a>Directrices de serialización
Este documento enumera las instrucciones que se deben tener en cuenta al diseñar una API para su serialización.  

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
 .NET proporciona tres tecnologías de serialización principales que están optimizadas para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de .NET relacionados con ellas.  
  
|Tecnología|Clases pertinentes|Notas|  
|----------------|----------------------|-----------|  
|Serialización de contratos de datos|<xref:System.Runtime.Serialization.DataContractAttribute><br /><br /> <xref:System.Runtime.Serialization.DataMemberAttribute><br /><br /> <xref:System.Runtime.Serialization.DataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.NetDataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer><br /><br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br /><br /> Servicios Web<br /><br /> JSON|  
|Serialización XML|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML <br />con control completo|  
|Serialización en tiempo de ejecución (Binary y SOAP)|<xref:System.SerializableAttribute><br /><br /> <xref:System.Runtime.Serialization.ISerializable><br /><br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 Al diseñar tipos nuevos, debería decidir cuales de estas tecnologías deben admitir esos tipos (en caso de que haya alguna). Las siguientes instrucciones describen cómo tomar una decisión y cómo proporcionar dicha compatibilidad. Estas instrucciones no están pensadas para ayudarle a elegir qué tecnología de serialización debería utilizar en la implementación de su aplicación o biblioteca. Tales instrucciones no están relacionadas directamente con el diseño de la API y, por lo tanto, no forman parte de este tema.  
  
## <a name="guidelines"></a>Instrucciones  
  
- Piense en la serialización al diseñar los nuevos tipos.  
  
     La serialización es un factor importante en el diseño de cualquier tipo, es posible que los programas necesiten conservar o transmitir instancias del tipo.  
  
### <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir  
 Un tipo dado puede admitir una o varias tecnologías de serialización, o ninguna.  
  
- CONSIDERE admitir la *serialización de contrato de datos* si puede que las instancias de su tipo deban conservarse o usarse en Servicios Web.  
  
- CONSIDERE la posibilidad de admitir la *serialización XML* en lugar de —o además de— la serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.  
  
     Esto puede ser necesario en algunos escenarios de interoperabilidad donde es necesario utilizar una construcción XML no admitida por la serialización de contrato de datos; por ejemplo, para generar atributos XML.  
  
- CONSIDERE la posibilidad de admitir la *serialización en tiempo de ejecución* si las instancias de su tipo necesitan traspasar los límites de .NET Remoting.  
  
- EVITE admitir la serialización en tiempo de ejecución o la serialización XML solo por motivos generales de persistencia. Preferencia por la serialización de contrato de datos  
  
#### <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos  
 Los tipos pueden admitir la serialización de contrato de datos mediante la aplicación de <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.  
  
 [!code-csharp[SerializationGuidelines#1](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#1)]
 [!code-vb[SerializationGuidelines#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#1)]  
  
1. CONSIDERE la posibilidad de marcar como públicos los miembros de datos del tipo si el tipo se puede utilizar con confianza parcial. Con plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros no públicos, pero solo los miembros públicos se pueden serializar y deserializar con confianza parcial.  
  
2. Implemente getter y setter en todas las propiedades que tienen Data-MemberAttribute. Los serializadores de contrato de datos requieren getter y setter para que el tipo se considere serializable. Si el tipo no se va a usar con confianza parcial, uno o los dos descriptores de acceso de propiedad pueden ser no públicos.  
  
     [!code-csharp[SerializationGuidelines#2](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#2)]
     [!code-vb[SerializationGuidelines#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#2)]  
  
3. CONSIDERE la posibilidad de usar devoluciones de llamada de serialización para la inicialización de instancias deserializadas.  
  
     No se llama a los constructores cuando se deserializan los objetos. Por consiguiente, cualquier lógica que se ejecute durante la construcción normal debe implementarse como una de las *devoluciones de llamada de serialización*.  
  
     [!code-csharp[SerializationGuidelines#3](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#3)]
     [!code-vb[SerializationGuidelines#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#3)]  
  
     El atributo <xref:System.Runtime.Serialization.OnDeserializedAttribute> es el atributo de devolución de llamada más utilizado. Los demás atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.  
  
4. CONSIDERE la posibilidad de usar <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar tipos concretos que se deberían utilizar al deserializar un gráfico de objetos complejo.  
  
     Por ejemplo, si una clase abstracta representa un tipo de un miembro de datos deserializado, el serializador necesitará la información del *tipo conocido* para decidir de qué tipo concreto se crearán instancias para asignarlas al miembro. Si el tipo conocido no se especifica utilizando el atributo, deberá pasarse al serializador explícitamente (puede hacerlo pasando tipos conocidos al constructor del serializador) o deberá especificarse en el archivo de configuración.  
  
     [!code-csharp[SerializationGuidelines#4](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#4)]
     [!code-vb[SerializationGuidelines#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#4)]  
  
     Cuando no se conoce la lista de tipos conocidos estáticamente (cuando se compila la clase **Person**), **KnownTypeAttribute** también puede señalar a un método que devuelve una lista de tipos conocidos en tiempo de ejecución.  
  
5. Tenga en cuenta la compatibilidad con versiones anteriores y posteriores al crear o cambiar tipos serializables.  
  
     Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa. Asegúrese de que entiende que los miembros de datos, incluso los privados e internos, no pueden sufrir cambios en sus nombres, tipos, o incluso su orden, en versiones futuras del tipo a menos que se tomen precauciones para conservar el contrato mediante el uso de parámetros explícitos para los atributos del contrato de datos. Pruebe la compatibilidad de la serialización cuando realice cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.  
  
6. CONSIDERE la posibilidad de implementar la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir los viajes de ida y vuelta entre distintas versiones del tipo.  
  
     La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. La propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> almacena cualquier dato de la versión futura del tipo que es desconocido para la versión actual. Cuando la versión actual se serialice y deserialice en una versión futura, los datos adicionales estarán disponibles en la secuencia serializada a través del valor de propiedad **ExtensionData**.  
  
     [!code-csharp[SerializationGuidelines#5](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#5)]
     [!code-vb[SerializationGuidelines#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#5)]  
  
     Para obtener más información, vea [Forward-Compatible Data Contracts](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío).  
  
#### <a name="supporting-xml-serialization"></a>Admitir la serialización XML  
 La serialización de contrato de datos es la tecnología de serialización principal (predeterminada) en .NET Framework, pero hay escenarios de serialización que la serialización de contrato de datos no admite. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control tan detallado, debe usarse la *serialización XML* y los tipos se deben diseñar para admitir esta tecnología de serialización.  
  
1. EVITE diseñar sus tipos concretamente para la serialización XML, a menos que tenga una razón de peso para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.  
  
     En otras palabras, no aplique atributos del espacio de nombres <xref:System.Xml.Serialization> a los nuevos tipos, a menos que sepa que el tipo se utilizará con la serialización XML. El siguiente ejemplo muestra cómo se puede usar **System.Xml.Serialization** para controlar la forma del XML generado.  
  
     [!code-csharp[SerializationGuidelines#6](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#6)]
     [!code-vb[SerializationGuidelines#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#6)]  
  
2. CONSIDERE la posibilidad de implementar la interfaz <xref:System.Xml.Serialization.IXmlSerializable> si desea un mayor control sobre la forma del XML serializado del que se proporciona aplicando los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, permiten controlar totalmente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando el atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>.  
  
#### <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución  
 La *serialización en tiempo de ejecución* es una tecnología usada por .NET Remoting. Si piensa que sus tipos se transportarán mediante .NET Remoting, debe asegurarse de que admitan la serialización en tiempo de ejecución.  
  
 La compatibilidad básica para la *serialización en tiempo de ejecución* se puede proporcionar aplicando el atributo <xref:System.SerializableAttribute> y, en escenarios más avanzados, se implementa un *patrón serializable en tiempo de ejecución* simple (implemente -<xref:System.Runtime.Serialization.ISerializable> y proporcione un constructor de serialización).  
  
1. CONSIDERE la posibilidad de admitir la serialización en tiempo de ejecución si sus tipos se van a usar con .NET Remoting. Por ejemplo, el espacio de nombres <xref:System.AddIn> usa .NET Remoting. Así, todos los tipos intercambiados entre los complementos **System.AddIn** deben admitir la serialización en tiempo de ejecución.  
  
     [!code-csharp[SerializationGuidelines#7](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#7)]
     [!code-vb[SerializationGuidelines#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#7)]  
  
2. CONSIDERE la implementación del *patrón serializable en tiempo de ejecución* si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.  
  
     El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.  
  
     [!code-csharp[SerializationGuidelines#8](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#8)]
     [!code-vb[SerializationGuidelines#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#8)]  
  
3. Proteja el constructor de serialización y proporcione dos parámetros con el tipo y el nombre que se indican en el ejemplo que se muestra aquí.  
  
     [!code-csharp[SerializationGuidelines#9](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#9)]
     [!code-vb[SerializationGuidelines#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#9)]  
  
4. Implemente los miembros ISerializable explícitamente.  
  
     [!code-csharp[SerializationGuidelines#10](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#10)]
     [!code-vb[SerializationGuidelines#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#10)]  
  
5. Aplique una petición de vínculo a la implementación **ISerializable.GetObjectData**. De este modo se garantiza que solo el núcleo de plena confianza y el serializador en tiempo de ejecución tienen acceso al miembro.  
  
     [!code-csharp[SerializationGuidelines#11](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#11)]
     [!code-vb[SerializationGuidelines#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#11)]  
  
## <a name="see-also"></a>Vea también

- [Utilización de contratos de datos](../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Serializador de contratos de datos](../../../docs/framework/wcf/feature-details/data-contract-serializer.md)
- [Tipos admitidos por el serializador de contratos de datos](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Serialización binaria](binary-serialization.md)
- [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md)
