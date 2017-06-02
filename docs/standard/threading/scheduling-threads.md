---
title: "Scheduling Threads | Microsoft Docs"
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
  - "threading [.NET Framework], scheduling"
  - "scheduling threads"
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Scheduling Threads
Cada subproceso tiene asignada una prioridad.  Inicialmente, a los subprocesos creados en Common Language Runtime se les asignan la prioridad **ThreadPriority.Normal**.  Los subprocesos creados fuera del motor en tiempo de ejecución mantienen la prioridad que tenían antes de entrar en el entorno administrado.  Con la propiedad **Thread.Priority**, puede obtener o establecer la prioridad de cualquier subproceso.  
  
 La ejecución de los subprocesos se planea en función de su prioridad.  Aunque los subprocesos se ejecuten dentro del motor en tiempo de ejecución, el sistema operativo asigna espacios de tiempo de procesador a todos los subprocesos.  Los detalles del algoritmo utilizado para determinar el orden en el que se ejecutan los subprocesos varían con cada sistema operativo.  En algunos sistemas operativos, el subproceso de mayor prioridad \(o aquellos subprocesos que pueden ejecutarse\) se programa siempre para ejecutarse primero.  Si hay disponibles varios subprocesos con la misma prioridad, el programador recorre los subprocesos con dicha prioridad y les concede a cada uno un espacio de tiempo fijo durante el que ejecutarse.  Siempre que esté disponible un subproceso de mayor prioridad para ejecutarse, no se ejecutan los subprocesos de menor prioridad.  Cuando no hay más subprocesos ejecutables con una prioridad dada, el programador pasa a la siguiente prioridad y programa los subprocesos de dicha prioridad para ejecutarse.  Si un subproceso de prioridad superior pasa a poder ejecutarse, se adelanta al subproceso de menor prioridad y se permite al subproceso de mayor prioridad volver a ejecutarse una vez más.  Sobre todo, el sistema operativo puede ajustar también prioridades de subprocesos de forma dinámica cuando una interfaz de usuario de aplicación pasa a ejecutarse de primer a segundo plano.  Otros sistemas operativos podrían usar un algoritmo de programación diferente.  
  
## Vea también  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)