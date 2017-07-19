---
title: "Latency Modes | Microsoft Docs"
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
  - "garbage collection, intrusiveness"
  - "garbage collection, latency modes"
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
caps.latest.revision: 41
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 41
---
# Latency Modes
Para reclamar objetos, el recolector de elementos no utilizados debe detener todos los subprocesos en ejecución en una aplicación.  En algunos casos, como cuando una aplicación recupera datos o muestra contenido, la recolección completa de elementos no utilizados puede producirse en un momento crítico y reducir el rendimiento.  Puede ajustar la tendencia a la intrusión del recolector de elementos no utilizados estableciendo la propiedad <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=fullName> en uno de los valores de <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>.  
  
 Latencia es el tiempo que el recolector de elementos no utilizados entra en su aplicación.  Durante los períodos de latencia baja, el recolector de elementos no utilizados es más conservador y menos intrusivo en la reclamación de objetos.  La enumeración <xref:System.Runtime.GCLatencyMode?displayProperty=fullName> proporciona dos opciones de configuración de latencia baja:  
  
-   <xref:System.Runtime.GCLatencyMode> suprime las recolecciones de generación 2 y realiza solo las recolecciones de generación 0 y 1.  Se puede usar solo durante breves períodos de tiempo.  En períodos más largos, si la memoria del sistema está bajo presión, el recolector de elementos no utilizados activará una colección que puede pausar brevemente la aplicación e interrumpir una operación crítica en el tiempo.  Esta opción está disponible solo para la recopilación de elementos no utilizados de estación de trabajo.  
  
-   <xref:System.Runtime.GCLatencyMode> suprime las recolecciones de generación 2 de primer plano y realiza solo las recolecciones de generación 0, 1 y las recolecciones de generación 2 de fondo.  Se puede usar durante periodos más largos de tiempo y está disponible para la recolección de elementos utilizados de estación de trabajo y de servidor.  Esta opción de configuración no se puede usar si la [recolección de elementos no utilizados simultánea](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) está deshabilitada.  
  
 Durante los períodos de latencia baja, se suprimen las recolecciones de generación 2 a menos que ocurra lo siguiente:  
  
-   El sistema recibe una notificación de memoria insuficiente desde el sistema operativo.  
  
-   El código de aplicación induce una recolección mediante una llamada al método <xref:System.GC.Collect%2A?displayProperty=fullName> y especifica 2 en el parámetro `generation`.  
  
 En la tabla siguiente se enumeran los escenarios de aplicación en los que se usan los valores de <xref:System.Runtime.GCLatencyMode>.  
  
|Modo de latencia|Escenarios de aplicación|  
|----------------------|------------------------------|  
|<xref:System.Runtime.GCLatencyMode>|Para las aplicaciones que no tienen interfaz de usuario u operaciones de servidor.<br /><br /> Este es el modo predeterminado cuando la [recolección de elementos no utilizados simultánea](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) está deshabilitada.|  
|<xref:System.Runtime.GCLatencyMode>|Para la mayoría de las aplicaciones que tienen una interfaz de usuario.<br /><br /> Este es el modo predeterminado cuando la [recolección de elementos no utilizados simultánea](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) está habilitada.|  
|<xref:System.Runtime.GCLatencyMode>|Para aplicaciones que tienen operaciones a corto plazo sujetas a limitación temporal durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales.  Por ejemplo, las aplicaciones que realizan funciones de adquisición de datos o representación de animación.|  
|<xref:System.Runtime.GCLatencyMode>|Para aplicaciones que tienen operaciones sujetas a limitación temporal con una duración limitada pero posiblemente larga durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales.  Por ejemplo, las aplicaciones que necesitan tiempos de respuesta rápidos, como los cambios de los datos del mercado durante las horas de comercio.<br /><br /> Este modo produce montón administrado de mayor tamaño que otros modos.  Como no compacta el montón administrado, es posible una fragmentación mayor.  Asegúrese de que hay suficiente memoria disponible.|  
  
## Directrices para usar una latencia baja  
 Cuando use el modo <xref:System.Runtime.GCLatencyMode>, tenga en cuenta las siguientes directrices:  
  
-   Haga que el período de tiempo de latencia baja sea lo más corto posible.  
  
-   Evite asignar gran cantidad de memoria durante los períodos de latencia baja.  Se pueden producir notificaciones de memoria insuficiente porque la recolección de elementos no utilizados reclama menos objetos.  
  
-   Mientras esté en modo de latencia baja, minimice el número de asignaciones que realiza, en particular las asignaciones en el montón de objetos grandes y de objetos anclados.  
  
-   Tenga en cuenta los subprocesos que podrían estar realizando asignaciones.  Como el valor de la propiedad <xref:System.Runtime.GCSettings.LatencyMode%2A> se aplica a todo el proceso, podría generar una <xref:System.OutOfMemoryException> en cualquier subproceso que pueda estar realizando asignaciones.  
  
-   Encapsule el código de latencia baja en regiones de ejecución restringidas \(para obtener más información, consulte [Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)\).  
  
-   Para forzar las recolecciones de generación 2 durante un período de latencia baja, llame al método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.GC?displayProperty=fullName>   
 [Colecciones inducidas](../../../docs/standard/garbage-collection/induced.md)   
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)