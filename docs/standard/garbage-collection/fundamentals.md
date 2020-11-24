---
title: Fundamentos de la recolección de elementos no utilizados
description: Obtenga información sobre cómo funciona el recolector de elementos no utilizados y cómo puede configurarse para un rendimiento óptimo.
ms.date: 11/15/2019
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background
- garbage collection, concurrent
- garbage collection, server
- garbage collection, workstation
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
ms.openlocfilehash: 1536aaf936eb8d55aa56b80b50639541e89c9d2c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827820"
---
# <a name="fundamentals-of-garbage-collection"></a>Fundamentos de la recolección de elementos no utilizados

En el Common Language Runtime (CLR), el recolector de elementos no utilizados (GC) actúa como administrador de memoria automático. El recolector de elementos no utilizados administra la asignación y liberación de la memoria de una aplicación. Esto significa que los desarrolladores que trabajan con código administrado no tienen que escribir código para realizar tareas de administración de memoria. La administración automática de la memoria puede eliminar problemas frecuentes, como olvidar liberar un objeto y causar una pérdida de memoria, o intentar acceder a la memoria de un objeto que ya se ha liberado.

En este artículo se describen los conceptos básicos de la recolección de elementos no utilizados.

## <a name="benefits"></a>Ventajas

El recolector de elementos no utilizados proporciona las siguientes ventajas:

- Exime a los desarrolladores de tener que liberar memoria manualmente.

- Asigna con eficacia los objetos del montón administrado.

- Reclama los objetos que ya no se utilizan, borra la memoria correspondiente y mantiene la memoria disponible para asignaciones futuras. Los objetos administrados obtienen automáticamente contenido limpio desde el principio, de modo que sus constructores no tienen que inicializar todos los campos de datos.

- Proporciona seguridad de memoria, al asegurarse de que un objeto no pueda utilizar el contenido de otro objeto.

## <a name="fundamentals-of-memory"></a>Fundamentos de memoria

En la lista siguiente se resumen los conceptos importantes de memoria de CLR.

- Cada proceso tiene propio espacio de direcciones virtuales independiente. Todos los procesos del equipo comparten la misma memoria física y el archivo de paginación, si hay alguno.

- De forma predeterminada, en los equipos de 32 bits, cada proceso tiene un espacio de direcciones virtuales en modo usuario de 2 GB.

- Como desarrollador de aplicaciones, solo trabaja con el espacio de direcciones virtuales y nunca manipula la memoria física directamente. El recolector de elementos no utilizados asigna y libera memoria virtual en el montón administrado.

  Si está escribiendo código nativo, use funciones de Windows para trabajar con el espacio de direcciones virtuales. Estas funciones asignan y liberan memoria virtual en pilas nativas.

- La memoria virtual puede estar en tres estados:

  | Estado | Descripción |
  |---------|---------|
  | Gratuito | El bloque de memoria no tiene ninguna referencia a ella y está disponible para su asignación. |
  | Reservada | El bloque de memoria está disponible para su uso y no se puede emplear para ninguna otra solicitud de asignación. Sin embargo, no puede almacenar datos en este bloque de memoria hasta que se confirme. |
  | Confirmado | El bloque de memoria se asigna al almacenamiento físico. |

- El espacio de direcciones virtuales puede llegar a fragmentarse. Esto significa que hay bloques libres, también conocidos como marcadores, en el espacio de direcciones. Cuando se solicita una asignación de memoria virtual, el administrador de memoria virtual tiene que encontrar un único bloque libre que sea suficientemente grande para satisfacer esa solicitud de asignación. Aunque tenga 2 GB de espacio disponible, una asignación que necesite 2 GB será incorrecta a menos que todo ese espacio disponible esté en un único bloque de direcciones.

- Puede quedarse sin memoria si no hay suficiente espacio de direcciones virtuales para reservar o espacio físico para confirmar.

  El archivo de paginación se usa aunque haya poca necesidad de memoria física (es decir, demanda de memoria física). La primera vez que se necesita memoria física, el sistema operativo debe hacer sitio en ella para almacenar los datos y hace una copia de seguridad en el archivo de paginación de algunos datos que están en la memoria física. Esos datos no se paginan hasta que no se necesitan, por lo que es posible encontrar paginación en situaciones donde haya muy poca necesidad de memoria física.
  
### <a name="memory-allocation"></a>Asignación de memoria

Cuando se inicializa un nuevo proceso, el motor en tiempo de ejecución reserva una región contigua de espacio de direcciones para el proceso. Este espacio de direcciones reservado se denomina montón administrado. El montón administrado mantiene un puntero a la dirección a la que se asignará el siguiente objeto del montón. Inicialmente, este puntero se establece en la dirección base del montón administrado. Todos los tipos de referencia se asignan en el montón administrado. Cuando una aplicación crea el primer tipo de referencia, se le asigna memoria en la dirección base del montón administrado. Cuando la aplicación crea el siguiente objeto, el recolector de elementos no utilizados le asigna memoria en el espacio de direcciones que sigue inmediatamente al primer objeto. Siempre que haya espacio de direcciones disponible, el recolector de elementos no utilizados continúa asignando espacio a los objetos nuevos de este modo.

La asignación de memoria desde el montón administrado es más rápida que la asignación de memoria no administrada. Como el tiempo de ejecución asigna memoria a los objetos agregando un valor a un puntero, este método es casi tan rápido como la asignación de memoria desde la pila. Además, puesto que los nuevos objetos que se asignan consecutivamente se almacenan uno junto a otro en el montón administrado, la aplicación puede acceder rápidamente a los objetos.

### <a name="memory-release"></a>Liberación de memoria

El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección basándose en las asignaciones realizadas. Cuando el recolector de elementos no utilizados lleva a cabo una recolección, libera la memoria de los objetos que ya no usa la aplicación. Determina qué objetos ya no se usan examinando las *raíces* de la aplicación. Las raíces de una aplicación incluyen campos estáticos, variables locales en la pila de un subproceso, registros de la CPU, identificadores de recolección de elementos no utilizados y la cola de finalización. Cada raíz hace referencia a un objeto del montón administrado, o bien se establece en null. El recolector de elementos no utilizados puede solicitar estas raíces al resto del entorno de ejecución. Con esta lista, el recolector de elementos no utilizados crea un gráfico que contiene todos los objetos que no se pueden alcanzar desde las raíces.

Los objetos que no están en el gráfico no se pueden alcanzar desde las raíces de la aplicación. El recolector de elementos no utilizados considera elementos no utilizados los objetos inalcanzables y libera la memoria que tienen asignada. Durante una recolección, el recolector de elementos no utilizados examina el montón administrado y busca los bloques de espacio de direcciones que ocupan los objetos que no se pueden alcanzar. Cuando detecta cada uno de los objetos inalcanzables, usa una función de copia de memoria para compactar los objetos alcanzables en la memoria y libera los bloques de espacios de direcciones asignados a los objetos no alcanzables. Una vez que se ha compactado la memoria de los objetos alcanzables, el recolector de elementos no utilizados hace las correcciones de puntero necesarias para que las raíces de la aplicación señalen a los objetos en sus nuevas ubicaciones. También sitúa el puntero del montón administrado después del último objeto alcanzable.

La memoria solo se compacta si, durante una recolección, se detecta un número significativo de objetos inalcanzables. Si todos los objetos del montón administrado sobreviven a una recolección, no hay necesidad de comprimir la memoria.

Para mejorar el rendimiento, el tiempo de ejecución asigna memoria a los objetos grandes en un montón aparte. El recolector de elementos no utilizados libera la memoria para los objetos grandes automáticamente. Pero, para no mover objetos grandes en la memoria, normalmente dicha memoria no se compacta.

## <a name="conditions-for-a-garbage-collection"></a>Condiciones para la recolección de elementos no utilizados

La recolección de elementos no utilizados se produce cuando se cumple alguna de las siguientes condiciones:

- El sistema tiene poca memoria física. Esto detecta cualquier la notificación memoria insuficiente desde el sistema operativo o de poca memoria indicada por el host.

- La memoria que utilizan los objetos asignados del montón administrado supera un umbral aceptable. Este umbral se ajusta continuamente a medida que se ejecuta el proceso.

- Se llama al método <xref:System.GC.Collect%2A?displayProperty=nameWithType> . En casi todos casos, no es necesario llamar a este método, porque el recolector de elementos no utilizados se ejecuta continuamente. Este método se utiliza principalmente para pruebas y situaciones singulares.

## <a name="the-managed-heap"></a>Montón administrado

Una vez que el CLR inicializa el recolector de elementos no utilizados, asigna un segmento de memoria para almacenar y administrar objetos. Esta memoria se denomina montón administrado, y se diferencia del montón nativo del sistema operativo.

Hay un montón administrado para cada proceso administrado. Todos los subprocesos del proceso asignan memoria a los objetos del mismo montón.

Para reservar memoria, el recolector de elementos no utilizados llama a la función [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) de Windows y reserva un segmento de memoria cada vez para las aplicaciones administradas. El recolector de elementos no utilizados también reserva segmentos según sea necesario y vuelve a liberarlos para el sistema operativo (después de borrarlos de todos los objetos) mediante una llamada a la función [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) de Windows.

> [!IMPORTANT]
> El tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas. La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.

Cuantos menos objetos se asignen al montón, menos trabajo tendrá que hacer el recolector de elementos no utilizados. Al asignar objetos, no use valores redondeados que superen sus necesidades; por ejemplo, no asigne una matriz de 32 bytes si solo necesita 15 bytes.

Cuando se desencadena una recolección de elementos no utilizados, el recolector de elementos no utilizados reclama la memoria ocupada por objetos muertos. El proceso de reclamación compacta los objetos activos para moverlos juntos, y el espacio muerto se quita, para reducir el montón. De este modo, se asegura de que los objetos que se asignan juntos permanezcan juntos en el montón administrado, a fin de conservar su situación.

La tendencia a la intrusión (frecuencia y duración) de las recolecciones de elementos no utilizados es el resultado del volumen de asignaciones y la cantidad de memoria que sobrevivió en el montón administrado.

El montón considerarse una acumulación de dos montones: el [montón de objetos grandes](large-object-heap.md) y el montón de objetos pequeños. El montón de objetos grandes contiene objetos de 85 000 bytes o más, que normalmente son matrices. Es raro que un objeto de instancia sea sumamente grande.

> [!TIP]
> Puede [configurar el tamaño de umbral](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) para que los objetos se dirijan al montón de objetos grandes.

## <a name="generations"></a>Generaciones

El algoritmo de GC se basa en varias consideraciones:

- Es más rápido compactar la memoria de una parte del montón administrado que la de todo el montón.
- Los objetos más recientes tienen una duración más corta y los objetos antiguos tienen una duración más larga.
- Los objetos más recientes suelen estar relacionados unos con otros y la aplicación accede a ellos más o menos al mismo tiempo.

La recolección de elementos no utilizados se produce principalmente con la reclamación de objetos de corta duración. Para optimizar el rendimiento del recolector de elementos no utilizados, el montón administrado se divide en tres generaciones: 0, 1 y 2, de forma que pueda manipular por separado los objetos de corta duración y los de larga duración. El recolector de elementos no utilizados almacena los nuevos objetos en la generación 0. Los objetos creados en las primeras etapas de la duración de la aplicación y que sobreviven a las recolecciones se promueven y se almacenan en las generaciones 1 y 2. Como es más rápido compactar una parte del montón administrado que todo el montón, este esquema permite que el recolector de elementos no utilizados libere la memoria en una generación específica en lugar de liberarla para todo el montón administrado cada vez que realiza una recolección.

- **Generación 0**. Es la generación más joven y contiene los objetos de corta duración. Un ejemplo de objeto de corta duración es una variable temporal. La recolección de elementos no utilizados se produce con mayor frecuencia en esta generación.

  Los objetos recién asignados constituyen una nueva generación de objetos y son colecciones de la generación 0, implícitamente. Sin embargo, si son objetos de gran tamaño, pasan al montón de objetos grandes (LOH), al que en ocasiones se denomina *generación 3*. La generación 3 es una generación física que se recopila de forma lógica como elemento de la generación 2.

  La mayoría de los objetos se reclaman para la recolección de elementos no utilizados en la generación 0 y no sobreviven a la generación siguiente.
  
  Si una aplicación trata de crear un objeto cuando la generación 0 está llena, el recolector de elementos no utilizados realiza una recolección en un intento de liberar espacio de direcciones para el objeto. Primero examina los objetos de la generación 0 y no todos los objetos del montón administrado. Una recolección de tan sólo la generación 0 a menudo recupera suficiente memoria para que la aplicación pueda continuar creando objetos.

- **Generación 1** Esta generación contiene objetos de corta duración y sirve como búfer entre los objetos de corta y larga duración.

  Una vez que el recolector de elementos no utilizados realiza una recolección de la generación 0, compacta la memoria de los objetos que se pueden alcanzar y los promueve a la generación 1. Dado que los objetos que sobreviven a las recolecciones suelen tener una duración más larga, es lógico promoverlos a una generación superior. El recolector de elementos no utilizados no tiene que volver a examinar los objetos de las generaciones 1 y 2 cada vez que realiza una recolección en la generación 0.
  
  Si una recolección de la generación 0 no recupera memoria suficiente para que la aplicación pueda crear un nuevo objeto, el recolector de elementos no utilizados puede realizar una recolección de la generación 1 y, después, de la generación 2. Los objetos de la generación 1 que sobreviven a las recolecciones se promueven a la generación 2.

- **Generación 2** Esta generación contiene los objetos de larga duración. Un ejemplo de objeto de larga duración es un objeto de una aplicación de servidor que contiene datos estáticos que están activos mientras dura el proceso.

  Los objetos de la generación 2 que sobreviven a una recolección se mantienen en esta generación hasta que en una recolección posterior se determina que no se pueden alcanzar.
  
  Los objetos del montón de objetos grandes (a veces denominado *generación 3*) también se recopilan en la generación 2.

Las recolecciones de elementos no utilizados se producen en generaciones concretas según lo permitan las condiciones. La recolección de una generación significa recolectar los objetos de esa generación y de todas las generaciones anteriores. Una recolección de elementos no utilizados de la generación 2 se denomina también recolección de elementos no utilizados completa, porque reclama los objetos de todas las generaciones (es decir, todos los objetos del montón administrado).

### <a name="survival-and-promotions"></a>Supervivencia y promociones

Los objetos que no se reclaman en una recolección de elementos no utilizados se denominan supervivientes y se promueven a la generación siguiente:

- Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 0 se promueven a la generación 1.
- Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 1 se promueven a la generación 2.
- Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 2 permanecen en la generación 2.

Cuando el recolector de elementos no utilizados detecta que la tasa de supervivencia es alta en una generación, aumenta el umbral de asignaciones para esa generación. La colección siguiente obtiene un tamaño sustancial de memoria reclamada. El CLR equilibra continuamente dos prioridades: no permitir que el espacio de trabajo de una aplicación adquiera un tamaño excesivo al retrasar la recolección de elementos no utilizados y no permitir que la recolección de elementos no utilizados se ejecute con mucha frecuencia.

### <a name="ephemeral-generations-and-segments"></a>Generaciones y segmentos efímeros

Dado que los objetos de las generaciones 0 y 1 son de corta duración, estas generaciones se denominan *generaciones efímeras*.

Las generaciones efímeras se asignan en el segmento de memoria denominado segmento efímero. Cada nuevo segmento adquirido por el recolector de elementos no utilizados se convierte en el nuevo segmento efímero y contiene los objetos que sobrevivieron a una recolección de elementos no utilizados de la generación 0. El segmento efímero anterior se convierte en el nuevo segmento de la generación 2.

El tamaño del segmento efímero varía según si un sistema es de 32 bits o de 64 bits y del tipo del recolector de elementos no utilizados que se está ejecutando ([GC de servidor o estación de trabajo](workstation-server-gc.md)). En la tabla siguiente se muestran los tamaños predeterminados del segmento efímero.

|GC de servidor/estación de trabajo|32 bits|64 bits|
|-|-------------|-------------|
|Estación de trabajo de catálogo global|16 MB|256 MB|
|Servidor de catálogo global|64 MB|4 GB|
|Servidor de catálogo global con > 4 CPU lógicas|32 MB|2 GB|
|Servidor de catálogo global con > 8 CPU lógicas|16 MB|1 GB|

El segmento efímero puede incluir objetos de la generación 2. Los objetos de la generación 2 pueden utilizar varios segmentos (tantos como necesite el proceso y la memoria permita).

La cantidad de memoria liberada como consecuencia de una recolección de elementos no utilizados efímera se limita al tamaño del segmento efímero. La cantidad de memoria que se libera es proporcional al espacio que ocupaban los objetos muertos.

## <a name="what-happens-during-a-garbage-collection"></a>Lo que sucede durante la recolección de elementos no utilizados

Una recolección de elementos no utilizados tiene las siguientes fases:

- Una fase de marcado que busca y crea una lista de todos los objetos activos.

- Una fase de reubicación, que actualiza las referencias a los objetos que se van a compactar.

- Una fase de compactación, que reclama el espacio ocupado por los objetos muertos y compacta los objetos supervivientes. En la fase de compactación se mueven los objetos que han sobrevivido a una recolección de elementos no utilizados hacia el extremo más antiguo del segmento.

  Debido a que las recolecciones de la generación 2 pueden ocupar varios segmentos, los objetos que se promueven a la generación 2 se pueden mover a un segmento anterior. Los supervivientes de las generaciones 1 y 2 se pueden mover a un segmento diferente, porque se promueven a la generación 2.

  Normalmente, el montón de objetos grandes no se compacta, porque al copiar objetos grandes se reduce el rendimiento. Sin embargo, en .NET Core y en .NET Framework 4.5.1 y versiones posteriores, se puede utilizar la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> para compactar el montón de objetos grandes a petición. Además, el montón de objetos grandes se compacta automáticamente cuando se establece un límite máximo mediante la especificación de:

  - un límite de memoria en un contenedor.
  - Las opciones de configuración en tiempo de ejecución [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#heap-limit) o [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#heap-limit-percent).

El recolector de elementos no utilizados utiliza la siguiente información para determinar si los objetos están activos:

- **Raíces de la pila**. Variables de pila proporcionadas por el compilador Just-In-Time (JIT) y el rastreador de pila. Las optimizaciones de JIT pueden prolongar o acortar regiones de código en las que se notifican variables de pila al recolector de elementos no utilizados.

- **Identificadores de recolección de elementos no utilizados**. Identificadores que señalan a objetos administrados y que se pueden asignar mediante código de usuario o mediante Common Language Runtime.

- **Datos estáticos**. Objetos estáticos de dominios de aplicación que podrían hacer referencia a otros objetos. Cada dominio de aplicación realiza el seguimiento de sus objetos estáticos.

Antes de que iniciarse una recolección de elementos no utilizados, todos los subprocesos administrados se suspenden salvo el subproceso que activó la recolección de elementos no utilizados.

En la ilustración siguiente se muestra un subproceso que desencadena una recolección de elementos no utilizados, lo que provoca la suspensión de los demás subprocesos.

![Cuando un subproceso activa una recolección de elementos no utilizados](media/gc-triggered.png)

## <a name="unmanaged-resources"></a>Recursos no administrados

En el caso de la mayoría de los objetos creados por la aplicación, puede utilizar la recolección de elementos no utilizados para realizar automáticamente las tareas de administración de memoria. Sin embargo, los recursos no administrados requieren una limpieza explícita. El tipo más habitual de recurso no administrado es un objeto que contiene un recurso del sistema operativo, como un identificador de archivo, identificador de ventana o conexión de red. Aunque el recolector de elementos no utilizados puede realizar el seguimiento del período de duración de un objeto administrado que encapsula un recurso no administrado, no tiene un conocimiento específico de cómo limpiar el recurso.

Cuando se crea un objeto que encapsula un recurso no administrado, es recomendable proporcionar el código necesario para limpiar dicho recurso en un método público `Dispose`. Si se proporciona un método `Dispose`, se permite que los usuarios del objeto liberen su memoria de manera explícita cuando hayan terminado de usarlo. Si se usa un objeto que encapsula un recurso no administrado, asegúrese de llamar a `Dispose` cuando sea necesario.

También debe proporcionar una forma de liberar los recursos no administrados en el caso de que un consumidor de su tipo olvide llamar a `Dispose`. Puede usar un controlador seguro para encapsular el recurso no administrado o invalidar el método <xref:System.Object.Finalize?displayProperty=nameWithType>.

Para obtener más información sobre la limpieza de recursos no administrados, vea [Limpieza de recursos no administrados](unmanaged.md).

## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados de estación de trabajo y de servidor](workstation-server-gc.md)
- [Recolección de elementos no utilizados en segundo plano](background-gc.md)
- [Opciones de configuración para la recolección de elementos no utilizados](../../core/run-time-config/garbage-collector.md)
- [Recolección de elementos no utilizados](index.md)
