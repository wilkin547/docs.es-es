---
title: Estructuras de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50db519410b9513725c3dc10637421ba8bb37ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698373"
---
# <a name="debugging-structures"></a>Estructuras de depuración

En esta sección se describen las estructuras no administradas que utiliza la API de depuración.

## <a name="in-this-section"></a>En esta sección
 [Estructura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) define un intervalo de direcciones.

 [Estructura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) define un IL para asignación de direcciones

 [CLR_DEBUGGING_VERSION (estructura)](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) define la versión del producto de common language runtime (CLR) con fines de depuración.

 [CodeChunkInfo (estructura)](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) representa un único fragmento de código en la memoria.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.

 [COR_ARRAY_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) proporciona información sobre el diseño de un objeto de matriz en la memoria.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) contiene los desplazamientos que se usan para asignar el lenguaje intermedio de Microsoft (MSIL) de código para código nativo.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) contiene la información de desplazamiento para un intervalo de código.

 [COR_FIELD (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) proporciona información sobre un campo en un objeto.

 [COR_GC_REFERENCE (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) contiene información sobre un objeto que se va a recolectar.

 [COR_HEAPINFO (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) proporciona información general sobre el montón de elementos no utilizados, incluso si es enumerable.

 [COR_HEAPOBJECT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) proporciona información sobre un objeto en el montón administrado.

 [COR_IL_MAP](cor-il-map-structure.md) especifica cambios en el desplazamiento relativo de una función.

 [COR_SEGMENT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) contiene información sobre una región de memoria del montón administrado.

 [COR_TYPEID (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) contiene un identificador de tipo.

 [COR_TYPE_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) proporciona información sobre el diseño de un objeto en memoria.

 [COR_VERSION](cor-version-structure.md) almacena el número de versión de cuatro partes estándar de common language runtime.

 [CorDebugBlockingObject (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) define un objeto que está bloqueando un subproceso y el motivo por qué se bloquea el subproceso.

 [CorDebugEHClause (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) representa una cláusula de control (EH) de la excepción para una parte determinada de lenguaje intermedio (IL).

 [CorDebugExceptionObjectStackFrame (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) representa información de un objeto de excepción del marco de pila.

 [CorDebugGuidToTypeMapping (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID correspondiente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) objeto.

 [Estructura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) define el contenedor para una solicitud de dirección del módulo.

 [Estructura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) define un búfer de transporte para obtener información de tiempo de ejecución de un método.

 [Estructura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) define un búfer de transporte para obtener información de tiempo de ejecución de un módulo.

 [Estructura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) define la información básica sobre un determinado método del generador de perfiles instrumentada.

 [StackTrace_SimpleContext (estructura)](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) proporciona un contexto simple que puede usarse en lugar de un completo `CONTEXT` estructura.

## <a name="related-sections"></a>Secciones relacionadas

 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
