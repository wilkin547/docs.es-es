---
title: Biblioteca de procesamiento paralelo basado en tareas (TPL)
description: Explore la biblioteca TPL, un conjunto de API y tipos públicos para simplificar el proceso de agregar paralelismo y simultaneidad a las aplicaciones en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 5c26799338b46f5f0420c3b082e7d84fade27a26
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830004"
---
# <a name="task-parallel-library-tpl"></a>Biblioteca de procesamiento paralelo basado en tareas (TPL)

La biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) es un conjunto de API y tipos públicos de los espacios de nombres <xref:System.Threading?displayProperty=nameWithType> y <xref:System.Threading.Tasks?displayProperty=nameWithType>. El propósito de la TPL es aumentar la productividad de los desarrolladores simplificando el proceso de agregar paralelismo y simultaneidad a las aplicaciones. La TPL escala el grado de simultaneidad de manera dinámica para usar con mayor eficacia todos los procesadores disponibles. Además, la TPL se encarga de la división del trabajo, la programación de los subprocesos en <xref:System.Threading.ThreadPool>, la compatibilidad con la cancelación, la administración de los estados y otros detalles de bajo nivel. Al utilizar la TPL, el usuario puede optimizar el rendimiento del código mientras se centra en el trabajo para el que el programa está diseñado.  
  
 A partir de .NET Framework 4, la biblioteca TPL es el modo preferido de escribir código multiproceso y en paralelo. Pero no todo el código es adecuado para la paralelización. Por ejemplo, si un bucle realiza solo una cantidad reducida de trabajo en cada iteración o no se ejecuta durante numerosas iteraciones, la sobrecarga de la paralelización puede dar lugar a una ejecución más lenta del código. Además, al igual que cualquier código multiproceso, la paralelización hace que la ejecución del programa sea más compleja. Aunque la TPL simplifica los escenarios de multithreading, recomendamos tener conocimientos básicos sobre conceptos de subprocesamiento, por ejemplo, bloqueos, interbloqueos y condiciones de carrera, para usar la TPL eficazmente.  
  
## <a name="related-articles"></a>Artículos relacionados  
  
|Title|Descripción|  
|-|-|  
|[Paralelismo de datos](data-parallelism-task-parallel-library.md)|Describe cómo crear bucles `for` y `foreach` paralelos (`For` y `For Each` en Visual Basic).|  
|[Programación asincrónica basada en tareas](task-based-asynchronous-programming.md)|Describe cómo crear y ejecutar tareas implícitamente mediante <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> o explícitamente usando objetos <xref:System.Threading.Tasks.Task> directamente.|  
|[Flujo de datos](dataflow-task-parallel-library.md)|Describe cómo utilizar los componentes de flujo de datos de la biblioteca de TPL Dataflow para controlar varias operaciones que deban comunicarse entre sí o procesar datos a medida que estén disponibles.|
|[Problemas potenciales en el paralelismo de datos y tareas](potential-pitfalls-in-data-and-task-parallelism.md)|Describe algunos problemas comunes y cómo evitarlos.|  
|[Parallel LINQ (PLINQ)](introduction-to-plinq.md)|Describe cómo lograr el paralelismo de datos con consultas LINQ.|  
|[Programación en paralelo](index.md)|Nodo de nivel superior de la programación en paralelo de .NET.|  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de programación en paralelo con .NET Core y .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
