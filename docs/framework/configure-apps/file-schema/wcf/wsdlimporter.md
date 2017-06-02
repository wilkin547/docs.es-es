---
title: "&lt;wsdlImporter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;wsdlImporter&gt;
Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web \(WSDL\) 1.1 con datos adjuntos de WS\-Policy.  
  
## Sintaxis  
  
```  
  
<metadata>  
      <wsdlImporters>  
      <wsdlImporter type="string" />  
   </wsdlImporters>  
</metadata>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`type`|El tipo de este elemento.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<wsdlImporters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web \(WSDL\) 1.1 con datos adjuntos de WS\-Policy.|  
  
## Comentarios  
 Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.  Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.  También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 <xref:System.ServiceModel.Description.WsdlImporter>   
 [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)