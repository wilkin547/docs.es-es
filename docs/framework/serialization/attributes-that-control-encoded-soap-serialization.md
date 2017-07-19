---
title: "Atributos que controlan la serializaci&#243;n SOAP codificada | Microsoft Docs"
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
  - "serialización, atributos"
  - "SOAP, serialización XML"
  - "serialización XML, atributos"
  - "serialización XML, SOAP"
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Atributos que controlan la serializaci&#243;n SOAP codificada
El documento de World Wide Web Consortium \(www.w3.org\) denominado "Protocolo simple de acceso a objetos \(SOAP\) 1.1" contiene una sección opcional \(la sección 5\) que describe cómo los parámetros SOAP pueden estar codificados.Para cumplir a la sección 5 de la especificación, debe utilizar un conjunto especial de atributos situado en el espacio de nombres [System.Xml.Serialization](frlrfSystemXmlSerialization).Aplique según corresponda esos atributos a las clases y miembros de clases y, a continuación, utilice [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) para serializar instancias de la clase o clases.  
  
 La tabla siguiente muestra los atributos, donde se pueden aplicar, y lo que hacen.Para obtener más información sobre el uso de estos atributos para controlar la serialización de XML vea [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) y [Cómo: Invalidar la serialización XML SOAP codificada](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md).  
  
 Para obtener más información sobre los atributos, vea [Atributos](../../../docs/standard/attributes/index.md).  
  
|Atributo|Se aplica a|Especifica|  
|--------------|-----------------|----------------|  
|[SoapAttributeAttribute](frlrfSystemXmlSerializationSoapAttributeAttributeClassTopic)|Campo público, propiedad, parámetro o valor devuelto.|El miembro de clase se serializará como un atributo XML.|  
|[SoapElementAttribute](frlrfSystemXmlSerializationSoapElementAttributeClassTopic)|Campo público, propiedad, parámetro o valor devuelto.|La clase se serializará como un elemento XML.|  
|[SoapEnumAttribute](frlrfSystemXmlSerializationSoapEnumAttributeClassTopic)|Campo público que es un identificador de enumeración.|Nombre de elemento del miembro de una enumeración.|  
|[SoapIgnoreAttribute](frlrfSystemXmlSerializationSoapIgnoreAttributeClassTopic)|Propiedades públicas y campos.|Se debería omitir la propiedad o campo cuando se serializa la clase contenedora.|  
|[SoapIncludeAttribute](frlrfSystemXmlSerializationSoapIncludeAttributeClassTopic)|Declaraciones de clase derivada públicas y métodos públicos para los documentos de lenguaje de descripción de servicios Web \(WSDL\).|El tipo debería estar incluido al generar los esquemas \(para ser reconocido cuando se serializa\).|  
|[SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)|Declaraciones de clase públicas.|La clase se debería serializar como un tipo de XML.|  
  
## Vea también  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [Cómo: Invalidar la serialización XML SOAP codificada](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [Atributos](../../../docs/standard/attributes/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)