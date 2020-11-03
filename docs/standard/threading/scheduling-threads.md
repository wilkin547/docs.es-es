---
title: Programación de subprocesos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
ms.openlocfilehash: 806d6620fd236c69a4f461f1e30f68a3fefc9b17
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188957"
---
# <a name="scheduling-threads"></a>Programación de subprocesos

Cada subproceso tiene una prioridad de subproceso asignada a él. A los subprocesos creados en Common Language Runtime se les asigna inicialmente la prioridad de <xref:System.Threading.ThreadPriority.Normal?displayProperty=nameWithType>. Los subprocesos creados fuera del tiempo de ejecución mantienen la prioridad que tenían antes de entrar en el entorno administrado. Puede obtener o establecer la prioridad de cualquier subproceso con la propiedad <xref:System.Threading.Thread.Priority?displayProperty=nameWithType>.  
  
 Los subprocesos están programados para ejecutarse según su prioridad. Aunque los subprocesos se ejecutan durante el tiempo de ejecución, el sistema operativo asigna intervalos de tiempo de procesador a todos los subprocesos. Los detalles del algoritmo de programación utilizado para determinar el orden en que se ejecutan los subprocesos varían en función de cada sistema operativo. En algunos sistemas operativos, el subproceso con la prioridad más alta (de entre los subprocesos que se pueden ejecutar) está programado siempre para que se ejecute primero. Si hay disponibles varios subprocesos con la misma prioridad, el programador recorre los subprocesos con dicha prioridad, dando a cada subproceso un intervalo de tiempo fijo para su ejecución. Siempre que un subproceso con una prioridad más alta esté disponible para su ejecución, los subprocesos con menor prioridad no se llegan a ejecutar. Si no hay más subprocesos ejecutables con una prioridad determinada, el programador pasa a la siguiente prioridad más baja y programa la ejecución de los subprocesos que tienen esa prioridad. Si un subproceso de prioridad superior se convierte en ejecutable, se relega el subproceso de menor prioridad y el subproceso con mayor prioridad se puede ejecutar una vez más. Sobre todo, el sistema operativo también puede ajustar las prioridades de los subprocesos de forma dinámica como una interfaz de usuario de la aplicación se mueve entre el primer y segundo plano. Otros sistemas operativos puede optar por utilizar un algoritmo de programación diferente.  
  
## <a name="see-also"></a>Vea también

- [Usar subprocesos y subprocesamiento](using-threads-and-threading.md)
- [Subprocesamiento administrado y no administrado en Windows](managed-and-unmanaged-threading-in-windows.md)
