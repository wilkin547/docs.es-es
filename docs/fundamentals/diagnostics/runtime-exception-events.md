---
title: Eventos en tiempo de ejecución de excepción
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica de las excepciones y el control de excepciones.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594723"
---
# <a name="net-runtime-exception-events"></a>Eventos de excepción en tiempo de ejecución de .NET

Estos eventos en tiempo de ejecución capturan información sobre las excepciones que se producen. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="exceptionthrown_v1-event"></a>Evento ExceptionThrown_V1

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Error (1)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|80|Se genera una excepción administrada.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|Tipo de la excepción; por ejemplo, `System.NullReferenceException`.|
|`ExceptionMessage`|`win:UnicodeString`|Mensaje actual de la excepción.|
|`EIPCodeThrow`|`win:Pointer`|Puntero de instrucción donde se ha producido la excepción.|
|`ExceptionHR`|`win:UInt32`|Excepción [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|
|`ExceptionFlags`|`win:UInt16`|`0x01`: HasInnerException.<br /><br /> `0x02`: IsNestedException.<br /><br /> `0x04`: IsRethrownException.<br /><br /> `0x08`: IsCorruptedStateException (indica que el estado del proceso está dañado; consulte [control de excepciones de estado dañadas](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> `0x10`: IsCLSCompliant (una excepción que se deriva de <xref:System.Exception> es conforme a CLS; en caso contrario, no es conforme a CLS).|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="exceptioncatchstart-event"></a>Evento ExceptionCatchStart

Este evento se genera cuando comienza un controlador Catch administrado.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|250|El tiempo de ejecución controla una excepción administrada.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Puntero de instrucción donde se ha producido la excepción.|
|`MethodID`|`win:Pointer`|Puntero al descriptor de método en el método en el que se produjo la excepción.|
|`MethodName`|`win:UnicodeString`|Nombre del método en el que se produjo la excepción.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="exceptioncatchstop-event"></a>Evento ExceptionCatchStop

Este evento se genera cuando finaliza un controlador Catch administrado.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|251|Se realiza un controlador catch de excepción administrada.|

## <a name="exceptionfinallystart-event"></a>Evento ExceptionFinallyStart

Este evento se genera cuando comienza un controlador final de excepción administrada.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|252|El tiempo de ejecución controla una excepción administrada.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Puntero de instrucción donde se ha producido la excepción.|
|`MethodID`|`win:Pointer`|Puntero al descriptor de método en el método en el que se produjo la excepción.|
|`MethodName`|`win:UnicodeString`|Nombre del método en el que se produjo la excepción.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="exceptionfinallystop-event"></a>Evento ExceptionFinallyStop

Este evento se genera cuando finaliza un controlador Catch administrado.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|253|Se realiza un controlador Finally de excepción administrada.|

## <a name="exceptionfilterstart-event"></a>Evento ExceptionFilterStart

Este evento se genera cuando comienza un filtrado de excepciones administrado.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|254|Comienza un filtrado de excepciones administradas.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Puntero de instrucción donde se ha producido la excepción.|
|`MethodID`|`win:Pointer`|Puntero al descriptor de método en el método en el que se produjo la excepción.|
|`MethodName`|`win:UnicodeString`|Nombre del método en el que se produjo la excepción.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="exceptionfilterstop-event"></a>Evento ExceptionFilterStop

Este evento se genera cuando finaliza un filtrado de excepciones administrado.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|

 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|255|Finaliza un filtrado de excepción administrado.|

## <a name="exceptionthrownstop-event"></a>Evento ExceptionThrownStop

Este evento se genera cuando el motor en tiempo de ejecución realiza el control de una excepción administrada que se produjo.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Informativo (4)|
  
 En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|256|Finaliza un filtrado de excepción administrado.|
