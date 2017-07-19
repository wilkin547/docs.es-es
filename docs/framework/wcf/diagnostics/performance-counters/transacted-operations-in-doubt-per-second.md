---
title: "Operaciones de transacci&#243;n dudosas por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Operaciones de transacci&#243;n dudosas por segundo
Nombre del contador: Operaciones de transacción en duda por segundo.  
  
## Descripción  
 El número de operaciones de transacción con un resultado en duda en este servicio en un segundo.  
  
 Este contador es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)