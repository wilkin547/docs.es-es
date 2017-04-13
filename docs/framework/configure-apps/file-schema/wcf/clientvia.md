---
title: "&lt;clientVia&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;clientVia&gt;
Especifica URI para el que se debe crear el canal de transporte.  Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.  
  
## Sintaxis  
  
```  
  
<clientVia viaUri="String"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`viaUri`|Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un extremo.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ClientViaElement>   
 <xref:System.ServiceModel.Description.ClientViaBehavior>