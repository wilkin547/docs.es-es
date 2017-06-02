---
title: "&lt;servicios&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;servicios&gt;
Los servicios se definen en la sección de `services` del archivo de configuración.  Cada servicio tiene su propia sección de configuración de `service`.  
  
 \<system.ServiceModel\>  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguna  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<servicio\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Defina el contrato de servicios, comportamiento y extremos del servicio determinado.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation \(WCF\).|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServicesSection>