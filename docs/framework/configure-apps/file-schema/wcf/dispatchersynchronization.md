---
title: "&lt;dispatcherSynchronization&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;dispatcherSynchronization&gt;
Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.  
  
## Sintaxis  
  
```  
  
<dispatcherSynchronizationBehavior   
   asynchronousSendEnabled=”Boolean”  
   maxPendingReceives="Integer" />  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|asynchronousSendEnabled|Booleano que especifica si el comportamiento de envío asincrónico está habilitado.|  
|`maxPendingReceives`|Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.<br /><br /> Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un extremo.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationBehaviorElement>   
 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>