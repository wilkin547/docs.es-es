---
title: "Extremo: Flujo de transacciones por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Extremo: Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo.  
  
## Descripción  
 Número de transacciones de flujo a las operaciones en este extremo en un segundo.Este contador se incrementa siempre que se encuentra un id. de transacción en un mensaje enviado al extremo.  
  
 Este contador es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)