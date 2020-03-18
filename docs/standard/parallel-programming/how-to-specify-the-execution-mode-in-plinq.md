---
title: 'Cómo: Especificar el modo de ejecución en PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: c602aba6e18f80b007b15cd61dfd2b48a36dd2c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139241"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Cómo: Especificar el modo de ejecución en PLINQ
En este ejemplo se muestra cómo forzar a PLINQ a omitir su heurística predeterminada y paralelizar una consulta, independientemente de la forma de la consulta.  
  
> [!WARNING]
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ está diseñado para aprovechar las oportunidades para la paralelización. Sin embargo, no todas las consultas se beneficiarán de la ejecución en paralelo. Por ejemplo, cuando una consulta contiene un delegado de usuario único que realiza muy poco trabajo, la consulta normalmente se ejecutará con mayor rapidez de forma secuencial. Esto se debe a que la sobrecarga necesaria para habilitar la ejecución en paralelo es más cara que la velocidad con que se obtiene. Por lo tanto, PLINQ no paraleliza automáticamente todas las consultas. Primero examina la forma de la consulta y los diversos operadores que la componen. En función de este análisis, PLINQ en el modo de ejecución predeterminado puede decidir ejecutar algunas o todas las consultas de forma secuencial. Sin embargo, en algunos casos, puede saber más sobre su consulta de lo que PLINQ es capaz de determinar a partir de su análisis. Por ejemplo, puede saber que un delegado es muy caro y que la consulta se beneficiará definitivamente de la paralelización. En tales casos, puede usar el método <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> y especificar el valor <xref:System.Linq.ParallelExecutionMode.ForceParallelism> para indicar a PLINQ que ejecute siempre la consulta de forma paralela.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Corte y pegue este código en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) y llame al método desde `Main`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
