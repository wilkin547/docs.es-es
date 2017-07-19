---
title: "&lt;timeOuts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;timeOuts&gt;
Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.  
  
## Sintaxis  
  
```  
  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`closeTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.|  
|`openTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<host\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Un elemento de configuración que especifica valores para un host de servicio.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 <xref:System.ServiceModel.ServiceHost.CloseTimeout%2A>   
 <xref:System.ServiceModel.ServiceHost.OpenTimeout%2A>   
 [Hospedaje](../../../../../docs/framework/wcf/feature-details/hosting.md)