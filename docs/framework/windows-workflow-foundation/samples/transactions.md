---
title: "Transacciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Transacciones
Esta sección contiene ejemplos que muestran escenarios que utilizan transacciones de flujo de trabajo en [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## En esta sección  
 [Ejecutar un flujo de trabajo en un objeto TransactionScope imperativo](../../../../docs/framework/windows-workflow-foundation/samples/execute-a-workflow-in-an-imperative-transactionscope.md)  
 Muestra cómo ejecutar un flujo de trabajo utilizando <xref:System.Activities.WorkflowInvoker> en un objeto <xref:System.Transactions.Transaction> con código C\# imperativo.  
  
 [Ámbito de convoy de transacción](../../../../docs/framework/windows-workflow-foundation/samples/transaction-convoy-scope.md)  
 Muestra cómo crear un modelo de actividad de mensajería de convoy paralelo junto con un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> para modelar un protocolo donde varias operaciones pueden suceder en cualquier orden y todas en la misma transacción.  
  
 [Revertir una transacción](../../../../docs/framework/windows-workflow-foundation/samples/transaction-rollback.md)  
 Muestra cómo crear un objeto <xref:System.Activities.NativeActivity> personalizado que tenga acceso al ambiente <xref:System.Activities.RuntimeTransactionHandle> para obtener la transacción ambiente y deshacerla explícitamente.  
  
 [Suprimir el ámbito de transacción](../../../../docs/framework/windows-workflow-foundation/samples/suppress-transaction-scope.md)  
 Muestra cómo crear una actividad `SuppressTransactionScope` personalizada para suprimir la transacción en tiempo de ejecución ambiente, si está presente.  
  
 [Colas de transacción](../../../../docs/framework/windows-workflow-foundation/samples/transacted-queues.md)  
 Muestra cómo integrar colas y transacciones en [!INCLUDE[wf1](../../../../includes/wf1-md.md)] para crear servicios escalables y fiables.