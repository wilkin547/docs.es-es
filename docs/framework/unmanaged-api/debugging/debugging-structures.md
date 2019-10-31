---
title: Estructuras de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123034"
---
# <a name="debugging-structures"></a><span data-ttu-id="26150-102">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="26150-102">Debugging Structures</span></span>

<span data-ttu-id="26150-103">En esta sección se describen las estructuras no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="26150-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="26150-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="26150-104">In This Section</span></span>
 <span data-ttu-id="26150-105">[Estructura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="26150-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="26150-106">[Estructura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Define una asignación de IL a dirección</span><span class="sxs-lookup"><span data-stu-id="26150-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="26150-107">[Estructura CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Define la versión del producto del Common Language Runtime (CLR) para fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="26150-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="26150-108">[Estructura CodeChunkInfo (](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Representa un único fragmento de código en memoria.</span><span class="sxs-lookup"><span data-stu-id="26150-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="26150-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contiene información sobre las funciones que están activas actualmente en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="26150-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="26150-110">[Estructura COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Proporciona información sobre el diseño de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="26150-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="26150-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="26150-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="26150-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contiene la información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="26150-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="26150-113">[Estructura COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Proporciona información sobre un campo de un objeto.</span><span class="sxs-lookup"><span data-stu-id="26150-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="26150-114">[Estructura COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contiene información sobre un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="26150-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="26150-115">[Estructura COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="26150-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="26150-116">[Estructura COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="26150-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="26150-117">[COR_IL_MAP](cor-il-map-structure.md) Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="26150-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="26150-118">[Estructura COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="26150-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="26150-119">[Estructura COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contiene un identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="26150-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="26150-120">[Estructura COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Proporciona información sobre el diseño de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="26150-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="26150-121">[COR_VERSION](cor-version-structure.md) Almacena el número de versión de cuatro partes estándar del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="26150-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="26150-122">[CorDebugBlockingObject (estructura](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) ) Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="26150-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="26150-123">[Estructura cordebugehclause (](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Representa una cláusula de control de excepciones (EH) para una parte determinada del lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="26150-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="26150-124">[Estructura cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Representa la información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="26150-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="26150-125">[Estructura cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Asigna un GUID de Windows Runtime a su objeto [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="26150-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="26150-126">[Estructura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="26150-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="26150-127">[Estructura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="26150-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="26150-128">[Estructura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="26150-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="26150-129">[Estructura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Define la información básica sobre un método instrumentado del generador de perfiles determinado.</span><span class="sxs-lookup"><span data-stu-id="26150-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="26150-130">[Estructura StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Proporciona un contexto simple que se puede utilizar en lugar de una estructura de `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="26150-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="26150-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="26150-131">Related Sections</span></span>

 [<span data-ttu-id="26150-132">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="26150-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="26150-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="26150-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="26150-134">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="26150-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="26150-135">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="26150-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="26150-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="26150-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
