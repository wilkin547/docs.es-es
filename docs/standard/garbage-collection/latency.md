---
title: Modos de latencia
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, intrusiveness
- garbage collection, latency modes
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
ms.openlocfilehash: a8eaf0c80aa32978eead80c51a905cbcd66a537b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74283593"
---
# <a name="latency-modes"></a>Modos de latencia

Para reclamar objetos, el recolector de elementos no utilizados (GC) debe detener todos los subprocesos en ejecución en una aplicación. El período de tiempo durante el que está activo el recolector de elementos no utilizados se conoce como su *latencia*.

En algunos casos, como cuando una aplicación recupera datos o muestra contenido, la recolección completa de elementos no utilizados puede producirse en un momento crítico y reducir el rendimiento. Puede ajustar la tendencia a la intrusión del recolector de elementos no utilizados estableciendo la propiedad <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType> en uno de los valores de <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>.

## <a name="low-latency-settings"></a>Configuración de latencia baja

El uso de una configuración de latencia "baja" significa que el recolector de elementos no utilizados interfiere menos en la aplicación. La recolección de elementos no utilizados es más conservadora sobre la recuperación de memoria.

La enumeración <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> proporciona dos opciones de configuración de latencia baja:

- [GCLatencyMode.LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) suprime las recolecciones de generación 2 y realiza solo las recolecciones de generación 0 y 1. Se puede usar solo durante breves períodos de tiempo. En períodos más largos, si la memoria del sistema está bajo presión, el recolector de elementos no utilizados activará una colección que puede pausar brevemente la aplicación e interrumpir una operación crítica en el tiempo. Esta opción está disponible solo para la recopilación de elementos no utilizados de estación de trabajo.

- [GCLatencyMode.SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) suprime las recolecciones de generación 2 de primer plano y realiza solo las recolecciones de generación 0, 1 y las recolecciones de generación 2 de segundo plano. Se puede usar durante periodos más largos de tiempo y está disponible para la recolección de elementos utilizados de estación de trabajo y de servidor. Esta opción de configuración no se puede usar si la recolección de elementos no utilizados en segundo plano está deshabilitada.

Durante los períodos de latencia baja, se suprimen las recolecciones de generación 2 a menos que ocurra lo siguiente:

- El sistema recibe una notificación de memoria insuficiente desde el sistema operativo.

- El código de aplicación induce una recolección mediante una llamada al método <xref:System.GC.Collect%2A?displayProperty=nameWithType> y especifica 2 en el parámetro `generation`.

## <a name="scenarios"></a>Escenarios

En la tabla siguiente se enumeran los escenarios de aplicación en los que se usan los valores de <xref:System.Runtime.GCLatencyMode>:

|Modo de latencia|Escenarios de aplicación|
|------------------|---------------------------|
|<xref:System.Runtime.GCLatencyMode.Batch>|Para las aplicaciones que no tienen interfaz de usuario (UI) u operaciones de servidor.<br /><br />Cuando se deshabilita la recolección de elementos no utilizados en segundo plano, este es el modo predeterminado para la recolección de elementos no utilizados de estación de trabajo y de servidor. El modo <xref:System.Runtime.GCLatencyMode.Batch> también invalida el valor [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), es decir, impide las recolecciones simultáneas o en segundo plano.|
|<xref:System.Runtime.GCLatencyMode.Interactive>|Para la mayoría de las aplicaciones que tienen una interfaz de usuario.<br /><br />Este es el modo predeterminado para la recolección de elementos no utilizados de estación de trabajo y de servidor. Sin embargo, si se hospeda una aplicación, la configuración del recolector de elementos no utilizados del proceso de hospedaje tiene prioridad.|
|<xref:System.Runtime.GCLatencyMode.LowLatency>|Para aplicaciones que tienen operaciones a corto plazo sujetas a limitación temporal durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales. Por ejemplo, las aplicaciones que realizan funciones de adquisición de datos o representación de animación.|
|<xref:System.Runtime.GCLatencyMode.SustainedLowLatency>|Para aplicaciones que tienen operaciones sujetas a limitación temporal con una duración limitada pero posiblemente larga durante las cuales las interrupciones del recolector de elementos no utilizados podrían ser perjudiciales. Por ejemplo, las aplicaciones que necesitan tiempos de respuesta rápidos, como los cambios de los datos del mercado durante las horas de comercio.<br /><br />Este modo produce montón administrado de mayor tamaño que otros modos. Como no compacta el montón administrado, es posible una fragmentación mayor. Asegúrese de que hay suficiente memoria disponible.|

## <a name="guidelines-for-using-low-latency"></a>Directrices para usar una latencia baja

Cuando use el modo [GCLatencyMode.LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency), tenga en cuenta las siguientes instrucciones:

- Haga que el período de tiempo de latencia baja sea lo más corto posible.

- Evite asignar gran cantidad de memoria durante los períodos de latencia baja. Se pueden producir notificaciones de memoria insuficiente porque la recolección de elementos no utilizados reclama menos objetos.

- Mientras esté en modo de latencia baja, minimice el número de asignaciones nuevas, en particular las asignaciones en el montón de objetos grandes y de objetos anclados.

- Tenga en cuenta los subprocesos que podrían estar realizando asignaciones. Como el valor de la propiedad <xref:System.Runtime.GCSettings.LatencyMode%2A> se aplica a todo el proceso, se pueden generar excepciones <xref:System.OutOfMemoryException> en cualquier subproceso que esté realizando asignaciones.

- Ajuste el código de latencia baja en regiones de ejecución restringidas. Para obtener más información, vea [Regiones de ejecución restringidas](../../../docs/framework/performance/constrained-execution-regions.md).

- Para forzar las recolecciones de generación 2 durante un período de latencia baja, llame al método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.GC?displayProperty=nameWithType>
- [Colecciones inducidas](../../../docs/standard/garbage-collection/induced.md)
- [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
