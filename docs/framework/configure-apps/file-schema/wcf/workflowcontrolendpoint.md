---
title: "&lt;workflowControlEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;workflowControlEndpoint&gt;
Este elemento de configuración define un extremo estándar para controlar la ejecución de instancias de flujo de trabajo \(crear, ejecutar, suspender, terminar, etc\).  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <workflowControlEndpoint>   
          <standardEndpoint  
                  name="String" />   
       </workflowControlEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Cadena que especifica el nombre de la configuración del extremo estándar.  El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de extremos estándar que son extremos predefinidos con una o más de sus propiedades \(dirección, enlace, contrato\) fijas.|  
  
## Vea también  
 <xref:System.ServiceModel.Activites.WorkflowControlEndpoint>