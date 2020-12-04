---
title: Eventos de tiempo de ejecución ThreadPool
description: Vea eventos de grupo de subprocesos en tiempo de ejecución .NET que recopilan información de diagnóstico sobre el grupo de subprocesos en .NET Core Los eventos de grupo de subprocesos son eventos de grupo de subprocesos de trabajo o de subproceso de e/s.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594729"
---
# <a name="net-runtime-thread-pool-events"></a>Eventos de grupo de subprocesos en tiempo de ejecución .NET

Estos eventos recopilan información sobre el trabajo y los subprocesos de e/s en ThreadPool. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="iothreadcreate_v1-event"></a>Evento IOThreadCreate_V1

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|44|Se crea un subproceso de E/S en el grupo de subprocesos.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Número de subprocesos de E/S, incluido el subproceso recién creado.|
|`NumRetired`|`win:UInt64`|Número de subprocesos de trabajo retirados.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="iothreadterminate_v1-event"></a>Evento IOThreadTerminate_V1

 En la tabla siguiente se muestra la palabra clave y el nivel

|Palabra clave para generar el evento|Nivel
|-----------------------------------|-----------
|`ThreadingKeyword` (0x10000)|Informativo (4)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|45|Se termina un subproceso de e/s en el grupo de subprocesos.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Número de subprocesos de E/S restantes en el grupo de subprocesos.|
|`NumRetired`|`win:UInt64`|Número de subprocesos de E/S retirados.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="iothreadretire_v1-event"></a>Evento IOThreadRetire_V1

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|46|Un subproceso de E/S se convierte en un candidato para la retirada.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Número de subprocesos de E/S restantes en el grupo de subprocesos.|
|`NumRetired`|`win:UInt64`|Número de subprocesos de E/S retirados.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="iothreadunretire_v1-event"></a>Evento IOThreadUnretire_V1

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|47|La retirada de un subproceso de E/S se anula debido a que llega una E/S dentro de un período de espera y después de que el subproceso se convierte en un candidato para la retirada.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Número de subprocesos de E/S en el grupo de subprocesos, incluido este.|
|`NumRetired`|`win:UInt64`|Número de subprocesos de E/S retirados.|
|`ClrInstanceID`|`Win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadstart-event"></a>Evento ThreadPoolWorkerThreadStart

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|50|Se crea un subproceso de trabajo.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadstop-event"></a>Evento ThreadPoolWorkerThreadStop

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|51|Se detiene un subproceso de trabajo.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadwait-event"></a>Evento ThreadPoolWorkerThreadWait

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|57|Un subproceso de trabajo inicia la espera de trabajo.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadretirementstart-event"></a>Evento ThreadPoolWorkerThreadRetirementStart

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|52|Se retira un subproceso de trabajo.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadretirementstop-event"></a>Evento ThreadPoolWorkerThreadRetirementStop

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|53|Un subproceso de trabajo retirado se vuelve activo.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a>Evento ThreadPoolWorkerThreadAdjustmentSample

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|54|Se refiere a la recopilación de información para un ejemplo; es decir, una medición del rendimiento con un determinado nivel de simultaneidad en un instante de tiempo.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|Número de finalizaciones por unidad de tiempo.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a>Evento ThreadPoolWorkerThreadAdjustmentAdjustment

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|55|Registra un cambio en el control, cuando el algoritmo de inserción de subproceso (hill-climbing) determina que tiene lugar un cambio en el nivel de simultaneidad.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|Rendimiento medio de un ejemplo de mediciones.|
|`NewWorkerThreadCount`|`win:UInt32`|Nuevo número de subprocesos de trabajo activos.|
|`Reason`|`win:UInt32`|Razón para el ajuste.<br /><br /> `0x0` Preparación.<br /><br /> `0x1` Inicial.<br /><br /> `0x2` -Movimiento aleatorio.<br /><br /> `0x3` -Movimiento de subida.<br /><br /> `0x4` -Cambiar punto.<br /><br /> `0x5` Estabilización.<br /><br /> `0x6` Colapso.<br /><br /> `0x7` -El subproceso agotó el tiempo de espera.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a>Evento ThreadPoolWorkerThreadAdjustmentStats

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|56|Recopila datos en el grupo de subprocesos.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|Cantidad de tiempo, en segundos, durante el que se recopilaron estas estadísticas.|
|`Throughput`|`win:Double`|Promedio de finalizaciones por segundo durante este intervalo.|
|`ThreadWave`|`win:Double`|Reservado para uso interno.|
|`ThroughputWave`|`win:Double`|Reservado para uso interno.|
|`ThroughputErrorEstimate`|`win:Double`|Reservado para uso interno.|
|`AverageThroughputErrorEstimate`|`win:Double`|Reservado para uso interno.|
|`ThroughputRatio`|`win:Double`|Mejora relativa en el rendimiento producida por variaciones en el número de subprocesos de trabajo activos durante este intervalo.|
|`Confidence`|`win:Double`|Medida de la validez del campo ThroughputRatio.|
|`NewcontrolSetting`|`win:Double`|El número de subprocesos de trabajo activos que servirá de línea de base para las variaciones futuras en el recuento de subprocesos activos.|
|`NewThreadWaveMagnitude`|`win:UInt16`|La magnitud de variaciones futuras en el recuento de subprocesos activos.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadpoolenqueue-event"></a>Evento ThreadPoolEnqueue

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|61|Se puso en cola un elemento de trabajo en la cola del grupo de subprocesos.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Puntero a la solicitud de trabajo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadpooldequeue-event"></a>Evento ThreadPoolDequeue

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|62|Se quitó la cola de un elemento de trabajo de la cola del grupo de subprocesos.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Puntero a la solicitud de trabajo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadpoolioenqueue-event"></a>Evento ThreadPoolIOEnqueue

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|63|Un subproceso pone en cola una notificación de finalización de e/s cuando se produce una finalización de e/s asincrónica.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Reservado para uso interno.|
|`Overlapped`|`win:Pointer`|Reservado para uso interno.|
|`MultiDequeues`|`win:Boolean`|Reservado para uso interno.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadpooliodequeue-event"></a>Evento ThreadPoolIODequeue

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|64|Un subproceso quita la cola de finalización de e/s.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Reservado para uso interno.|
|`Overlapped`|`win:Pointer`|Reservado para uso interno.|
|`MultiDequeues`|`win:Boolean`|Reservado para uso interno.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadpooliopack-event"></a>Evento ThreadPoolIOPack

 En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Detallado (5)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|65|Se llama al módulo de e/s superpuesta de ThreadPool.|

 En la tabla siguiente se muestran los datos del evento

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Reservado para uso interno.|
|`Overlapped`|`win:Pointer`|Reservado para uso interno.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadcreating-event"></a>Evento ThreadCreating

 En la tabla siguiente se muestran las palabras clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`ThreadCreating`|70|Se ha creado el subproceso.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Id. de subproceso|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="threadrunning-event"></a>Evento ThreadRunning

 En la tabla siguiente se muestran las palabras clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`ThreadRunning`|71|El subproceso ha empezado a ejecutarse.|

 En la siguiente tabla se muestran los datos del evento.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Id. de subproceso|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
