---
title: "&lt;dateTimeSerialization&gt; (Elemento) | Microsoft Docs"
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
  - "<dateTimeSerialization> (elemento)"
  - "dateTimeSerialization (elemento)"
  - "serialización XML, configuración"
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;dateTimeSerialization&gt; (Elemento)
Determina el modo de serialización XML de los objetos <xref:System.DateTime>.  
  
## Sintaxis  
  
```  
  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributos|Descripción|  
|---------------|-----------------|  
|`mode`|Opcional.  Especifica el modo de serialización.  Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .  De manera predeterminada, es **RoundTrip**.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|system.xml.serialization|El elemento de nivel superior para controlar la serialización XML.|  
  
## Comentarios  
 En las versiones 1.0 y 1.1 de .Net Framework, así como en la versión 2.0 y posteriores cuando esta propiedad se establece en **Local**, <xref:System.DateTime>, los objetos siempre reciben formato según la hora local.  Es decir, la información de zona horaria local siempre se incluye con los datos serializados.  Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .Net Framework.  
  
 En la versión 2.0 y las versiones posteriores de .NET Framework que han establecido esta propiedad en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en el local, Hora UTC o una zona horaria no especificada.  Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.  Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.  
  
## Vea también  
 <xref:System.DateTime>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<schemaImporterExtensions\> \(Elemento\)](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<add\> \(Elemento para \<xmlSchemaImporterExtensions\>\)](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)