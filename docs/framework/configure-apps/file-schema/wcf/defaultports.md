---
title: "&lt;defaultPorts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;defaultPorts&gt;
Colección de puertos predeterminados que enumeran los extremos de comunicaciones predeterminados que escucha la aplicación cliente.  
  
## Sintaxis  
  
```  
  
<useRequestHeadersForMetadataAddress>  
   <defaultPorts>  
      <add scheme="http" port="integer" />  
   </defaultPorts>  
</useRequestHeadersForMetadataAddress>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\> de \<defaultPorts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Lista de puertos predeterminados.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>