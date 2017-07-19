---
title: "&lt;baseAddresses&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;baseAddresses&gt;
Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.  Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.  
  
## Sintaxis  
  
```  
  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<host\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Un elemento de configuración que especifica valores para un host de servicio.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>   
 [Hospedaje](../../../../../docs/framework/wcf/feature-details/hosting.md)