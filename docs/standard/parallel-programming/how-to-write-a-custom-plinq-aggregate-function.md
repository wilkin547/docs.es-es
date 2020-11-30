---
title: 'Cómo: Escribir una función de agregado personalizada de PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
ms.openlocfilehash: dc03802c960c0926380d7b7fa44fdf436b8fea89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734262"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Cómo: Escribir una función de agregado personalizada de PLINQ

En este ejemplo se muestra cómo utilizar el método <xref:System.Linq.ParallelEnumerable.Aggregate%2A> para aplicar una función de agregación personalizada a una secuencia de origen.  
  
> [!WARNING]
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se calcula la desviación estándar de una secuencia de enteros.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 Este ejemplo utiliza una sobrecarga del operador de consulta estándar agregado que sea único en PLINQ. Esta sobrecarga adopta un delegado adicional <xref:System.Func%603?displayProperty=nameWithType> como tercer parámetro de entrada. Este delegado combina los resultados de todos los subprocesos antes de realizar el cálculo final de los resultados agregados. En este ejemplo se agregan las sumas de todos los subprocesos.  
  
 Tenga en cuenta que, cuando un cuerpo de expresiones lambda consta de una única expresión, el valor devuelto del delegado <xref:System.Func%602?displayProperty=nameWithType> es el valor de la expresión.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
