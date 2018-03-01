---
title: "Cómo: Acelerar cuerpos de bucle pequeños"
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
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fb1c39d3eb2c0b68182f49d8aa5dcc4e652f9215
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-speed-up-small-loop-bodies"></a>Cómo: Acelerar cuerpos de bucle pequeños
Si un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> tiene un cuerpo pequeño, su rendimiento puede ser menor que el del bucle secuencial equivalente, como el bucle [for](~/docs/csharp/language-reference/keywords/for.md) de C# y el bucle [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) de Visual Basic. El menor rendimiento se debe a la sobrecarga implicada en la partición de los datos y al costo de invocar un delegado en cada iteración del bucle. Para abordar estos escenarios, la clase <xref:System.Collections.Concurrent.Partitioner> proporciona el método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, que permite proporcionar un bucle secuencial para el cuerpo del delegado de manera que el delegado solo se invoque una sola vez por partición, en lugar de una vez por cada iteración. Para más información, consulte [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) (Particionadores personalizados para PLINQ y TPL).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 El enfoque que se muestra en este ejemplo resulta útil cuando el bucle realiza una cantidad mínima de trabajo. A medida que el trabajo requiere más procesamiento, probablemente obtendrá un rendimiento igual o mejor usando un bucle <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con el particionador predeterminado.  
  
## <a name="see-also"></a>Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)  
 [Particionadores personalizados para PLINQ y TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
