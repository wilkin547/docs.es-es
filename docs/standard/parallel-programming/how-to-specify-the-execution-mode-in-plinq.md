---
title: "Cómo: Especificar el modo de ejecución en PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Cómo: Especificar el modo de ejecución en PLINQ
En este ejemplo se muestra cómo forzar a PLINQ a omitir su heurística predeterminada y ejecutar una consulta, independientemente de la forma de la consulta en paralelo.  
  
> [!WARNING]
>  La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ está diseñado para aprovechar las oportunidades para la ejecución en paralelo. Sin embargo, no todas las consultas se beneficiarán de la ejecución en paralelo. Por ejemplo, cuando una consulta contiene un delegado de usuario único que realiza mucho trabajo, la consulta normalmente se ejecutará con mayor rapidez secuencialmente. Esto es porque la sobrecarga necesaria para habilitar la ejecución en paralelo es más cara que la velocidad a la que se obtiene. Por lo tanto, PLINQ no paralelizar automáticamente todas las consultas. Primero examina la forma de la consulta y los diversos operadores que lo componen. En función de este análisis, PLINQ en el modo de ejecución predeterminado puede decidir ejecutar algunos o todos de la consulta de forma secuencial. Sin embargo, en algunos casos puede saber más acerca de la consulta que PLINQ es capaz de determinar su análisis. Por ejemplo, puede saber que un delegado es muy caro, y que la consulta se beneficiará definitivamente de la ejecución en paralelo. En tales casos, puede usar el <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> método y especifique la <xref:System.Linq.ParallelExecutionMode.ForceParallelism> valor para indicar a PLINQ que ejecute siempre la consulta de forma paralela.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Corte y pegue este código en el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) y llame al método desde `Main`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
