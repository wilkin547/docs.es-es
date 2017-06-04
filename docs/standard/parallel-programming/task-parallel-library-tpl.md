---
title: "Task Parallel Library (TPL) | Microsoft Docs"
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
  - ".NET, concurrency in"
  - ".NET, parallel programming in"
  - "Parallel Programming"
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
caps.latest.revision: 37
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 37
---
# Task Parallel Library (TPL)
La biblioteca TPL \(Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas\) es un conjunto de API y tipos públicos de los espacios de nombres <xref:System.Threading?displayProperty=fullName> y <xref:System.Threading.Tasks?displayProperty=fullName>.  El propósito de la TPL es aumentar la productividad de los desarrolladores simplificando el proceso de agregar paralelismo y simultaneidad a las aplicaciones.  La TPL escala el grado de simultaneidad de manera dinámica para usar con mayor eficacia todos los procesadores disponibles.  Además, la TPL se encarga de la división del trabajo, la programación de los subprocesos en <xref:System.Threading.ThreadPool>, la compatibilidad con la cancelación, la administración de los estados y otros detalles de bajo nivel.  Al utilizar la TPL, el usuario puede optimizar el rendimiento del código mientras se centra en el trabajo para el que el programa está diseñado.  
  
 A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], la TPL es el modo preferido de escribir código paralelo y multiproceso.  Sin embargo, no todo el código se presta para la paralelización; por ejemplo, si un bucle realiza solo una cantidad reducida de trabajo en cada iteración o no se ejecuta para un gran número de iteraciones, la sobrecarga de la paralelización puede dar lugar a una ejecución más lenta del código.  Además, al igual que cualquier código multiproceso, la paralelización hace que la ejecución del programa sea más compleja.  Aunque la TPL simplifica los escenarios de multithreading, recomendamos tener conocimientos básicos sobre conceptos de subprocesamiento, por ejemplo, bloqueos, interbloqueos y condiciones de carrera, para usar la TPL eficazmente.  
  
## Temas relacionados  
  
|||  
|-|-|  
|Título|Descripción|  
|[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|Describe cómo crear bucles `for` y `foreach` paralelos \(`For` y `For Each` en Visual Basic\).|  
|[Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|Describe cómo crear y ejecutar tareas implícitamente mediante <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName> o explícitamente usando objetos <xref:System.Threading.Tasks.Task> directamente.|  
|[Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|Describe cómo utilizar los componentes de flujo de datos de la biblioteca de TPL Dataflow para controlar varias operaciones que deban comunicarse entre sí o procesar datos a medida que estén disponibles.|  
|[Using TPL with Other Asynchronous Patterns](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|Describe cómo utilizar la TPL con otros modelos asincrónicos de .NET.|  
|[Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|Describe algunos problemas comunes y cómo evitarlos.|  
|[Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Describe cómo lograr el paralelismo de datos con consultas LINQ.|  
|[Parallel Programming](../../../docs/standard/parallel-programming/index.md)|Nodo de nivel superior de la programación en paralelo de .NET.|  
  
## Vea también  
 [Ejemplos de programación paralela en .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)