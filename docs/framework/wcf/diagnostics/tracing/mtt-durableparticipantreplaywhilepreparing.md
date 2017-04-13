---
title: "Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
El servicio de protocolo WS\-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar.Por consiguiente, se anuló la transacción.  
  
## Descripción  
 Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando.Se trata de un mensaje no válido para este estado y se va a anular la transacción.  
  
## Solución de problemas  
 Recibir este error puede indicar que un participante duradero \(incluidos los administradores de transacciones subordinados\) se ha recuperado del error, aunque no se sabe a ciencia cierta el resultado de la transacción y solicita su estado.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)