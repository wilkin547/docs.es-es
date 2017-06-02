---
title: "Microsoft.Transactions.TransactionBridge.PreparedMessageRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
Se envió un reintento de mensaje preparado a un coordinador que no responde.  
  
## Descripción  
 Se realiza un seguimiento en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de “preparado” a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.  
  
## Solución de problemas  
 Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos.Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)