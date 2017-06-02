---
title: "Flujo de transacciones por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Flujo de transacciones por segundo
Nombre del contador: flujo de transacciones por segundo  
  
## Descripción  
 Número de transacciones en esta operación en un segundo.  Este contador se incrementa cuando se encuentra presente un id. de transacción en un mensaje enviado a la operación.  
  
 Este es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)