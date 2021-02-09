---
description: 'Más información acerca de: Automatic Memory Management'
title: Automatic Memory Management
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, automatic memory management
- memory, allocating
- memory, automatic memory management
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- managed heap
- runtime, automatic memory management
ms.assetid: d4850de5-fa63-4936-a250-5678d118acba
ms.openlocfilehash: 1897167faecb112ffa4aa7b0dd0c8bb55b8d9459
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99629973"
---
# <a name="automatic-memory-management"></a>Automatic Memory Management

La administración de memoria automática es uno de los servicios que proporciona Common Language Runtime durante la [ejecución administrada](managed-execution-process.md). El recolector de elementos no utilizados de Common Language Runtime administra la asignación y liberación de la memoria de una aplicación. Esto significa que los programadores no tienen que escribir código para realizar tareas de administración de memoria al programar aplicaciones administradas. La administración automática de la memoria puede eliminar problemas frecuentes, como olvidar liberar un objeto y causar una pérdida de memoria, o intentar tener acceso a la memoria de un objeto que ya se ha liberado. En esta sección se describe cómo asigna y libera memoria el recolector de elementos no utilizados.  
  
## <a name="allocating-memory"></a>Asignar memoria  

 Cuando se inicializa un nuevo proceso, el motor en tiempo de ejecución reserva una región contigua de espacio de direcciones para el proceso. Este espacio de direcciones reservado se denomina montón administrado. El montón administrado mantiene un puntero a la dirección a la que se asignará el siguiente objeto del montón. Inicialmente, este puntero se establece en la dirección base del montón administrado. Todos los [tipos de referencia](base-types/common-type-system.md) se asignan en el montón administrado. Cuando una aplicación crea el primer tipo de referencia, se le asigna memoria en la dirección base del montón administrado. Cuando la aplicación crea el siguiente objeto, el recolector de elementos no utilizados le asigna memoria en el espacio de direcciones que sigue inmediatamente al primer objeto. Siempre que haya espacio de direcciones disponible, el recolector de elementos no utilizados continúa asignando espacio a los objetos nuevos de este modo.  
  
 La asignación de memoria desde el montón administrado es más rápida que la asignación de memoria no administrada. Como el tiempo de ejecución asigna memoria a los objetos agregando un valor a un puntero, este método es casi tan rápido como la asignación de memoria desde la pila. Además, puesto que los nuevos objetos que se asignan consecutivamente se almacenan uno junto a otro en el montón administrado, la aplicación puede tener un acceso muy rápido a los objetos.  
  
<a name="cpconautomaticmemorymanagementreleasingmemoryanchor1"></a>

## <a name="releasing-memory"></a>Liberar memoria  

 El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección basándose en las asignaciones realizadas. Cuando el recolector de elementos no utilizados lleva a cabo una recolección, libera la memoria de los objetos que ya no usa la aplicación. Determina qué objetos ya no se usan examinando las raíces de la aplicación. Todas las aplicaciones tienen un conjunto de raíces. Cada raíz hace referencia a un objeto del montón administrado, o bien se establece en null. Las raíces de una aplicación incluyen campos estáticos, variables locales y parámetros de pila de un subproceso y registros de la CPU. El recolector de elementos no utilizados tiene acceso a la lista de raíces activas que el [compilador Just-In-Time (JIT)](managed-execution-process.md) y el runtime mantienen. Con esta lista examina las raíces de la aplicación y, durante este proceso, crea un gráfico que contiene todos los objetos que no se pueden alcanzar desde las raíces.  
  
 Los objetos que no están en el gráfico no se pueden alcanzar desde las raíces de la aplicación. El recolector de elementos no utilizados considera elementos no utilizados a los objetos inalcanzables y libera la memoria que tienen asignada. Durante una recolección, el recolector de elementos no utilizados examina el montón administrado y busca los bloques de espacio de direcciones que ocupan los objetos que no se pueden alcanzar. Cuando detecta cada uno de los objetos inalcanzables, usa una función de copia de memoria para compactar los objetos alcanzables en la memoria y libera los bloques de espacios de direcciones asignados a los objetos no alcanzables. Una vez que se ha compactado la memoria de los objetos alcanzables, el recolector de elementos no utilizados hace las correcciones de puntero necesarias para que las raíces de la aplicación señalen a los objetos en sus nuevas ubicaciones. También sitúa el puntero del montón administrado después del último objeto alcanzable. Tenga en cuenta que la memoria sólo se compacta si, durante una recolección, se detecta un número significativo de objetos inalcanzables. Si todos los objetos del montón administrado sobreviven a una recolección, no hay necesidad de comprimir la memoria.  
  
 Para mejorar el rendimiento, el tiempo de ejecución asigna memoria a los objetos grandes en un montón aparte. El recolector de elementos no utilizados libera la memoria para los objetos grandes automáticamente. Sin embargo, para no mover objetos grandes en la memoria, dicha memoria no se compacta.  
  
## <a name="generations-and-performance"></a>Generaciones y rendimiento  

 Para optimizar el rendimiento del recolector de elementos no utilizados, el montón administrado se divide en tres generaciones: 0, 1 y 2. El algoritmo de recolección de elementos no utilizados del runtime se basa en diversas generalizaciones que la industria de software informático ha detectado como ciertas al experimentar con esquemas de recolección de elementos no utilizados. Primero, es más rápido compactar la memoria de una parte del montón administrado que la de todo el montón. En segundo lugar, los objetos más recientes tienen una duración más corta y los objetos antiguos tienen una duración más larga. Por último, los objetos más recientes suelen estar relacionados unos con otros y la aplicación tiene acceso a ellos más o menos al mismo tiempo.  
  
 El recolector de elementos no utilizados del runtime almacena los nuevos objetos en la generación 0. Los objetos creados en las primeras etapas de la duración de la aplicación y que sobreviven a las recolecciones se promueven y se almacenan en las generaciones 1 y 2. El proceso de promoción de objetos se describe más adelante en este tema. Como es más rápido compactar una parte del montón administrado que todo el montón, este esquema permite que el recolector de elementos no utilizados libere la memoria en una generación específica en lugar de liberarla para todo el montón administrado cada vez que realiza una recolección.  
  
 En realidad, el recolector de elementos no utilizados realiza una recolección cuando se llena la generación 0. Si una aplicación trata de crear un nuevo objeto cuando la generación 0 está llena, el recolector de elementos no utilizados detecta que no queda espacio de direcciones en la generación 0 para asignárselo. El recolector de elementos no utilizados realiza una recolección, en un intento de liberar espacio de direcciones para el objeto en la generación 0. Primero examina los objetos de la generación 0 y no todos los objetos del montón administrado. Éste es un enfoque más eficaz, ya que los objetos nuevos suelen tener una duración más corta y se espera que la aplicación no utilice muchos de los objetos de la generación 0 cuando se realice una recolección. Además, una recolección de tan sólo la generación 0 a menudo recupera suficiente memoria para que la aplicación pueda continuar creando nuevos objetos.  
  
 Una vez que el recolector de elementos no utilizados realiza una recolección de la generación 0, compacta la memoria de los objetos que se pueden alcanzar como se ha explicado antes en este tema, en [Liberar memoria](#cpconautomaticmemorymanagementreleasingmemoryanchor1). A continuación, el recolector de elementos no utilizados promueve estos objetos y considera que esta parte del montón administrado está en la generación 1. Dado que los objetos que sobreviven a las recolecciones suelen tener una duración más larga, es lógico promoverlos a una generación superior. En consecuencia, el recolector de elementos no utilizados no tiene que volver a examinar los objetos de las generaciones 1 y 2 cada vez que realiza una recolección en la generación 0.  
  
 Una vez que el recolector de elementos no utilizados realiza su primera recolección de la generación 0 y promueve los objetos que se pueden alcanzar a la generación 1, considera que lo que queda del montón administrado forma parte de la generación 0. Continúa asignando memoria a los nuevos objetos de la generación 0 hasta que la generación 0 está completa y es necesario realizar otra recolección. En este momento, el motor de optimización del recolector de elementos no utilizados determina si es necesario examinar los objetos de generaciones más antiguas. Por ejemplo, si una recolección de la generación 0 no recupera memoria suficiente para que la aplicación pueda completar correctamente su intento de crear un nuevo objeto, el recolector de elementos no utilizados puede realizar una recolección de la generación 1 y, a continuación, de la generación 2. Si con ello no recupera suficiente memoria, el recolector de elementos no utilizados puede realizar una recolección de las generaciones 2, 1 y 0. Después de cada recolección, el recolector de elementos no utilizados compacta los objetos que puede alcanzar en la generación 0 y los promueve a la generación 1. Los objetos de la generación 1 que sobreviven a las recolecciones se promueven a la generación 2. Como el recolector de elementos no utilizados solo admite tres generaciones, los objetos de la generación 2 que sobreviven a una recolección se mantienen en esta generación hasta que en una recolección posterior se determina que no se pueden alcanzar.  
  
## <a name="releasing-memory-for-unmanaged-resources"></a>Liberar memoria para recursos no administrados  

 En el caso de la mayoría de los objetos creados por la aplicación, puede utilizar el recolector de elementos no utilizados para realizar automáticamente las tareas de administración de memoria. Sin embargo, los recursos no administrados requieren una limpieza explícita. El tipo más habitual de recurso no administrado es un objeto que contiene un recurso del sistema operativo, como un identificador de archivo, identificador de ventana o conexión de red. Aunque el recolector de elementos no utilizados puede realizar el seguimiento del período de duración de un objeto administrado que encapsula un recurso no administrado, no tiene un conocimiento específico de cómo limpiar el recurso. Cuando se crea un objeto que encapsula un recurso no administrado, es recomendable proporcionar el código necesario para limpiar dicho recurso en un método público **Dispose**. Si se proporciona un método **Dispose**, se permite que los usuarios del objeto liberen su memoria de manera explícita cuando hayan terminado de usarlo. Si se utiliza un objeto que encapsula un recurso no administrado, se debe conocer la existencia de **Dispose** y llamarlo cuando sea necesario. Para más información sobre la limpieza de recursos no administrados y el ejemplo de un modelo de diseño para implementar **Dispose**, consulte [Recolección de elementos no utilizados](garbage-collection/index.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.GC>
- [Recolección de elementos no utilizados](garbage-collection/index.md)
- [Proceso de ejecución administrada](managed-execution-process.md)
