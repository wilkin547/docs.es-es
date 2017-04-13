---
title: "PiiLoggingNotAllowed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# PiiLoggingNotAllowed
Id: 108  
  
 Gravedad: error  
  
 Categoría: seguimiento  
  
## Descripción  
 Este evento indica que ningún PII conocido se está registrando.  No se permite el registro de un PII conocido.  Para permitir el registro de un PII conocido, establezca "enableLoggingKnownPii" en `true` en Machine.config.  El evento enumera el nombre y el id. de proceso.  
  
## Vea también  
 [Registro de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Referencia general de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)