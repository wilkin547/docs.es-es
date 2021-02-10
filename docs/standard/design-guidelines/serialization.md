---
description: 'Más información acerca de: Serialización'
title: Serialización
ms.date: 10/22/2008
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: a12163c01da2f9eed19de05b0434c02d05ca99b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713304"
---
# <a name="serialization"></a>Serialización

La serialización es el proceso de convertir un objeto a un formulario que pueda conservarse o transportarse fácilmente. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y deserializarlo en la máquina de destino.

 .NET Framework proporciona tres tecnologías de serialización principales optimizadas para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.

|**Nombre de tecnología**|**Tipos principales**|**Escenarios**|
|-------------------------|--------------------|-------------------|
|**Serialización de contratos de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />Servicios Web<br />JSON|
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con control total sobre la forma del XML|
|**Serialización en tiempo de ejecución (Binary y SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|

 ✔️ PIENSE en la serialización al diseñar los nuevos tipos.

## <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir

 ✔️ CONSIDERE admitir la serialización de contrato de datos si puede que las instancias de su tipo deban conservarse o usarse en Servicios Web.

 ✔️ CONSIDERE la posibilidad de admitir la serialización XML en lugar de —o además de— la serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.

 Esto puede ser necesario en algunos escenarios de interoperabilidad donde es necesario utilizar una construcción XML no admitida por la serialización de contrato de datos; por ejemplo, para generar atributos XML.

 ✔️ CONSIDERE la posibilidad de admitir la serialización en tiempo de ejecución si las instancias de su tipo necesitan traspasar los límites de .NET Remoting.

 ❌ EVITE admitir la serialización en tiempo de ejecución o la serialización XML solo por motivos generales de persistencia. Se tiene preferencia por la serialización de contrato de datos.

## <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos

 Los tipos pueden admitir la serialización de contrato de datos mediante la aplicación de <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.

 ✔️ CONSIDERE la posibilidad de marcar como públicos los miembros de datos del tipo si el tipo se puede utilizar con confianza parcial.

 Con plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros no públicos, pero solo los miembros públicos se pueden serializar y deserializar con confianza parcial.

 ✔️ IMPLEMENTE un captador y un establecedor en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute>. Los serializadores de contrato de datos requieren tanto el captador como el establecedor para que el tipo se considere serializable. (En .NET Framework 3.5 SP1, algunas propiedades de colección pueden ser solo get). Si el tipo no se va a usar con confianza parcial, uno o los dos descriptores de acceso de propiedad pueden ser no públicos.

 ✔️ CONSIDERE la posibilidad de usar devoluciones de llamada de serialización para la inicialización de instancias deserializadas.

 No se llama a los constructores cuando se deserializan los objetos. (Hay excepciones a la regla. Se llama a los constructores de colecciones marcadas con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> durante la deserialización). Por consiguiente, cualquier lógica que se ejecute durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.

 `OnDeserializedAttribute` es el atributo de devolución de llamada más utilizado. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.

 ✔️ CONSIDERE la posibilidad de usar <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar tipos concretos que se deberían utilizar al deserializar un gráfico de objetos complejo.

 ✔️ TENGA EN CUENTA la compatibilidad con versiones anteriores y posteriores al crear o cambiar tipos serializables.

 Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa.

 Asegúrese de que entiende que los miembros de datos, incluso los privados e internos, no pueden sufrir cambios en sus nombres, tipos, o incluso su orden, en versiones futuras del tipo a menos que se tomen precauciones para conservar el contrato mediante el uso de parámetros explícitos para los atributos del contrato de datos.

 Pruebe la compatibilidad de la serialización cuando realice cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.

 ✔️ CONSIDERE la posibilidad de implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir los viajes de ida y vuelta entre distintas versiones del tipo.

 La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. La propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> se utiliza para almacenar los datos de la versión futura del tipo que es desconocido para la versión actual, por lo que no puede almacenarlos en sus miembros de datos. Cuando la versión actual se serialize y deserialize en una versión futura, los datos adicionales estarán disponibles en la secuencia serializada.

## <a name="supporting-xml-serialization"></a>Admitir la serialización XML

 La serialización de contrato de datos es la tecnología de serialización principal (predeterminada) en .NET Framework, pero hay escenarios de serialización que la serialización de contrato de datos no admite. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control tan detallado, debe usarse la serialización XML y los tipos se deben diseñar para admitir esta tecnología de serialización.

 ❌ EVITE diseñar sus tipos concretamente para la serialización XML, a menos que tenga una razón de peso para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.

 ✔️ CONSIDERE la posibilidad de implementar la interfaz <xref:System.Xml.Serialization.IXmlSerializable> si desea un mayor control sobre la forma del XML serializado del que se proporciona aplicando los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, permiten controlar totalmente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando `XmlSchemaProviderAttribute`.

## <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución

 La serialización en tiempo de ejecución es una tecnología usada por .NET Remoting. Si piensa que sus tipos se transportarán mediante .NET Remoting, debe asegurarse de que admitan la serialización en tiempo de ejecución.

 La compatibilidad básica para la serialización en tiempo de ejecución se puede proporcionar aplicando <xref:System.SerializableAttribute> y, en escenarios más avanzados, se implementa un patrón serializable en tiempo de ejecución simple (implemente <xref:System.Runtime.Serialization.ISerializable> y proporcione un constructor de serialización).

 ✔️ CONSIDERE la posibilidad de admitir la serialización en tiempo de ejecución si sus tipos se van a usar con .NET Remoting. Por ejemplo, el espacio de nombres <xref:System.AddIn?displayProperty=nameWithType> utiliza .NET Remoting. Así, todos los tipos intercambiados entre los complementos `System.AddIn` deben admitir la serialización en tiempo de ejecución.

 ✔️ CONSIDERE la implementación del patrón serializable en tiempo de ejecución si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.

 El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.

 ✔️ PROTEJA el constructor de serialización y proporcione dos parámetros con el tipo y el nombre que se indican en el ejemplo que se muestra aquí.

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

 ✔️ IMPLEMENTE los miembros <xref:System.Runtime.Serialization.ISerializable> explícitamente.

 ✔️ APLIQUE una petición de vínculo a la implementación <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>. De este modo se garantiza que solo el núcleo de plena confianza y el serializador en tiempo de ejecución tienen acceso al miembro.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de uso](usage-guidelines.md)
