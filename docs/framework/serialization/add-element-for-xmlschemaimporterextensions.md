---
title: "&lt;add&gt; (Elemento para &lt;xmlSchemaImporterExtensions&gt;) | Microsoft Docs"
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
  - "<add> (elemento para <xmlSchemaImporterExtensions>)"
  - "serialización XML, configuración"
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;add&gt; (Elemento para &lt;xmlSchemaImporterExtensions&gt;)
Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework.  Para obtener más información acerca de los archivos de configuración, consulte [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<XmlSchemaImporterExtensions\>  
\<add\>  
  
## Sintaxis  
  
```  
  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**name**|Un nombre sencillo que se utiliza para buscar la instancia.|  
|**type**|Requerido.  Especifica la clase de extensión de esquema que se agrega.  El valor de atributo de **type** debe estar en una línea e incluye el nombre de tipo completo.  Cuando el ensamblado se encuentra en la caché global de ensamblados \(GAC\), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<xmlSchemaImporterExtensions\>|Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .|  
  
## Ejemplo  
 El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [\<system.xml.serialization\> \(Elemento\)](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [\<schemaImporterExtensions\> \(Elemento\)](../../../docs/framework/serialization/schemaimporterextensions-element.md)