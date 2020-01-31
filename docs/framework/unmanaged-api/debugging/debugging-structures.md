---
title: Estructuras de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793755"
---
# <a name="debugging-structures"></a>Estructuras de depuración

En esta sección se describen las estructuras no administradas que utiliza la API de depuración.

## <a name="in-this-section"></a>Esta sección
 [Estructura de CLRDATA_ADDRESS_RANGE](clrdata-address-range-structure.md) Define un intervalo de direcciones.

 [Estructura de CLRDATA_IL_ADDRESS_MAP](clrdata-il-address-map-structure.md) Define una asignación de IL a dirección

 [Estructura de CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Define la versión del producto del Common Language Runtime (CLR) para fines de depuración.

 [Estructura CodeChunkInfo (](codechunkinfo-structure.md) Representa un único fragmento de código en memoria.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contiene información sobre las funciones que están activas actualmente en los marcos de un subproceso.

 [Estructura de COR_ARRAY_LAYOUT](cor-array-layout-structure.md) Proporciona información sobre el diseño de un objeto de matriz en la memoria.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contiene la información de desplazamiento para un intervalo de código.

 [Estructura de COR_FIELD](cor-field-structure.md) Proporciona información sobre un campo de un objeto.

 [Estructura de COR_GC_REFERENCE](cor-gc-reference-structure.md) Contiene información sobre un objeto que se va a recolectar como elemento no utilizado.

 [Estructura de COR_HEAPINFO](cor-heapinfo-structure.md) Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable.

 [Estructura de COR_HEAPOBJECT](cor-heapobject-structure.md) Proporciona información sobre un objeto en el montón administrado.

 [COR_IL_MAP](cor-il-map-structure.md) Especifica los cambios en el desplazamiento relativo de una función.

 [Estructura de COR_SEGMENT](cor-segment-structure.md) Contiene información sobre una región de memoria en el montón administrado.

 [Estructura de COR_TYPEID](cor-typeid-structure.md) Contiene un identificador de tipo.

 [Estructura de COR_TYPE_LAYOUT](cor-type-layout-structure.md) Proporciona información sobre el diseño de un objeto en la memoria.

 [COR_VERSION](cor-version-structure.md) Almacena el número de versión de cuatro partes estándar del Common Language Runtime.

 [CorDebugBlockingObject (estructura](cordebugblockingobject-structure.md) ) Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.

 [Estructura cordebugehclause (](cordebugehclause-structure.md) Representa una cláusula de control de excepciones (EH) para una parte determinada del lenguaje intermedio (IL).

 [Estructura cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) Representa la información del marco de pila de un objeto de excepción.

 [Estructura cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) Asigna un GUID de Windows Runtime a su objeto [ICorDebugType](icordebugtype-interface.md) correspondiente.

 [Estructura DacpGetModuleAddress](dacpgetmoduleaddress-structure.md) Define el contenedor para una solicitud de dirección del módulo.

 [Estructura DacpMethodDescData](dacpmethoddescdata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un método.

 [Estructura DacpModuleData](dacpmoduledata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un módulo.

 [Estructura DacpReJitData](dacprejitdata-structure.md) Define la información básica sobre un método instrumentado del generador de perfiles determinado.

 [Estructura de StackTrace_SimpleContext](stacktrace-simplecontext-structure.md) Proporciona un contexto simple que se puede utilizar en lugar de una estructura de `CONTEXT` completa.

## <a name="related-sections"></a>Secciones relacionadas

 [Coclases para la depuración](debugging-coclasses.md)

 [Interfaces de depuración](debugging-interfaces.md)

 [Funciones estáticas globales de depuración](debugging-global-static-functions.md)

 [Enumeraciones de depuración](debugging-enumerations.md)

 [Depuración](index.md)
