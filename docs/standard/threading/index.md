---
title: Subprocesamiento administrado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f2a8792818e837f019403aa84c2c2e98db0b2b89
ms.contentlocale: es-es
ms.lasthandoff: 09/05/2017

---
# <a name="managed-threading"></a>Subprocesamiento administrado
Tanto si va a desarrollar aplicaciones para equipos con uno o varios procesadores, desea que la aplicación proporcione la interacción con mayor capacidad de respuesta con el usuario, incluso si la aplicación actualmente hace otro trabajo. Usar varios subprocesos de ejecución es una de las formas más eficaces de mantener que la aplicación siga respondiendo al usuario y, al mismo tiempo, usar el procesador entre eventos de usuario o durante los mismos. Si bien esta sección presenta los conceptos básicos del subprocesamiento, se centra en los conceptos del subprocesamiento administrado y su uso.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la programación multiprocesos se simplifica significativamente con las clases <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> y <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), clases de colecciones simultáneas nuevas en el espacio de nombres <xref:System.Collections.Concurrent?displayProperty=fullName> y un nuevo modelo de programación basado en el concepto de tareas en lugar de en los subprocesos. Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).  
  
## <a name="in-this-section"></a>En esta sección  
 [Principios básicos del subprocesamiento administrado](../../../docs/standard/threading/managed-threading-basics.md)  
 Proporciona información general sobre el subprocesamiento administrado y describe cuándo usar varios subprocesos.  
  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)  
 Explica cómo crear, iniciar, pausar, reanudar y anular subprocesos.  
  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Describe los niveles de sincronización, cómo evitar interbloqueos y condiciones de carrera, equipos con un procesador y con varios procesadores, además de otros problemas de subprocesamiento.  
  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 Describe las clases administradas que puede usar para sincronizar las actividades de subprocesamientos y los datos de objetos accedidos en distintos subprocesos, y proporciona información general sobre los subprocesos de grupos de subprocesos.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Threading>  
 Contiene clases para usar y sincronizar subprocesos administrados.  
  
 <xref:System.Collections.Concurrent>  
 Contiene clases de colección seguras para usarlas con varios subprocesos.  
  
 <xref:System.Threading.Tasks>  
 Contiene clases para crear y programar tareas de procesamiento simultáneo.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona información genera sobre los dominios de aplicación y de su uso en Common Language Infrastructure.  
  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)  
 Describe las ventajas de rendimiento y el funcionamiento básico de la E/S asincrónica.  
  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Proporciona información general sobre la programación asincrónica.  
  
 [Llamada a métodos sincrónicos de forma asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Explica cómo llamar a métodos en los subprocesos de grupos de subprocesos con características integradas de delegados.  
  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 Describe las bibliotecas de programación en paralelo, las que simplifican el uso de varios subprocesos en las aplicaciones.  
  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Describe un sistema para ejecutar consultas en paralelo a fin de aprovechar los distintos procesadores.

