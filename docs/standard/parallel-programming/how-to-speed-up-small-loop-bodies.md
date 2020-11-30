---
title: 'Cómo: Acelerar cuerpos de bucle pequeños'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 2597e37ed5901d704c94ff960bcb4b2c97633392
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722410"
---
# <a name="how-to-speed-up-small-loop-bodies"></a>Cómo: Acelerar cuerpos de bucle pequeños

Si un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> tiene un cuerpo pequeño, su rendimiento puede ser menor que el del bucle secuencial equivalente, como el bucle [for](../../csharp/language-reference/keywords/for.md) de C# y el bucle [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) de Visual Basic. El menor rendimiento se debe a la sobrecarga implicada en la partición de los datos y al costo de invocar un delegado en cada iteración del bucle. Para abordar estos escenarios, la clase <xref:System.Collections.Concurrent.Partitioner> proporciona el método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, que permite proporcionar un bucle secuencial para el cuerpo del delegado de manera que el delegado solo se invoque una sola vez por partición, en lugar de una vez por cada iteración. Para más información, consulte [Custom Partitioners for PLINQ and TPL](custom-partitioners-for-plinq-and-tpl.md) (Particionadores personalizados para PLINQ y TPL).  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 El enfoque que se muestra en este ejemplo resulta útil cuando el bucle realiza una cantidad mínima de trabajo. A medida que el trabajo requiere más procesamiento, probablemente obtendrá un rendimiento igual o mejor usando un bucle <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con el particionador predeterminado.  
  
## <a name="see-also"></a>Vea también

- [Data Parallelism](data-parallelism-task-parallel-library.md) (Paralelismo de datos)
- [Particionadores personalizados para PLINQ y TPL](custom-partitioners-for-plinq-and-tpl.md)
- [Iteradores (C#)](../../csharp/programming-guide/concepts/iterators.md)
- [Iteradores (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md)
- [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md)
