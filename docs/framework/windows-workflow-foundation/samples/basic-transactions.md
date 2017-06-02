---
title: "Transacciones | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
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
---
# Transacciones
Esta sección contiene ejemplos que muestran las transacciones de flujo de trabajo de [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## En esta sección  
 [TransactionScope básico](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Consta de cuatro escenarios que muestran cómo anidar instancias de <xref:System.Activities.Statements.TransactionScope>.  
  
 [Uso de TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Muestra cómo pasar una transacción de un cliente a un servidor utilizando <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir un mensaje con una transacción de flujo y determinar la duración de la transacción en el servidor.  
  
 [Anidamiento de TransactionScope dentro de un servicio](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 Consta de dos escenarios que muestran cómo administrar las instancias de la actividad <xref:System.Activities.Statements.TransactionScope> dentro de un servicio.