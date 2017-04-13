---
title: "Garbage Collection | Microsoft Docs"
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
  - "memory, garbage collection"
  - "garbage collection, automatic memory management"
  - "GC [.NET Framework]"
  - "memory, allocating"
  - "common language runtime, garbage collection"
  - "garbage collector"
  - "cleanup operations"
  - "garbage collection"
  - "memory, releasing"
  - "common language runtime, automatic memory management"
  - "automatic memory management"
  - "runtime, automatic memory management"
  - "runtime, garbage collection"
  - "garbage collection, about"
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: 36
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 36
---
# Garbage Collection
El recolector de elementos no utilizados de .NET Framework administra la asignación y liberación de la memoria de la aplicación.  Cada vez que se crea un objeto nuevo, el Common Language Runtime asigna al objeto memoria del montón administrado.  Siempre que haya espacio de direcciones disponible en el montón nativo, el motor en tiempo de ejecución continúa asignando espacio a los objetos nuevos.  No obstante, la memoria no es infinita.  En ocasiones, el recolector de elementos no utilizados debe realizar una recolección para liberar alguna memoria.  El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección, según las asignaciones que se estén realizando.  Cuando el recolector de elementos no utilizados realiza una recolección, comprueba si en el montón administrado hay objetos que la aplicación ya no utiliza y realiza las operaciones necesarias para reclamar su memoria.  
  
<a name="related_topics"></a>   
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)|Describe cómo funciona la recolección de elementos no utilizados, cómo se asignan los objetos en el montón administrado y otros conceptos básicos.|  
|[Garbage Collection and Performance](../../../docs/standard/garbage-collection/performance.md)|Describe las comprobaciones de rendimiento que se pueden utilizar para diagnosticar los problemas con la recolección de elementos no utilizados y los problemas de rendimiento.|  
|[Colecciones inducidas](../../../docs/standard/garbage-collection/induced.md)|Describe cómo hacer que se produzca una recolección de elementos no utilizados.|  
|[Latency Modes](../../../docs/standard/garbage-collection/latency.md)|Describe los modos que determinan la tendencia a la intrusión de la recolección de elementos no utilizados.|  
|[Optimization for Shared Web Hosting](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Describe cómo optimizar la recolección de elementos no utilizados en servidores compartidos entre varios sitios web pequeños.|  
|[Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md)|Describe cómo se determina cuándo una recolección de elementos no utilizados completa está próxima y cuándo se ha completado.|  
|[Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Describe cómo supervisar el uso de la CPU y la memoria por un dominio de aplicación.|  
|[Weak References](../../../docs/standard/garbage-collection/weak-references.md)|Describe las características que permiten al recolector de elementos no utilizados recoger un objeto y, mientras tanto, permitir que la aplicación tenga acceso a ese objeto.|  
  
## Reference  
 <xref:System.GC?displayProperty=fullName>  
  
 <xref:System.GCCollectionMode?displayProperty=fullName>  
  
 <xref:System.GCNotificationStatus?displayProperty=fullName>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>  
  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>  
  
 <xref:System.IDisposable?displayProperty=fullName>  
  
## Vea también  
 [Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)