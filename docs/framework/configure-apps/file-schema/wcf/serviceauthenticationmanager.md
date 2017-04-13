---
title: "&lt;serviceAuthenticationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;serviceAuthenticationManager&gt;
Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <serviceAuthenticationManager serviceAuthenticationManagerType =”String”/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|serviceAuthenticationManagerType|Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>