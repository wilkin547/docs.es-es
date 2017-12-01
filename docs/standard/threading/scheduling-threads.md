---
title: Planear subprocesos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a>Planear subprocesos
Cada subproceso tiene una prioridad de subproceso asignada a él. Los subprocesos creados en common language runtime se les asigna inicialmente la prioridad de **ThreadPriority.Normal**. Los subprocesos creados fuera del runtime mantienen la prioridad que tenían antes de entrar en el entorno administrado. Puede obtener o establecer la prioridad de los subprocesos con el **Thread.Priority** propiedad.  
  
 Subprocesos están programados para ejecutarse según su prioridad. Aunque la ejecución de subprocesos en tiempo de ejecución, todos los subprocesos se asignan intervalos de tiempo de procesador por el sistema operativo. Los detalles del algoritmo de programación utilizado para determinar el orden en que se ejecutan subprocesos varía en función de cada sistema operativo. En algunos sistemas operativos, el subproceso con la prioridad más alta (de esos subprocesos que se pueden ejecutar) está programado siempre que se ejecute primero. Si hay disponibles varios subprocesos con la misma prioridad, el programador recorre los subprocesos de prioridad, dando a cada subproceso de un intervalo de tiempo fijo en el que se va a ejecutar. Siempre que un subproceso con una prioridad más alta está disponible para su ejecución, los subprocesos con menor prioridad no se obtienen ejecutar. Cuando hay subprocesos más ya no se puede ejecutar en una prioridad determinada, el programador se mueve a la siguiente prioridad inferior y programe los subprocesos de dicha prioridad para la ejecución. Si un subproceso de prioridad superior se convierta en ejecutable, se ve relegado el subproceso de menor prioridad y el subproceso con mayor prioridad se puede ejecutar una vez más. Sobre todo, el sistema operativo también puede ajustar las prioridades de subproceso dinámicamente como interfaz de usuario de la aplicación se mueve entre el primer y segundo plano. Otros sistemas operativos puede optar por utilizar un algoritmo de programación diferente.  
  
## <a name="see-also"></a>Vea también  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Subprocesamiento administrado y no administrado en Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
