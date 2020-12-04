---
title: Supervisar eventos de tiempo de ejecución de contención de bloqueo
description: Vea eventos ETW que recopilan información específica de las contenciones de bloqueo del monitor.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594706"
---
# <a name="net-runtime-contention-events"></a>Eventos de contención en tiempo de ejecución de .NET

Estos eventos en tiempo de ejecución capturan información sobre las contenciones de bloqueo de monitor como con `Monitor.Enter` o la palabra clave Lock de C#. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="contentionstart_v1-event"></a>Evento ContentionStart_V1

Este evento se genera al inicio de una contención de bloqueo de monitor.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Se inicia una contención de bloqueo de monitor.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` para administrado; `1` para nativo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="contentionstop_v1-event"></a>Evento ContentionStop_V1

Este evento se emite al final de una contención de bloqueo de monitor.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|91|Finaliza una contención de bloqueo de monitor.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` para administrado; `1` para nativo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
|`DurationNs`|`win:Double`|Duración de la contención en nanosegundos.|
