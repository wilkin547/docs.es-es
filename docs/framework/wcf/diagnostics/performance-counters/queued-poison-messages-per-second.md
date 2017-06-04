---
title: "Mensajes dudosos en cola por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Mensajes dudosos en cola por segundo
Nombre de contador: Mensajes dudosos en cola por segundo.  
  
## Descripción  
 Número de mensajes marcados como dudosos por el transporte en cola en este servicio en un segundo.  
  
 Este es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)