---
title: Paralelismo de datos (biblioteca TPL)
description: Vea cómo la biblioteca TPL admite el paralelismo de datos para realizar la misma operación simultáneamente en los elementos de una colección o matriz de origen en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, data
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
ms.openlocfilehash: 9d0fe1afef126a9c4f73a74d969d36df27182be9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829380"
---
# <a name="data-parallelism-task-parallel-library"></a>Paralelismo de datos (biblioteca TPL)
El *paralelismo de datos* hace referencia a los escenarios en los que la misma operación se realiza simultáneamente (es decir, en paralelo) en elementos de una colección o matriz de origen. En las operaciones paralelas de datos, se crean particiones de la colección de origen para que varios subprocesos puedan funcionar simultáneamente en segmentos diferentes.  
  
 La biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) admite el paralelismo de datos a través de la clase <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>. Esta clase proporciona las implementaciones paralelas basadas en método de los bucles [for](../../csharp/language-reference/keywords/for.md) y [foreach](../../csharp/language-reference/keywords/foreach-in.md) (`For` y `For Each` en Visual Basic). Se escribe la lógica del bucle para un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> de forma muy similar a como se escribiría un bucle secuencial. No tiene que crear los subprocesos ni poner en la cola los elementos de trabajo. En bucles básicos, no es preciso tomar bloqueos. TPL administra todo el trabajo de bajo nivel. Para obtener información detallada sobre el uso de <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>, descargue el documento [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222) (Patrones de programación en paralelo: descripción y aplicación de los patrones en paralelo con .NET Framework 4). En el siguiente ejemplo de código se muestra un bucle `foreach` simple y su equivalente paralelo.  
  
> [!NOTE]
> En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 Cuando un bucle paralelo se ejecuta, la TPL crea particiones del origen de datos para que el bucle pueda funcionar simultáneamente en varias partes. En segundo plano, el programador de tareas crea particiones de la tarea según los recursos del sistema y la carga de trabajo. Cuando es posible, el programador redistribuye el trabajo entre varios subprocesos y procesadores si se desequilibra la carga de trabajo.  
  
> [!NOTE]
> También puede proporcionar un programador o creador de particiones personalizado. Para más información, consulte [Particionadores personalizados para PLINQ y TPL](custom-partitioners-for-plinq-and-tpl.md) y [Programadores de tareas](xref:System.Threading.Tasks.TaskScheduler).  
  
 Los métodos <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> tienen varias sobrecargas que permiten detener o ejecutar la ejecución de bucles, supervisar el estado del bucle en otros subprocesos, mantener el estado de subprocesos locales, finalizar los objetos de subprocesos locales, controlar el grado de simultaneidad, etc. Los tipos del asistente que habilitan esta funcionalidad son <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions>, <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> y <xref:System.Threading.CancellationTokenSource>.  
  
 Para obtener más información, vea [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222) (Patrones de programación en paralelo: descripción y aplicación de los patrones en paralelo con .NET Framework 4).  
  
 PLINQ admite el paralelismo de datos con sintaxis declarativa o de consulta. Para más información, consulte [Parallel LINQ (PLINQ)](introduction-to-plinq.md) (LINQ en paralelo [PLINQ]).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Cómo: Escribir un bucle Parallel.For sencillo](how-to-write-a-simple-parallel-for-loop.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.For%2A> en cualquier matriz o colección de origen <xref:System.Collections.Generic.IEnumerable%601> indexable.|  
|[Cómo: Escribir un bucle Parallel.ForEach sencillo](how-to-write-a-simple-parallel-foreach-loop.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> en cualquier colección de origen <xref:System.Collections.Generic.IEnumerable%601>.|  
|[Cómo: Detener o interrumpir un bucle Parallel.For](/previous-versions/dotnet/netframework-4.0/dd460721(v=vs.100))|Describe cómo detenerse o salir de un bucle paralelo de forma que todos los subprocesos se informen de la acción.|  
|[Cómo: Escribir un bucle Parallel.For con variables locales de subproceso](how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.For%2A> en el que cada subproceso mantiene una variable privada que no está visible para cualquier otro subproceso y cómo sincronizar los resultados de todos los subprocesos cuando el bucle se completa.|  
|[Cómo: Escribir un bucle Parallel.ForEach con variables locales de partición](how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> en el que cada subproceso mantiene una variable privada que no está visible para cualquier otro subproceso y cómo sincronizar los resultados de todos los subprocesos cuando el bucle se completa.|  
|[Cómo: Cancelar un bucle Parallel.For o ForEach](how-to-cancel-a-parallel-for-or-foreach-loop.md)|Describe cómo cancelar un bucle paralelo utilizando un <xref:System.Threading.CancellationToken?displayProperty=nameWithType>|  
|[Cómo: Acelerar cuerpos de bucle pequeños](how-to-speed-up-small-loop-bodies.md)|Describe una manera de acelerar la ejecución cuando el cuerpo de un bucle es muy pequeño.|  
|[Biblioteca TPL](task-parallel-library-tpl.md)|Proporciona información general sobre la biblioteca TPL.|  
|[Programación en paralelo](index.md)|Presenta la programación paralela en .NET Framework.|  
  
## <a name="see-also"></a>Vea también

- [Programación en paralelo](index.md)
