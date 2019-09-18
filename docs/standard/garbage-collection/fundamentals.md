---
title: Fundamentos de la recolección de elementos no utilizados
description: Obtenga información sobre cómo funciona el recolector de elementos no utilizados y cómo puede configurarse para un rendimiento óptimo.
ms.date: 03/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background garbage collection
- garbage collection, concurrent garbage collection
- garbage collection, server garbage collection
- garbage collection, workstation garbage collection
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ba6c46116d809e2881eee37b080e1952e2eb6a0
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895276"
---
# <a name="fundamentals-of-garbage-collection"></a>Fundamentos de la recolección de elementos no utilizados

<a name="top"></a> En el Common Language Runtime (CLR), el recolector de elementos no utilizados actúa como administrador de memoria automático. Proporciona las siguientes ventajas:

- Permite desarrollar la aplicación sin tener que liberar memoria manualmente para los objetos que ha creado.

- Asigna con eficacia los objetos del montón administrado.

- Reclama los objetos que ya no se utilizan, borra la memoria correspondiente y mantiene la memoria disponible para asignaciones futuras. Los objetos administrados obtienen automáticamente contenido limpio desde el principio, de modo que sus constructores no tienen que inicializar todos los campos de datos.

- Proporciona seguridad de memoria, al asegurarse de que un objeto no pueda utilizar el contenido de otro objeto.

 En este tema se describen los conceptos básicos de la recolección de elementos no utilizados.

<a name="fundamentals_of_memory"></a>

## <a name="fundamentals-of-memory"></a>Fundamentos de memoria

En la lista siguiente se resumen los conceptos importantes de memoria de CLR.

- Cada proceso tiene propio espacio de direcciones virtuales independiente. Todos los procesos del equipo comparten la misma memoria física y comparten el archivo de paginación si hay alguno.

- De forma predeterminada, en los equipos de 32 bits, cada proceso tiene un espacio de direcciones virtuales en modo usuario de 2 GB.

- Como desarrollador de aplicaciones, solo trabaja con el espacio de direcciones virtuales y nunca manipula la memoria física directamente. El recolector de elementos no utilizados asigna y libera memoria virtual en el montón administrado.

  Si está escribiendo código nativo, use funciones de Win32 para trabajar con el espacio de direcciones virtuales. Estas funciones asignan y liberan memoria virtual en pilas nativas.

- La memoria virtual puede estar en tres estados:

  - Libre. El bloque de memoria no tiene ninguna referencia a ella y está disponible para su asignación.

  - Reservado. El bloque de memoria está disponible para su uso y no se puede emplear para ninguna otra solicitud de asignación. Sin embargo, no puede almacenar datos en este bloque de memoria hasta que se confirme.

  - Confirmado. El bloque de memoria se asigna al almacenamiento físico.

- El espacio de direcciones virtuales puede llegar a fragmentarse. Esto significa que hay bloques libres, también conocidos como marcadores, en el espacio de direcciones. Cuando se solicita una asignación de memoria virtual, el administrador de memoria virtual tiene que encontrar un único bloque libre que sea suficientemente grande para satisfacer esa solicitud de asignación. Aunque tenga 2 GB de espacio disponible, la asignación que necesita 2 GB será incorrecta a menos que todo ese espacio disponible esté en un único bloque de direcciones.

- Puede quedarse sin memoria si no tiene espacio de direcciones virtuales para reservar o espacio físico para confirmar.

El archivo de paginación se usa aunque haya poca necesidad de memoria física (es decir, demanda de memoria física). La primera vez que se necesita mucha memoria física, el sistema operativo debe hacer sitio en la memoria física para almacenar los datos y hace una copia de seguridad en el archivo de paginación de algunos datos que están en la memoria física. Esos datos no se paginan hasta que no se necesitan, por lo que es posible encontrar paginación en situaciones donde haya muy poca necesidad de memoria física.

[Volver al principio](#top)

<a name="conditions_for_a_garbage_collection"></a>

## <a name="conditions-for-a-garbage-collection"></a>Condiciones para la recolección de elementos no utilizados

La recolección de elementos no utilizados se produce cuando se cumple alguna de las siguientes condiciones:

- El sistema tiene poca memoria física. Esto detecta cualquier la notificación memoria insuficiente desde el sistema operativo o de poca memoria indicada por el host.

- La memoria que utilizan los objetos asignados del montón administrado supera un umbral aceptable. Este umbral se ajusta continuamente a medida que se ejecuta el proceso.

- Se llama al método <xref:System.GC.Collect%2A?displayProperty=nameWithType> . En casi todos casos, no es necesario llamar a este método, porque el recolector de elementos no utilizados se ejecuta continuamente. Este método se utiliza principalmente para pruebas y situaciones singulares.

[Volver al principio](#top)

<a name="the_managed_heap"></a>

## <a name="the-managed-heap"></a>Montón administrado

Una vez que el CLR inicializa el recolector de elementos no utilizados, asigna un segmento de memoria para almacenar y administrar objetos. Esta memoria se denomina montón administrado, y se diferencia del montón nativo del sistema operativo.

Hay un montón administrado para cada proceso administrado. Todos los subprocesos del proceso asignan memoria a los objetos del mismo montón.

Para reservar memoria, el recolector de elementos no utilizados llama a la función [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) de Win32 y reserva un segmento de memoria cada vez para las aplicaciones administradas. El recolector de elementos no utilizados también reserva segmentos según sea necesario y vuelve a liberarlos para el sistema operativo (después de borrarlos de todos los objetos) llamando a la función [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) de Win32.

> [!IMPORTANT]
> El tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas. La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.

Cuantos menos objetos se asignen al montón, menos trabajo tendrá que hacer el recolector de elementos no utilizados. Al asignar objetos, no use valores redondeados que superen sus necesidades; por ejemplo, no asigne una matriz de 32 bytes si solo necesita 15 bytes.

Cuando se desencadena una recolección de elementos no utilizados, el recolector de elementos no utilizados reclama la memoria ocupada por objetos muertos. El proceso de reclamación compacta los objetos activos para moverlos juntos, y el espacio muerto se quita, para reducir el montón. De este modo, se asegura de que los objetos que se asignan juntos permanezcan juntos en el montón administrado, a fin de conservar su situación.

La tendencia a la intrusión (frecuencia y duración) de las recolecciones de elementos no utilizados es el resultado del volumen de asignaciones y la cantidad de memoria que sobrevivió en el montón administrado.

El montón considerarse una acumulación de dos montones: el [montón de objetos grandes](large-object-heap.md) y el montón de objetos pequeños.

El [montón de objetos grandes](large-object-heap.md) contiene objetos muy grandes de 85 000 bytes o más. Los objetos del montón de objetos grandes suelen ser matrices. Es raro que un objeto de instancia sea sumamente grande.

[Volver al principio](#top)

<a name="generations"></a>

## <a name="generations"></a>Generaciones

El montón se organiza en generaciones, para poder administrar objetos de larga y corta duración. La recolección de elementos no utilizados se produce principalmente con la reclamación de objetos de corta duración que suelen ocupar solamente una parte reducida del montón. Hay tres generaciones de objetos en el montón:

- **Generación 0**. Es la generación más joven y contiene los objetos de corta duración. Un ejemplo de objeto de corta duración es una variable temporal. La recolección de elementos no utilizados se produce con mayor frecuencia en esta generación.

  Los objetos recién asignados constituyen una nueva generación de objetos e implícitamente son recolecciones de generación 0, a menos que sean objetos grandes, en cuyo caso entran en el montón de objetos grandes en una recolección de la generación 2.

  La mayoría de los objetos se reclaman para la recolección de elementos no utilizados en la generación 0 y no sobreviven a la generación siguiente.

- **Generación 1** Esta generación contiene objetos de corta duración y sirve como búfer entre los objetos de corta y larga duración.

- **Generación 2** Esta generación contiene los objetos de larga duración. Un ejemplo de objeto de larga duración es un objeto de una aplicación de servidor que contiene datos estáticos que están activos mientras dura el proceso.

Las recolecciones de elementos no utilizados se producen en generaciones concretas según lo permitan las condiciones. La recolección de una generación significa recolectar los objetos de esa generación y de todas las generaciones anteriores. Una recolección de elementos no utilizados de la generación 2 se denomina también recolección de elementos no utilizados completa, porque reclama todos los objetos de todas las generaciones (es decir, todos los objetos del montón administrado).

### <a name="survival-and-promotions"></a>Supervivencia y promociones

Los objetos que no se reclaman en una recolección de elementos no utilizados se denominan supervivientes y se promueven a la generación siguiente. Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 0 se promueven a la generación 1; los que sobreviven a una recolección de elementos no utilizados de la generación 1 se promueven a la generación 2; y los que sobreviven a una recolección de elementos no utilizados de la generación 2 permanecen en esa misma generación.

Cuando el recolector de elementos no utilizados detecta que la tasa de supervivencia es alta en una generación, aumenta el umbral de asignaciones para esa generación, de modo que la recolección siguiente obtenga un tamaño sustancial de memoria reclamada. El CLR equilibra continuamente dos prioridades: no permitir que el espacio de trabajo de una aplicación adquiera un tamaño excesivo y no permitir que la recolección de elementos no utilizados tarde demasiado tiempo.

### <a name="ephemeral-generations-and-segments"></a>Generaciones y segmentos efímeros

Dado que los objetos de las generaciones 0 y 1 son de corta duración, estas generaciones se denominan generaciones efímeras.

Las generaciones efímeras se deben asignar en el segmento de memoria denominado segmento efímero. Cada nuevo segmento adquirido por el recolector de elementos no utilizados se convierte en el nuevo segmento efímero y contiene los objetos que sobrevivieron a una recolección de elementos no utilizados de la generación 0. El segmento efímero anterior se convierte en el nuevo segmento de la generación 2.

El tamaño del segmento efímero varía según si un sistema es de 32 o de 64 bits y del tipo del recolector de elementos no utilizados que se está ejecutando. En la siguiente tabla se muestran los valores predeterminados.

||32 bits|64 bits|
|-|-------------|-------------|
|Estación de trabajo de catálogo global|16 MB|256 MB|
|Servidor de catálogo global|64 MB|4 GB|
|Servidor de catálogo global con > 4 CPU lógicas|32 MB|2 GB|
|Servidor de catálogo global con > 8 CPU lógicas|16 MB|1 GB|

El segmento efímero puede incluir objetos de la generación 2. Los objetos de la generación 2 pueden utilizar varios segmentos (tantos como necesite el proceso y la memoria permita).

La cantidad de memoria liberada como consecuencia de una recolección de elementos no utilizados efímera se limita al tamaño del segmento efímero. La cantidad de memoria que se libera es proporcional al espacio que ocupaban los objetos muertos.

[Volver al principio](#top)

<a name="what_happens_during_a_garbage_collection"></a>

## <a name="what-happens-during-a-garbage-collection"></a>Lo que sucede durante la recolección de elementos no utilizados

Una recolección de elementos no utilizados tiene las siguientes fases:

- Una fase de marcado que busca y crea una lista de todos los objetos activos.

- Una fase de reubicación, que actualiza las referencias a los objetos que se van a compactar.

- Una fase de compactación, que reclama el espacio ocupado por los objetos muertos y compacta los objetos supervivientes. En la fase de compactación se mueven los objetos que han sobrevivido a una recolección de elementos no utilizados hacia el extremo más antiguo del segmento.

  Debido a que las recolecciones de la generación 2 pueden ocupar varios segmentos, los objetos que se promueven a la generación 2 se pueden mover a un segmento anterior. Los supervivientes de las generaciones 1 y 2 se pueden mover a un segmento diferente, porque se promueven a la generación 2.

  Normalmente, el montón de objetos grandes no se compacta, porque al copiar objetos grandes se reduce el rendimiento. Sin embargo, a partir de .NET Framework 4.5.1, se puede utilizar la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> para compactar el montón de objetos grandes a petición.

El recolector de elementos no utilizados utiliza la siguiente información para determinar si los objetos están activos:

- **Raíces de la pila**. Variables de pila proporcionadas por el compilador Just-In-Time (JIT) y el rastreador de pila. Tenga en cuenta que las optimizaciones de JIT pueden prolongar o acortar regiones de código en las que se notifican variables de pila al recolector de elementos no utilizados.

- **Identificadores de recolección de elementos no utilizados**. Identificadores que señalan a objetos administrados y que se pueden asignar mediante código de usuario o mediante Common Language Runtime.

- **Datos estáticos**. Objetos estáticos de dominios de aplicación que podrían hacer referencia a otros objetos. Cada dominio de aplicación realiza el seguimiento de sus objetos estáticos.

Antes de que iniciarse una recolección de elementos no utilizados, todos los subprocesos administrados se suspenden salvo el subproceso que activó la recolección de elementos no utilizados.

En la ilustración siguiente se muestra un subproceso que desencadena una recolección de elementos no utilizados, lo que provoca la suspensión de los demás subprocesos.

![Cuando un subproceso activa una recolección](../../../docs/standard/garbage-collection/media/gc-triggered.png "GC_Triggered") Subproceso que desencadena una recolección de elementos no utilizados

[Volver al principio](#top)

<a name="manipulating_unmanaged_resources"></a>

## <a name="manipulating-unmanaged-resources"></a>Manipular recursos no administrados

Si los objetos administrados hacen referencia a objetos no administrados mediante sus identificadores de archivos nativos, es necesario liberar explícitamente los objetos no administrados, ya que el recolector de elementos no utilizados únicamente realiza el seguimiento de la memoria del montón administrado.

Los usuarios de su objeto administrado podrían no disponer de los recursos nativos utilizados por el objeto. Para realizar la limpieza, puede hacer que su objeto administrado sea susceptible de finalización. La finalización está compuesta de acciones de limpieza que el usuario ejecuta cuando el objeto ya no se utiliza. Cuando el objeto administrados muere, realiza acciones de limpieza que se especifican en su método finalizador.

Cuando se detecta que un objeto susceptible de finalización está muerto, su finalizador se coloca en una cola para que se ejecuten sus acciones de limpieza, pero el objeto en sí se promueve a la generación siguiente. Por tanto, tendrá que esperar hasta la siguiente recolección de elementos no utilizados que se produzca en esa generación (y que no tiene por qué ser necesariamente la próxima recolección de elementos no utilizados) para determinar si se ha recuperado el objeto.

[Volver al principio](#top)

<a name="workstation_and_server_garbage_collection"></a>

## <a name="workstation-and-server-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo y de servidor

El recolector de elementos no utilizados se ajusta automáticamente y puede funcionar en gran variedad de escenarios. Puede usar un valor del archivo de configuración para establecer el tipo de recolección de elementos no utilizados en función de las características de la carga de trabajo. El CLR proporciona los tipos siguientes de recolección de elementos no utilizados:

- Recolección de elementos no utilizados de estación de trabajo, para las estaciones de trabajo cliente y los equipos independientes. Se trata de la configuración predeterminada para el [elemento \<gcServer>](../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) del esquema de configuración del tiempo de ejecución.

  La recolección de elementos no utilizados de estación de trabajo puede ser simultánea o no simultánea. La recolección simultánea de elementos no utilizados permite que los subprocesos administrados continúen con sus operaciones durante una recolección de elementos no utilizados.

  A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza la recolección simultánea de elementos no utilizados.

- Recolección de elementos no utilizados de servidor, diseñada para las aplicaciones de servidor que necesitan un alto nivel de rendimiento y escalabilidad. La recolección de elementos no utilizados de servidor puede ser no simultánea o en segundo plano.

En las siguientes ilustraciones se muestran los subprocesos dedicados que realizan la recolección de elementos no utilizados en un servidor.

![Subprocesos de recolección de elementos no utilizados del servidor](../../../docs/standard/garbage-collection/media/gc-server.png "GC_Server") Recolección de elementos no utilizados del servidor

### <a name="configuring-garbage-collection"></a>Configurar la recolección de elementos no utilizados

Puede utilizar el [elemento \<gcServer>](../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) del esquema de configuración del tiempo de ejecución para especificar el tipo de recolección de elementos no utilizados que el CLR debe realizar. Cuando el atributo `enabled` de este elemento está establecido en `false` (el valor predeterminado), el CLR realiza la recolección de elementos no utilizados de estación de trabajo. Cuando se establece el atributo `enabled` en `true`, el CLR realiza la recolección de elementos no utilizados de servidor.

La recolección de elementos no utilizados simultánea se especifica con el [elemento \<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) del esquema de configuración del tiempo de ejecución. El valor predeterminado es `enabled`. Esta configuración controla la recolección de elementos no utilizados tanto simultánea como en segundo plano.

También puede especificar la recolección de elementos no utilizados de servidor con interfaces de hospedaje no administradas. Tenga en cuenta que ASP.NET y SQL Server habilitan automáticamente la recolección de elementos no utilizados de servidor si la aplicación se hospeda dentro de uno de estos entornos.

### <a name="comparing-workstation-and-server-garbage-collection"></a>Comparación de la recolección de elementos no utilizados de estación de trabajo y de servidor

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de estación de trabajo:

- La recolección se produce en el subproceso del usuario que desencadenó la recolección de elementos no utilizados y permanece en la misma prioridad. Como los subprocesos de usuario suelen ejecutarse con prioridad normal, el recolector de elementos no utilizados (que se ejecuta en un subproceso de prioridad normal) debe competir con otros subprocesos por el tiempo de la CPU.

  Los subprocesos que ejecutan código nativo no se suspenden.

- La recolección de elementos no utilizados de estación de trabajo siempre se utiliza en un equipo que tiene un solo procesador, sin tener en cuenta el valor de [\<gcServer>](../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md). Si especifica la recolección de elementos no utilizados de servidor, el CLR usa la recolección de elementos no utilizados de estación de trabajo con la simultaneidad deshabilitada.

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de servidor:

- La recolección se produce en varios subprocesos dedicados que se ejecutan en el nivel de prioridad `THREAD_PRIORITY_HIGHEST` .

- Para cada CPU se proporciona un montón y un subproceso dedicado para realizar recolección de elementos no utilizados y, al mismo tiempo, se recolectan los montones. Cada montón contiene un montón de objetos pequeños y un montón de objetos grandes; a todos ellos se puede tener acceso mediante código de usuario. Los objetos de montones diferentes pueden hacerse referencia a entre sí.

- Dado que varios subprocesos de recolección de elementos no utilizados funcionan juntos, la recolección de elementos no utilizados de servidor es más rápida que la de estación de trabajo, con un montón del mismo tamaño.

- La recolección de elementos no utilizados de servidor suele tener segmentos de mayor tamaño. Sin embargo, tenga en cuenta que esto es solo una generalización: el tamaño de los segmentos es específico de la implementación y está sujeto a cambios. No debe hacer ninguna suposición sobre el tamaño de los segmentos asignados por el recolector de elementos no utilizados al optimizar la aplicación.

- La recolección de elementos no utilizados de servidor puede consumir gran cantidad de recursos. Por ejemplo, si hay 12 procesos que se ejecutan en un equipo con 4 procesadores, habrá 48 subprocesos de recolección de elementos no utilizados dedicados, en caso de que todos utilicen la recolección de elementos no utilizados de servidor. En una situación de carga de memoria elevada, si todos los procesos empiezan a realizar la recolección de elementos no utilizados, el recolector de elementos no utilizados tendrá 48 subprocesos que programar.

Si se ejecutan centenares de instancias de una aplicación, puede ser más conveniente utilizar la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados deshabilitada. De este modo se realizarán menos cambios de contexto, lo que puede mejorar el rendimiento.

[Volver al principio](#top)

<a name="concurrent_garbage_collection"></a>

## <a name="concurrent-garbage-collection"></a>Recolección de elementos no utilizados simultánea

En la recolección de elementos no utilizados de estación de trabajo o de servidor, se puede habilitar la recolección simultánea de elementos no utilizados, que permite ejecutar subprocesos de manera simultánea con un subproceso dedicado que realiza la recolección de elementos no utilizados durante la mayor parte del tiempo que dura la recolección. Esta opción solo afecta a las recolecciones de elementos no utilizados de la generación 2; las generaciones 0 y 1 no son nunca simultáneas porque finalizan muy rápidamente.

La recolección de elementos no utilizados simultánea permite mayor capacidad de respuesta de las aplicaciones interactivas, pues minimiza las pausas en una recolección. Los subprocesos administrados pueden continuar ejecutándose la mayoría del tiempo mientras se ejecuta el subproceso de recolección de elementos no utilizados simultánea. Esto da lugar a pausas más cortas mientras se está produciendo una recolección de elementos no utilizados.

Para mejorar el rendimiento cuando hay varios procesos en ejecución, deshabilite la recolección de elementos no utilizados simultánea. Para ello, agregue un [elemento \<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) al archivo de configuración de la aplicación y establezca el valor de su atributo `enabled` en `"false"`.

La recolección de elementos no utilizados simultánea se realiza en un subproceso dedicado. De forma predeterminada, el CLR ejecuta la recolección de elementos no utilizados de estación de trabajo con la simultaneidad habilitada. Esto se cumple en los equipos de uno o varios procesadores.

La capacidad del usuario para asignar pequeños objetos del montón durante una recolección de elementos no utilizados simultánea está limitada por los objetos que quedan en el segmento efímero al iniciarse dicha recolección. En cuanto se llega al final del segmento, tendrá que esperar a que finalice la recolección de elementos no utilizados simultánea, mientras se suspenden los subprocesos administrados que tienen que realizar las asignaciones de objetos pequeños.

La recolección simultánea de elementos no utilizados tiene un espacio de trabajo ligeramente mayor (en comparación con la recolección de elementos no utilizados no simultánea), porque durante la recolección simultánea se pueden asignar objetos. Sin embargo, esto puede afectar al rendimiento, porque los objetos que asigna pasan a formar parte de su espacio de trabajo. En esencia, la recolección de elementos no utilizados simultánea cambia recursos de CPU y memoria por pausas más breves.

En la siguiente se muestra la recolección de elementos no utilizados simultánea realizada en un subproceso dedicado independiente.

![Subprocesos de recolección simultánea de elementos no utilizados](../../../docs/standard/garbage-collection/media/gc-concurrent.png "GC_Concurrent") Recolección simultánea de elementos no utilizados

[Volver al principio](#top)

<a name="background_garbage_collection"></a>

## <a name="background-workstation-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo en segundo plano

La recolección de elementos no utilizados en segundo plano reemplaza la recolección simultánea de elementos no utilizados de la estación de trabajo a partir de .NET Framework 4 y reemplaza a la recolección simultánea de elementos no utilizados de servidor a partir de .NET Framework 4.5.  En la recolección de elementos no utilizados en segundo plano, las generaciones efímeras (0 y 1) se recolectan según sea necesario mientras la recolección de la generación 2 está en curso. Se realiza en un subproceso dedicado y solo es aplicable a las recolecciones de la generación 2. La recolección de elementos no utilizados en segundo plano se habilita automáticamente de forma predeterminada y se puede habilitar o deshabilitar con la opción de configuración [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) en aplicaciones de .NET Framework. 

> [!NOTE]
> La recolección de elementos no utilizados en segundo plano únicamente está disponible en .NET Framework 4 y versiones posteriores. En .NET Framework 4, solo se admite para la recolección de elementos no utilizados de la estación de trabajo. A partir de .NET Framework 4.5, la recolección de elementos no utilizados en segundo plano está disponible para estaciones de trabajo y servidores.

Una recolección de las generaciones efímeras durante una recolección de elementos no utilizados en segundo plano se denomina recolección de elementos no utilizados en primer plano. Cuando se producen recolecciones de elementos no utilizados en primer plano, se suspenden todos los subprocesos administrados.

Cuando hay en curso una recolección de elementos no utilizados en segundo plano y se han asignado suficientes objetos en la generación 0, el CLR realiza una recolección de elementos no utilizados en primer plano de las generaciones 0 o 1. El subproceso de recolección de elementos no utilizados en segundo plano dedicado realiza comprobaciones en puntos seguros frecuentes para determinar si existe alguna solicitud de recolección de elementos no utilizados en primer plano. Si la hay, la recolección en segundo plano se suspende para que la recolección de elementos no utilizados en primer plano se pueda llevar a cabo. Una vez completada la recolección de elementos no utilizados en primer plano, se reanudan el subproceso de recolección de elementos no utilizados en segundo plano dedicado y los subprocesos del usuario.

La recolección de elementos no utilizados en segundo plano quita las restricciones de asignación impuestas por la recolección simultánea de elementos no utilizados, porque se pueden producir recolecciones de elementos no utilizados efímeras durante una recolección en segundo plano. Esto significa que la recolección de elementos no utilizados en segundo plano puede quitar objetos muertos de las generaciones efímeras y también expandir el montón si es preciso durante una recolección de elementos no utilizados en la generación 1.

En la siguiente ilustración se muestra la recolección de elementos no utilizados en segundo plano realizada en un subproceso dedicado independiente en una estación de trabajo:

![Diagrama que muestra la recolección de elementos no utilizados de estación de trabajo en segundo plano.](./media/fundamentals/background-workstation-garbage-collection.png)

[Volver al principio](#top)

<a name="background_server_garbage_collection"></a>

## <a name="background-server-garbage-collection"></a>Recolección de elementos no utilizados de servidor en segundo plano

A partir de .NET Framework 4.5, la recolección de elementos no utilizados de servidor en segundo plano es el modo predeterminado. Para elegir este modo, establezca el atributo `enabled` del [elemento \<gcServer>](../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) en `true` en el esquema de configuración del tiempo de ejecución. Este modo funciona de forma similar a la recolección de elementos no utilizados de estación de trabajo en segundo plano, descrita en la sección anterior, pero hay algunas diferencias. La recolección de elementos no utilizados de estación de trabajo en segundo plano usa un subproceso dedicado de recolección de elementos no utilizados en segundo plano, mientras que la recolección de elementos no utilizados de servidor en segundo plano utiliza varios subprocesos, normalmente un subproceso dedicado para cada procesador lógico. A diferencia del subproceso de recolección de elementos no utilizados en segundo plano de la estación de trabajo, no se agota el tiempo de espera de estos subprocesos.

En la siguiente ilustración se muestra la recolección de elementos no utilizados en segundo plano realizada en un subproceso dedicado independiente en un servidor:

![Diagrama que muestra la recolección de elementos no utilizados de servidor en segundo plano.](./media/fundamentals/background-server-garbage-collection.png)

## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
