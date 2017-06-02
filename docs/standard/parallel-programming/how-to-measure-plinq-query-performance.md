---
title: "How to: Measure PLINQ Query Performance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, how to measure performance"
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Measure PLINQ Query Performance
En este ejemplo se muestra cómo usar la clase <xref:System.Diagnostics.Stopwatch> para medir el tiempo que tarda en ejecutarse una consulta PLINQ.  
  
## Ejemplo  
 En este ejemplo se usa un bucle `foreach` vacío \(`For Each` en Visual Basic\) para medir el tiempo que tarda en ejecutarse la consulta.  En el código real, normalmente, el bucle contiene pasos de procesamiento adicionales que aumentan el tiempo de ejecución total de la consulta.  Observe que el cronómetro se inicia justo antes del bucle, porque es en ese momento cuando comienza la ejecución de la consulta.  Si necesita una medición más exacta, puede usar la propiedad `ElapsedTicks` en lugar de `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 El tiempo de ejecución total es una medida útil cuando se prueban implementaciones de consultas, pero no siempre lo dice todo.  Para obtener una vista más detallada y completa de la interacción de los subprocesos de consulta entre sí y con otros procesos en ejecución, use el visualizador de simultaneidad.  Para obtener más información, vea [Visualizador de simultaneidad](../Topic/Concurrency%20Visualizer.md).  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)