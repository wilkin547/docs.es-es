---
title: "How to: Control Ordering in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to control ordering"
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Control Ordering in a PLINQ Query
En estos ejemplos, se muestra cómo se controla el orden en una consulta PLINQ usando el método de extensión <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
> [!WARNING]
>  Estos ejemplos sirven principalmente para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  
  
## Ejemplo  
 En el siguiente ejemplo se mantiene el orden de la secuencia de origen.  A veces esto resulta necesario, por ejemplo, cuando algunos operadores de consulta necesitan una secuencia de origen ordenada para generar los resultados correctos.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## Ejemplo  
 En el siguiente ejemplo se muestran algunos operadores de consulta cuya secuencia de origen es muy probable que esté ordenada.  Estos operadores pueden funcionar en secuencias no ordenadas, aunque pueden generar resultados inesperados.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample del proyecto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) y presione F5.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo se mantiene el orden en la primera parte de una consulta, cómo se quita el orden para aumentar el rendimiento de una cláusula de combinación y cómo se aplica de nuevo el orden a la secuencia del resultado final.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample del proyecto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) y presione F5.  
  
## Vea también  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)