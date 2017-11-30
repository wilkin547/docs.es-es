---
title: "Principios básicos del subprocesamiento administrado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>Principios básicos del subprocesamiento administrado
Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subprocesamiento administrado así como para explicar algunas características básicas. Para obtener información sobre las clases que proporcionan características adicionales, consulte [objetos y características](../../../docs/standard/threading/threading-objects-and-features.md) y [información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 El resto de los temas de esta sección se tratan temas más avanzados, incluida la interacción del subprocesamiento administrado con el sistema operativo Windows.  
  
> [!NOTE]
>  En el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y los datos en programas multiproceso. Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).  
  
## <a name="in-this-section"></a>En esta sección  
 [Subprocesos y subprocesamiento](../../../docs/standard/threading/threads-and-threading.md)  
 Explica las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar el grupo de subprocesos.  
  
 [Excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.  
  
 [Sincronizar datos para subprocesamiento múltiple](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Describe las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.  
  
 [Estados de subprocesos administrados](../../../docs/standard/threading/managed-thread-states.md)  
 Describe los Estados de subprocesos básicos y explica cómo detectar si un subproceso se está ejecutando.  
  
 [Subprocesos de primer y segundo plano](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Explica las diferencias entre los subprocesos de primer plano y fondo.  
  
 [Subprocesamiento administrado y no administrado en Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Describe la relación entre subprocesos administrados y no administrados, enumera los administrados equivalentes para las API de subprocesamiento de Windows y describe la interacción entre apartamentos COM y subprocesos administrados.  
  
 [Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Describe la colección de elementos no utilizados y de suspensión del subproceso.  
  
 [Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Describe los mecanismos de almacenamiento relacionados con subprocesos.  
  
 [Cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Describe las operaciones sincrónicas asincrónicas o de ejecución prolongada puede cancelarse mediante el uso de un token de cancelación.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Threading.Thread>  
 Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Proporciona una manera segura para implementar multithreading junto con objetos de interfaz de usuario.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)  
 Describe las clases administradas que se usa para sincronizar las actividades de varios subprocesos.  
  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Describe los problemas comunes con subprocesamiento múltiple y estrategias para evitar problemas.  
  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 Describe las Task Parallel Library y PLINQ, que simplifican considerablemente el trabajo de creación de aplicaciones de .NET Framework asincrónicas y multiproceso.
