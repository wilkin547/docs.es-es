---
title: Programación en paralelo en .NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c0ea65b0a61719c85ab1da53bcc99f5d43a3210b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="parallel-programming-in-net"></a>Programación en paralelo en .NET
Muchos equipos y estaciones de trabajo tienen dos o cuatro núcleos (es decir, CPU) que permiten ejecutar varios subprocesos simultáneamente. Se espera que los equipos en un futuro cercano tengan significativamente más núcleos. Para aprovecharse del hardware de hoy y del mañana, puede paralelizar el código para distribuir el trabajo entre varios procesadores. En el pasado, la paralelización requería manipulación de bajo nivel de los subprocesos y bloqueos. [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] y [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] mejoran la compatibilidad para la programación paralela proporcionando un nuevo runtime, nuevos tipos de biblioteca de clases y nuevas herramientas de diagnóstico. Estas características simplifican el desarrollo en paralelo, de modo que pueda escribir código paralelo eficaz, específico y escalable de forma natural sin tener que trabajar directamente con subprocesos ni el bloque de subprocesos. La siguiente ilustración proporciona una información general de alto nivel de la arquitectura de programación paralela en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 ![Arquitectura de programación en paralelo de .NET](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Tecnología|Description|  
|----------------|-----------------|  
|[Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Proporciona documentación para la clase <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, que incluye versiones paralelas de `For` y bucles `ForEach`, y también para la clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, que representa la manera preferida de expresar las operaciones asincrónicas.|  
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Una implementación paralela de LINQ to Objects que significativamente mejora el rendimiento en muchos casos.|  
|[Estructuras de datos para la programación paralela](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Proporciona vínculos a documentación sobre las clases de colección seguras para subprocesos, tipos de sincronización ligeros y tipos para la inicialización diferida.|  
|[Herramientas de diagnóstico paralelo](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Proporciona vínculos a documentación sobre las ventanas de depurador de Visual Studio para las tareas y las pilas paralelas, y [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer), que está compuesto por un conjunto de vistas en el Generador de perfiles de [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] que puede usar para depurar y ajustar el rendimiento de código paralelo.|  
|[Particionadores personalizados para PLINQ y TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Describe cómo funcionan los particionadores y cómo configurar particionadores predeterminados o crear nuevos.|  
|[Programadores de tareas](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Describe cómo funcionan los programadores y cómo se pueden configurar los programadores predeterminados.|  
|[Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Proporciona información general sobre expresiones lambda en C# y Visual Basic, y presenta cómo se utilizan en PLINQ y Task Parallel Library.|  
|[Información adicional](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Proporciona vínculos a documentación adicional y recursos de ejemplo sobre programación paralela en .NET Framework.|  
  
## <a name="see-also"></a>Vea también  
 [Patrones para la programación paralela: comprender y aplicar patrones paralelos con .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222)  
 [Samples for Parallel Programming with the .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) (Ejemplos de programación en paralelo con .NET Framework)
