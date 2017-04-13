---
title: "Managed Threading | Microsoft Docs"
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
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading
Independientemente de si está programando para equipos con un procesador o con varios, deseará que la aplicación proporcione la interacción más rápida posible con el usuario, incluso si ésta está realizando actualmente otro trabajo.  El uso de varios subprocesos de ejecución es una de las formas más eficaces para mantener la respuesta de la aplicación al usuario y, al mismo tiempo, permite utilizar el procesador entre o incluso durante los eventos del usuario.  Aunque esta sección presenta los conceptos básicos del subprocesamiento, se centra en conceptos relacionados con el subprocesamiento administrado y su utilización.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la programación multiproceso se ha simplificado considerablemente con las clases <xref:System.Threading.Tasks.Task?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>, [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), nuevas clases de colección simultáneas en el espacio de nombres <xref:System.Collections.Concurrent?displayProperty=fullName> y un nuevo modelo de programación que está basado en el concepto de tareas en lugar de subprocesos.  Para obtener más información, vea [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## En esta sección  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)  
 Ofrece información general sobre el subprocesamiento administrado y explica cuándo utilizar múltiples subprocesos.  
  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 Explica cómo crear, iniciar, pausar, reanudar y anular subprocesos.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Describe los niveles de sincronización, cómo evitar interbloqueos y condiciones de carrera, equipos multiprocesador y de un solo procesador y otras cuestiones relacionadas con el subprocesamiento.  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)  
 Describe las clases administradas que se pueden utilizar para sincronizar las actividades de subprocesos y el acceso a datos de objetos en distintos subprocesos, y ofrece información general sobre subprocesos del grupo de subprocesos.  
  
## Referencia  
 <xref:System.Threading>  
 Contiene clases para utilizar y sincronizar subprocesos administrados.  
  
 <xref:System.Collections.Concurrent>  
 Contiene clases de colección que son seguras para su uso con varios subprocesos.  
  
 <xref:System.Threading.Tasks>  
 Contiene clases para crear y programar tareas de procesamiento simultáneas.  
  
## Secciones relacionadas  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona información general acerca de los dominios de aplicación y el uso que hace de ellos la infraestructura de Common Language.  
  
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)  
 Describe las ventajas de rendimiento y el funcionamiento básico de la E\/S asincrónica.  
  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Proporciona información general acerca de la programación asincrónica.  
  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Explica cómo llamar a métodos de subprocesos ThreadPool utilizando las características integradas de delegados.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Describe las bibliotecas de programación paralelas, que simplifican el uso de varios subprocesos en aplicaciones.  
  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Describe un sistema para ejecutar consultas en paralelo con el fin de aprovechar la presencia de varios procesadores.