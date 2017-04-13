---
title: "Atributos que controlan la serializaci&#243;n XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "atributos [.NET Framework], serialización XML"
  - "clases, serializar"
  - "serialización, atributos"
  - "esquema XML, serializar"
  - "serialización XML, atributos"
  - "XmlSerializer (clase), serializar"
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Atributos que controlan la serializaci&#243;n XML
Se pueden aplicar atributos a clases y a miembros de clase en la siguiente tabla para controlar la manera en que [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) serializa o deserializa una instancia de la clase.Para entender cómo estos atributos controlan la serialización XML, vea [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md).  
  
 Estos atributos también se pueden utilizar para controlar los mensajes SOAP de estilo literales generados por un servicio Web XML.Para obtener más información sobre cómo aplicar estos atributos a un método de servicios Web XML, vea [Serialización XML con servicios web XML](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md).  
  
 Para obtener más información sobre los atributos, vea [Atributos](../../../docs/standard/attributes/index.md).  
  
|Atributo|Se aplica a|Especifica|  
|--------------|-----------------|----------------|  
|[XmlAnyAttributeAttribute](frlrfSystemXmlSerializationXmlAnyAttributeAttributeClassTopic)|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic) objects.|Al deserializar, la matriz estará llena de objetos [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic) que representan todos los atributos XML desconocidos para el esquema.|  
|[XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic)|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos [XmlElement](frlrfSystemXmlXmlElementClassTopic) objects.|Al deserializar, la matriz estará llena de objetos [XmlElement](frlrfSystemXmlXmlElementClassTopic) que representan todos los atributos XML desconocidos para el esquema|  
|[XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic)|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos complejos.|Los miembros de la matriz se generarán como miembros de una matriz de XML.|  
|[XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic)|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos complejos.|Los tipos derivados que se pueden insertar en una matriz.Normalmente aplicado junto con un [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic).|  
|[XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic)|Campo público, propiedad, parámetro o valor devuelto.|El miembro se serializará como un atributo XML.|  
|[XmlChoiceIdentifierAttribute](frlrfSystemXmlSerializationXmlChoiceIdentifierAttributeClassTopic)|Campo público, propiedad, parámetro o valor devuelto.|El miembro se puede desambiguar adicionalmente utilizando una enumeración.|  
|[XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic)|Campo público, propiedad, parámetro o valor devuelto.|El campo o propiedad se serializará como un elemento XML.|  
|[XmlEnumAttribute](frlrfSystemXmlSerializationXmlEnumAttributeClassTopic)|Campo público que es un identificador de enumeración.|Nombre de elemento del miembro de una enumeración.|  
|[XmlIgnoreAttribute](frlrfSystemXmlSerializationXmlIgnoreAttributeClassTopic)|Propiedades públicas y campos.|Se debería omitir la propiedad o campo cuando se serializa la clase contenedora.|  
|[XmlIncludeAttribute](frlrfSystemXmlSerializationXmlIncludeAttributeClassTopic)|Declaraciones de clase derivada públicas y valores devueltos de métodos públicos para los documentos de lenguaje de descripción de servicios Web \(WSDL\).|La clase debería estar incluida al generar los esquemas \(para ser reconocido cuando se serializa\).|  
|[XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic)|Declaraciones de clase públicas.|Controla la serialización XML del destino de atributo como elemento raíz XML.Utilice el atributo para especificar el espacio de nombres y nombre de elemento.|  
|[XmlTextAttribute](frlrfSystemXmlSerializationXmlTextAttributeClassTopic)|Propiedades públicas y campos.|La propiedad o campo se debería serializar como texto XML.|  
|[XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)|Declaraciones de clase públicas.|El nombre y espacio de nombres del tipo XML.|  
  
 Además de estos atributos, que se encuentran todos en el espacio de nombres [System.Xml.Serialization](frlrfSystemxmlserialization) también se puede aplicar el atributo [System.ComponentModel.DefaultValueAttribute](frlrfSystemComponentModelDefaultValueAttributeClassTopic) a un campo.**DefaultValueAttribute** establece el valor que estará asignado automáticamente al miembro si no se especifica ningún valor.  
  
 Para controlar la serialización de SOAP XML codificada vea [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
## Vea también  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)