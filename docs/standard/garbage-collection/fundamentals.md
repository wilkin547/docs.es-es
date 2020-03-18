---
title: Fundamentos de la recolección de elementos no utilizados
description: Obtenga información sobre cómo funciona el recolector de elementos no utilizados y cómo puede configurarse para un rendimiento óptimo.
ms.date: 11/15/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, generations
- garbage collection, background
- garbage collection, concurrent
- garbage collection, server
- garbage collection, workstation
- garbage collection, managed heap
ms.assetid: 67c5a20d-1be1-4ea7-8a9a-92b0b08658d2
ms.openlocfilehash: ea8aef03d2f5837f35ecb31209e57853c0c8257b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398548"
---
# <a name="fundamentals-of-garbage-collection"></a>Fundamentos de la recolección de elementos no utilizados

En el Common Language Runtime (CLR), el recolector de elementos no utilizados (GC) actúa como administrador de memoria automático. Proporciona las siguientes ventajas:

- Permite desarrollar la aplicación sin tener que liberar memoria manualmente.

- Asigna con eficacia los objetos del montón administrado.

- Reclama los objetos que ya no se utilizan, borra la memoria correspondiente y mantiene la memoria disponible para asignaciones futuras. Los objetos administrados obtienen automáticamente contenido limpio desde el principio, de modo que sus constructores no tienen que inicializar todos los campos de datos.

- Proporciona seguridad de memoria, al asegurarse de que un objeto no pueda utilizar el contenido de otro objeto.

En este artículo se describen los conceptos básicos de la recolección de elementos no utilizados.

## <a name="fundamentals-of-memory"></a>Fundamentos de memoria

En la lista siguiente se resumen los conceptos importantes de memoria de CLR.

- Cada proceso tiene propio espacio de direcciones virtuales independiente. Todos los procesos del equipo comparten la misma memoria física y el archivo de paginación, si hay alguno.

- De forma predeterminada, en los equipos de 32 bits, cada proceso tiene un espacio de direcciones virtuales en modo usuario de 2 GB.

- Como desarrollador de aplicaciones, solo trabaja con el espacio de direcciones virtuales y nunca manipula la memoria física directamente. El recolector de elementos no utilizados asigna y libera memoria virtual en el montón administrado.

  Si está escribiendo código nativo, use funciones de Windows para trabajar con el espacio de direcciones virtuales. Estas funciones asignan y liberan memoria virtual en pilas nativas.

- La memoria virtual puede estar en tres estados:

  - Libre. El bloque de memoria no tiene ninguna referencia a ella y está disponible para su asignación.

  - Reservado. El bloque de memoria está disponible para su uso y no se puede emplear para ninguna otra solicitud de asignación. Sin embargo, no puede almacenar datos en este bloque de memoria hasta que se confirme.

  - Confirmado. El bloque de memoria se asigna al almacenamiento físico.

- El espacio de direcciones virtuales puede llegar a fragmentarse. Esto significa que hay bloques libres, también conocidos como marcadores, en el espacio de direcciones. Cuando se solicita una asignación de memoria virtual, el administrador de memoria virtual tiene que encontrar un único bloque libre que sea suficientemente grande para satisfacer esa solicitud de asignación. Aunque tenga 2 GB de espacio disponible, la asignación que necesita 2 GB será incorrecta a menos que todo ese espacio disponible esté en un único bloque de direcciones.

- Puede quedarse sin memoria si no hay suficiente espacio de direcciones virtuales para reservar o espacio físico para confirmar.

  El archivo de paginación se usa aunque haya poca necesidad de memoria física (es decir, demanda de memoria física). La primera vez que se necesita mucha memoria física, el sistema operativo debe hacer sitio en la memoria física para almacenar los datos y hace una copia de seguridad en el archivo de paginación de algunos datos que están en la memoria física. Esos datos no se paginan hasta que no se necesitan, por lo que es posible encontrar paginación en situaciones donde haya muy poca necesidad de memoria física.

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

Cuantos menos objetos se asignen al montón, menos trabajo tendrá que hacer el recolector de elementos no utilizados. Al asignar objetos, no use valores redondeados que superen sus necesidades; por ejemplo, no asigne una matriz de 32 bytes si solo necesita 15 bytes.

Cuando se desencadena una recolección de elementos no utilizados, el recolector de elementos no utilizados reclama la memoria ocupada por objetos muertos. El proceso de reclamación compacta los objetos activos para moverlos juntos, y el espacio muerto se quita, para reducir el montón. De este modo, se asegura de que los objetos que se asignan juntos permanezcan juntos en el montón administrado, a fin de conservar su situación.

La tendencia a la intrusión (frecuencia y duración) de las recolecciones de elementos no utilizados es el resultado del volumen de asignaciones y la cantidad de memoria que sobrevivió en el montón administrado.

El montón considerarse una acumulación de dos montones: el [montón de objetos grandes](large-object-heap.md) y el montón de objetos pequeños.

El [montón de objetos grandes](large-object-heap.md) contiene objetos muy grandes de 85 000 bytes o más. Los objetos del montón de objetos grandes suelen ser matrices. Es raro que un objeto de instancia sea sumamente grande.

> [!TIP]
> Puede [configurar el tamaño de umbral](../../core/run-time-config/garbage-collector.md#large-object-heap-threshold) para que los objetos se dirijan al montón de objetos grandes.

## <a name="generations"></a>Generaciones

El montón se organiza en generaciones, para poder administrar objetos de larga y corta duración. La recolección de elementos no utilizados se produce principalmente con la reclamación de objetos de corta duración que suelen ocupar solamente una parte reducida del montón. Hay tres generaciones de objetos en el montón:

- **Generación 0**. Es la generación más joven y contiene los objetos de corta duración. Un ejemplo de objeto de corta duración es una variable temporal. La recolección de elementos no utilizados se produce con mayor frecuencia en esta generación.

  Los objetos recién asignados constituyen una nueva generación de objetos y son colecciones de la generación 0, implícitamente. Sin embargo, si son objetos grandes, van al montón de objetos grandes en una colección de la generación 2.

  La mayoría de los objetos se reclaman para la recolección de elementos no utilizados en la generación 0 y no sobreviven a la generación siguiente.

- **Generación 1** Esta generación contiene objetos de corta duración y sirve como búfer entre los objetos de corta y larga duración.

- **Generación 2** Esta generación contiene los objetos de larga duración. Un ejemplo de objeto de larga duración es un objeto de una aplicación de servidor que contiene datos estáticos que están activos mientras dura el proceso.

Las recolecciones de elementos no utilizados se producen en generaciones concretas según lo permitan las condiciones. La recolección de una generación significa recolectar los objetos de esa generación y de todas las generaciones anteriores. Una recolección de elementos no utilizados de la generación 2 se denomina también recolección de elementos no utilizados completa, porque reclama todos los objetos de todas las generaciones (es decir, todos los objetos del montón administrado).

### <a name="survival-and-promotions"></a>Supervivencia y promociones

Los objetos que no se reclaman en una recolección de elementos no utilizados se denominan supervivientes y se promueven a la generación siguiente. Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 0 se promueven a la generación 1; los que sobreviven a una recolección de elementos no utilizados de la generación 1 se promueven a la generación 2; y los que sobreviven a una recolección de elementos no utilizados de la generación 2 permanecen en esa misma generación.

Cuando el recolector de elementos no utilizados detecta que la tasa de supervivencia es alta en una generación, aumenta el umbral de asignaciones para esa generación. La colección siguiente obtiene un tamaño sustancial de memoria reclamada. El CLR equilibra continuamente dos prioridades: no permitir que el espacio de trabajo de una aplicación adquiera un tamaño excesivo al retrasar la recolección de elementos no utilizados y no permitir que la recolección de elementos no utilizados se ejecute con mucha frecuencia.

### <a name="ephemeral-generations-and-segments"></a>Generaciones y segmentos efímeros

Dado que los objetos de las generaciones 0 y 1 son de corta duración, estas generaciones se denominan generaciones efímeras.

Las generaciones efímeras se deben asignar en el segmento de memoria denominado segmento efímero. Cada nuevo segmento adquirido por el recolector de elementos no utilizados se convierte en el nuevo segmento efímero y contiene los objetos que sobrevivieron a una recolección de elementos no utilizados de la generación 0. El segmento efímero anterior se convierte en el nuevo segmento de la generación 2.

El tamaño del segmento efímero varía según si un sistema es de 32 bits o de 64 bits y del tipo del recolector de elementos no utilizados que se está ejecutando. En la siguiente tabla se muestran los valores predeterminados.

||32 bits|64 bits|
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

  - un límite de memoria en un contenedor o
  - las opciones de configuración en tiempo de ejecución [GCHeapHardLimit](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitcomplus_gcheaphardlimit) o [GCHeapHardLimitPercent](../../core/run-time-config/garbage-collector.md#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)

El recolector de elementos no utilizados utiliza la siguiente información para determinar si los objetos están activos:

- **Raíces de la pila**. Variables de pila proporcionadas por el compilador Just-In-Time (JIT) y el rastreador de pila. Las optimizaciones de JIT pueden prolongar o acortar regiones de código en las que se notifican variables de pila al recolector de elementos no utilizados.

- **Identificadores de recolección de elementos no utilizados**. Identificadores que señalan a objetos administrados y que se pueden asignar mediante código de usuario o mediante Common Language Runtime.

- **Datos estáticos**. Objetos estáticos de dominios de aplicación que podrían hacer referencia a otros objetos. Cada dominio de aplicación realiza el seguimiento de sus objetos estáticos.

Antes de que iniciarse una recolección de elementos no utilizados, todos los subprocesos administrados se suspenden salvo el subproceso que activó la recolección de elementos no utilizados.

En la ilustración siguiente se muestra un subproceso que desencadena una recolección de elementos no utilizados, lo que provoca la suspensión de los demás subprocesos.

![Cuando un subproceso activa una recolección de elementos no utilizados](./media/gc-triggered.png)

## <a name="manipulate-unmanaged-resources"></a>Manipulación de recursos no administrados

Si los objetos administrados hacen referencia a objetos no administrados mediante sus identificadores de archivos nativos, es necesario liberar explícitamente los objetos no administrados, ya que el recolector de elementos no utilizados únicamente realiza el seguimiento de la memoria del montón administrado.

Los usuarios del objeto administrado podrían no disponer de los recursos nativos utilizados por el objeto. Para realizar la limpieza, puede hacer que el objeto administrado sea susceptible de finalización. La finalización está compuesta de acciones de limpieza que se ejecutan cuando el objeto ya no se utiliza. Cuando el objeto administrado muere, realiza acciones de limpieza que se especifican en su método finalizador.

Cuando se detecta que un objeto susceptible de finalización está muerto, su finalizador se coloca en una cola para que se ejecuten sus acciones de limpieza, pero el objeto en sí se promueve a la generación siguiente. Por tanto, tendrá que esperar hasta la siguiente recolección de elementos no utilizados que se produzca en esa generación (y que no tiene por qué ser necesariamente la próxima recolección de elementos no utilizados) para determinar si se ha recuperado el objeto.

Para obtener más información acerca de la finalización, vea <xref:System.Object.Finalize?displayProperty=nameWithType>.

## <a name="workstation-and-server-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo y de servidor

El recolector de elementos no utilizados se ajusta automáticamente y puede funcionar en gran variedad de escenarios. Puede usar un [valor del archivo de configuración](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) para establecer el tipo de recolección de elementos no utilizados en función de las características de la carga de trabajo. El CLR proporciona los tipos siguientes de recolección de elementos no utilizados:

- La recolección de elementos no utilizados (GC) de estación de trabajo está diseñada para aplicaciones cliente. Es el tipo de GC predeterminado para aplicaciones independientes. En el caso de las aplicaciones hospedadas, por ejemplo, las que se hospedan en ASP.NET, el host determina el tipo de GC predeterminado.

  La recolección de elementos no utilizados de estación de trabajo puede ser simultánea o no simultánea. La recolección simultánea de elementos no utilizados permite que los subprocesos administrados continúen con sus operaciones durante una recolección de elementos no utilizados. La [recolección de elementos no utilizados en segundo plano](#background-workstation-garbage-collection) reemplaza la [recolección simultánea de elementos no utilizados](#concurrent-garbage-collection) en .NET Framework 4 y versiones posteriores.

- Recolección de elementos no utilizados de servidor, diseñada para las aplicaciones de servidor que necesitan un alto nivel de rendimiento y escalabilidad.

  - En .NET Core, la recolección de elementos no utilizados de servidor puede ser no simultánea o en segundo plano.

  - En .NET Framework 4.5 y versiones posteriores, la recolección de elementos no utilizados de servidor puede ser no simultánea o en segundo plano (la recolección de elementos no utilizados en segundo plano reemplaza la recolección de elementos no utilizados simultánea). En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados de servidor no es simultánea.

En las siguientes ilustraciones se muestran los subprocesos dedicados que realizan la recolección de elementos no utilizados en un servidor:

![Subprocesos de recolección de elementos no utilizados de servidor](./media/gc-server.png)

### <a name="compare-workstation-and-server-garbage-collection"></a>Comparar la recolección de elementos no utilizados de estación de trabajo y de servidor

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de estación de trabajo:

- La recolección se produce en el subproceso del usuario que desencadenó la recolección de elementos no utilizados y permanece en la misma prioridad. Como los subprocesos de usuario suelen ejecutarse con prioridad normal, el recolector de elementos no utilizados (que se ejecuta en un subproceso de prioridad normal) debe competir con otros subprocesos por el tiempo de la CPU. (Los subprocesos que ejecutan código nativo no se suspenden en la recolección de elementos no utilizados de servidor o de estación de trabajo).

- La recolección de elementos no utilizados de estación de trabajo siempre se utiliza en un equipo que tiene un solo procesador, sin tener en cuenta el [valor de configuración](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

Estas son algunas consideraciones sobre subprocesos y rendimiento para la recolección de elementos no utilizados de servidor:

- La recolección se produce en varios subprocesos dedicados que se ejecutan en el nivel de prioridad `THREAD_PRIORITY_HIGHEST` .

- Para cada CPU se proporciona un montón y un subproceso dedicado para realizar recolección de elementos no utilizados y, al mismo tiempo, se recolectan los montones. Cada montón contiene un montón de objetos pequeños y un montón de objetos grandes; a todos ellos se puede tener acceso mediante código de usuario. Los objetos de montones diferentes pueden hacerse referencia a entre sí.

- Dado que varios subprocesos de recolección de elementos no utilizados funcionan juntos, la recolección de elementos no utilizados de servidor es más rápida que la de estación de trabajo, con un montón del mismo tamaño.

- La recolección de elementos no utilizados de servidor suele tener segmentos de mayor tamaño. Sin embargo, esto es solo una generalización: el tamaño de los segmentos es específico de la implementación y está sujeto a cambios. No haga ninguna suposición sobre el tamaño de los segmentos asignados por el recolector de elementos no utilizados al optimizar la aplicación.

- La recolección de elementos no utilizados de servidor puede consumir gran cantidad de recursos. Por ejemplo, imagine que hay 12 procesos que usan GC de servidor ejecutándose en un equipo con 4 procesadores. Si todos los procesos tienen que recopilar elementos no utilizados al mismo tiempo, interfieren entre sí, ya que serían 12 subprocesos programados en el mismo procesador. Si los procesos están activos, no es recomendable que todos usen GC de servidor.

Si se ejecutan centenares de instancias de una aplicación, puede ser más conveniente utilizar la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados deshabilitada. De este modo se realizarán menos cambios de contexto, lo que puede mejorar el rendimiento.

## <a name="background-workstation-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo en segundo plano

En la recolección de elementos no utilizados de estación de trabajo en segundo plano, las generaciones efímeras (0 y 1) se recolectan según sea necesario mientras la recolección de la generación 2 está en curso. La recolección de elementos no utilizados de estación de trabajo en segundo plano se realiza en un subproceso dedicado y solamente se aplica a las recolecciones de la generación 2.

La recolección de elementos no utilizados en segundo plano se puede habilitar o deshabilitar de forma predeterminada con la opción de configuración [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) o la opción [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) en aplicaciones de .NET Core.

> [!NOTE]
> La recolección de elementos no utilizados en segundo plano reemplaza la [recolección simultánea de elementos no utilizados](#concurrent-garbage-collection) en .NET Framework 4 y versiones posteriores. En .NET Framework 4, solo se admite para la recolección de elementos no utilizados de estación de trabajo. A partir de .NET Framework 4.5, la recolección de elementos no utilizados en segundo plano está disponible para estaciones de trabajo y servidores.

Una recolección de las generaciones efímeras durante una recolección de elementos no utilizados en segundo plano se denomina recolección de elementos no utilizados en primer plano. Cuando se producen recolecciones de elementos no utilizados en primer plano, se suspenden todos los subprocesos administrados.

Cuando hay en curso una recolección de elementos no utilizados en segundo plano y se han asignado suficientes objetos en la generación 0, el CLR realiza una recolección de elementos no utilizados en primer plano de las generaciones 0 o 1. El subproceso de recolección de elementos no utilizados en segundo plano dedicado realiza comprobaciones en puntos seguros frecuentes para determinar si existe alguna solicitud de recolección de elementos no utilizados en primer plano. Si la hay, la recolección en segundo plano se suspende para que la recolección de elementos no utilizados en primer plano se pueda llevar a cabo. Una vez completada la recolección de elementos no utilizados en primer plano, se reanudan el subproceso de recolección de elementos no utilizados en segundo plano dedicado y los subprocesos del usuario.

La recolección de elementos no utilizados en segundo plano quita las restricciones de asignación impuestas por la recolección simultánea de elementos no utilizados, porque se pueden producir recolecciones de elementos no utilizados efímeras durante una recolección en segundo plano. La recolección de elementos no utilizados en segundo plano puede eliminar objetos inactivos procedentes de generaciones efímeras. También puede expandir el montón si es necesario durante una recolección de elementos no utilizados de generación 1.

En la siguiente ilustración se muestra la recolección de elementos no utilizados en segundo plano realizada en un subproceso dedicado independiente en una estación de trabajo:

![Recolección de elementos no utilizados de estación de trabajo en segundo plano](./media/fundamentals/background-workstation-garbage-collection.png)

### <a name="background-server-garbage-collection"></a>Recolección de elementos no utilizados de servidor en segundo plano

A partir de .NET Framework 4.5, la recolección de elementos no utilizados de servidor en segundo plano es el modo predeterminado.

La recolección de elementos no utilizados de servidor en segundo plano funciona de forma similar a la recolección de elementos no utilizados de estación de trabajo en segundo plano, descrita en la sección anterior, pero hay algunas diferencias:

- La recolección de elementos no utilizados de estación de trabajo en segundo plano usa un subproceso dedicado de recolección de elementos no utilizados en segundo plano, mientras que la recolección de elementos no utilizados de servidor en segundo plano utiliza varios subprocesos. Normalmente, hay un subproceso dedicado para cada procesador lógico.

- A diferencia del subproceso de recolección de elementos no utilizados en segundo plano de la estación de trabajo, no se agota el tiempo de espera de estos subprocesos.

En la siguiente ilustración se muestra la recolección de elementos no utilizados en segundo plano realizada en un subproceso dedicado independiente en un servidor:

![Recolección de elementos no utilizados de servidor en segundo plano](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Recolección de elementos no utilizados simultánea

> [!TIP]
> Esta sección es aplicable a:
>
> - .NET Framework 3.5 y versiones anteriores para la recolección de elementos no utilizados de estación de trabajo
> - .NET Framework 4 y versiones anteriores para la recolección de elementos no utilizados de servidor
>
> La [recolección de elementos no utilizados en segundo plano](#background-workstation-garbage-collection) reemplaza a la de elementos no utilizados simultánea en versiones posteriores.

En la recolección de elementos no utilizados de estación de trabajo o de servidor, se puede [habilitar la recolección simultánea de elementos no utilizados](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), que permite ejecutar subprocesos de manera simultánea con un subproceso dedicado que realiza la recolección de elementos no utilizados durante la mayor parte del tiempo que dura la recolección. Esta opción solo afecta a las recolecciones de elementos no utilizados de la generación 2; las generaciones 0 y 1 no son nunca simultáneas porque finalizan muy rápidamente.

La recolección de elementos no utilizados simultánea permite mayor capacidad de respuesta de las aplicaciones interactivas, pues minimiza las pausas en una recolección. Los subprocesos administrados pueden continuar ejecutándose la mayoría del tiempo mientras se ejecuta el subproceso de recolección de elementos no utilizados simultánea. Esto da lugar a pausas más cortas mientras se está produciendo una recolección de elementos no utilizados.

La recolección de elementos no utilizados simultánea se realiza en un subproceso dedicado. De forma predeterminada, el CLR ejecuta la recolección de elementos no utilizados de estación de trabajo con la simultaneidad habilitada. Esto se cumple en los equipos de uno o varios procesadores.

En la siguiente se muestra la recolección de elementos no utilizados simultánea realizada en un subproceso dedicado independiente.

![Subprocesos de recolección simultánea de elementos no utilizados](./media/gc-concurrent.png)

## <a name="see-also"></a>Vea también

- [Opciones de configuración para la recolección de elementos no utilizados](../../core/run-time-config/garbage-collector.md)
- [Recolección de elementos no utilizados](index.md)
