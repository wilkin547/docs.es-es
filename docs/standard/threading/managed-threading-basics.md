---
title: Principios básicos del subprocesamiento administrado
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: bec769043ab630b37609bed12302ceff5b90474a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139228"
---
# <a name="managed-threading-basics"></a>Principios básicos del subprocesamiento administrado

Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subproceso administrado así como para explicar algunas características básicas. Para obtener información sobre las clases que proporcionan características adicionales, vea [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md) e [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 En el resto de los temas de esta sección se tratan cuestiones más avanzadas, incluida la interacción del subproceso administrado con el sistema operativo Windows.  
  
> [!NOTE]
> En .NET Framework 4, la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso. Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).  
  
## <a name="in-this-section"></a>En esta sección

 [Subprocesos y subprocesamiento](../../../docs/standard/threading/threads-and-threading.md)  
 Se explican las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar subprocesos del grupo de subprocesos.  
  
 [Excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Se describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.  
  
 [Sincronizar datos para subprocesamiento múltiple](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Se describen las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.  
  
 [Subprocesos de primer y segundo plano](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Se explican las diferencias entre los subprocesos en primer y segundo plano.  
  
 [Subprocesamiento administrado y no administrado en Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Se describe la relación entre subprocesos administrados y no administrados, se enumeran los administrados equivalentes para las API de subprocesos de Windows y se describe la interacción entre apartamentos COM y subprocesos administrados.  
  
 [Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Se describen los mecanismos de almacenamiento relacionados con subprocesos.  
  
## <a name="reference"></a>Referencia

 <xref:System.Threading.Thread>  
 Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Proporciona una manera segura de implementar multithreading junto con objetos de interfaz de usuario.  
  
## <a name="related-sections"></a>Secciones relacionadas

 [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Se describen las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.  
  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Se describen los problemas comunes con multithreading y las estrategias para evitar problemas.  
  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 Describe la biblioteca TPL y PLINQ, que simplifican significativamente el trabajo de crear aplicaciones de .NET Framework asincrónicas y multiproceso.
