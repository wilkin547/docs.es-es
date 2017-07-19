---
title: "Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
El servicio de protocolo WS\-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil.El resultado de la transacción puede estar en duda si el participante vuelve.  
  
## Descripción  
 Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.  
  
## Solución de problemas  
 Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado.El período de tiempo predeterminado es de 180 segundos.Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS\-AT.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)