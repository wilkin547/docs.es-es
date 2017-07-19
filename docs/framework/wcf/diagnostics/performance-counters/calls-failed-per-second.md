---
title: "Errores de llamadas por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Errores de llamadas por segundo
Nombre de contador: errores de llamadas por segundo  
  
## Descripción  
 Número de llamadas con excepciones no atendidas en esta operación en un segundo.  
  
 Este es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)  
  
 El contador se incrementa siempre que se produce una excepción no controlada en esta operación.  
  
## Vea también  
 [Especificación y administración de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)