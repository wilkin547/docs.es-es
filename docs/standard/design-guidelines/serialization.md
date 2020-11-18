---
title: Serialización
ms.date: 10/22/2008
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: 85481e9d759a71346d83c66f67d9623fc32e76ec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828678"
---
# <a name="serialization"></a>Serialización
La serialización es el proceso de convertir un objeto en un formato que se puede almacenar o transportar fácilmente. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y deserializarlo en el equipo de destino.

 El .NET Framework ofrece tres tecnologías de serialización principales optimizadas para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.

|**Nombre de tecnología**|**Tipos principales**|**Escenarios**|
|-------------------------|--------------------|-------------------|
|**Serialización de contratos de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />Servicios Web<br />JSON|
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con control total sobre la forma del XML|
|**Serialización en tiempo de ejecución (binario y SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|

 ✔️ Piense en la serialización al diseñar nuevos tipos.

## <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir
 ✔️ considere la posibilidad de admitir la serialización de contrato de datos si es posible que las instancias de su tipo deban conservarse o usarse en servicios Web.

 ✔️ considere la posibilidad de admitir la serialización XML en lugar de o además de la serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.

 Esto puede ser necesario en algunos escenarios de interoperabilidad en los que necesite usar una construcción XML que no sea compatible con la serialización de contrato de datos, por ejemplo, para generar atributos XML.

 ✔️ considere la posibilidad de admitir la serialización en tiempo de ejecución si las instancias de su tipo necesitan viajar a través de límites de .NET Remoting.

 ❌ Evite admitir la serialización en tiempo de ejecución o la serialización XML solo por motivos de persistencia generales. Prefiere la serialización de contrato de datos en su lugar.

## <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos
 Los tipos pueden admitir la serialización de contrato de datos aplicando <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.

 ✔️ considere la posibilidad de marcar los miembros de datos de su tipo como público si el tipo se puede usar en confianza parcial.

 En plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros no públicos, pero solo los miembros públicos se pueden serializar y deserializar en confianza parcial.

 ✔️ implementar un captador y un establecedor en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute> . Los serializadores de contrato de datos requieren el captador y el establecedor para que el tipo se considere serializable. (En .NET Framework 3,5 SP1, algunas propiedades de colección pueden ser de solo lectura). Si el tipo no se va a usar en confianza parcial, uno o ambos de los descriptores de acceso de propiedad pueden ser no públicos.

 ✔️ CONSIDERE el uso de las devoluciones de llamada de serialización para la inicialización de instancias deserializadas.

 No se llama a los constructores cuando se deserializan los objetos. (Hay excepciones a la regla. Se llama a los constructores de colecciones marcadas con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> durante la deserialización). Por consiguiente, cualquier lógica que se ejecute durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.

 `OnDeserializedAttribute` es el atributo de devolución de llamada que se usa con más frecuencia. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.

 ✔️ considere la posibilidad de usar <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar tipos concretos que deben usarse al deserializar un gráfico de objetos complejo.

 ✔️ tener en cuenta la compatibilidad con versiones anteriores y posteriores al crear o cambiar tipos serializables.

 Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa.

 Asegúrese de que entiende que los miembros de datos, incluso los privados e internos, no pueden cambiar sus nombres, tipos o incluso su orden en versiones futuras del tipo, a menos que se realice una atención especial para conservar el contrato mediante parámetros explícitos para los atributos del contrato de datos.

 Probar la compatibilidad de la serialización al realizar cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.

 ✔️ considere la posibilidad de implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir el recorrido de ida y vuelta entre diferentes versiones del tipo.

 La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. La <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> propiedad se usa para almacenar los datos de la versión futura del tipo que es desconocido para la versión actual y, por tanto, no puede almacenarlos en sus miembros de datos. Cuando la versión actual se serializa y deserializa posteriormente en una versión futura, los datos adicionales estarán disponibles en la secuencia serializada.

## <a name="supporting-xml-serialization"></a>Admitir la serialización XML
 La serialización de contrato de datos es la tecnología de serialización principal (predeterminada) en el .NET Framework, pero hay escenarios de serialización que la serialización de contrato de datos no admite. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control preciso, se debe usar la serialización XML y es necesario diseñar los tipos para admitir esta tecnología de serialización.

 ❌ Evite diseñar los tipos específicamente para la serialización XML, a menos que tenga un motivo muy seguro para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.

 ✔️ considere la posibilidad <xref:System.Xml.Serialization.IXmlSerializable> de implementar la interfaz si desea tener un mayor control sobre la forma del XML serializado que la que se ofrece al aplicar los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, permiten controlar totalmente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando `XmlSchemaProviderAttribute` .

## <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución
 La serialización en tiempo de ejecución es una tecnología que usa .NET Remoting. Si cree que los tipos se transportarán mediante .NET Remoting, debe asegurarse de que admiten la serialización en tiempo de ejecución.

 La compatibilidad básica con la serialización en tiempo de ejecución se puede proporcionar aplicando y <xref:System.SerializableAttribute> escenarios más avanzados implican la implementación de un patrón serializable en tiempo de ejecución simple (implemente <xref:System.Runtime.Serialization.ISerializable> y proporcione el constructor de serialización).

 ✔️ considere la posibilidad de admitir la serialización en tiempo de ejecución si los tipos se van a utilizar con .NET Remoting. Por ejemplo, el <xref:System.AddIn?displayProperty=nameWithType> espacio de nombres utiliza .NET Remoting y, por tanto, todos los tipos intercambiados entre los `System.AddIn` Complementos deben admitir la serialización en tiempo de ejecución.

 ✔️ considere la posibilidad de implementar el patrón serializable en tiempo de ejecución si desea tener un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.

 El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.

 ✔️ Haga que el constructor de serialización esté protegido y proporcione dos parámetros con el tipo y el nombre exactamente como se muestra en el ejemplo.

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

 ✔️ implementar los <xref:System.Runtime.Serialization.ISerializable> miembros explícitamente.

 ✔️ aplicar una petición de vínculo a la <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementación. Esto garantiza que solo el núcleo de plena confianza y el serializador en tiempo de ejecución tienen acceso al miembro.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de uso](usage-guidelines.md)
