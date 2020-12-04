---
title: Eventos de Runtime de interoperabilidad
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica de la interoperabilidad.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Interop events (CoreCLR)
- ETW, EventPipe, LTTng interop events (CoreCLR)
ms.openlocfilehash: 5635fb55b3a6ffa3f5611da80cdb2909e226e2ea
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594704"
---
# <a name="net-runtime-interop-events"></a>Eventos de interoperabilidad de .NET Runtime

Estos eventos en tiempo de ejecución capturan información sobre la generación de código auxiliar del lenguaje intermedio común (CIL). Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="ilstubgenerated-event"></a>Evento ILStubGenerated

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`InteropKeyword` (0 x 2000)|Informativo (4)|
  
|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ILStubGenerated`|88|Se genera un código auxiliar de IL.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt16`|Identificador del módulo.|
|`StubMethodID`|`win:UInt64`|Identificador del método de código auxiliar.|
|`StubFlags`|`win:UInt32`|Marcas para el código auxiliar:<br /><br /> `0x1` -Interoperabilidad inversa.<br /><br /> `0x2` -Interoperabilidad COM.<br /><br /> `0x4` -Código auxiliar generado por NGen.exe.<br /><br /> `0x8` Delegado.<br /><br /> `0x10` -Argumento variable.<br /><br /> `0x20` -Destinatario no administrado.<br /><br /> `0x40` -Serialización de struct|
|`ManagedInteropMethodToken`|`win:UInt32`|Token del método de interoperabilidad administrado.|
|`ManagedInteropMethodNameSpace`|`win:UnicodeString`|El espacio de nombres y el tipo de inclusión del método de interoperabilidad administrado.|
|`ManagedInteropMethodName`|`win:UnicodeString`|Nombre del método de interoperabilidad administrado.|
|`ManagedInteropMethodSignature`|`win:UnicodeString`|Firma del método de interoperabilidad administrado.|
|`NativeMethodSignature`|`win:UnicodeString`|Firma del método nativo.|
|`StubMethodSignature`|`win:UnicodeString`|Firma del método de código auxiliar.|
|`StubMethodILCode`|`win:UnicodeString`|Código de lenguaje intermedio común (CIL) del método de código auxiliar.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|
