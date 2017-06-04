---
title: "&lt;schemaImporterExtensions&gt; (Elemento) | Microsoft Docs"
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
  - "<schemaImporterExtensions> (elemento)"
  - "schemaImporterExtensions (elemento)"
  - "serialización XML, configuración"
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;schemaImporterExtensions&gt; (Elemento)
Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.  Para obtener más información sobre los archivos de configuración, vea [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Sintaxis  
  
```  
  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\> \(Elemento para \<xmlSchemaImporterExtensions\>\)](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)|Agrega tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.|  
  
## Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)|El elemento de nivel superior para controlar la serialización XML.|  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo agregar tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.  
  
```  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\> \(Elemento\)](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<add\> \(Elemento para \<xmlSchemaImporterExtensions\>\)](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)