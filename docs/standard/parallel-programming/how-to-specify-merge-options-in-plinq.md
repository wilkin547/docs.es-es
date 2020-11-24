---
title: 'Cómo: Especificar opciones de combinación en PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
ms.openlocfilehash: 91c5ac91538942368b66399bf0bc0132a15bf667
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825603"
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Cómo: Especificar opciones de combinación en PLINQ
En este ejemplo se muestra cómo especificar las opciones de combinación que se aplicarán a todos los operadores subsiguientes en una consulta PLINQ. No es necesario establecer las opciones de combinación explícitamente, pero, en caso de establecerlas, se puede mejorar el rendimiento. Para más información sobre las opciones de combinación, consulte las [opciones de combinación en PLINQ](merge-options-in-plinq.md).  
  
> [!WARNING]
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el comportamiento de las opciones de combinación en un escenario básico que tiene un origen no ordenado y aplica una función cara a cada elemento.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 En casos donde la opción <xref:System.Linq.ParallelMergeOptions.AutoBuffered> incurre en una latencia indeseable antes de que se produzca el primer elemento, pruebe la opción <xref:System.Linq.ParallelMergeOptions.NotBuffered> para proporcionar elementos de resultados más rápido y sin problemas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelMergeOptions>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
