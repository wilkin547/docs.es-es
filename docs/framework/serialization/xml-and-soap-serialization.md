---
title: "Serializaci&#243;n de SOAP y XML | Microsoft Docs"
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
  - "serialización"
  - "serialización, acerca de la serialización"
  - "serialización, SOAP"
  - "SOAP, serialización XML"
  - "serialización XML"
  - "serialización XML, SOAP"
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serializaci&#243;n de SOAP y XML
La serialización XML convierte \(serializa\) las propiedades y campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML \(XSD\).La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie \(en este caso, a XML\) para almacenaje y transporte.  
  
 Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma.Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets.A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.  
  
 La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.  
  
 Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>.Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.  
  
## En esta sección  
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)  
 Proporciona una definición general de serialización, particularmente la serialización XML.  
  
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)  
 Proporciona las instrucciones paso a paso para serializar un objeto.  
  
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)  
 Proporciona las instrucciones paso a paso para deserializar un objeto  
  
 [Ejemplos de serialización XML](../../../docs/framework/serialization/examples-of-xml-serialization.md)  
 Proporciona ejemplos que muestran los fundamentos de serialización XML.  
  
 [Herramienta de definición de esquema XML y serialización XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 Describe cómo utilizar la herramienta XML Schema Definition para crear clases que se adhieren a un esquema del lenguaje de definición de esquemas XML \(XSD\) determinado o que generan un esquema XML de un archivo .dll.  
  
 [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)  
 Describe cómo controlar la serialización utilizando los atributos.  
  
 [Atributos que controlan la serialización XML](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)  
 Hace una lista de los atributos que se utilizan para controlar la serialización XML.  
  
 [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 Presenta un escenario avanzado que muestra cómo generar varias secuencias XML invalidando la serialización.  
  
 [Cómo: Controlar la serialización de clases derivadas](../../../docs/framework/serialization/how-to-control-serialization-of-derived-classes.md)  
 Ofrece un ejemplo que muestra cómo controlar la serialización de clases derivadas.  
  
 [Cómo: Calificar el elemento XML y los nombres del atributo XML](../../../docs/framework/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 Describe cómo definir y controlar la manera en la que los espacios de nombres XML se utilizan en la secuencia XML.  
  
 [Serialización XML con servicios web XML](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)  
 Explica cómo la serialización XML se utiliza en servicios Web XML.  
  
 [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 Describe cómo utilizar la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias de XML SOAP codificadas que cumple con la sección 5 del documento del World Wide Web Consortium \(www.w3.org\) titulado "Protocolo simple de acceso a objetos \(SOAP\) 1.1"  
  
 [Cómo: Invalidar la serialización XML SOAP codificada](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 Describe el proceso para invalidar serialización XML de objetos como mensajes SOAP.  
  
 [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)  
 Hace una lista de los atributos que se utilizan para controlar la serialización codificada SOAP.  
  
 [\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)  
 El elemento de configuración de nivel superior para controlar la serialización XML.  
  
 [\<dateTimeSerialization\> \(Elemento\)](../../../docs/framework/serialization/datetimeserialization-element.md)  
 Controla el modo de la serialización de los objetos <xref:System.DateTime>.  
  
 [\<schemaImporterExtensions\> \(Elemento\)](../../../docs/framework/serialization/schemaimporterextensions-element.md)  
 Contiene tipos que son utilizados por la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.  
  
 [\<add\> \(Elemento para \<xmlSchemaImporterExtensions\>\)](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)  
 Agrega tipos que utiliza la clase <xref:System.Xml.Serialization.XmlSchemaImporter> .  
  
## Secciones relacionadas  
 [Advanced Development Technologies](http://msdn.microsoft.com/es-es/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 Proporciona vínculos para más información sobre tareas y técnicas de desarrollo sofisticadas de .NET Framework.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/es-es/1e64af78-d705-4384-b08d-591a45f4379c)  
 Proporciona los temas que describen y explican cómo programar los servicios Web XML utilizando ASP.NET.  
  
## Vea también  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)