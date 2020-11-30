---
title: Colecciones inducidas
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
ms.openlocfilehash: 25e94221355569931a31b566a53434cbed9ea93f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714242"
---
# <a name="induced-collections"></a>Colecciones inducidas

En la mayoría de los casos, el recolector de elementos no utilizados puede determinar cuál es el mejor momento para realizar una recolección y se debe permitir su ejecución de forma independiente. Hay ocasiones excepcionales en que una recolección forzada puede mejorar el rendimiento de la aplicación. En estos casos, se puede inducir la recolección de elementos no utilizados utilizando el método <xref:System.GC.Collect%2A?displayProperty=nameWithType> para forzar una recolección de elementos no utilizados.  
  
 Use el método <xref:System.GC.Collect%2A?displayProperty=nameWithType> cuando haya una reducción significativa de la cantidad de memoria que se está usando en un punto específico del código de la aplicación. Por ejemplo, si la aplicación utiliza un cuadro de diálogo complejo que tiene varios controles, llamar a <xref:System.GC.Collect%2A> cuando se cierra el cuadro de diálogo podría mejorar el rendimiento porque reclama inmediatamente la memoria que usa este. Asegúrese de que la aplicación no induce la recolección de elementos no utilizados con demasiada frecuencia, ya que este hecho puede reducir el rendimiento si el recolector de elementos no utilizados intenta reclamar objetos en el momento inadecuado. Puede proporcionar un valor de enumeración <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType> al método <xref:System.GC.Collect%2A> para recopilarlo solo cuando la recolección sea productiva, como se explica en la sección siguiente.  
  
## <a name="gc-collection-mode"></a>Modo de colección de GC  

 Puede usar una de las sobrecargas del método <xref:System.GC.Collect%2A?displayProperty=nameWithType>, que incluye un valor <xref:System.GCCollectionMode> para especificar el comportamiento de una colección forzada, como se indica a continuación.  
  
|Valor de `GCCollectionMode`|Description|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|Usa el valor predeterminado de la recolección de elementos no utilizados para la versión de .NET en ejecución.|  
|<xref:System.GCCollectionMode.Forced>|Obliga a que la recolección de elementos no utilizados se produzca inmediatamente. Esto equivale a llamar a la sobrecarga <xref:System.GC.Collect?displayProperty=nameWithType>. Tiene como consecuencia una recolección completa de bloqueo de todas las generaciones.<br /><br /> También puede compactar el montón de objetos grandes si establece la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> en <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> antes de forzar una recolección de elementos no utilizados de bloqueo completa inmediata.|  
|<xref:System.GCCollectionMode.Optimized>|Permite al recolector de elementos no utilizados determinar si la hora actual es la adecuada para reclamar objetos.<br /><br /> El recolector de elementos no utilizados puede determinar que una recolección no esté justificada por su insuficiente productividad, en cuyo caso volverá sin reclamar objetos.|  
  
## <a name="background-or-blocking-collections"></a>Colecciones de fondo o de bloqueo  

 Puede llamar a la sobrecarga del método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType> para especificar si una recolección inducida se está bloqueando o no. El tipo de colección realizado depende de una combinación de los parámetros `mode` y `blocking` del método. `mode` es un miembro de la enumeración <xref:System.GCCollectionMode> y `blocking` es un valor <xref:System.Boolean>. En la tabla siguiente se resume la interacción de los argumentos `mode` y `blocking`.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> o <xref:System.GCCollectionMode.Default>|Se realiza una recolección de bloqueo lo antes posible. Si una colección en segundo plano está en curso y la generación es 0 o 1, el método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> desencadena inmediatamente una colección de bloqueo y vuelve cuando la colección finaliza. Si una colección en segundo plano está en curso y el parámetro `generation` es 2, el método espera hasta que finaliza la colección en segundo plano, desencadena una generación de bloqueo 2 y luego vuelve.|Se realiza una recolección lo antes posible. El método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> solicita una colección en segundo plano, pero esto no se garantiza; puede que aún se realice una colección de bloqueo, dependiendo de las circunstancias. Si una colección en segundo plano ya está en curso, el método vuelve inmediatamente.|  
|<xref:System.GCCollectionMode.Optimized>|Se puede realizar una recolección de bloqueo, dependiendo del estado del recolector de elementos no utilizados y del parámetro `generation`. El recolector de elementos no utilizados intenta proporcionar un rendimiento óptimo.|Se puede realizar una recolección, según el estado del recolector de elementos no utilizados. El método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> solicita una colección en segundo plano, pero esto no se garantiza; puede que aún se realice una colección de bloqueo, dependiendo de las circunstancias. El recolector de elementos no utilizados intenta proporcionar un rendimiento óptimo. Si una colección en segundo plano ya está en curso, el método vuelve inmediatamente.|  
  
## <a name="see-also"></a>Vea también

- [Modos de latencia](latency.md)
- [Recolección de elementos no utilizados](index.md)
