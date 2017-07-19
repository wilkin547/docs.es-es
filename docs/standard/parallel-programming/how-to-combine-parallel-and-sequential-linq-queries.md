---
title: "How to: Combine Parallel and Sequential LINQ Queries | Microsoft Docs"
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
  - "parallel queries, combine parallel and sequential"
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Combine Parallel and Sequential LINQ Queries
En este ejemplo, se muestra cómo usar el método <xref:System.Linq.ParallelEnumerable.AsSequential%2A> para indicar a PLINQ que procese secuencialmente todos los operadores posteriores de la consulta.  Aunque el procesamiento secuencial es por lo general más lento que el procesamiento en paralelo, a veces es necesario para generar resultados correctos.  
  
> [!WARNING]
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra un escenario en el que se requiere <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, a saber, para conservar el orden que se estableció en una cláusula anterior de la consulta.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## Compilar el código  
 Para compilar y ejecutar este código, péguelo en el proyecto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md), agregue una línea para llamar al método desde `Main` y, a continuación, presione F5.  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)