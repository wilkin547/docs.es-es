---
title: "Parallel Programming in the .NET Framework | Microsoft Docs"
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
  - "parallel programming"
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Parallel Programming in the .NET Framework
Muchos equipos y estaciones de trabajo tienen dos o cuatro núcleos \(es decir, CPU\) que permiten ejecutar varios subprocesos simultáneamente.  Se espera que los equipos en un futuro cercano tengan significativamente más núcleos.  Para aprovecharse del hardware de hoy y del mañana, puede paralelizar el código para distribuir el trabajo entre varios procesadores.  En el pasado, la paralelización requería manipulación de bajo nivel de los subprocesos y bloqueos.  [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] y [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] mejoran la compatibilidad para la programación paralela proporcionando un nuevo runtime, nuevos tipos de biblioteca de clases y nuevas herramientas de diagnóstico.  Estas características simplifican el desarrollo en paralelo, de modo que pueda escribir código paralelo eficaz, específico y escalable de forma natural sin tener que trabajar directamente con subprocesos ni el bloque de subprocesos.  La siguiente ilustración proporciona una información general de alto nivel de la arquitectura de programación paralela en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 ![Arquitectura de programación en paralelo de .NET](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL\_Architecture")  
  
## Temas relacionados  
  
|Tecnología|Descripción|  
|----------------|-----------------|  
|[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Proporciona documentación para la clase <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>, que incluye versiones paralelas de `For` y bucles `ForEach`, y también para la clase <xref:System.Threading.Tasks.Task?displayProperty=fullName>, que representa la manera preferida de expresar las operaciones asincrónicas.|  
|[Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Una implementación paralela de LINQ to Objects que significativamente mejora el rendimiento en muchos casos.|  
|[Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Proporciona vínculos a documentación sobre las clases de colección seguras para subprocesos, tipos de sincronización ligeros y tipos para la inicialización diferida.|  
|[Parallel Diagnostic Tools](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Proporciona vínculos a documentación sobre las ventanas de depurador de Visual Studio para las tareas y las pilas paralelas, y [Visualizador de simultaneidad](../Topic/Concurrency%20Visualizer.md), que está compuesto por un conjunto de vistas en el Generador de perfiles de [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] que puede utilizar para depurar y ajustar el rendimiento de código paralelo.|  
|[Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Describe cómo funcionan los particionadores y cómo configurar particionadores predeterminados o crear nuevos.|  
|[Task Schedulers](../Topic/Task%20Schedulers.md)|Describe cómo funcionan los programadores y cómo se pueden configurar los programadores predeterminados.|  
|[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Proporciona información general sobre expresiones lambda en C\# y Visual Basic, y presenta cómo se utilizan en PLINQ y Task Parallel Library.|  
|[For Further Reading](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Proporciona vínculos a documentación adicional y recursos de ejemplo sobre programación paralela en .NET Framework.|  
  
## Vea también  
 [Patrones para la programación paralela: comprender y aplicar patrones paralelos con .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)   
 [Ejemplos de programación paralela en .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)