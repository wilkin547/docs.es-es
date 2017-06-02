---
title: "How to: Specify the Execution Mode in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use execution mode"
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Specify the Execution Mode in PLINQ
En este ejemplo se muestra cómo forzar a PLINQ a omitir su heurística predeterminada y ejecutar en paralelo una consulta sin tener en cuenta la forma de la consulta.  
  
> [!WARNING]
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ está diseñado para aprovechar las oportunidades para la ejecución en paralelo.  Sin embargo, no todas las consultas se benefician de la ejecución en paralelo.  Por ejemplo, cuando una consulta contiene un delegado de usuario único que hace muy poco trabajo, la consulta normalmente se ejecutará más rápidamente de forma secuencial.  Esto se debe a que la sobrecarga necesaria para habilitar la ejecución en paralelo es más costosa que la velocidad que se obtiene.  Por consiguiente, PLINQ no ejecuta en paralelo cada consulta de forma automática.  Primero examina la forma de la consulta y los diversos operadores que la comprenden.  En función de este análisis, PLINQ en el modo de ejecución predeterminado puede decidir ejecutar algunas consultas o todas ellas secuencialmente.  Sin embargo, en algunos casos puede saber sobre su consulta más de lo que PLINQ puede determinar a partir de su análisis.  Por ejemplo, puede saber que un delegado es muy costoso y que la consulta se beneficiará definitivamente de la ejecución en paralelo.  En esos casos, puede usar el método <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> y especificar el valor <xref:System.Linq.ParallelExecutionMode> para indicar a PLINQ que ejecute siempre la consulta en paralelo.  
  
## Compilar el código  
 Corte y pegue este código en [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) y llame al método desde `Main`.  
  
## Vea también  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)