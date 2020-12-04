---
title: Eventos de tiempo de ejecución de método
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica de métodos, como eventos de método CLR, marcadores de método CLR o eventos detallados de método CLR, y MethodJittingStarted.
ms.date: 11/13/2020
helpviewer_keywords:
- Method events (CoreCLR)
- ETW, EventPipe, LTTng method events (CoreCLR)
ms.openlocfilehash: f9d08efa420670cf7a8c863f115ff270998f2dca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594702"
---
# <a name="net-runtime-method-events"></a>Eventos de métodos en tiempo de ejecución de .NET

Estos eventos recopilan información que es específica de los métodos. La carga de estos eventos es necesaria para la resolución de símbolos. Además, estos eventos proporcionan información útil, como los métodos que se cargan y descargan. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

Todos los eventos de método tienen un nivel de “Informativo (4)”. Todos los eventos detallados de método tienen un nivel de “Detallado (5)”.

Todos los eventos de método se generan mediante la palabra clave `JITKeyword` (0x10) o la palabra clave `NGenKeyword` (0x20) con el proveedor de runtime, o `JitRundownKeyword` (0x10) o `NGENRundownKeyword` (0x20) con el proveedor de detención.

Las versiones V2 de estos eventos incluyen ReJITID, las versiones v1 no.

## <a name="methodload_v1-event"></a>Evento MethodLoad_V1

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|141|Se genera cuando un método se carga just-in-time (carga JIT) o se carga una imagen NGEN. Los métodos dinámicos y genéricos no usan esta versión para cargas de método. Los asistentes de JIT nunca usan esta versión.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|Informativo (4)|
|`NGenKeyword` (0x20)|Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio del método.|
|`MethodSize`|`win:UInt32`|Tamaño del método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0x4: método de código compilado JIT (en caso contrario, código de imagen nativa de NGEN).<br /><br /> 0x8: método del asistente.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodload_v2-event"></a>Evento MethodLoad_V2

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`MethodLoad_V2`|141|Se genera cuando un método se carga just-in-time (carga JIT) o se carga una imagen NGEN. Los métodos dinámicos y genéricos no usan esta versión para cargas de método. Los asistentes de JIT nunca usan esta versión.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|Informativo (4)|
|`NGenKeyword` (0x20)|Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio del método.|
|`MethodSize`|`win:UInt32`|Tamaño del método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0x4: método de código compilado JIT (en caso contrario, código de imagen nativa de NGEN).<br /><br /> 0x8: método del asistente.|
|`ReJITID`|`win:UInt64`|IDENTIFICADOR de ReJIT del método.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodunload_v1-event"></a>Evento MethodUnLoad_V1

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`MethodUnLoad_V1`|142|Se genera cuando se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos nunca usan esta versión para descargas de método.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10)|Informativo (4)|
|`NGenKeyword` 0x20|Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio del método.|
|`MethodSize`|`win:UInt32`|Tamaño del método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0x4: método de código compilado JIT (en caso contrario, código de imagen nativa de NGEN).<br /><br /> 0x8: método del asistente.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodunload_v2-event"></a>Evento MethodUnLoad_V2

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`MethodUnLoad_V2`|142|Se genera cuando se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos nunca usan esta versión para descargas de método.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10)|Informativo (4)|
|`NGenKeyword` 0x20|Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio del método.|
|`MethodSize`|`win:UInt32`|Tamaño del método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0x4: método de código compilado JIT (en caso contrario, código de imagen nativa de NGEN).<br /><br /> 0x8: método del asistente.|
|`ReJITID`|`win:UInt64`|IDENTIFICADOR de ReJIT del método.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="r2rgetentrypoint-event"></a>Evento R2RGetEntryPoint

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`R2RGetEntryPoint`|159|Se genera cuando finaliza una búsqueda de punto de entrada R2R.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método R2R.|
|`MethodNamespace`|`win:UnicodeString`|Espacio de nombres del método que se va a buscar.|
|`MethodName`|`win:UnicodeString`|Nombre del método que se va a buscar.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`EntryPoint`|`win:UInt64`|Puntero al punto de entrada del método R2R.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="r2rgetentrypointstart-event"></a>Evento R2RGetEntryPointStart

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`R2RGetEntryPointStart`|160|Se genera cuando se inicia una búsqueda de punto de entrada R2R.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método R2R.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodloadverbose_v1-event"></a>Evento MethodLoadVerbose_V1

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Se genera cuando la carga de un método es JIT o se carga una imagen NGEN. Los métodos dinámicos y genéricos siempre usan esta versión para cargas de método. Los asistentes de JIT siempre usan esta versión.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único del método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio.|
|`MethodSize`|`win:UInt32`|Longitud de método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0 x 4: método compilado JIT (de lo contrario, generado por NGen.exe)<br /><br /> 0x8: método del asistente.|
|`MethodNameSpace`|`win:UnicodeString`|Nombre del espacio de nombres completo que está asociado al método.|
|`MethodName`|`win:UnicodeString`|Nombre de clase completo que está asociado al método.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodloadverbose_v2-event"></a>Evento MethodLoadVerbose_V2

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Se genera cuando la carga de un método es JIT o se carga una imagen NGEN. Los métodos dinámicos y genéricos siempre usan esta versión para cargas de método. Los asistentes de JIT siempre usan esta versión.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único del método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio.|
|`MethodSize`|`win:UInt32`|Longitud de método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0 x 4: método compilado JIT (de lo contrario, generado por NGen.exe)<br /><br /> 0x8: método del asistente.|
|`MethodNameSpace`|`win:UnicodeString`|Nombre del espacio de nombres completo que está asociado al método.|
|`MethodName`|`win:UnicodeString`|Nombre de clase completo que está asociado al método.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`ReJITID`|`win:UInt64`|IDENTIFICADOR de ReJIT del método.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodunloadverbose_v1-event"></a>Evento MethodUnLoadVerbose_V1

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V1`|144|Se genera cuando se destruye un método dinámico, se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos siempre usan esta versión para descargas de método.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único del método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio.|
|`MethodSize`|`win:UInt32`|Longitud de método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0 x 4: método compilado JIT (de lo contrario, generado por NGen.exe)<br /><br /> 0x8: método del asistente.|
|`MethodNameSpace`|`win:UnicodeString`|Nombre del espacio de nombres completo que está asociado al método.|
|`MethodName`|`win:UnicodeString`|Nombre de clase completo que está asociado al método.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodunloadverbose_v2-event"></a>Evento MethodUnLoadVerbose_V2

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V2`|144|Se genera cuando se destruye un método dinámico, se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos siempre usan esta versión para descargas de método.|

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Informativo (4)|
|`NGenKeyword` 0x20 |Informativo (4)|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único del método. Para los métodos del asistente JIT, se establece en la dirección de inicio del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método (0 para asistentes de JIT).|
|`MethodStartAddress`|`win:UInt64`|Dirección de inicio.|
|`MethodSize`|`win:UInt32`|Longitud de método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodFlags`|`win:UInt32`|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0 x 4: método compilado JIT (de lo contrario, generado por NGen.exe)<br /><br /> 0x8: método del asistente.|
|`MethodNameSpace`|`win:UnicodeString`|Nombre del espacio de nombres completo que está asociado al método.|
|`MethodName`|`win:UnicodeString`|Nombre de clase completo que está asociado al método.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`ReJITID`|`win:UInt64`|IDENTIFICADOR de ReJIT del método.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodjittingstarted_v1-event"></a>Evento MethodJittingStarted_V1

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITKeyword` (0 x 10) |Detallado (5)|
|`NGenKeyword` 0x20 |Detallado (5)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodJittingStarted_V1`|145|Se genera cuando se está realizando la compilación JIT de un método.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único del método.|
|`ModuleID`|`win:UInt64`|Identificador del módulo al que pertenece este método.|
|`MethodToken`|`win:UInt32`|0 para métodos dinámicos y asistentes de JIT.|
|`MethodILSize`|`win:UInt32`|Tamaño del lenguaje intermedio común (CIL) del método que se va a compilar con JIT.|
|`MethodNameSpace`|`win:UnicodeString`|Nombre de clase completo que está asociado al método.|
|`MethodName`|`win:UnicodeString`|Nombre del método.|
|`MethodSignature`|`win:UnicodeString`|Signatura del método (lista separada por comas de nombres de tipo).|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodjitinliningsucceeded-event"></a>Evento MethodJitInliningSucceeded

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Detallado (5)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodJitInliningSucceeded`|185|Se genera cuando el compilador JIT inserta correctamente un método.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Espacio de nombres del método que se está compilando.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Nombre del método que se está compilando.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Firma del método (lista separada por comas de nombres de tipo) que se está compilando.|
|`InlinerNamespace`|`win:UnicodeString`|Espacio de nombres del método insertado ("primario").|
|`InlinerName`|`win:UnicodeString`|Nombre del método del insertador ("primario").|
|`InlinerNameSignature`|`win:UnicodeString`|Firma del método insertado ("Parent") (lista separada por comas de nombres de tipo).|
|`InlineeNamespace`|`win:UnicodeString`|Espacio de nombres del método inline ("Child").|
|`InlineeName`|`win:UnicodeString`|Nombre del método insertado ("secundario").|
|`InlineeNameSignature`|`win:UnicodeString`|Firma del método inline ("Child") (lista separada por comas de nombres de tipo).|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodjitinliningfailed-event"></a>Evento MethodJitInliningFailed

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Detallado (5)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodJitInliningFailed`|192|Se genera cuando el compilador JIT no pudo insertar un método.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Espacio de nombres del método que se está compilando.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Nombre del método que se está compilando.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Firma del método (lista separada por comas de nombres de tipo) que se está compilando.|
|`InlinerNamespace`|`win:UnicodeString`|Espacio de nombres del método insertado ("primario").|
|`InlinerName`|`win:UnicodeString`|Nombre del método del insertador ("primario").|
|`InlinerNameSignature`|`win:UnicodeString`|Firma del método insertado ("Parent") (lista separada por comas de nombres de tipo).|
|`InlineeNamespace`|`win:UnicodeString`|Espacio de nombres del método inline ("Child").|
|`InlineeName`|`win:UnicodeString`|Nombre del método insertado ("secundario").|
|`InlineeNameSignature`|`win:UnicodeString`|Firma del método inline ("Child") (lista separada por comas de nombres de tipo).|
|`FailAlways`|`win:Boolean`|Indica si el método está marcado como no pueda insertar.|
|`FailReason`|`win:UnicodeString`|No se pudo insertar el motivo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodjittailcallsucceeded-event"></a>Evento MethodJitTailCallSucceeded

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Detallado (5)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodJitTailCallSucceeded`|192|Generado por el compilador JIT cuando se puede llamar a un método correctamente.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Espacio de nombres del método que se está compilando.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Nombre del método que se está compilando.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Firma del método (lista separada por comas de nombres de tipo) que se está compilando.|
|`CallerNamespace`|`win:UnicodeString`|Espacio de nombres del método de llamada.|
|`CallerName`|`win:UnicodeString`|Nombre del método de llamada.|
|`CallerNameSignature`|`win:UnicodeString`|Firma del método de llamada (lista separada por comas de nombres de tipo).|
|`CalleeNamespace`|`win:UnicodeString`|Espacio de nombres del método de destinatario.|
|`CalleeName`|`win:UnicodeString`|Nombre del método de destinatario.|
|`CalleeNameSignature`|`win:UnicodeString`|Firma del método de destinatario (lista separada por comas de nombres de tipo).|
|`TailPrefix`|`win:Boolean`|Indica si se trata de una instrucción de prefijo de cola.|
|`TailCallType`|`win:UInt32`|El tipo de llamada de cola.<br/><br/>0: llamada de cola optimizada (epílogo + JMP)<br/><br/>1: llamada de cola recursiva (método, llamadas a la cola)<br/><br/>2: llamada a la cola asistida del ayudante|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodjittailcallfailed-event"></a>Evento MethodJitTailCallFailed

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Detallado (5)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`MethodJitTailCallFailed`|191|Generado por el compilador JIT cuando no se pudo llamar a un método.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Espacio de nombres del método que se está compilando.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Nombre del método que se está compilando.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Firma del método (lista separada por comas de nombres de tipo) que se está compilando.|
|`CallerNamespace`|`win:UnicodeString`|Espacio de nombres del método de llamada.|
|`CallerNam`e|`win:UnicodeString`|Nombre del método de llamada.|
|`CallerNameSignature`|`win:UnicodeString`|Firma del método de llamada (lista separada por comas de nombres de tipo).|
|`CalleeNamespace`|`win:UnicodeString`|Espacio de nombres del método de destinatario.|
|`CalleeName`|`win:UnicodeString`|Nombre del método de destinatario.|
|`CalleeNameSignature`|`win:UnicodeString`|Firma del método de destinatario (lista separada por comas de nombres de tipo).|
|`TailPrefix`|`win:Boolean`|Indica si se trata de una instrucción de prefijo de cola.|
|`FailReason`|`win:UnicodeString`|Motivo del error de llamada de cola.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="methodiltonativemap-event"></a>Evento MethodILToNativeMap

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`JittedMethodILToNativeMapKeyword` (0x20000) |Detallado (5)|

|Evento|Id. de evento|Descripción|
|----------------|---------------|-----------------|
|`MethodILToNativeMap`|190|Asigna el evento de asignación de IL a nativo para métodos compilados JIT.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Identificador único de un método.|
|`ReJITID`|`win:UInt64`|IDENTIFICADOR de ReJIT del método.|
|`MethodExtent`|`win:UInt8`|La extensión del método JIT.|
|`CountOfMapEntries`|`win:UInt8`|Número de entradas de mapa|
|`ILOffsets`|`win:UInt32`|Desplazamiento IL.|
|`NativeOffsets`|`win:UInt32`|Desplazamiento del código nativo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
