---
title: "Data Parallelism (Task Parallel Library) | Microsoft Docs"
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
  - "parallelism, data"
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
caps.latest.revision: 25
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 25
---
# Data Parallelism (Task Parallel Library)
El *paralelismo de datos* hace referencia a los escenarios en los que la misma operación se realiza simultáneamente \(es decir, en paralelo\) en elementos de una colección o matriz de origen.  En las operaciones paralelas de datos, se crean particiones de la colección de origen para que varios subprocesos puedan funcionar simultáneamente en segmentos diferentes.  
  
 La biblioteca TPL \(Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas\) admite el paralelismo de datos a través de la clase <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>.  Esta clase proporciona las implementaciones paralelas basadas en método de los bucles [for](../Topic/for%20\(C%23%20Reference\).md) y [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md) \(`For` y `For Each` en Visual Basic\).  Se escribe la lógica del bucle para un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> o <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> de forma muy similar a como se escribiría un bucle secuencial.  No tiene que crear los subprocesos ni poner en la cola los elementos de trabajo.  En bucles básicos, no es preciso tomar bloqueos.  TPL administra todo el trabajo de bajo nivel.  Para obtener información más detallada sobre el uso de <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>, descargue el documento [Patrones para la programación paralela: comprender y aplicar patrones paralelos con .NET Framework 4](http://www.microsoft.com/download/details.aspx?id=19222).  En el siguiente ejemplo de código se muestra un bucle `foreach` simple y su equivalente paralelo.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL.  Si no está familiarizado con las expresiones lambda en C\# o Visual Basic, vea [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 Cuando un bucle paralelo se ejecuta, la TPL crea particiones del origen de datos para que el bucle pueda funcionar simultáneamente en varias partes.  En segundo plano, el programador de tareas crea particiones de la tarea según los recursos del sistema y la carga de trabajo.  Cuando es posible, el programador redistribuye el trabajo entre varios subprocesos y procesadores si se desequilibra la carga de trabajo.  
  
> [!NOTE]
>  También puede proporcionar un programador o creador de particiones personalizado.  Para obtener más información, consulte [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) y [Task Schedulers](../Topic/Task%20Schedulers.md).  
  
 Los métodos <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> tienen varias sobrecargas que permiten detener o ejecutar la ejecución de bucles, supervisar el estado del bucle en otros subprocesos, mantener el estado de subprocesos locales, finalizar los objetos de subprocesos locales, controlar el grado de simultaneidad, etc.  Los tipos de aplicación auxiliar que habilitan esta funcionalidad son <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions>, <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> y <xref:System.Threading.CancellationTokenSource>.  
  
 Para obtener más información, consulte [Patrones de programación en paralelo](http://go.microsoft.com/fwlink/p/?LinkId=265491).  
  
 PLINQ admite el paralelismo de datos con sintaxis declarativa o de consulta.  Para obtener más información, consulte [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.For%2A> en cualquier matriz o colección de origen <xref:System.Collections.Generic.IEnumerable%601> indexable.|  
|[How to: Write a Simple Parallel.ForEach Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> en cualquier colección de origen <xref:System.Collections.Generic.IEnumerable%601>.|  
|[How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/es-es/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)|Describe cómo detenerse o salir de un bucle paralelo de forma que todos los subprocesos se informen de la acción.|  
|[How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.For%2A> en el que cada subproceso mantiene una variable privada que no está visible para cualquier otro subproceso y cómo sincronizar los resultados de todos los subprocesos cuando el bucle se completa.|  
|[How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)|Describe cómo escribir un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> en el que cada subproceso mantiene una variable privada que no está visible para cualquier otro subproceso y cómo sincronizar los resultados de todos los subprocesos cuando el bucle se completa.|  
|[How to: Cancel a Parallel.For or ForEach Loop](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|Describe cómo cancelar un bucle paralelo utilizando un <xref:System.Threading.CancellationToken?displayProperty=fullName>|  
|[How to: Speed Up Small Loop Bodies](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|Describe una manera de acelerar la ejecución cuando el cuerpo de un bucle es muy pequeño.|  
|[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Proporciona información general sobre Task Parallel Library.|  
|[Parallel Programming](../../../docs/standard/parallel-programming/index.md)|Presenta la programación paralela en .NET Framework.|  
  
## Vea también  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)