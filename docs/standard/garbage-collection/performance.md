---
title: Recolección de elementos no utilizados y rendimiento
description: Obtenga información sobre los problemas relacionados con la recolección de elementos no utilizados y el uso de memoria. Aprenda a minimizar el efecto de la recolección de elementos no utilizados en las aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, troubleshooting
- garbage collection, performance
ms.assetid: c203467b-e95c-4ccf-b30b-953eb3463134
ms.openlocfilehash: 15ca3fd06bb607a4f0257b4c5cd62f9c935c6913
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827547"
---
# <a name="garbage-collection-and-performance"></a>Recolección de elementos no utilizados y rendimiento

En este tema se describen problemas relacionados con la recolección de elementos no utilizados y el uso de memoria. Se tratan problemas relativos al montón administrado y se explica cómo minimizar el efecto de la recolección de elementos no utilizados en las aplicaciones. Cada problema contiene vínculos a procedimientos que puede emplear para investigar los problemas.

## <a name="performance-analysis-tools"></a>Herramientas de análisis de rendimiento

En las próximas siguientes se describen las herramientas disponibles para investigar los problemas de uso de memoria y de recolección de elementos no utilizados. Los [procedimientos](#performance-check-procedures) que se muestran más adelante en este tema hacen referencia a estas herramientas.

### <a name="memory-performance-counters"></a>Contadores de rendimiento de memoria

Puede usar contadores de rendimiento para recopilar datos de rendimiento. Para obtener instrucciones, vea [Generar perfiles en tiempo de ejecución](../../framework/debug-trace-profile/runtime-profiling.md). La categoría CLR Memory de .NET de los contadores de rendimiento, como se describe en [Contadores de rendimiento en .NET Framework](../../framework/debug-trace-profile/performance-counters.md), ofrece información sobre el recolector de elementos no utilizados.

### <a name="debugging-with-sos"></a>Depurar con SOS

Puede usar el [depurador de Windows (WinDbg)](/windows-hardware/drivers/debugger/index) para inspeccionar objetos del montón administrado.

Para instalar WinDbg, instale las Herramientas de depuración para Windows desde la página [Download Debugging Tools for Windows](/windows-hardware/drivers/debugger/debugger-download-tools) (Descarga de Herramientas de depuración para Windows).

### <a name="garbage-collection-etw-events"></a>Eventos ETW de recolección de elementos no utilizados

El Seguimiento de eventos para Windows (ETW) es un sistema de seguimiento que complementa la compatibilidad con la generación de perfiles y la depuración proporcionada por .NET. A partir de .NET Framework 4, los [eventos de ETW de recolección de elementos no utilizados](../../framework/performance/garbage-collection-etw-events.md) capturan información útil para analizar el montón administrado desde un punto de vista estadístico. Por ejemplo, el evento `GCStart_V1`, que se genera cuando está a punto de producirse una recolección de elementos no utilizados, proporciona la siguiente información:

- La generación de objetos que se recolecta.

- Lo que desencadenó la recolección de elementos no utilizados.

- Tipo de recolección de elementos no utilizados (simultánea o no simultánea).

El registro de eventos ETW es eficaz y no enmascara ningún problema de rendimiento asociado a la recolección de elementos no utilizados. Un proceso puede proporcionar sus propios eventos junto con los eventos ETW. Cuando se registran, tanto los eventos de la aplicación como los eventos de la recolección de elementos no utilizados se pueden poner en correlación para determinar cómo y cuándo se producen problemas de pila. Por ejemplo, una aplicación de servidor puede proporcionar eventos al comienzo y al final de una solicitud de cliente.

### <a name="the-profiling-api"></a>La API de generación de perfiles

Las interfaces de generación de perfiles de Common Language Runtime (CLR) proporcionan información detallada sobre los objetos que se vieron afectados durante la recolección de elementos no utilizados. Un generador de perfiles puede recibir una notificación cuando se inicia y finaliza una recolección de elementos no utilizados. Puede proporcionar informes sobre los objetos del montón administrado, incluida una identificación de los objetos de cada generación. Para más información, consulte [Información general sobre la generación de perfiles](../../framework/unmanaged-api/profiling/profiling-overview.md).

Los generadores de perfiles pueden proporcionar información completa. Sin embargo, los generadores de perfiles complejos pueden modificar el comportamiento de una aplicación.

### <a name="application-domain-resource-monitoring"></a>Supervisión de recursos de dominio de aplicación

A partir de .NET Framework 4, la supervisión de recursos del dominio de la aplicación (ARM) permite a los anfitriones supervisar el uso de la CPU y la memoria por parte del dominio de la aplicación. Para más información, consulte [Supervisión de recursos de dominio de aplicación](app-domain-resource-monitoring.md).

## <a name="troubleshooting-performance-issues"></a>Solucionar problemas de rendimiento

El primer paso consiste en [determinar si el problema es realmente la recolección de elementos no utilizados](#IsGC). Si determina que lo es, seleccione un elemento de la lista siguiente para solucionar el problema.

- [Se inicia una excepción de memoria insuficiente](#Issue_OOM)

- [El proceso usa demasiada memoria](#Issue_TooMuchMemory)

- [El recolector de elementos no utilizados no recupera los objetos con la rapidez suficiente](#Issue_NotFastEnough)

- [El montón administrado está demasiado fragmentado](#Issue_Fragmentation)

- [Las pausas de la recolección de elementos no utilizados son demasiado largas](#Issue_LongPauses)

- [La generación 0 es demasiado grande](#Issue_Gen0)

- [El uso de CPU durante una recolección de elementos no utilizados es demasiado alto](#Issue_HighCPU)

<a name="Issue_OOM"></a>

### <a name="issue-an-out-of-memory-exception-is-thrown"></a>Problema: Se inicia una excepción de memoria insuficiente

Hay dos casos justificados para que se produzca una excepción <xref:System.OutOfMemoryException> administrada:

- La escasez de memoria virtual.

  El recolector de elementos no utilizados asigna memoria del sistema en segmentos de un tamaño predeterminado. Si una asignación necesita un segmento adicional, pero no queda ningún bloque libre contiguo en el espacio de memoria virtual del proceso, se producirá un error en la asignación del montón administrado.

- No tener suficiente memoria física para asignar.

|Comprobaciones de rendimiento|
|------------------------|
|[Determine si la excepción de memoria insuficiente está administrada.](#OOMIsManaged)<br /><br /> [Determine cuánta memoria virtual se puede reservar.](#GetVM)<br /><br /> [Determine si hay suficiente memoria física.](#Physical)|

Si determina que la excepción no es legítima, póngase en contacto con el servicio de atención al cliente y soporte técnico de Microsoft, y proporcione la información siguiente:

- La pila con la excepción administrada de memoria insuficiente.

- Un volcado de memoria completo.

- Los datos que demuestran que no es una excepción legítima de memoria insuficiente, incluidos los datos que muestran que la memoria virtual o la memoria física no supone ningún problema.

<a name="Issue_TooMuchMemory"></a>

### <a name="issue-the-process-uses-too-much-memory"></a>Problema: El proceso usa demasiada memoria

Un supuesto común es que el uso de memoria que aparece en la pestaña **Rendimiento** del Administrador de tareas de Windows puede indicar cuándo se está usando demasiada memoria. Sin embargo, esa información pertenece al espacio de trabajo; no proporciona información sobre el uso de memoria virtual.

Si determina que el problema está provocado por el montón administrado, debe medir el montón administrado a lo largo del tiempo para determinar cualquier patrón.

Si determina que el problema no está provocado por el montón administrado, debe usar la depuración nativa.

|Comprobaciones de rendimiento|
|------------------------|
|[Determine cuánta memoria virtual se puede reservar.](#GetVM)<br /><br /> [Determine cuánta memoria está confirmando el montón administrado.](#ManagedHeapCommit)<br /><br /> [Determine cuánta memoria reserva el montón administrado.](#ManagedHeapReserve)<br /><br /> [Determine los objetos grandes de la generación 2.](#ExamineGen2)<br /><br /> [Determine las referencias a objetos.](#ObjRef)|

<a name="Issue_NotFastEnough"></a>

### <a name="issue-the-garbage-collector-does-not-reclaim-objects-fast-enough"></a>Problema: El recolector de elementos no utilizados no recupera los objetos con la rapidez suficiente

Cuando parezca que la recolección de elementos no utilizados no está recuperando los objetos según lo esperado, debe determinar si hay alguna referencia segura a esos objetos.

También puede encontrar este problema si no se ha producido ninguna recolección de elementos no utilizados para la generación que contiene un objeto muerto, lo que indica que el finalizador del objeto muerto no se ha ejecutado. Por ejemplo, esto puede ocurrir cuando se ejecuta una aplicación de contenedor uniproceso (STA) y el subproceso que atiende a la cola del finalizador no la puede llamar.

|Comprobaciones de rendimiento|
|------------------------|
|[Compruebe las referencias a objetos.](#ObjRef)<br /><br /> [Determine si se ha ejecutado un finalizador.](#Induce)<br /><br /> [Determine si hay objetos en espera de finalización.](#Finalize)|

<a name="Issue_Fragmentation"></a>

### <a name="issue-the-managed-heap-is-too-fragmented"></a>Problema: El montón administrado está demasiado fragmentado

El nivel de fragmentación se calcula como la proporción de espacio disponible con respecto a la memoria total asignada para la generación. Para la generación 2, un nivel aceptable de fragmentación es inferior al 20%. Puesto que la generación 2 puede llegar a ser muy grande, la proporción de fragmentación es más importante que el valor absoluto.

El hecho de tener mucho espacio disponible en la generación 0 no supone ningún problema porque esta es la generación donde se asignan nuevos objetos.

Siempre se produce fragmentación en el montón de objetos grandes porque no se compacta. Los objetos libres adyacentes se contraen de forma natural en un único espacio para satisfacer las solicitudes de asignación de objetos grandes.

La fragmentación puede convertirse en un problema en las generaciones 1 y 2. Si estas generaciones tienen una gran cantidad de espacio disponible después de una recolección de elementos no utilizados, el uso de objetos de una aplicación puede necesitar modificaciones y debe considerar la posibilidad de volver a evaluar la duración de los objetos de larga duración.

El anclaje excesivo de objetos puede aumentar la fragmentación. Si la fragmentación es elevada, puede que haya demasiados objetos anclados.

Si la fragmentación de la memoria virtual está impidiendo que el recolector de elementos no utilizados agregue segmentos, puede deberse a una de las causas siguientes:

- Carga y descarga frecuentes de muchos ensamblados pequeños.

- Almacenamiento de demasiadas referencias a objetos COM al interoperar con código no administrado.

- Creación de objetos grandes transitorios, lo que hace que el montón de objetos grandes asigne y libere segmentos del montón con frecuencia.

  Al hospedar el CLR, una aplicación puede solicitar que el recolector de elementos no utilizados conserve sus segmentos. Esto reduce la frecuencia de las asignaciones de segmentos. Para ello se emplea la marca STARTUP_HOARD_GC_VM en la [enumeración STARTUP_FLAGS](../../framework/unmanaged-api/hosting/startup-flags-enumeration.md).

|Comprobaciones de rendimiento|
|------------------------|
|[Determine la cantidad de espacio disponible en el montón administrado.](#Fragmented)<br /><br /> [Determine el número de objetos anclados.](#Pinned)|

Si cree que no hay ninguna causa que justifique la fragmentación, póngase en contacto con el servicio de atención al cliente y soporte técnico de Microsoft.

<a name="Issue_LongPauses"></a>

### <a name="issue-garbage-collection-pauses-are-too-long"></a>Problema: Las pausas de la recolección de elementos no utilizados son demasiado largas

La recolección de elementos no utilizados funciona en tiempo real flexible, por lo que una aplicación debe poder tolerar algunas pausas. Un criterio para el tiempo real flexible es que el 95% de las operaciones debe finalizar a tiempo.

En la recolección de elementos no utilizados simultánea, se permite la ejecución de subprocesos administrados durante una recolección, lo que significa que las pausas son mínimas.

Las recolecciones de elementos no utilizados efímeras (las generaciones 0 y 1) solo duran algunos milisegundos, por lo que no suele ser viable reducir las pausas. Sin embargo, puede reducir las pausas en las recolecciones de la generación 2 cambiando el modelo de las solicitudes de asignación de una aplicación.

Otro método más preciso consiste en usar [eventos ETW de recolección de elementos no utilizados](../../framework/performance/garbage-collection-etw-events.md). Puede averiguar los controles de tiempo para las recolecciones si suma las diferencias de marca de tiempo para una secuencia de eventos. La secuencia de recolección completa incluye la suspensión del motor de ejecución, la recolección de elementos no utilizados propiamente dicha y la reanudación del motor de ejecución.

Puede usar [notificaciones de recolección de elementos no utilizados](notifications.md) para determinar si se va a realizar una recolección de generación 2 en un servidor y si redirigir las solicitudes a otro servidor podría solucionar los problemas de las pausas.

|Comprobaciones de rendimiento|
|------------------------|
|[Determine la duración de una recolección de elementos no utilizados.](#TimeInGC)<br /><br /> [Determine lo que desencadenó una recolección de elementos no utilizados.](#Triggered)|

<a name="Issue_Gen0"></a>

### <a name="issue-generation-0-is-too-big"></a>Problema: La generación 0 es demasiado grande

Es probable que la generación 0 tenga un número mayor de objetos en un sistema de 64 bits, sobre todo cuando se usa la recolección de elementos no utilizados de servidor en lugar de la de estación de trabajo. Esto se debe a que el umbral para desencadenar una recolección de elementos no utilizados de generación 0 es más alto en estos entornos y las recolecciones de generación 0 pueden llegar a ser mucho mayores. El rendimiento mejora cuando una aplicación asigna más memoria antes de que se desencadene una recolección de elementos no utilizados.

<a name="Issue_HighCPU"></a>

### <a name="issue-cpu-usage-during-a-garbage-collection-is-too-high"></a>Problema: El uso de CPU durante una recolección de elementos no utilizados es demasiado alto

El uso de CPU será elevado durante una recolección de elementos no utilizados. Si se dedica una cantidad significativa de tiempo de proceso a una recolección de elementos no utilizados, el número de recolecciones es demasiado frecuente o la recolección está durando demasiado. Una proporción de asignación de objetos mayor en el montón administrado hace que la recolección de elementos no utilizados se realice con más frecuencia. Al disminuir la proporción de asignación se reduce la frecuencia de las recolecciones de elementos no utilizados.

Puede supervisar las proporciones de asignación mediante el contador de rendimiento `Allocated Bytes/second`. Para obtener más información, vea [Contadores de rendimiento en .NET Framework](../../framework/debug-trace-profile/performance-counters.md).

La duración de una recolección suele depender del número de objetos que sobrevivan después de la asignación. El recolector de elementos no utilizados debe pasar por una gran cantidad de memoria si hay que recolectar muchos objetos. El trabajo para compactar los supervivientes lleva mucho tiempo. Para determinar cuántos objetos se controlaron durante una recolección, establezca un punto de interrupción en el depurador al final de una recolección de elementos no utilizados para una generación especificada.

|Comprobaciones de rendimiento|
|------------------------|
|[Determine si el uso elevado de CPU está provocado por la recolección de elementos no utilizados.](#HighCPU)<br /><br /> [Establezca un punto de interrupción al final de la recolección de elementos no utilizados.](#GenBreak)|

## <a name="troubleshooting-guidelines"></a>Instrucciones para la solución de problemas

En esta sección se describen instrucciones debe tener en cuenta cuando empiece las investigaciones.

### <a name="workstation-or-server-garbage-collection"></a>Recolección de elementos no utilizados de estación de trabajo o de servidor

Determine si está usando el tipo correcto de recolección de elementos no utilizados. Si la aplicación emplea varios subprocesos e instancias de objeto, use la recolección de elementos no utilizados de servidor en lugar de la de estación de trabajo. La recolección de elementos no utilizados de servidor funciona en varios subprocesos, mientras que la de estación de trabajo necesita que varias instancias de una aplicación ejecuten sus propios subprocesos de recolección de elementos no utilizados y compitan por el tiempo de CPU.

Una aplicación que tenga una carga baja y realice tareas con poca frecuencia en segundo plano, como un servicio, puede usar la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados deshabilitada.

### <a name="when-to-measure-the-managed-heap-size"></a>Cuándo medir el tamaño del montón administrado

A menos que esté usando un generador de perfiles, tendrá que establecer un modelo de medida coherente para diagnosticar eficazmente los problemas de rendimiento. Tenga en cuenta lo siguiente a la hora de establecer una programación:

- Si mide después de una recolección de elementos no utilizados de generación 2, todo el montón administrado estará libre de elementos no utilizados (objetos muertos).

- Si mide inmediatamente después de una recolección de elementos no utilizados de generación 0, los objetos de las generaciones 1 y 2 no se recolectarán todavía.

- Si mide inmediatamente antes de una recolección de elementos no utilizados, se medirá toda la asignación posible antes de que comience dicha recolección.

- La medición durante una recolección de elementos no utilizados es problemática, ya que las estructuras de datos del recolector de elementos no utilizados no están en un estado válido para el cruce seguro y quizás no se obtengan resultados completos. Esto es intencionado.

- Cuando se usa la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados, los objetos recuperados no se compactan, por lo que el tamaño del montón puede ser igual o mayor (la fragmentación puede hacer que parezca mayor).

- La recolección de elementos no utilizados simultánea en la generación 2 se retrasa cuando la carga de memoria física es demasiado alta.

En el procedimiento siguiente se describe cómo establecer un punto de interrupción para que pueda medir el montón administrado.

<a name="GenBreak"></a>

#### <a name="to-set-a-breakpoint-at-the-end-of-garbage-collection"></a>Para establecer un punto de interrupción al final de la recolección de elementos no utilizados

- En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente:

  **bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**

  donde **GcCondemnedGeneration** se establece en la generación que se prefiera. Este comando necesita símbolos privados.

  Este comando fuerza una interrupción si **RestartEE** se ejecuta una vez recuperados los objetos de generación 2 para la recolección de elementos no utilizados.

  En la recolección de elementos no utilizados de servidor, solo un subproceso llama a **RestartEE**, por lo que el punto de interrupción solo se producirá una vez durante una recolección de elementos no utilizados de generación 2.

## <a name="performance-check-procedures"></a>Procedimientos para comprobar el rendimiento

En esta sección se describen los procedimientos siguientes para aislar la causa del problema de rendimiento:

- [Determine si el problema está provocado por la recolección de elementos no utilizados.](#IsGC)

- [Determine si la excepción de memoria insuficiente está administrada.](#OOMIsManaged)

- [Determine cuánta memoria virtual se puede reservar.](#GetVM)

- [Determine si hay suficiente memoria física.](#Physical)

- [Determine cuánta memoria está confirmando el montón administrado.](#ManagedHeapCommit)

- [Determine cuánta memoria reserva el montón administrado.](#ManagedHeapReserve)

- [Determine los objetos grandes de la generación 2.](#ExamineGen2)

- [Determine las referencias a objetos.](#ObjRef)

- [Determine si se ha ejecutado un finalizador.](#Induce)

- [Determine si hay objetos en espera de finalización.](#Finalize)

- [Determine la cantidad de espacio disponible en el montón administrado.](#Fragmented)

- [Determine el número de objetos anclados.](#Pinned)

- [Determine la duración de una recolección de elementos no utilizados.](#TimeInGC)

- [Determine lo que desencadenó una recolección de elementos no utilizados.](#Triggered)

- [Determine si el uso elevado de CPU está provocado por la recolección de elementos no utilizados.](#HighCPU)

<a name="IsGC"></a>

### <a name="to-determine-whether-the-problem-is-caused-by-garbage-collection"></a>Para determinar si el problema está provocado por la recolección de elementos no utilizados

- Examine los dos contadores de rendimiento de memoria siguientes:

  - **% de tiempo de la GC**. Muestra el porcentaje de tiempo transcurrido que se dedicó a realizar una recolección de elementos no utilizados después del último ciclo de recolección. Use este contador para determinar si el recolector de elementos no utilizados está dedicando demasiado tiempo a hacer que haya espacio disponible en el montón administrado. Si el tiempo dedicado a la recolección de elementos no utilizados es relativamente bajo, podría indicar un problema de recursos fuera del montón administrado. Puede que este contador no sea exacto cuando se invoca una recolección de elementos no utilizados simultánea o en segundo plano.

  - **Número de bytes totales confirmados**. Muestra la cantidad de memoria virtual confirmada actualmente por el recolector de elementos no utilizados. Use este contador para determinar si la memoria usada por el recolector de elementos no utilizados es una parte excesiva de la memoria que su aplicación emplea.

  La mayoría de los contadores de rendimiento de memoria se actualizan al final de cada recolección de elementos no utilizados. Por tanto, puede que no reflejen las condiciones actuales sobre las que desea obtener información.

<a name="OOMIsManaged"></a>

### <a name="to-determine-whether-the-out-of-memory-exception-is-managed"></a>Para determinar si la excepción de memoria insuficiente está administrada

1. En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando de impresión de excepciones (**pe**):

    **!pe**

    Si la excepción es administrada, se mostrará <xref:System.OutOfMemoryException> como el tipo de excepción, como se muestra en el ejemplo siguiente.

    ```console
    Exception object: 39594518
    Exception type: System.OutOfMemoryException
    Message: <none>
    InnerException: <none>
    StackTrace (generated):
    ```

2. Si el resultado no especifica ninguna excepción, tiene que determinar de qué subproceso procede la excepción de memoria insuficiente. Escriba el comando siguiente en el depurador para mostrar todos los subprocesos con sus pilas de llamadas:

    **~\*KB**

    El argumento `RaiseTheException` indica el subproceso con la pila que tiene llamadas de excepción. Este es el objeto de excepción administrado.

    ```console
    28adfb44 7923918f 5b61f2b4 00000000 5b61f2b4 mscorwks!RaiseTheException+0xa0
    ```

3. Puede usar el comando siguiente para volcar las excepciones anidadas.

    **!pe -nested**

    Si no encuentra ninguna excepción, la excepción de memoria insuficiente se originó desde código no administrado.

<a name="GetVM"></a>

### <a name="to-determine-how-much-virtual-memory-can-be-reserved"></a>Para determinar cuánta memoria virtual se puede reservar

- En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente para obtener la mayor región disponible:

  **!address -summary**

  La mayor región disponible se muestra como en el resultado siguiente.

  ```console
  Largest free region: Base 54000000 - Size 0003A980
  ```

  En este ejemplo, el tamaño de la mayor región disponible es de aproximadamente 24000 KB (3A980 en hexadecimal). Esta región es mucho menor que cuando el recolector de elementos no utilizados necesita un segmento.

  o bien

- Use el comando **vmstat**:

  **!vmstat**

  La mayor región disponible es el valor mayor de la columna MAXIMUM, como se muestra en el resultado siguiente.

  ```console
  TYPE        MINIMUM   MAXIMUM     AVERAGE   BLK COUNT   TOTAL
  ~~~~        ~~~~~~~   ~~~~~~~     ~~~~~~~   ~~~~~~~~~~  ~~~~
  Free:
  Small       8K        64K         46K       36          1,671K
  Medium      80K       864K        349K      3           1,047K
  Large       1,384K    1,278,848K  151,834K  12          1,822,015K
  Summary     8K        1,278,848K  35,779K   51          1,824,735K
  ```

<a name="Physical"></a>

### <a name="to-determine-whether-there-is-enough-physical-memory"></a>Para determinar si hay suficiente memoria física

1. Inicie el Administrador de tareas de Windows.

2. En la pestaña **Rendimiento**, busque el valor confirmado. (En Windows 7, busque **Asignación (KB)** en el grupo **Sistema**).

    Si el **Total** se aproxima al **Límite** hay poca memoria física.

<a name="ManagedHeapCommit"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-is-committing"></a>Para determinar cuánta memoria está confirmando el montón administrado

- Use el contador de rendimiento de memoria `# Total committed bytes` para obtener el número de bytes que el montón administrado está confirmando. El recolector de elementos no utilizados confirma fragmentos de un segmento a medida que son necesarios, no todos al mismo tiempo.

  > [!NOTE]
  > No use el contador de rendimiento `# Bytes in all Heaps`, ya que no representa el uso de memoria real por parte del montón administrado. En este valor se incluye el tamaño de una generación y es realmente su tamaño umbral; es decir, el tamaño que induce una recolección de elementos no utilizados si la generación se llena de objetos. Por tanto, este valor suele ser cero.

<a name="ManagedHeapReserve"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-reserves"></a>Para determinar cuánta memoria reserva el montón administrado

- Use el contador de rendimiento de memoria `# Total reserved bytes`.

  El recolector de elementos no utilizados reserva memoria en segmentos y puede determinar dónde comienza un segmento mediante el comando **eeheap**.

  > [!IMPORTANT]
  > Aunque puede determinar la cantidad de memoria que el recolector de elementos no utilizados asigna a cada segmento, el tamaño del segmento es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas. La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.

- En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:

  **!eeheap -gc**

  El resultado es el siguiente.

  ```console
  Number of GC Heaps: 2
  ------------------------------
  Heap 0 (002db550)
  generation 0 starts at 0x02abe29c
  generation 1 starts at 0x02abdd08
  generation 2 starts at 0x02ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  02ab0000 02ab0038  02aceff4 0x0001efbc(126908)
  Large object heap starts at 0x0aab0038
    segment    begin allocated     size
  0aab0000 0aab0038  0aab2278 0x00002240(8768)
  Heap Size   0x211fc(135676)
  ------------------------------
  Heap 1 (002dc958)
  generation 0 starts at 0x06ab1bd8
  generation 1 starts at 0x06ab1bcc
  generation 2 starts at 0x06ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  06ab0000 06ab0038  06ab3be4 0x00003bac(15276)
  Large object heap starts at 0x0cab0038
    segment    begin allocated     size
  0cab0000 0cab0038  0cab0048 0x00000010(16)
  Heap Size    0x3bbc(15292)
  ------------------------------
  GC Heap Size   0x24db8(150968)
  ```

  Las direcciones indicadas por "segment" son las direcciones iniciales de los segmentos.

<a name="ExamineGen2"></a>

### <a name="to-determine-large-objects-in-generation-2"></a>Para determinar los objetos grandes de la generación 2

- En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:

  **!dumpheap –stat**

  Si el montón administrado es grande, **dumpheap** puede tardar bastante en finalizar.

  Puede empezar el análisis por las últimas líneas del resultado, ya que muestran los objetos que usan la mayor parte del espacio. Por ejemplo:

  ```console
  2c6108d4   173712     14591808 DevExpress.XtraGrid.Views.Grid.ViewInfo.GridCellInfo
  00155f80      533     15216804      Free
  7a747c78   791070     15821400 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700930     19626040 System.Collections.Specialized.ListDictionary
  2c64e36c    78644     20762016 DevExpress.XtraEditors.ViewInfo.TextEditViewInfo
  79124228   121143     29064120 System.Object[]
  035f0ee4    81626     35588936 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    40182     90664128 System.Collections.Hashtable+bucket[]
  790fa3e0  3154024    137881448 System.String
  Total 8454945 objects
  ```

  El último objeto mostrado es una cadena y es el que ocupa más espacio. Puede examinar la aplicación para ver cómo se pueden optimizar los objetos de cadena. Para ver las cadenas comprendidas entre 150 y 200 bytes, escriba lo siguiente:

  **!dumpheap -type System.String -min 150 -max 200**

  A continuación se muestra un ejemplo de los resultados.

  ```console
  Address  MT           Size  Gen
  1875d2c0 790fa3e0      152    2 System.String HighlightNullStyle_Blotter_PendingOrder-11_Blotter_PendingOrder-11
  …
  ```

  Puede ser más eficaz usar un entero en lugar de una cadena para un identificador. Si la misma cadena se está repitiendo miles de veces, considere la posibilidad de asignación al grupo interno de cadenas. Para obtener más información sobre la asignación al grupo interno de cadenas, vea el tema de referencia sobre el método <xref:System.String.Intern%2A?displayProperty=nameWithType>.

<a name="ObjRef"></a>

### <a name="to-determine-references-to-objects"></a>Para determinar las referencias a objetos

- En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente para mostrar las referencias a objetos:

  **!gcroot**

  `-or-`

- Para determinar las referencias para un objeto concreto, incluya la dirección:

  **!gcroot 1c37b2ac**

  Las raíces encontradas en pilas pueden ser falsos positivos. Para obtener más información, use el comando `!help gcroot`.

  ```console
  ebx:Root:19011c5c(System.Windows.Forms.Application+ThreadContext)->
  19010b78(DemoApp.FormDemoApp)->
  19011158(System.Windows.Forms.PropertyStore)->
  … [omitted]
  1c3745ec(System.Data.DataTable)->
  1c3747a8(System.Data.DataColumnCollection)->
  1c3747f8(System.Collections.Hashtable)->
  1c376590(System.Collections.Hashtable+bucket[])->
  1c376c98(System.Data.DataColumn)->
  1c37b270(System.Data.Common.DoubleStorage)->
  1c37b2ac(System.Double[])
  Scan Thread 0 OSTHread 99c
  Scan Thread 6 OSTHread 484
  ```

  El comando **gcroot** puede tardar mucho en finalizar. Todo objeto no reclamado en la recolección de elementos no utilizados es un objeto activo. Esto implica que alguna raíz se almacena directa o indirectamente en el objeto, por lo que **gcroot** debe devolver información de ruta de acceso al objeto. Debe examinar los gráficos devueltos y ver por qué todavía se hace referencia a estos objetos.

<a name="Induce"></a>

### <a name="to-determine-whether-a-finalizer-has-been-run"></a>Para determinar si se ha ejecutado un finalizador

- Ejecute un programa de prueba que contenga el código siguiente:

  ```csharp
  GC.Collect();
  GC.WaitForPendingFinalizers();
  GC.Collect();
  ```

  Si la prueba resuelve el problema, significa que el recolector de elementos no utilizados no estaba recuperando objetos porque los finalizadores de esos objetos se habían suspendido. El método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> permite que los finalizadores completen sus tareas y corrige el problema.

<a name="Finalize"></a>

### <a name="to-determine-whether-there-are-objects-waiting-to-be-finalized"></a>Para determinar si hay objetos en espera de finalización

1. En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:

    **!finalizequeue**

    Observe el número de objetos que están listos para la finalización. Si el número es elevado, debe examinar por qué estos finalizadores no pueden progresar en absoluto o con la rapidez suficiente.

2. Para obtener un resultado de subprocesos, escriba el comando siguiente:

    **threads -special**

    Este comando proporciona resultados como el siguiente.

    ```console
       OSID     Special thread type
    2    cd0    DbgHelper
    3    c18    Finalizer
    4    df0    GC SuspendEE
    ```

    El subproceso finalizador indica qué finalizador, si hay alguno, se está ejecutando actualmente. Cuando un subproceso finalizador no está ejecutando ningún finalizador, está esperando un evento para indicarle que haga su trabajo. La mayoría de las veces verá el subproceso finalizador en este estado porque se ejecuta en THREAD_HIGHEST_PRIORITY y se presupone que termina de ejecutar los finalizadores, si hay alguno, muy rápidamente.

<a name="Fragmented"></a>

### <a name="to-determine-the-amount-of-free-space-in-the-managed-heap"></a>Para determinar la cantidad de espacio disponible en el montón administrado

- En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:

  **!dumpheap -type Free -stat**

  Este comando muestra el tamaño total de todos los objetos disponibles en el montón administrado, como se muestra en el ejemplo siguiente.

  ```console
  total 230 objects
  Statistics:
        MT    Count    TotalSize Class Name
  00152b18      230     40958584      Free
  Total 230 objects
  ```

- Para determinar el espacio disponible en la generación 0, escriba el comando siguiente para obtener información sobre el consumo de memoria por generación:

  **!eeheap -gc**

  Este comando muestra un resultado similar al siguiente. La última línea muestra el segmento efímero.

  ```console
  Heap 0 (0015ad08)
  generation 0 starts at 0x49521f8c
  generation 1 starts at 0x494d7f64
  generation 2 starts at 0x007f0038
  ephemeral segment allocation context: none
  segment  begin     allocated  size
  00178250 7a80d84c  7a82f1cc   0x00021980(137600)
  00161918 78c50e40  78c7056c   0x0001f72c(128812)
  007f0000 007f0038  047eed28   0x03ffecf0(67103984)
  3a120000 3a120038  3a3e84f8   0x002c84c0(2917568)
  46120000 46120038  49e05d04   0x03ce5ccc(63855820)
  ```

- Calcule el espacio usado por la generación 0:

  **? 49e05d04-0x49521f8c**

  El resultado es el siguiente. La generación 0 ocupa aproximadamente 9 MB.

  ```console
  Evaluate expression: 9321848 = 008e3d78
  ```

- El comando siguiente vuelca el espacio disponible dentro del intervalo de la generación 0:

  **!dumpheap -type Free -stat 0x49521f8c 49e05d04**

  El resultado es el siguiente.

  ```console
  ------------------------------
  Heap 0
  total 409 objects
  ------------------------------
  Heap 1
  total 0 objects
  ------------------------------
  Heap 2
  total 0 objects
  ------------------------------
  Heap 3
  total 0 objects
  ------------------------------
  total 409 objects
  Statistics:
        MT    Count TotalSize Class Name
  0015a498      409   7296540      Free
  Total 409 objects
  ```

  Este resultado muestra que la parte de la generación 0 del montón está usando 9 MB de espacio para los objetos y tiene 7 MB disponibles. Este análisis muestra hasta qué punto la generación 0 contribuye a la fragmentación. Esta cantidad de uso del montón se debe descontar de la cantidad total como la causa de fragmentación por parte de los objetos de larga duración.

<a name="Pinned"></a>

### <a name="to-determine-the-number-of-pinned-objects"></a>Para determinar el número de objetos anclados

- En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:

  **!gchandles**

  Las estadísticas mostradas incluyen el número de identificadores anclados, como se muestra en el ejemplo siguiente.

  ```console
  GC Handle Statistics:
  Strong Handles:      29
  Pinned Handles:      10
  ```

<a name="TimeInGC"></a>

### <a name="to-determine-the-length-of-time-in-a-garbage-collection"></a>Para determinar la duración de una recolección de elementos no utilizados

- Examine el contador de rendimiento de memoria `% Time in GC`.

  El valor se calcula usando un tiempo de intervalo de muestra. Como los contadores se actualizan al final de cada recolección de elementos no utilizados, el ejemplo actual tendrá el mismo valor que el ejemplo anterior si no se realizó ninguna recolección durante el intervalo.

  Tiempo de recolección se obtiene multiplicando el tiempo de intervalo de muestra por el valor de porcentaje.

  Los datos siguientes muestran cuatro intervalos de muestreo de dos segundos para un estudio de 8 segundos. Las columnas `Gen0`, `Gen1` y `Gen2` muestran el número de recolecciones de elementos no utilizados que se produjeron durante ese intervalo para esa generación.

  ```console
  Interval    Gen0    Gen1    Gen2    % Time in GC
          1       9       3       1              10
          2      10       3       1               1
          3      11       3       1               3
          4      11       3       1               3
  ```

  Esta información no indica cuándo se produjo la recolección de elementos no utilizados, pero puede determinar el número de recolecciones de elementos no utilizados que se produjeron en un intervalo de tiempo. Suponiendo el caso peor, la décima recolección de elementos no utilizados de generación 0 terminó al principio del segundo intervalo y la undécima recolección de elementos no utilizados de generación 0 terminó al final del quinto intervalo. El tiempo transcurrido entre el final de la décima recolección de elementos no utilizados y el final de la undécima recolección de elementos no utilizados es de aproximadamente 2 segundos y el contador de rendimiento muestra un 3%, por lo que la duración de la undécima recolección de elementos no utilizados de generación 0 fue de (2 segundos * 3% = 60 ms).

  En este ejemplo, hay 5 periodos.

  ```console
  Interval    Gen0    Gen1    Gen2     % Time in GC
          1       9       3       1                3
          2      10       3       1                1
          3      11       4       2                1
          4      11       4       2                1
          5      11       4       2               20
  ```

  La segunda recolección de elementos no utilizados de generación 2 se inició durante el tercer intervalo y terminó en el quinto intervalo. Suponiendo el caso peor, la última recolección de elementos no utilizados fue de una generación 0 que terminó al principio del segundo intervalo y la recolección de elementos no utilizados de generación 2 terminó al final del quinto intervalo. Por tanto, el tiempo transcurrido entre el final de la recolección de elementos no utilizados de generación 0 y el final de la recolección de elementos no utilizados de generación 2 es de 4 segundos. Puesto que el contador `% Time in GC` muestra un 20%, el tiempo máximo que la recolección de elementos no utilizados de generación 2 podría haber tardado es (4 segundos * 20% = 800 ms).

- También puede determinar la duración de una recolección de elementos no utilizados mediante [eventos ETW de recolección de elementos no utilizados](../../framework/performance/garbage-collection-etw-events.md) y analizar la información para averiguar la duración de la recolección de elementos no utilizados.

  Por ejemplo, los datos siguiente muestran una secuencia de eventos que se produjo durante una recolección de elementos no utilizados no simultánea.

  ```console
  Timestamp    Event name
  513052        GCSuspendEEBegin_V1
  513078        GCSuspendEEEnd
  513090        GCStart_V1
  517890        GCEnd_V1
  517894        GCHeapStats
  517897        GCRestartEEBegin
  517918        GCRestartEEEnd
  ```

  La suspensión del subproceso administrado tardó 26 us (`GCSuspendEEEnd` – `GCSuspendEEBegin_V1`).

  La recolección de elementos no utilizados real tardó 4,8 ms (`GCEnd_V1` – `GCStart_V1`).

  La reanudación de los subprocesos administrados tardó 21 us (`GCRestartEEEnd` – `GCRestartEEBegin`).

  El resultado siguiente proporciona un ejemplo de recolección de elementos no utilizados en segundo plano, e incluye los campos de proceso, subproceso y evento. (No se muestra todos los datos.)

  ```console
  timestamp(us)    event name            process    thread    event field
  42504385        GCSuspendEEBegin_V1    Test.exe    4372             1
  42504648        GCSuspendEEEnd         Test.exe    4372
  42504816        GCStart_V1             Test.exe    4372        102019
  42504907        GCStart_V1             Test.exe    4372        102020
  42514170        GCEnd_V1               Test.exe    4372
  42514204        GCHeapStats            Test.exe    4372        102020
  42832052        GCRestartEEBegin       Test.exe    4372
  42832136        GCRestartEEEnd         Test.exe    4372
  63685394        GCSuspendEEBegin_V1    Test.exe    4744             6
  63686347        GCSuspendEEEnd         Test.exe    4744
  63784294        GCRestartEEBegin       Test.exe    4744
  63784407        GCRestartEEEnd         Test.exe    4744
  89931423        GCEnd_V1               Test.exe    4372        102019
  89931464        GCHeapStats            Test.exe    4372
  ```

  El evento `GCStart_V1` en 42504816 indica que se trata de una recolección de elementos no utilizados en segundo plano, ya que el último campo es `1`. Esta se convierte en la recolección de elementos no utilizados número 102019.

  El evento `GCStart` se produce porque se necesita una recolección de elementos no utilizados efímera antes de iniciar una recolección de elementos no utilizados en segundo plano. Esta se convierte en la recolección de elementos no utilizados número 102020.

  En 42514170, la recolección de elementos no utilizados número 102020 finaliza. Los subprocesos administrados se reinician en este momento. Esto se completa en el subproceso 4372, que desencadenó esta recolección de elementos no utilizados en segundo plano.

  En el subproceso 4744, se produce una suspensión. Esta es la última vez que la recolección de elementos no utilizados en segundo plano tiene que suspender subprocesos administrados. Esta duración es de aproximadamente 99 ms ((63784407-63685394)/1000).

  El evento `GCEnd` para la recolección de elementos no utilizados en segundo plano está en 89931423. Esto significa que la recolección de elementos no utilizados en segundo plano duró alrededor de 47 segundos ((89931423-42504816)/1000).

  Mientras los subprocesos administrados se están ejecutando, puede producirse cualquier número de recolecciones de elementos no utilizados efímeras.

<a name="Triggered"></a>

### <a name="to-determine-what-triggered-a-garbage-collection"></a>Para determinar qué desencadenó una recolección de elementos no utilizados

- En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente para mostrar todos los subprocesos con sus pilas de llamadas:

  **~\*KB**

  Este comando muestra un resultado similar al siguiente.

  ```console
  0012f3b0 79ff0bf8 mscorwks!WKS::GCHeap::GarbageCollect
  0012f454 30002894 mscorwks!GCInterface::CollectGeneration+0xa4
  0012f490 79fa22bd fragment_ni!request.Main(System.String[])+0x48
  ```

  Si la recolección de elementos no utilizados se produjo por una notificación de memoria insuficiente del sistema operativo, la pila de llamadas es similar, salvo que el subproceso es el subproceso finalizador. El subproceso finalizador obtiene una notificación asincrónica de memoria insuficiente e induce la recolección de elementos no utilizados.

  Si la recolección de elementos no utilizados se produjo por la asignación de memoria, la pila aparece de la manera siguiente:

  ```console
  0012f230 7a07c551 mscorwks!WKS::GCHeap::GarbageCollectGeneration
  0012f2b8 7a07cba8 mscorwks!WKS::gc_heap::try_allocate_more_space+0x1a1
  0012f2d4 7a07cefb mscorwks!WKS::gc_heap::allocate_more_space+0x18
  0012f2f4 7a02a51b mscorwks!WKS::GCHeap::Alloc+0x4b
  0012f310 7a02ae4c mscorwks!Alloc+0x60
  0012f364 7a030e46 mscorwks!FastAllocatePrimitiveArray+0xbd
  0012f424 300027f4 mscorwks!JIT_NewArr1+0x148
  000af70f 3000299f fragment_ni!request..ctor(Int32, Single)+0x20c
  0000002a 79fa22bd fragment_ni!request.Main(System.String[])+0x153
  ```

  Un asistente Just-In-Time (`JIT_New*`) llama finalmente a `GCHeap::GarbageCollectGeneration`. Si determina que las recolecciones de elementos no utilizados de generación 2 se deben a asignaciones, debe averiguar qué objetos recolecta una recolección de elementos no utilizados de generación 2 y cómo evitarlas. Es decir, debe determinar la diferencia entre el inicio y el final de una recolección de elementos no utilizados de generación 2 y los objetos que causaron la recolección de generación 2.

  Por ejemplo, escriba el comando siguiente en el depurador para mostrar el comienzo de una recolección de generación 2:

  **!dumpheap –stat**

  Resultado de ejemplo (abreviado para mostrar los objetos que usan más espacio):

  ```console
  79124228    31857      9862328 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  00155f80    21248     12256296      Free
  79103b6c   297003     13068132 System.Threading.ReaderWriterLock
  7a747ad4   708732     14174640 System.Collections.Specialized.HybridDictionary
  7a747c78   786498     15729960 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  035f0ee4    89192     38887712 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  7912c444    91616     71887080 System.Double[]
  791242ec    32451     82462728 System.Collections.Hashtable+bucket[]
  790fa3e0  2459154    112128436 System.String
  Total 6471774 objects
  ```

  Repita el comando al final de la generación 2:

  **!dumpheap –stat**

  Resultado de ejemplo (abreviado para mostrar los objetos que usan más espacio):

  ```console
  79124228    26648      9314256 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  79103b6c   296770     13057880 System.Threading.ReaderWriterLock
  7a747ad4   708730     14174600 System.Collections.Specialized.HybridDictionary
  7a747c78   786497     15729940 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  00155f80    13806     34007212      Free
  035f0ee4    89187     38885532 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    32370     82359768 System.Collections.Hashtable+bucket[]
  790fa3e0  2440020    111341808 System.String
  Total 6417525 objects
  ```

  Los objetos `double[]` desaparecieron del final del resultado, lo que significa que se recopilaron. Estos objetos ocupan aproximadamente 70 MB. Los objetos restantes no cambiaron mucho. Por tanto, estos objetos `double[]` eran la razón por la que se produjo esta recolección de elementos no utilizados de generación 2. El paso siguiente consiste en determinar por qué están allí los objetos `double[]` y por qué murieron. Puede preguntar al desarrollador del código la procedencia de estos objetos o puede usar el comando **gcroot**.

<a name="HighCPU"></a>

### <a name="to-determine-whether-high-cpu-usage-is-caused-by-garbage-collection"></a>Para determinar si el uso elevado de CPU está provocado por la recolección de elementos no utilizados

- Correlacione el valor del contador de rendimiento de memoria `% Time in GC` con el tiempo de proceso.

  Si el valor de `% Time in GC` tiene un pico a la vez que el tiempo de proceso, la recolección de elementos no utilizados está provocando un uso de CPU elevado. De lo contrario, genere un perfil de la aplicación para averiguar dónde se está produciendo el uso elevado.

## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados](index.md)
