---
title: "Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
El servicio de protocolo WS\-AT recibió un mensaje Prepared o Repay desde un participante volátil desconocido.Se devolvió un error al participante, declara que el resultado de la transacción es dudoso.  
  
## Descripción  
 Se realiza un seguimiento si el Administrador de transacciones local recibe un mensaje Prepared o Replay desde una inscripción volátil de la que ya se ha olvidado.  
  
## Solución de problemas  
 Investigue las causas potenciales de los últimos mensajes que proceden del participante volátil.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)