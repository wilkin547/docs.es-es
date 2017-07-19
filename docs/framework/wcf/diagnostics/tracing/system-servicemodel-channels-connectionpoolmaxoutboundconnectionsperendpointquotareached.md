---
title: "Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
El servicio de protocolo WS\-AT no pudo dar de alta en una transacción con el contexto de coordinación proporcionado.  
  
## Descripción  
 Se realiza un seguimiento cuando MSDTC no puede dar de alta en una transacción para un protocolo 2pc concreto.Esto puede ocurrir porque la transacción ya no existe, no se permite dar de alta ya o hay demasiadas inscripciones presentes.  
  
## Solución de problemas  
 Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.  
  
## Vea también  
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)