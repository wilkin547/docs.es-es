---
title: "Eventos ETW en Task Parallel Library y PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tareas, eventos ETW"
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Eventos ETW en Task Parallel Library y PLINQ
Tanto Task Parallel Library como PLINQ generan eventos ETW \(Seguimiento de eventos de Windows\) que puede utilizar para perfilar y solucionar problemas de aplicaciones con herramientas como el Analizador de rendimiento de Windows.  Sin embargo, en la mayoría de los escenarios, la manera mejor al código de aplicación paralelo profile es utilizar [Visualizador de simultaneidad](../Topic/Concurrency%20Visualizer.md) en [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].  
  
## Eventos ETW de Task Parallel Library  
 En la estructura EVENT\_HEADER, el GUID ProviderId para los eventos generados por <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> e <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName> es:  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### Comienzo de bucle paralelo  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|Indica el tipo de bucle:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=fullName>|El valor de inicio del contador de bucle|  
|ExclusiveTo|<xref:System.Int64?displayProperty=fullName>|El valor final del contador de bucle|  
  
### Fin de bucle paralelo  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|El número total de iteraciones.|  
  
### Comienzo de Invoke paralela  
 EVENT\_DESCRIPTOR.Task \= 3  
  
 EVENT\_DESCRIPTOR.Id \= 3  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|El número total de iteraciones.|  
|operationType|<xref:System.Int32?displayProperty=fullName>|Indica el tipo de bucle:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=fullName>|El número de acciones que se ejecutarán en la invocación paralela.|  
  
### Fin de Invoke paralela  
 EVENT\_DESCRIPTOR.Task \= 4  
  
 EVENT\_DESCRIPTOR.Id \= 4  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|El identificador único que se usa para indicar la anidación y los pares de eventos con semántica de bifurcación o combinación.|  
  
## Eventos ETW de PLINQ  
 El GUID EVENT\_HEADER.ProviderId de PLINQ es:  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### Comienza la consulta paralela  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Un identificador de consulta único.|  
  
### Fin de la consulta paralela  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Datos del usuario  
  
|**Name**|**Tipo**|**Descripción**|  
|--------------|--------------|---------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|El identificador del objeto TaskScheduler que inició el bucle.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|El identificador de la tarea que inició el bucle.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Un identificador de consulta único.|  
  
## Vea también  
 [ETW Events in the .NET Framework](../../../docs/framework/performance/etw-events.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)