---
title: "How to: Specify Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use merge options"
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Specify Merge Options in PLINQ
En este ejemplo se muestra cómo especificar las opciones de combinación que se aplicarán a todos los operadores subsiguientes en una consulta PLINQ.  No tiene que establecer las opciones de combinación explícitamente, pero, si lo hace, puede mejorar rendimiento.  Para obtener más información acerca de las opciones de combinación, vea [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra el comportamiento de las opciones de combinación en un escenario básico que tiene un origen no ordenado y aplica una función que utiliza muchos recursos a cada elemento.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 Cuando la opción <xref:System.Linq.ParallelMergeOptions> incurre en una latencia no deseable antes de proporcionar el primer elemento, pruebe la opción <xref:System.Linq.ParallelMergeOptions> para proporcionar elementos del resultado de una manera más rápida y sencilla.  
  
## Vea también  
 <xref:System.Linq.ParallelMergeOptions>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)