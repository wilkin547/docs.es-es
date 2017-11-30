---
title: "Cómo: Escribir una función de agregado personalizada de PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Cómo: Escribir una función de agregado personalizada de PLINQ
Este ejemplo muestra cómo utilizar el <xref:System.Linq.ParallelEnumerable.Aggregate%2A> método para aplicar una función de agregación personalizada a una secuencia de origen.  
  
> [!WARNING]
>  La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se calcula la desviación estándar de una secuencia de enteros.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 Este ejemplo utiliza una sobrecarga del operador de consulta estándar agregado que sea único en PLINQ. Esta sobrecarga toma un archivo extra <xref:System.Func%603?displayProperty=nameWithType> como tercer parámetro de entrada. Este delegado combina los resultados de todos los subprocesos antes de realizar el cálculo final en los resultados agregados. En este ejemplo se sume las sumas de todos los subprocesos.  
  
 Tenga en cuenta que, cuando un cuerpo de la expresión lambda consta de una única expresión, el valor devuelto de la <xref:System.Func%602?displayProperty=nameWithType> delegado es el valor de la expresión.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
