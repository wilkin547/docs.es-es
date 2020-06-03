---
title: Programación en paralelo en .NET
ms.date: 09/12/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
ms.openlocfilehash: 7adc37374876ebe4dd47e30afa06b5199f34dad5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290699"
---
# <a name="parallel-programming-in-net"></a>Programación en paralelo en .NET

Muchos equipos y estaciones de trabajo personales tienen varios núcleos de CPU que permiten ejecutar múltiples subprocesos simultáneamente. Para aprovecharse del hardware, puede paralelizar el código para distribuir el trabajo entre varios procesadores.

En el pasado, la paralelización requería manipulación de bajo nivel de los subprocesos y bloqueos. Visual Studio y .NET Framework mejoran la compatibilidad para la programación paralela proporcionando un tiempo de ejecución, tipos de biblioteca de clases y herramientas de diagnóstico. Estas características, que se presentaron con .NET Framework 4, simplifican el desarrollo en paralelo. Puede escribir código paralelo eficaz, específico y escalable de forma natural sin tener que trabajar directamente con subprocesos ni el bloque de subprocesos.

La siguiente ilustración proporciona una información general de alto nivel de la arquitectura de programación paralela en .NET Framework:

![Arquitectura de programación en paralelo de .NET](./media/tpl-architecture.png)

## <a name="related-topics"></a>Temas relacionados

|Tecnología|Descripción|
|----------------|-----------------|
|[Biblioteca TPL](task-parallel-library-tpl.md)|Proporciona documentación para la clase <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, que incluye versiones paralelas de `For` y bucles `ForEach`, y también para la clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, que representa la manera preferida de expresar las operaciones asincrónicas.|
|[Parallel LINQ (PLINQ)](introduction-to-plinq.md)|Una implementación paralela de LINQ to Objects que significativamente mejora el rendimiento en muchos casos.|
|[Estructuras de datos para la programación paralela](data-structures-for-parallel-programming.md)|Proporciona vínculos a documentación sobre las clases de colección seguras para subprocesos, tipos de sincronización ligeros y tipos para la inicialización diferida.|
|[Herramientas de diagnóstico paralelo](parallel-diagnostic-tools.md)|Proporciona vínculos a documentación sobre las ventanas del depurador de Visual Studio para las tareas y pilas paralelas y para el [visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).|
|[Particionadores personalizados para PLINQ y TPL](custom-partitioners-for-plinq-and-tpl.md)|Describe cómo funcionan los particionadores y cómo configurar particionadores predeterminados o crear nuevos.|
|[Programadores de tareas](xref:System.Threading.Tasks.TaskScheduler)|Describe cómo funcionan los programadores y cómo se pueden configurar los programadores predeterminados.|
|[Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md)|Proporciona información general sobre expresiones lambda en C# y Visual Basic, y presenta cómo se utilizan en PLINQ y Task Parallel Library.|
|[Información adicional](for-further-reading-parallel-programming.md)|Proporciona vínculos a información adicional y recursos de ejemplo para programación paralela en .NET.|

## <a name="see-also"></a>Vea también

- [Información general de Async](../async.md)
- [Subprocesamiento administrado](../threading/index.md)
