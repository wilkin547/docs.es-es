---
title: Serialization1
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db06feefdd9697fd53d64bce60ae11c7e74f8c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578071"
---
# <a name="serialization"></a>Serialización
La serialización es el proceso de convertir un objeto en un formato que se puede almacenar o transportar con facilidad. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y deserializar en el equipo de destino.  
  
 .NET Framework proporciona tres tecnologías de serialización principal que se optimizan para varios escenarios de serialización. En la siguiente tabla se enumeran estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.  
  
|**Nombre de la tecnología**|**Tipos principales**|**Escenarios**|  
|-------------------------|--------------------|-------------------|  
|**Serialización de contrato de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />Servicios Web<br />JSON|  
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con un control total sobre la forma del XML|  
|**Serialización en tiempo de ejecución (binario y SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ HACER** reflexión acerca de la serialización al diseñar nuevos tipos.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Elegir la tecnología de serialización correcta que se va a admitir  
 **Considere la posibilidad de ✓** admitir la serialización de contrato de datos si instancias de su tipo deba conservarse o puede usar en los servicios Web.  
  
 **Considere la posibilidad de ✓** admitir la serialización de XML en lugar de o además de serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.  
  
 Esto puede ser necesario en algunos escenarios donde es necesario usar un XML construcción la interoperabilidad que no es compatible con la serialización de contrato de datos, por ejemplo, para generar los atributos XML.  
  
 **Considere la posibilidad de ✓** admitir la serialización en tiempo de ejecución si necesitan instancias de su tipo de viajar a través de límites de .NET Remoting.  
  
 **X evitar** admite la serialización en tiempo de ejecución o serialización XML solo por razones de persistencia general. Prefiere la serialización de contrato de datos en su lugar.  
  
## <a name="supporting-data-contract-serialization"></a>Admitir la serialización de contrato de datos  
 Tipos pueden admitir la serialización de contrato de datos aplicando el <xref:System.Runtime.Serialization.DataContractAttribute> para el tipo y la <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros (campos y propiedades) del tipo.  
  
 **Considere la posibilidad de ✓** marcar los miembros de datos de su tipo público si el tipo se puede utilizar en confianza parcial.  
  
 En plena confianza, los serializadores de contrato de datos pueden serializar y deserializar los tipos y miembros, pero solo los miembros públicos se pueden serializar y deserializar en una confianza parcial.  
  
 **✓ HACER** implementar un captador y establecedor en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute>. Serializadores de contrato de datos requieren el captador y el establecedor para el tipo que se consideran serializables. (En .NET Framework 3.5 SP1, algunas propiedades de colección pueden ser sólo get.) Si el tipo no se va a usar con confianza parcial, uno o los dos descriptores de acceso de propiedad pueden ser no públicos.  
  
 **Considere la posibilidad de ✓** utilizando las devoluciones de llamada de serialización para la inicialización de instancias deserializados.  
  
 No se llama a los constructores cuando se deserializan los objetos. (No hay excepciones a esta regla. Constructores de colecciones marcan con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> durante la deserialización se llama.) Por lo tanto, cualquier lógica que se ejecuta durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.  
  
 `OnDeserializedAttribute` es el atributo de uso más frecuente de devolución de llamada. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se pueden utilizar para marcar devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, por último, después de la serialización, respectivamente.  
  
 **✓ Considere la posibilidad de** mediante el <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar los tipos concretos que se deben usar al deserializar un gráfico de objeto complejo.  
  
 **✓ HACER** considere la posibilidad de compatibilidad con versiones anteriores y posteriores al crear o cambiar los tipos serializables.  
  
 Tenga presente que las secuencias serializadas de futuras versiones del tipo se puedan deserializar en la versión actual del tipo y viceversa.  
  
 Asegúrese de que comprende que los miembros de datos, incluso privados e internos, no pueden cambiar sus nombres, tipos o incluso su orden en versiones futuras del tipo a menos que es tener un cuidado especial para conservar el contrato mediante parámetros explícitos para los atributos de contrato de datos .  
  
 Probar la compatibilidad de serialización al realizar cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior, y viceversa.  
  
 **✓ Considere la posibilidad de** implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir la ida y vuelta entre las distintas versiones del tipo.  
  
 La interfaz permite al serializador asegurarse de que no se pierden datos durante los viajes de ida y vuelta. El <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> propiedad se utiliza para almacenar los datos de la versión futura del tipo que se conoce a la versión actual y, por lo tanto no puede almacenar en sus miembros de datos. Cuando la versión actual posteriormente se serializa y deserializa en una versión futura, los datos adicionales estará disponibles en la secuencia serializada.  
  
## <a name="supporting-xml-serialization"></a>Admitir la serialización XML  
 Serialización de contrato de datos es el principal (valor predeterminado) la tecnología de serialización en .NET Framework, pero hay escenarios de serialización que no admite la serialización de contrato de datos. Por ejemplo, no proporciona control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control exhaustivo de este tipo, la serialización XML debe utilizarse y debe diseñar sus tipos admiten esta tecnología de serialización.  
  
 **X evitar** diseñar sus tipos específicamente para la serialización de XML, a menos que tenga un motivo muy seguro para controlar la forma del XML generado. Esta tecnología de serialización ha sido reemplazada por la serialización de contrato de datos que se describió en la sección anterior.  
  
 **✓ Considere la posibilidad de** implementar la <xref:System.Xml.Serialization.IXmlSerializable> interfaz si desea tener un mayor control sobre la forma del XML serializado que lo que se ofrece mediante la aplicación de los atributos de serialización XML. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, le permiten controlar completamente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo mediante la aplicación de la `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Admitir la serialización en tiempo de ejecución  
 Serialización en tiempo de ejecución es una tecnología que utiliza .NET Remoting. Si cree que sus tipos se se puede transportar mediante .NET Remoting, debe asegurarse de que admiten la serialización en tiempo de ejecución.  
  
 La compatibilidad básica para la serialización en tiempo de ejecución puede proporcionarse mediante la aplicación de la <xref:System.SerializableAttribute>, y escenarios más avanzados implican implementar un patrón de Serializable en tiempo de ejecución simple (implementar <xref:System.Runtime.Serialization.ISerializable> y proporcione el constructor de serialización).  
  
 **Considere la posibilidad de ✓** admitir la serialización en tiempo de ejecución si sus tipos se utilizará con .NET Remoting. Por ejemplo, el <xref:System.AddIn?displayProperty=nameWithType> espacio de nombres usa .NET Remoting y, por lo que todos los tipos que se intercambian entre `System.AddIn` complementos necesitan admitir la serialización en tiempo de ejecución.  
  
 **✓ Considere la posibilidad de** implementar el patrón Serializable en tiempo de ejecución si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar los datos cuando se serializan o deserializan.  
  
 El patrón es muy simple. Todo lo que necesita hacer es implementar la interfaz <xref:System.Runtime.Serialization.ISerializable> y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.  
  
 **✓ HACER** Marque el constructor de serialización protegido y proporcionar dos parámetros con tipo y con el nombre tal y como se muestra en este ejemplo.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ HACER** implementar la `ISerializable` miembros explícitamente.  
  
 **✓ HACER** aplicar una petición de vínculo a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementación. Esto garantiza que solo totalmente de confianza principal y el serializador en tiempo de ejecución tienen acceso al miembro.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
