---
title: "&lt;add&gt; de &lt;baseAddresses&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;add&gt; de &lt;baseAddresses&gt;
Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.  
  
## Sintaxis  
  
```  
  
<add baseAddress="string" />  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`baseAddress`|Cadena que especifica una dirección base usada por el host del servicio.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<baseAddresses\>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Una colección de elementos de `baseAddress`.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>   
 [Hospedaje](../../../../../docs/framework/wcf/feature-details/hosting.md)