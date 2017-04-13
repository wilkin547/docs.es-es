---
title: "Extremo: Errores en llamadas por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Extremo: Errores en llamadas por segundo
Nombre del contador: Errores de llamadas por segundo.  
  
## Descripción  
 Número de llamadas que tienen excepciones no controladas y son recibidas por este extremo en un segundo.  
  
 Este es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)  
  
 Este contador se incrementa siempre que se produce una excepción no controlada en este extremo.  
  
## Vea también  
 [Especificación y administración de errores en contratos y servicios](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)