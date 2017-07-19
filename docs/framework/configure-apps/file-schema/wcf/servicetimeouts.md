---
title: "&lt;serviceTimeouts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;serviceTimeouts&gt;
Especifica el tiempo de espera para un servicio.  
  
## Sintaxis  
  
```  
  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`transactionTimeout`|Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.  El valor predeterminado es "00:00:00".|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>