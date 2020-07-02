---
title: Principios básicos del subprocesamiento administrado
description: Vea vínculos a otros artículos de subprocesamiento administrado, que tratan temas tales como las excepciones, la sincronización de datos, los subprocesos en primer plano y en segundo plano, el almacenamiento local, etc.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: d4a4ceabf29bd0f6f537e59ba477f9da686b1ef5
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769098"
---
# <a name="managed-threading-basics"></a>Principios básicos del subprocesamiento administrado

Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subproceso administrado así como para explicar algunas características básicas. Para obtener información sobre las clases que proporcionan características adicionales, vea [Objetos y características de subprocesos](threading-objects-and-features.md) e [Información general sobre los primitivos de sincronización](overview-of-synchronization-primitives.md).  
  
 En el resto de los temas de esta sección se tratan cuestiones más avanzadas, incluida la interacción del subproceso administrado con el sistema operativo Windows.  
  
> [!NOTE]
> En .NET Framework 4, la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso. Para más información, consulte [Programación en paralelo](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>En esta sección

 [Subprocesos y subprocesamiento](threads-and-threading.md)  
 Se explican las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar subprocesos del grupo de subprocesos.  
  
 [Excepciones en subprocesos administrados](exceptions-in-managed-threads.md)  
 Se describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.  
  
 [Sincronizar datos para subprocesamiento múltiple](synchronizing-data-for-multithreading.md)  
 Se describen las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.  
  
 [Subprocesos de primer y segundo plano](foreground-and-background-threads.md)  
 Se explican las diferencias entre los subprocesos en primer y segundo plano.  
  
 [Subprocesamiento administrado y no administrado en Windows](managed-and-unmanaged-threading-in-windows.md)  
 Se describe la relación entre subprocesos administrados y no administrados, se enumeran los administrados equivalentes para las API de subprocesos de Windows y se describe la interacción entre apartamentos COM y subprocesos administrados.  
  
 [Almacenamiento local para el subproceso: Campos estáticos relacionados con subprocesos y ranuras de datos](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Se describen los mecanismos de almacenamiento relacionados con subprocesos.  
  
## <a name="reference"></a>Referencia

 <xref:System.Threading.Thread>  
 Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Proporciona una manera segura de implementar multithreading junto con objetos de interfaz de usuario.  
  
## <a name="related-sections"></a>Secciones relacionadas

 [Información general sobre las primitivas de sincronización](overview-of-synchronization-primitives.md)  
 Se describen las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.  
  
 [Procedimientos recomendados para el subprocesamiento administrado](managed-threading-best-practices.md)  
 Se describen los problemas comunes con multithreading y las estrategias para evitar problemas.  
  
 [Programación en paralelo](../parallel-programming/index.md)  
 Describe la biblioteca TPL y PLINQ, que simplifican significativamente el trabajo de crear aplicaciones de .NET Framework asincrónicas y multiproceso.
