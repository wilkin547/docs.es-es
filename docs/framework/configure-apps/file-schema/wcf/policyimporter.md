---
title: "&lt;policyImporter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;policyImporter&gt;
Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.  
  
## Sintaxis  
  
```  
  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`type`|El tipo de este elemento.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<policyImporters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.|  
  
## Comentarios  
 Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>   
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)