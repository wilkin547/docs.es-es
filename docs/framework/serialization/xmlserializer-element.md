---
title: "&lt;xmlSerializer&gt; (Elemento) | Microsoft Docs"
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
  - "<xmlSerializer> (elemento)"
  - "serialización XML, configuración"
  - "xmlSerializer (elemento)"
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;xmlSerializer&gt; (Elemento)
Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.  
  
## Sintaxis  
  
```  
  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**checkDeserializeAdvances**|Especifica si se comprueba el progreso de <xref:System.Xml.Serialization.XmlSerializer>.  Establezca el atributo a "verdadero" o "falso."  El valor predeterminado es "true".|  
|**useLegacySerializationGeneration**|Especifica si <xref:System.Xml.Serialization.XmlSerializer> usa generación de serialización heredada, que genera ensamblados escribiendo código de C\# en un archivo y después compilándolo en un ensamblado.  De manera predeterminada, es **false**.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)|Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## Comentarios  
 De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza.  Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización.  Si se detecta este tipo de condición, se producirá una excepción con el mensaje siguiente: "Error interno: error al adelantar la deserialización sobre la secuencia subyacente."  
  
 Recibir este mensaje necesariamente no indica que un ataque por denegación de servicio está en curso.  En algunas circunstancias raras, el mecanismo de detección de bucle sin fin genera un positivo falso y la excepción se producirá para un mensaje entrante legítimo.  Si encuentra que en su aplicación determinada este nivel de protección adicional está rechazando los mensajes legítimos, establezca el atributo **checkDeserializeAdvances** como "falso".  
  
## Ejemplo  
 En el ejemplo de código siguiente se establece el atributo **checkDeserializeAdvances** como "false".  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Xml.Serialization.XmlSerializer>   
 [\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)