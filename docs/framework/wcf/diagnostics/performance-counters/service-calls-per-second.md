---
title: "Servicio: Llamadas por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Servicio: Llamadas por segundo
Nombre del contador: llamadas por segundo.  
  
## Descripción  
 El número de llamadas por segundo a este servicio.  
  
 Es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la formula siguiente.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\), donde el numerador \(N\) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador \(D\) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.