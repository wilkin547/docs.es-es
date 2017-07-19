---
title: "Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
El equipo de estado para la inscripción de un participante introdujo el estado finalizado.  
  
## Descripción  
 Seguido cuando una inscripción de participante subordinado ha completado el procesamiento 2pc.Se puede confirmar o anular el resultado de la inscripción.También se sigue si cualquier participante vota ReadOnly durante Prepare.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)