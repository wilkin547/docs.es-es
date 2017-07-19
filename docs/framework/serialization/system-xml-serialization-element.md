---
title: "&lt;system.xml.serialization&gt; (Elemento) | Microsoft Docs"
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
  - "<system.xml.serialization> (elemento)"
  - "system.xml.serialization (elemento)"
  - "serialización XML, configuración"
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;system.xml.serialization&gt; (Elemento)
El elemento de nivel superior para controlar la serialización XML.  Para obtener más información acerca de los archivos de configuración, consulte [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Sintaxis  
  
```  
  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<dateTimeSerialization\> \(Elemento\)](../../../docs/framework/serialization/datetimeserialization-element.md)|Determina el modo de serialización XML de los objetos <xref:System.DateTime>.|  
|[\<schemaImporterExtensions\> \(Elemento\)](../../../docs/framework/serialization/schemaimporterextensions-element.md)|Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<configuration\>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.  
  
```  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\> \(Elemento\)](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<schemaImporterExtensions\> \(Elemento\)](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<add\> \(Elemento para \<xmlSchemaImporterExtensions\>\)](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)