---
title: "CoordinatorRecoveryLogEntryCorrupt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# CoordinatorRecoveryLogEntryCorrupt
Id: 139  
  
 Gravedad: error  
  
 Categoría: TransactionBridge  
  
## Descripción  
 Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar.Se pueden producir pérdidas de datos como resultado de este error.El evento detalla una lista de id. de transacción, datos de recuperación \(codificados con Base64\), excepción, nombre de proceso e id. de proceso.  
  
## Vea también  
 [Registro de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Referencia general de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)