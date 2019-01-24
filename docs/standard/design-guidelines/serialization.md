---
title: Serialization1
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: KrzysztofCwalina
ms.openlocfilehash: c2a5a69186e41642abf77357db8b04e2611a43f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513151"
---
# <a name="serialization"></a>Serialización
La serialización es el proceso de convertir un objeto en un formato que se pueda almacenar o transportar fácilmente. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y se puede deserializar en el equipo de destino.  
  
 .NET Framework proporciona tres tecnologías de serialización principales que se optimizan para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.  
  
|**Nombre de la tecnología**|**Tipos principales**|**Escenarios**|  
|-------------------------|--------------------|-------------------|  
|**Serialización de contrato de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />Servicios Web<br />JSON|  
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con control total sobre la forma del XML|  
|**Serialización de tiempo de ejecución (Binary y SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ DO** reflexión acerca de la serialización al diseñar nuevos tipos.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir  
 **✓ CONSIDER** admitir la serialización de contrato de datos si instancias de su tipo deba conservarse o puede usar en los servicios Web.  
  
 **✓ CONSIDER** admitir la serialización de XML en lugar de o además de serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.  
  
 Esto puede ser necesario en algunos escenarios donde es necesario usar un archivo XML a construir la interoperabilidad que no es compatible con la serialización de contrato de datos, por ejemplo, para generar atributos XML.  
  
 **✓ CONSIDER** admitir la serialización en tiempo de ejecución si necesitan instancias de su tipo de viajar a través de límites de .NET Remoting.  
  
 **X AVOID** admite la serialización en tiempo de ejecución o serialización XML solo por razones de persistencia general. Prefiere la serialización de contrato de datos en su lugar.  
  
## <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos  
 Los tipos pueden admitir la serialización de contrato de datos aplicando el <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y el <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.  
  
 **✓ CONSIDER** marcar los miembros de datos de su tipo público si el tipo se puede utilizar en confianza parcial.  
  
 Con plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros, pero se pueden serializar y deserializar con confianza parcial solo miembros públicos.  
  
 **✓ DO** implementar un captador y establecedor en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute>. Los serializadores de contrato de datos requieren getter y setter para que el tipo se considere serializable. (En .NET Framework 3.5 SP1, algunas propiedades de colección pueden ser solo get.) Si el tipo no se va a usar con confianza parcial, uno o los dos descriptores de acceso de propiedad pueden ser no públicos.  
  
 **✓ CONSIDER** utilizando las devoluciones de llamada de serialización para la inicialización de instancias deserializados.  
  
 No se llama a los constructores cuando se deserializan los objetos. (Hay excepciones a esta regla. Constructores de colecciones marcan con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se llaman durante la deserialización.) Por lo tanto, cualquier lógica que se ejecuta durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.  
  
 `OnDeserializedAttribute` es el atributo de devolución de llamada más utilizado. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.  
  
 **✓ CONSIDER** mediante el <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar los tipos concretos que se deben usar al deserializar un gráfico de objeto complejo.  
  
 **✓ DO** considere la posibilidad de compatibilidad con versiones anteriores y posteriores al crear o cambiar los tipos serializables.  
  
 Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa.  
  
 Asegúrese de que comprender que los miembros de datos, incluso los privados e internos, no pueden cambiar sus nombres, tipos o incluso su orden en versiones futuras del tipo a menos que se tomen precauciones para conservar el contrato mediante parámetros explícitos para los atributos de contrato de datos .  
  
 Probar la compatibilidad de serialización cuando realice cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.  
  
 **✓ CONSIDER** implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir la ida y vuelta entre las distintas versiones del tipo.  
  
 La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. El <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> propiedad se usa para almacenar datos de la versión futura del tipo que es desconocido para la versión actual y, por lo tanto no puede almacenar en sus miembros de datos. Cuando se serializa y deserializa en una versión futura posteriormente la versión actual, los datos adicionales estarán disponibles en la secuencia serializada.  
  
## <a name="supporting-xml-serialization"></a>Admitir la serialización XML  
 Serialización de contrato de datos es el principal (predeterminado) la tecnología de serialización en .NET Framework, pero hay escenarios de serialización no se admite la serialización de contrato de datos. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control tan detallado, debe usarse la serialización XML, y debe diseñar sus tipos para admitir esta tecnología de serialización.  
  
 **X AVOID** diseñar sus tipos específicamente para la serialización de XML, a menos que tenga un motivo muy seguro para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.  
  
 **✓ CONSIDER** implementar la <xref:System.Xml.Serialization.IXmlSerializable> interfaz si desea tener un mayor control sobre la forma del XML serializado que lo que se ofrece mediante la aplicación de los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, le permiten controlar totalmente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando el `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución  
 Serialización en tiempo de ejecución es una tecnología utilizada por .NET Remoting. Si cree que sus tipos se transportarán mediante .NET Remoting, deberá asegurarse de que admiten la serialización en tiempo de ejecución.  
  
 La compatibilidad básica para la serialización en tiempo de ejecución se puede proporcionar aplicando el <xref:System.SerializableAttribute>, y escenarios más avanzados implican la implementación de un patrón de Serializable en tiempo de ejecución simple (implemente <xref:System.Runtime.Serialization.ISerializable> y proporcione el constructor de serialización).  
  
 **✓ CONSIDER** admitir la serialización en tiempo de ejecución si sus tipos se utilizará con .NET Remoting. Por ejemplo, el <xref:System.AddIn?displayProperty=nameWithType> espacio de nombres usa .NET Remoting y, por lo que todos los tipos intercambiados entre `System.AddIn` complementos que necesita admitir la serialización en tiempo de ejecución.  
  
 **✓ CONSIDER** implementar el patrón Serializable en tiempo de ejecución si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.  
  
 El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.  
  
 **✓ DO** Marque el constructor de serialización protegido y proporcionar dos parámetros con tipo y con el nombre tal y como se muestra en este ejemplo.  
  
```csharp
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```
  
 **✓ DO** implementar la `ISerializable` miembros explícitamente.  
  
 **✓ DO** aplicar una petición de vínculo a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementación. Esto garantiza que solo totalmente de confianza core y el serializador en tiempo de ejecución tienen acceso al miembro.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
