---
title: 'Cómo: Combinar consultas LINQ paralelas y secuenciales'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 4c04afb23a168a9cff60962bd5a75a65e3ebca4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134192"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Cómo: Combinar consultas LINQ paralelas y secuenciales
Este ejemplo muestra cómo utilizar el método <xref:System.Linq.ParallelEnumerable.AsSequential%2A> para indicar a PLINQ que procese secuencialmente todos los operadores subsiguientes en la consulta. Aunque el procesamiento secuencial es normalmente más lento que el paralelo, a veces es necesario para generar resultados correctos.  
  
> [!WARNING]
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un escenario en el que <xref:System.Linq.ParallelEnumerable.AsSequential%2A> es necesario, concretamente, para conservar el orden que se estableció en una cláusula de la consulta anterior.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar y ejecutar este código, péguelo en el [ejemplo de datos PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto, agregue una línea para llamar al método desde `Main` y presione F5.  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
