---
title: Biblioteca de procesamiento paralelo basado en tareas (TPL)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 6785041730a048fb08677dbd054f727e351185d4
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588588"
---
# <a name="task-parallel-library-tpl"></a>Biblioteca de procesamiento paralelo basado en tareas (TPL)
La biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) es un conjunto de API y tipos públicos de los espacios de nombres <xref:System.Threading?displayProperty=nameWithType> y <xref:System.Threading.Tasks?displayProperty=nameWithType>. El propósito de la TPL es aumentar la productividad de los desarrolladores simplificando el proceso de agregar paralelismo y simultaneidad a las aplicaciones. La TPL escala el grado de simultaneidad de manera dinámica para usar con mayor eficacia todos los procesadores disponibles. Además, la TPL se encarga de la división del trabajo, la programación de los subprocesos en <xref:System.Threading.ThreadPool>, la compatibilidad con la cancelación, la administración de los estados y otros detalles de bajo nivel. Al utilizar la TPL, el usuario puede optimizar el rendimiento del código mientras se centra en el trabajo para el que el programa está diseñado.  
  
 A partir de .NET Framework 4, la TPL es el modo preferido de escribir código paralelo y multiproceso. Sin embargo, no todo el código se presta para la paralelización; por ejemplo, si un bucle realiza solo una cantidad reducida de trabajo en cada iteración o no se ejecuta para un gran número de iteraciones, la sobrecarga de la paralelización puede dar lugar a una ejecución más lenta del código. Además, al igual que cualquier código multiproceso, la paralelización hace que la ejecución del programa sea más compleja. Aunque la TPL simplifica los escenarios de multithreading, recomendamos tener conocimientos básicos sobre conceptos de subprocesamiento, por ejemplo, bloqueos, interbloqueos y condiciones de carrera, para usar la TPL eficazmente.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Description|  
|-|-|  
|[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)|Describe cómo crear bucles `for` y `foreach` paralelos (`For` y `For Each` en Visual Basic).|  
|[Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|Describe cómo crear y ejecutar tareas implícitamente mediante <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> o explícitamente usando objetos <xref:System.Threading.Tasks.Task> directamente.|  
|[Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|Describe cómo utilizar los componentes de flujo de datos de la biblioteca de TPL Dataflow para controlar varias operaciones que deban comunicarse entre sí o procesar datos a medida que estén disponibles.|  
|[Usar TPL con otros patrones asincrónicos](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|Describe cómo utilizar la TPL con otros modelos asincrónicos de .NET.|  
|[Problemas potenciales en el paralelismo de datos y tareas](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|Describe algunos problemas comunes y cómo evitarlos.|  
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)|Describe cómo lograr el paralelismo de datos con consultas LINQ.|  
|[Programación en paralelo](../../../docs/standard/parallel-programming/index.md)|Nodo de nivel superior de la programación en paralelo de .NET.|  
  
## <a name="see-also"></a>Vea también

- [Samples for Parallel Programming with the .NET Framework](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) (Ejemplos de programación en paralelo con .NET Framework)
