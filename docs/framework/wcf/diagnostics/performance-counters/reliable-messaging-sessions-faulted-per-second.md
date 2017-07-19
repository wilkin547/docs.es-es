---
title: "Errores en sesiones de mensajer&#237;a de confianza por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Errores en sesiones de mensajer&#237;a de confianza por segundo
Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.  
  
## Descripción  
 Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.  
  
 Este contador es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)