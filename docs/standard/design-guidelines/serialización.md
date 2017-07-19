---
title: "Serialization1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Serializaci&#243;n
La serialización es el proceso de convertir un objeto en un formato que se pueda almacenar o transportar fácilmente. Por ejemplo, puede serializar un objeto, transportarlo a través de Internet mediante HTTP y deserializa en el equipo de destino.  
  
 .NET Framework proporciona tres tecnologías de serialización principales optimizadas para diversos escenarios de serialización. En la tabla siguiente se enumera estas tecnologías y los principales tipos de Framework relacionados con estas tecnologías.  
  
|**Nombre de la tecnología**|**Tipos principales**|**Escenarios**|  
|---------------------------------|---------------------------|--------------------|  
|**Serialización de contrato de datos**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistencia general<br />servicios Web<br />JSON|  
|**Serialización XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con un control completo sobre la forma de XML|  
|**Serialización de tiempo de ejecución \(binario y SOAP\)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ hacer** reflexión acerca de la serialización al diseñar nuevos tipos.  
  
## Elegir la tecnología de serialización correctos al soporte técnico  
 **✓ considere** admite la serialización de contrato de datos si las instancias de su tipo deba conservarse o usarse en servicios Web.  
  
 **✓ considere** admitir la serialización XML en lugar de o además de serialización de contrato de datos si necesita más control sobre el formato XML que se genera cuando se serializa el tipo.  
  
 Esto puede ser necesario en algunos escenarios donde es necesario usar un archivo XML a construir la interoperabilidad que no es compatible con la serialización de contrato de datos, por ejemplo, para generar atributos XML.  
  
 **✓ considere** admitir la serialización en tiempo de ejecución si necesitan desplazarse a través de límites de .NET Remoting instancias de su tipo.  
  
 **Evitar X** admitir la serialización en tiempo de ejecución o serialización XML sólo por motivos de persistencia general. Preferiría serialización de contrato de datos.  
  
## Serialización de contrato de datos auxiliares  
 Tipos pueden admitir la serialización de contrato de datos aplicando el <xref:System.Runtime.Serialization.DataContractAttribute> para el tipo y la <xref:System.Runtime.Serialization.DataMemberAttribute> a los miembros \(campos y propiedades\) del tipo.  
  
 **✓ considere** marcar los miembros de datos de su público de tipo si el tipo se puede utilizar en confianza parcial.  
  
 En plena confianza, los serializadores de contrato de datos pueden serializar y deserializar tipos y miembros, pero sólo los miembros públicos se pueden serializar y deserializar con confianza parcial.  
  
 **✓ hacer** implemente getter y setter en todas las propiedades que tienen <xref:System.Runtime.Serialization.DataMemberAttribute>. Los serializadores de contrato de datos requieren el captador y el establecedor para el tipo se considere serializable. \(En .NET Framework 3.5 SP1, algunas propiedades de colección pueden ser sólo get.\) Si no utiliza el tipo de confianza parcial, uno o ambos de los descriptores de acceso de propiedad pueden ser no públicos.  
  
 **✓ considere** utilizando las devoluciones de llamada de serialización para la inicialización de instancias deserializadas.  
  
 Los constructores no se llaman cuando se deserializan los objetos. \(Hay excepciones a esta regla. Constructores de colecciones se marcan con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> durante la deserialización se llama.\) Por lo tanto, cualquier lógica que se ejecuta durante la construcción normal debe implementarse como una de las devoluciones de llamada de serialización.  
  
 `OnDeserializedAttribute` es el atributo de devolución de llamada utilizadas con más frecuencia. Los otros atributos de la familia son <xref:System.Runtime.Serialization.OnDeserializingAttribute>,  <xref:System.Runtime.Serialization.OnSerializingAttribute>, y <xref:System.Runtime.Serialization.OnSerializedAttribute>. Se puede utilizar para marcar las devoluciones de llamada que se ejecutan antes de la deserialización, antes de la serialización y, finalmente, después de la serialización, respectivamente.  
  
 **✓, considere la posibilidad de** mediante el <xref:System.Runtime.Serialization.KnownTypeAttribute> para indicar tipos concretos que se deben utilizar al deserializar un gráfico de objeto complejo.  
  
 **✓ hacer** considerar la compatibilidad con versiones anteriores y posteriores al crear o cambiar tipos serializables.  
  
 Tenga en cuenta que las secuencias serializadas de futuras versiones de su tipo se puede deserializar en la versión actual del tipo y viceversa.  
  
 Asegúrese de que entiende que los miembros de datos, incluso los privados e internos, no pueden cambiar sus nombres, tipos o incluso su orden en versiones futuras del tipo a menos que se tomen precauciones para conservar el contrato mediante parámetros explícitos para los atributos de contrato de datos.  
  
 Probar la compatibilidad de serialización cuando realice cambios en los tipos serializables. Pruebe a deserializar la nueva versión en una versión anterior y viceversa.  
  
 **✓ considere** implementar <xref:System.Runtime.Serialization.IExtensibleDataObject> para permitir la ida y vuelta entre las distintas versiones del tipo.  
  
 La interfaz permite al serializador asegurarse de que no se pierdan datos durante la ida y vuelta. El <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=fullName> propiedad se utiliza para almacenar cualquier dato de la futura versión del tipo que es desconocido para la versión actual y, por lo tanto no puede almacenar en sus miembros de datos. Cuando la versión actual se serializa y deserializa en una versión futura posteriormente, los datos adicionales estarán disponibles en la secuencia serializada.  
  
## Admitir la serialización XML  
 Serialización de contrato de datos es el principal \(predeterminado\) la tecnología de serialización en .NET Framework, pero hay escenarios de serialización que no admite la serialización de contrato de datos. Por ejemplo, no le otorga control total sobre la forma del XML generado o utilizado por el serializador. Si se requiere un control tan detallado, debe utilizarse la serialización XML y que necesita para diseñar sus tipos compatibles con la tecnología de serialización.  
  
 **Evitar X** diseñar sus tipos específicamente para la serialización XML, a menos que tenga una razón de peso para controlar la forma del XML generado. Esta tecnología de serialización se ha sustituido por la serialización de contrato de datos se describe en la sección anterior.  
  
 **✓ considere** implementar la <xref:System.Xml.Serialization.IXmlSerializable> Si desea más control sobre la forma del XML serializado que se proporciona al aplicar los atributos de serialización XML de la interfaz. Dos métodos de la interfaz, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> y <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, permiten controlar totalmente la secuencia XML serializada. También puede controlar el esquema XML que se genera para el tipo aplicando el `XmlSchemaProviderAttribute`.  
  
## Admitir la serialización en tiempo de ejecución  
 Serialización en tiempo de ejecución es una tecnología que utiliza .NET Remoting. Si cree que sus tipos se transportarán mediante .NET Remoting, debe asegurarse de que admiten la serialización en tiempo de ejecución.  
  
 Se puede proporcionar la compatibilidad básica para la serialización en tiempo de ejecución mediante la aplicación de la <xref:System.SerializableAttribute>, y escenarios más avanzados implican implementar un patrón de Serializable en tiempo de ejecución simple \(implemente <xref:System.Runtime.Serialization.ISerializable> y proporcionan el constructor de serialización\).  
  
 **✓ considere** compatibilidad de serialización en tiempo de ejecución si sus tipos se utilizará con .NET Remoting. Por ejemplo, el <xref:System.AddIn?displayProperty=fullName> espacio de nombres usa .NET Remoting y todos los tipos intercambiados entre `System.AddIn` complementos necesitan admitir la serialización en tiempo de ejecución.  
  
 **✓ considere** implementa el patrón Serializable en tiempo de ejecución si desea un control completo sobre el proceso de serialización. Por ejemplo, si desea transformar datos como obtiene serializa o deserializa.  
  
 El patrón es muy sencillo. Todo lo que necesita hacer es implementar la <xref:System.Runtime.Serialization.ISerializable> interfaz y proporcionar un constructor especial que se utiliza cuando se deserializa el objeto.  
  
 **✓ hacer** proteger al constructor de serialización y proporcionar dos parámetros con tipo y con el nombre exactamente como se muestra en el ejemplo aquí.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ hacer** implementar los `ISerializable` miembros explícitamente.  
  
 **✓ hacer** aplique una petición de vínculo a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> implementación. Esto garantiza que sólo totalmente de confianza principal y el serializador en tiempo de ejecución tienen acceso al miembro.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)