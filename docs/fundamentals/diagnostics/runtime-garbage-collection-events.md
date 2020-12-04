---
title: Eventos de Runtime de recolección de elementos no utilizados
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica del recolector de elementos no utilizados de .NET.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594707"
---
# <a name="net-runtime-garbage-collection-events"></a>Eventos de recolección de elementos no utilizados de .NET Runtime

Estos eventos recopilan información sobre la recolección de elementos no utilizados. Ayudan en el diagnóstico y la depuración, incluida la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="gcstart_v2-event"></a>Evento GCStart_V2

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCStart_V1`|1|Se ha iniciado una recolección de elementos no utilizados.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Recolección de elementos no utilizados número *n*.|
|`Depth`|`win:UInt32`|Generación que se está recopilando.|
|`Reason`|`win:UInt32`|¿Por qué se desencadenó la recolección de elementos no utilizados:<br /><br /> `0x0` -Asignación del montón de objetos pequeños.<br /><br /> `0x1` Inducida.<br /><br /> `0x2` -Memoria insuficiente.<br /><br /> `0x3` Vacía.<br /><br /> `0x4` -Asignación del montón de objetos grandes.<br /><br /> `0x5` -Espacio insuficiente (para el montón de objetos pequeños).<br /><br /> `0x6` -Espacio insuficiente (para el montón de objetos grandes).<br /><br /> `0x7` -Inducido pero no forzado como bloqueo.|
|`Type`|`win:UInt32`|`0x0` -La recolección de elementos no utilizados bloqueada fuera de la recolección de elementos no utilizados.<br /><br /> `0x1` -Recolección de elementos no utilizados en segundo plano.<br /><br /> `0x2` -La recolección de elementos no utilizados bloqueada durante la recolección de elementos no utilizados en segundo plano|
|`ClrInstanceID`|win:UInt16|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gcend_v1-event"></a>Evento GCEnd_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCEnd_V1`|2|La recolección de elementos no utilizados ha finalizado.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Recolección de elementos no utilizados número *n*.|
|`Depth`|`win:UInt32`|Generación que se recopiló.|
|`ClrInstanceID`|win:UInt16|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gcheapstats_v2-event"></a>Evento GCHeapStats_V2

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|4|Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|Tamaño, en bytes, de la memoria de la generación 0.|
|`TotalPromotedSize0`|`win:UInt64`|Número de bytes que se promueven de generación 0 a generación 1.|
|`GenerationSize1`|`win:UInt64`|Tamaño, en bytes, de la memoria de la generación 1.|
|`TotalPromotedSize1`|`win:UInt64`|Número de bytes que se promueven de generación 1 a generación 2.|
|`GenerationSize2`|`win:UInt64`|Tamaño, en bytes, de la memoria de la generación 2.|
|`TotalPromotedSize2`|`win:UInt64`|Número de bytes que sobrevivieron en la generación 2 después de la última recolección.|
|`GenerationSize3`|`win:UInt64`|Tamaño, en bytes, del montón de objetos grandes.|
|`TotalPromotedSize3`|`win:UInt64`|Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.|
|`FinalizationPromotedSize`|`win:UInt64`|Tamaño total, en bytes, de los objetos que están listos para la finalización.|
|`FinalizationPromotedCount`|`win:UInt64`|Número de objetos que están listos para la finalización.|
|`PinnedObjectCount`|`win:UInt32`|Número de objetos anclados (inamovibles).|
|`SinkBlockCount`|`win:UInt32`|Número de bloques de sincronización en uso.|
|`GCHandleCount`|`win:UInt32`|Número de controles de recolección de elementos no utilizados en uso.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
|`GenerationSize4`|`win:UInt64`|Tamaño, en bytes, del montón de objetos anclados.|
|`TotalPromotedSize4`|`win:UInt64`|Número de bytes que sobrevivieron en el montón de objetos anclados después de la última recolección.|

## <a name="gccreatesegment_v1-event"></a>Evento GCCreateSegment_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|5|Se ha creado un nuevo segmento de recopilación de elementos no utilizados. Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|Dirección del segmento.|
|`Size`|`win:UInt64`|Tamaño del segmento.|
|`Type`|`win:UInt32`|0x0: montón de objetos pequeños.<br /><br /> 0x1: montón de objetos grandes.<br /><br /> 0x2: montón de solo lectura.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas. La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.

## <a name="gcfreesegment_v1-event"></a>Evento GCFreeSegment_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|6|Se ha liberado un segmento de recolección de elementos no utilizados.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|Dirección del segmento.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gcrestarteebegin_v1-event"></a>Evento GCRestartEEBegin_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|7|Ha comenzado la reanudación de la suspensión de Common Language Runtime.|

Este evento no tiene datos de evento.

## <a name="gcrestarteeend_v1-event"></a>Evento GCRestartEEEnd_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|3|Ha finalizado la reanudación de la suspensión de Common Language Runtime.|

Este evento no tiene datos de evento.

## <a name="gcsuspendeeend_v1-event"></a>Evento GCSuspendEEEnd_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|8|Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.|

Este evento no tiene datos de evento.

## <a name="gcsuspendeebegin_v1-event"></a>Evento GCSuspendEEBegin_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|8|Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Recolección de elementos no utilizados número *n*.|
|`Reason`|`win:UInt32`|Motivo de la suspensión de EE.<br/><br/>`0x0`: Suspender para otros<br/><br/>`0x1`: Suspender para GC.<br/><br/>`0x2`: Suspender para el cierre de AppDomain.<br/><br/>`0x3`: Suspender para el paso del código.<br/><br/>`0x4`: Suspender para apagar.<br/><br/>`0x5`: Suspender para el depurador.<br/><br/>`0x6`: Suspend para la preparación de GC.<br/><br/>`0x7`: Suspender el barrido del depurador|

## <a name="gcallocationtick_v3-event"></a>Evento GCAllocationTick_V3

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Verbose (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|10|Cada vez se asignan aproximadamente 100 KB.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|Tamaño de la asignación, en bytes. Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes). Si la asignación es mayor, este campo contiene un valor truncado. Use `AllocationAmount64` para asignaciones muy grandes.|
|`AllocationKind`|`win:UInt32`|`0x0` -Asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).<br /><br /> `0x1` -Asignación de objetos grandes (la asignación está en un montón de objetos grandes).|
|`AllocationAmount64`|`win:UInt64`|Tamaño de la asignación, en bytes. Este valor es preciso para asignaciones muy grandes.|
|`TypeId`|`win:Pointer`|Dirección de la MethodTable. Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).|
|`TypeName`|`win:UnicodeString`|Nombre del tipo que se asignó. Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).|
|`HeapIndex`|`win:UInt32`|Montón al que se ha asignado el objeto. Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.|
|`Address`|`win:Pointer`|Dirección del último objeto asignado.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gccreateconcurrentthread_v1-event"></a>Evento GCCreateConcurrentThread_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|11|El subproceso de recolección de elementos no utilizados simultánea se creó.|

Este evento no tiene datos de evento.

## <a name="gcterminateconcurrentthread_v1-event"></a>Evento GCTerminateConcurrentThread_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|12|El subproceso de recolección de elementos no utilizados simultánea finalizó.|

Este evento no tiene datos de evento.

## <a name="gcfinalizersbegin_v1-event"></a>Evento GCFinalizersBegin_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|14|Inicio de los finalizadores en ejecución.|

Este evento no tiene datos de evento.

## <a name="gcfinalizersend_v1-event"></a>Evento GCFinalizersEnd_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|13|Final de los finalizadores en ejecución.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|Número de finalizadores que se ejecutó.|
|`ClrInstanceID`|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="setgchandle-event"></a>Evento SetGCHandle

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCHandleKeyword` 0X2|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`SetGCHandle`|30|Se ha establecido un identificador de GC.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Dirección del identificador asignado.|
|`ObjectID`|`win:Pointer`|Dirección del objeto cuyo identificador se creó.|
|`Kind`|`win:UInt32`|El tipo de identificador de GC que se estableció. <br /><br />`0x0`: WeakShort <br/><br/>`0x1`: WeakLong <br /><br />`0x2`: Strong <br /><br />`0x3`: Anclado <br /><br />`0x4`: Variable<br /><br />`0x5`: RefCounted <br /><br />`0x6`: Dependiente<br /><br />`0x7`: AsyncPinned<br /><br />`0x8`: Identificador sizedref|
|`Generation`|`win:UInt32`|La generación del objeto cuyo identificador se creó.|
|`AppDomainID`|`win:UInt64`|IDENTIFICADOR de AppDomain.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="destroygchandle-event"></a>Evento DestroyGCHandle

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCHandleKeyword` 0X2|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|31|Se destruye un identificador de GC.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Dirección del identificador destruido.|
|`ClrInstanceID`|win:UInt16|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="pinobjectatgctime-event"></a>Evento PinObjectAtGCTime

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Detallado (5)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|33|Se ancló un objeto durante un GC.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|Dirección del identificador.|
|`ObjectID`|`win:Pointer`|Dirección del objeto anclado.|
|`ObjectSize`|`win:UInt64`|Tamaño del objeto anclado.|
|`TypeName`|`win:UnicodeString`|Nombre del tipo del objeto anclado.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gctriggered-event"></a>Evento GCTriggered

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Detallado (5)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCTriggered`|33|Se ha desencadenado un GC.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|Motivo por el que se desencadenó un GC.<br/><br/>`0x0`: AllocSmall<br/><br/>`0x1`: Inducido <br/><br/>`0x2`: LowMemory <br/><br/>`0x3`: Vacío <br/><br/>`0x4`: AllocLarge <br/><br/>`0x5`: OutOfSpaceSmallObjectHeap <br/><br/>`0x6`: OutOfSpaceLargeObjectHeap <br/><br/>`0x7`:InducedNoForce <br/><br/>`0x8`: Stress <br/><br/>`0x9`: InducedLowMemory|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="increasememorypressure-event"></a>Evento IncreaseMemoryPressure

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Información (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|200|Se aumentó la presión de memoria.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ClrInstanceID`|win:UInt16|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="decreasememorypressure-event"></a>Evento DecreaseMemoryPressure

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Información (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|201|Se disminuyó la presión de memoria.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|Bytes liberados.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="gcmarkwithtype-event"></a>Evento GCMarkWithType

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Información (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|----------------|---------------|-----------------|
|`GCMarkWithType`|202|Se ha marcado una raíz de GC durante la fase de marca de GC.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|El número de montón.|
|`ClrInstanceID`|win:UInt16|IDENTIFICADOR único de la instancia de CoreCLR.|
|`Type`|`win:UInt32`|Tipo raíz del GC.<br/><br/>`0x0`: Stack<br/><br/>`0x1`: Finalizador<br/><br/>`0x2`: Handle<br/><br/>`0x3`: Anterior<br/><br/>`0x4`: Identificador sizedref<br/><br/>`0x5`: Desbordamiento<br/><br/>|
|`Bytes`|`win:UInt64`|Número de bytes marcados como.|

## <a name="gcjoin_v2-event"></a>Evento GCJoin_V2

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`GCKeyword` (0x1)|Detallado (5)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`GCJoin_V2`|203|Un subproceso GC combinado.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|El número de montón|
|`JoinTime`|`win:UInt32`|Indica si este evento se desencadena al principio de una combinación o el final de una combinación (para el inicio de la combinación `0x0` , para el extremo de la `0x1` combinación)|
|`JoinType`|`win:UInt32`|Tipo de combinación. <br/><br/>`0x0`: Última combinación<br/><br/>`0x1`: Join <br/><br/>`0x2`: Reiniciar <br/><br/>`0x3`: Primera combinación inversa<br/><br/>`0x4`: Combinación inversa<br/><br/>|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
