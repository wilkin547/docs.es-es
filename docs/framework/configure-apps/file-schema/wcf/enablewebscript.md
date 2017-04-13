---
title: "&lt;enableWebScript&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;enableWebScript&gt;
Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.  
  
## Sintaxis  
  
```  
  
<enableWebScript />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el conjunto de comportamientos del extremo.|  
  
## Comentarios  
 ESte comportamiento sólo se debería utilizar junto con el enlace estándar [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) o el elemento de enlace [\<webMessageEncoding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md).  Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>   
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>   
 [Integración de AJAX y compatibilidad de JSON](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)