---
title: Eventos ETW en Task Parallel Library y PLINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, ETW events
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9e3ff6c4ec8febda93136c5ac88223b5baf80124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="etw-events-in-task-parallel-library-and-plinq"></a>Eventos ETW en Task Parallel Library y PLINQ
Tanto la biblioteca TPL como PLINQ generan eventos ETW (Seguimiento de eventos de Windows) que puede usar para generar perfiles y solucionar problemas de aplicaciones con herramientas como el Analizador de rendimiento de Windows. En cambio, en la mayoría de los escenarios, la mejor forma de generar perfiles del código de aplicación paralelo es usar el [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer) en [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].  
  
## <a name="task-parallel-library-etw-events"></a>Eventos ETW de la biblioteca TPL  
 En la estructura EVENT_HEADER, el GUID ProviderId para los eventos generados por <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> es:  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### <a name="parallel-loop-begin"></a>Comienzo de bucle paralelo  
 EVENT_DESCRIPTOR.Task = 1  
  
 EVENT_DESCRIPTOR.Id = 1  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|OperationType|<xref:System.Int32?displayProperty=nameWithType>|Indica el tipo de bucle:<br /><br /> 1 = ParallelInvoke<br /><br /> 2 = ParallelFor<br /><br /> 3 = ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=nameWithType>|El valor de inicio del contador de bucle|  
|ExclusiveTo|<xref:System.Int64?displayProperty=nameWithType>|El valor final del contador de bucle|  
  
### <a name="parallel-loop-end"></a>Fin de bucle paralelo  
 EVENT_DESCRIPTOR.Task = 2  
  
 EVENT_DESCRIPTOR.Id = 2  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|totalIterations|<xref:System.Int64?displayProperty=nameWithType>|El número total de iteraciones|  
  
### <a name="parallel-invoke-begin"></a>Comienzo de la invocación paralela  
 EVENT_DESCRIPTOR.Task = 3  
  
 EVENT_DESCRIPTOR.Id = 3  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|totalIterations|<xref:System.Int64?displayProperty=nameWithType>|El número total de iteraciones|  
|operationType|<xref:System.Int32?displayProperty=nameWithType>|Indica el tipo de bucle:<br /><br /> 1 = ParallelInvoke<br /><br /> 2 = ParallelFor<br /><br /> 3 = ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=nameWithType>|El número de acciones que se ejecutarán en la invocación paralela.|  
  
### <a name="parallel-invoke-end"></a>Fin de la invocación paralela  
 EVENT_DESCRIPTOR.Task = 4  
  
 EVENT_DESCRIPTOR.Id = 4  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
  
## <a name="plinq-etw-events"></a>Eventos ETW de PLINQ  
 El GUID EVENT_HEADER.ProviderId de PLINQ es:  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### <a name="parallel-query-begin"></a>Comienzo de la consulta paralela  
 EVENT_DESCRIPTOR.Task = 1  
  
 EVENT_DESCRIPTOR.Id = 1  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|QueryID|<xref:System.Int32?displayProperty=nameWithType>|Un identificador de consulta único.|  
  
### <a name="parallel-query-end"></a>Fin de la consulta paralela  
 EVENT_DESCRIPTOR.Task = 2  
  
 EVENT_DESCRIPTOR.Id = 2  
  
#### <a name="user-data"></a>Datos del usuario  
  
|**Nombre**|**ype**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|El identificador del objeto TaskScheduler que ha iniciado el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|El identificador de la tarea que ha iniciado el bucle.|  
|QueryID|<xref:System.Int32?displayProperty=nameWithType>|Un identificador de consulta único.|  
  
## <a name="see-also"></a>Vea también  
 [Eventos ETW en .NET Framework](../../../docs/framework/performance/etw-events.md)  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
