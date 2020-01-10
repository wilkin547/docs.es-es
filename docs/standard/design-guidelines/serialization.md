---
title: Serialización
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: fb5d714e2452f1b9c1dcc79cc179b35a2dd48fec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709080"
---
# <a name="serialization"></a>Serialización
La serialización es el proceso de convertir un objeto en un formato que se puede almacenar o transportar fácilmente. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y deserializarlo en el equipo de destino.  
  
 El .NET Framework ofrece tres tecnologías de serialización principales optimizadas para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.  
  
|**Nombre de la tecnología**|**Tipos principales**|**Escenarios**|  
|-------------------------|--------------------|-------------------|  
|**Serialización de contrato de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />Servicios Web de<br />JSON|  
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con control total sobre la forma del XML|  
|**Serialización en tiempo de ejecución (binario y SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|Comunicación remota de .NET|  
  
 **✓ DO** reflexión acerca de la serialización al diseñar nuevos tipos.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir  
 **✓ CONSIDER** admitir la serialización de contrato de datos si instancias de su tipo deba conservarse o puede usar en los servicios Web.  
  
 **✓ CONSIDER** admitir la serialización de XML en lugar de o además de serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.  
  
 Esto puede ser necesario en algunos escenarios de interoperabilidad en los que necesite usar una construcción XML que no sea compatible con la serialización de contrato de datos, por ejemplo, para generar atributos XML.  
  
 **✓ CONSIDER** admitir la serialización en tiempo de ejecución si necesitan instancias de su tipo de viajar a través de límites de .NET Remoting.  
  
 **X AVOID** admite la serialización en tiempo de ejecución o serialización XML solo por razones de persistencia general. Prefiere la serialización de contrato de datos en su lugar.  
  
## <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos  
 Los tipos pueden admitir la serialización de contrato de datos aplicando el <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y el <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.  
  
 **✓ CONSIDER** marcar los miembros de datos de su tipo público si el tipo se puede utilizar en confianza parcial.  
  
 En plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros no públicos, pero solo los miembros públicos se pueden serializar y deserializar en confianza parcial.  
  
 **✓ DO** implementar un captador y establecedor en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute>. Los serializadores de contrato de datos requieren el captador y el establecedor para que el tipo se considere serializable. (En .NET Framework 3,5 SP1, algunas propiedades de colección pueden ser de solo lectura). Si el tipo no se va a usar en confianza parcial, uno o ambos de los descriptores de acceso de propiedad pueden ser no públicos.  
  
 **✓ CONSIDER** utilizando las devoluciones de llamada de serialización para la inicialización de instancias deserializados.  
  
 No se llama a los constructores cuando se deserializan los objetos. (Hay excepciones a la regla. Se llama a los constructores de colecciones marcadas con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> durante la deserialización). Por consiguiente, cualquier lógica que se ejecute durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.  
  
 `OnDeserializedAttribute` es el atributo de devolución de llamada que se usa con más frecuencia. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.  
  
 **✓ CONSIDER** mediante el <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar los tipos concretos que se deben usar al deserializar un gráfico de objeto complejo.  
  
 **✓ DO** considere la posibilidad de compatibilidad con versiones anteriores y posteriores al crear o cambiar los tipos serializables.  
  
 Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa.  
  
 Asegúrese de que entiende que los miembros de datos, incluso los privados e internos, no pueden cambiar sus nombres, tipos o incluso su orden en versiones futuras del tipo, a menos que se realice una atención especial para conservar el contrato usando parámetros explícitos para los atributos del contrato de datos. .  
  
 Probar la compatibilidad de la serialización al realizar cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.  
  
 **✓ CONSIDER** implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir la ida y vuelta entre las distintas versiones del tipo.  
  
 La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. La propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> se utiliza para almacenar los datos de la versión futura del tipo que es desconocido para la versión actual, por lo que no puede almacenarlos en sus miembros de datos. Cuando la versión actual se serializa y deserializa posteriormente en una versión futura, los datos adicionales estarán disponibles en la secuencia serializada.  
  
## <a name="supporting-xml-serialization"></a>Admitir la serialización XML  
 La serialización de contrato de datos es la tecnología de serialización principal (predeterminada) en el .NET Framework, pero hay escenarios de serialización que la serialización de contrato de datos no admite. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control preciso, se debe usar la serialización XML y es necesario diseñar los tipos para admitir esta tecnología de serialización.  
  
 **X AVOID** diseñar sus tipos específicamente para la serialización de XML, a menos que tenga un motivo muy seguro para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.  
  
 **✓ CONSIDER** implementar la <xref:System.Xml.Serialization.IXmlSerializable> interfaz si desea tener un mayor control sobre la forma del XML serializado que lo que se ofrece mediante la aplicación de los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, permiten controlar por completo la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando el `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución  
 La serialización en tiempo de ejecución es una tecnología que usa .NET Remoting. Si cree que los tipos se transportarán mediante .NET Remoting, debe asegurarse de que admiten la serialización en tiempo de ejecución.  
  
 La compatibilidad básica para la serialización en tiempo de ejecución se puede proporcionar aplicando el <xref:System.SerializableAttribute>y escenarios más avanzados implican la implementación de un patrón serializable en tiempo de ejecución simple (implemente <xref:System.Runtime.Serialization.ISerializable> y proporcione el constructor de serialización).  
  
 **✓ CONSIDER** admitir la serialización en tiempo de ejecución si sus tipos se utilizará con .NET Remoting. Por ejemplo, el espacio de nombres <xref:System.AddIn?displayProperty=nameWithType> usa .NET Remoting y, por tanto, todos los tipos intercambiados entre `System.AddIn` complementos deben admitir la serialización en tiempo de ejecución.  
  
 **✓ CONSIDER** implementar el patrón Serializable en tiempo de ejecución si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.  
  
 El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.  
  
 **✓ DO** Marque el constructor de serialización protegido y proporcionar dos parámetros con tipo y con el nombre tal y como se muestra en este ejemplo.  
  
```csharp
[Serializable]  
public class Person : ISerializable
{  
    protected Person(SerializationInfo info, StreamingContext context)
    {  
        // ...  
    }  
}  
```
  
 **✓ DO** implementar la <xref:System.Runtime.Serialization.ISerializable> miembros explícitamente.  
  
 **✓ DO** aplicar una petición de vínculo a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementación. Esto garantiza que solo el núcleo de plena confianza y el serializador en tiempo de ejecución tienen acceso al miembro.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
