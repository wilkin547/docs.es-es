---
title: "How to: Write a Custom PLINQ Aggregate Function | Microsoft Docs"
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
  - "PLINQ queries, how to create aggregate function"
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Write a Custom PLINQ Aggregate Function
En este ejemplo, se muestra cómo utilizar el método <xref:System.Linq.ParallelEnumerable.Aggregate%2A> para aplicar una función de agregación personalizada a una secuencia de origen.  
  
> [!WARNING]
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 En el siguiente ejemplo se calcula la desviación estándar de una secuencia de enteros.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 En este ejemplo se utiliza una sobrecarga del operador de consulta estándar Aggregate, que solo existe en PLINQ.  Esta sobrecarga toma un delegado <xref:System.Func%603?displayProperty=fullName> adicional como tercer parámetro de entrada.  Este delegado combina los resultados de todos los subprocesos antes de realizar el cálculo final en los resultados agregados.  En este ejemplo sumamos las sumas de todos los subprocesos.  
  
 Tenga en cuenta que cuando el cuerpo de una expresión lambda está compuesto por una única expresión, el valor devuelto del delegado <xref:System.Func%602?displayProperty=fullName> es el valor de la expresión.  
  
## Vea también  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)