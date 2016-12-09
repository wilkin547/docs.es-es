---
title: Modos de latencia
description: Modos de latencia
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 810bd8be-5a48-42c6-b080-3afdb31fc61b
translationtype: Human Translation
ms.sourcegitcommit: de0dab146fc811e895dc32f98f877db5e757f82b
ms.openlocfilehash: 6976bb49e9124a787abb1c0a2791cda86dac1007

---

# <a name="latency-modes"></a>Modos de latencia

Para reclamar objetos, el recolector de elementos no utilizados debe detener todos los subprocesos en ejecución en una aplicación. En algunos casos, como cuando una aplicación recupera datos o muestra contenido, la recolección completa de elementos no utilizados puede producirse en un momento crítico y reducir el rendimiento. Puede ajustar la tendencia a la intrusión del recolector de elementos no utilizados. Para ello, establezca la propiedad [GCSettings.LatencyMode](xref:System.Runtime.GCSettings.LatencyMode) en uno de los valores de [System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode). 

Latencia es el tiempo que el recolector de elementos no utilizados entra en su aplicación. Durante los períodos de latencia baja, el recolector de elementos no utilizados es más conservador y menos intrusivo en la reclamación de objetos. La enumeración [System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode) proporciona dos opciones de configuración de latencia baja:

* [LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) suprime las recolecciones de generación 2 y realiza solo las recolecciones de generación 0 y 1. Se puede usar solo durante breves períodos de tiempo. En períodos más largos, si la memoria del sistema está bajo presión, el recolector de elementos no utilizados activará una colección que puede pausar brevemente la aplicación e interrumpir una operación crítica en el tiempo. Esta opción está disponible solo para la recopilación de elementos no utilizados de estación de trabajo. 

* [SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) suprime las recolecciones de generación 2 de primer plano y realiza solo las recolecciones de generación 0, 1 y las recolecciones de generación 2 de segundo plano. Se puede usar durante periodos más largos de tiempo y está disponible para la recolección de elementos utilizados de estación de trabajo y de servidor. Esta opción de configuración no se puede usar si la [recolección de elementos no utilizados simultánea](https://msdn.microsoft.com/library/yhwwzef8.aspx) está deshabilitada.

Durante los períodos de latencia baja, se suprimen las recolecciones de generación 2 a menos que ocurra lo siguiente:

* El sistema recibe una notificación de memoria insuficiente desde el sistema operativo.

* El código de aplicación induce una recolección mediante una llamada al método [GC.Collect](xref:System.GC.Collect(System.Int32)) y la especificación de 2 en el parámetro de generación.

En la tabla siguiente se enumeran los escenarios de aplicación en los que se usan los valores de [GCLatencyMode](xref:System.Runtime.GCLatencyMode).

Modo de latencia | Escenarios de aplicación
------------ | --------------------- 
[Batch](xref:System.Runtime.GCLatencyMode.Batch) | Para las aplicaciones que no tienen interfaz de usuario u operaciones de servidor. Este es el modo predeterminado cuando la [recolección de elementos no utilizados simultánea](https://msdn.microsoft.com/library/yhwwzef8.aspx) está deshabilitada.
[Interactive](xref:System.Runtime.GCLatencyMode.Interactive) | Para la mayoría de las aplicaciones que tienen una interfaz de usuario. Para las aplicaciones que no tienen interfaz de usuario u operaciones de servidor. Este es el modo predeterminado cuando la [recolección de elementos no utilizados simultánea](https://msdn.microsoft.com/library/yhwwzef8.aspx) está habilitada.
[LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) | Para aplicaciones que tienen operaciones a corto plazo sujetas a limitación temporal durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales. Por ejemplo, las aplicaciones que realizan funciones de adquisición de datos o representación de animación.
[SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) | Para aplicaciones que tienen operaciones sujetas a limitación temporal con una duración limitada pero posiblemente larga durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales. Por ejemplo, las aplicaciones que necesitan tiempos de respuesta rápidos, como los cambios de los datos del mercado durante las horas de comercio.   Este modo produce montón administrado de mayor tamaño que otros modos. Como no compacta el montón administrado, es posible una fragmentación mayor. Asegúrese de que hay suficiente memoria disponible.
 
## <a name="guidelines-for-using-low-latency"></a>Directrices para usar una latencia baja

Cuando use el modo [LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency), tenga en cuenta las siguientes instrucciones:

* Haga que el período de tiempo de latencia baja sea lo más corto posible.

* Evite asignar gran cantidad de memoria durante los períodos de latencia baja. Se pueden producir notificaciones de memoria insuficiente porque la recolección de elementos no utilizados reclama menos objetos. 

* Mientras esté en modo de latencia baja, minimice el número de asignaciones que realiza, en particular las asignaciones en el montón de objetos grandes y de objetos anclados. 

* Tenga en cuenta los subprocesos que podrían estar realizando asignaciones. Como el valor de la propiedad [LatencyMode](xref:System.Runtime.GCSettings.LatencyMode) se aplica a todo el proceso, podría generar una excepción [OutOfMemoryException](xref:System.OutOfMemoryException) en cualquier subproceso que pueda estar realizando asignaciones. 

* Para forzar las recolecciones de generación 2 durante un período de latencia baja, llame al método [GC.Collect(Int32, GCCollectionMode)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode)).

## <a name="see-also"></a>Vea también

[System.GC](xref:System.GC)

[Colecciones inducidas](induced.md)

[Recolección de elementos no utilizados en .NET](index.md)



<!--HONumber=Nov16_HO3-->


