---
title: Diferencias entre la recolección de elementos no utilizados (GC) en estaciones de trabajo y servidores
description: Obtenga información sobre la recolección de elementos no utilizados de estación de trabajo y de servidor en .NET.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 6b8e5f6802e5d44669b95d43d4e897fa4a418512
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82103494"
---
# <a name="workstation-and-server-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo y de servidor

El recolector de elementos no utilizados se ajusta automáticamente y puede funcionar en gran variedad de escenarios. Pero puede [establecer el tipo de recolección de elementos no utilizados](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) en función de las características de la carga de trabajo. El CLR proporciona los tipos siguientes de recolección de elementos no utilizados:

- La recolección de elementos no utilizados (GC) de estación de trabajo, que está diseñada para las aplicaciones cliente. Es el tipo de GC predeterminado para las aplicaciones independientes. En el caso de las aplicaciones hospedadas, por ejemplo, las que se hospedan en ASP.NET, el host determina el tipo de GC predeterminado.

  La recolección de elementos no utilizados de estación de trabajo puede ser simultánea o no simultánea. La recolección simultánea (o *en segundo plano*) de elementos no utilizados permite que los subprocesos administrados continúen con sus operaciones durante una recolección de elementos no utilizados. La [recolección de elementos no utilizados en segundo plano](background-gc.md) reemplaza la [recolección simultánea de elementos no utilizados](background-gc.md#concurrent-garbage-collection) en .NET Framework 4 y versiones posteriores.

- Recolección de elementos no utilizados de servidor, diseñada para las aplicaciones de servidor que necesitan un alto nivel de rendimiento y escalabilidad.

  - En .NET Core, la recolección de elementos no utilizados de servidor puede ser no simultánea o en segundo plano.

  - En .NET Framework 4.5 y versiones posteriores, la recolección de elementos no utilizados de servidor puede ser no simultánea o en segundo plano. En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados de servidor no es simultánea.

En las siguientes ilustraciones se muestran los subprocesos dedicados que realizan la recolección de elementos no utilizados en un servidor:

![Subprocesos de recolección de elementos no utilizados de servidor](./media/gc-server.png)

## <a name="performance-considerations"></a>Consideraciones sobre el rendimiento

### <a name="workstation-gc"></a>Estación de trabajo de catálogo global

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de estación de trabajo:

- La recolección se produce en el subproceso del usuario que desencadenó la recolección de elementos no utilizados y permanece en la misma prioridad. Como los subprocesos de usuario suelen ejecutarse con prioridad normal, el recolector de elementos no utilizados (que se ejecuta en un subproceso de prioridad normal) debe competir con otros subprocesos por el tiempo de la CPU. (Los subprocesos que ejecutan código nativo no se suspenden en la recolección de elementos no utilizados de servidor o de estación de trabajo).

- La recolección de elementos no utilizados de estación de trabajo siempre se utiliza en un equipo que tiene un solo procesador, sin tener en cuenta el [valor de configuración](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

### <a name="server-gc"></a>Servidor de catálogo global

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de servidor:

- La recolección se produce en varios subprocesos dedicados que se ejecutan en el nivel de prioridad `THREAD_PRIORITY_HIGHEST` .

- Para cada CPU se proporciona un montón y un subproceso dedicado para realizar recolección de elementos no utilizados y, al mismo tiempo, se recolectan los montones. Cada montón contiene un montón de objetos pequeños y un montón de objetos grandes; a todos ellos se puede tener acceso mediante código de usuario. Los objetos de montones diferentes pueden hacerse referencia a entre sí.

- Dado que varios subprocesos de recolección de elementos no utilizados funcionan juntos, la recolección de elementos no utilizados de servidor es más rápida que la de estación de trabajo, con un montón del mismo tamaño.

- La recolección de elementos no utilizados de servidor suele tener segmentos de mayor tamaño. Sin embargo, esto es solo una generalización: el tamaño de los segmentos es específico de la implementación y está sujeto a cambios. No haga ninguna suposición sobre el tamaño de los segmentos asignados por el recolector de elementos no utilizados al optimizar la aplicación.

- La recolección de elementos no utilizados de servidor puede consumir gran cantidad de recursos. Por ejemplo, imagine que hay 12 procesos que usan GC de servidor que se ejecutan en un equipo con cuatro procesadores. Si todos los procesos tienen que recopilar elementos no utilizados al mismo tiempo, interfieren entre sí, ya que serían 12 subprocesos programados en el mismo procesador. Si los procesos están activos, no es recomendable que todos usen GC de servidor.

Si se ejecutan centenares de instancias de una aplicación, puede ser más conveniente utilizar la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados deshabilitada. De este modo se realizarán menos cambios de contexto, lo que puede mejorar el rendimiento.

## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados en segundo plano](background-gc.md)
- [Opciones de configuración de tiempo de ejecución para la recolección de elementos no utilizados](../../core/run-time-config/garbage-collector.md)
