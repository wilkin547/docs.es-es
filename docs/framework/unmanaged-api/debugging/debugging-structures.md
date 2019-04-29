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
# <a name="debugging-structures"></a><span data-ttu-id="8d717-102">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-102">Debugging Structures</span></span>

<span data-ttu-id="8d717-103">En esta sección se describen las estructuras no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="8d717-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8d717-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8d717-104">In This Section</span></span>
 <span data-ttu-id="8d717-105">[Estructura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8d717-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="8d717-106">[Estructura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) define un IL para asignación de direcciones</span><span class="sxs-lookup"><span data-stu-id="8d717-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="8d717-107">[CLR_DEBUGGING_VERSION (estructura)](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) define la versión del producto de common language runtime (CLR) con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="8d717-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="8d717-108">[CodeChunkInfo (estructura)](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8d717-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="8d717-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d717-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="8d717-110">[COR_ARRAY_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) proporciona información sobre el diseño de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8d717-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="8d717-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) contiene los desplazamientos que se usan para asignar el lenguaje intermedio de Microsoft (MSIL) de código para código nativo.</span><span class="sxs-lookup"><span data-stu-id="8d717-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="8d717-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) contiene la información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="8d717-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="8d717-113">[COR_FIELD (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="8d717-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="8d717-114">[COR_GC_REFERENCE (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) contiene información sobre un objeto que se va a recolectar.</span><span class="sxs-lookup"><span data-stu-id="8d717-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="8d717-115">[COR_HEAPINFO (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) proporciona información general sobre el montón de elementos no utilizados, incluso si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="8d717-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="8d717-116">[COR_HEAPOBJECT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8d717-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="8d717-117">[COR_IL_MAP](cor-il-map-structure.md) especifica cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="8d717-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="8d717-118">[COR_SEGMENT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) contiene información sobre una región de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8d717-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="8d717-119">[COR_TYPEID (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) contiene un identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="8d717-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="8d717-120">[COR_TYPE_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) proporciona información sobre el diseño de un objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="8d717-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="8d717-121">[COR_VERSION](cor-version-structure.md) almacena el número de versión de cuatro partes estándar de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8d717-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="8d717-122">[CorDebugBlockingObject (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) define un objeto que está bloqueando un subproceso y el motivo por qué se bloquea el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d717-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="8d717-123">[CorDebugEHClause (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) representa una cláusula de control (EH) de la excepción para una parte determinada de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="8d717-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="8d717-124">[CorDebugExceptionObjectStackFrame (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) representa información de un objeto de excepción del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="8d717-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="8d717-125">[CorDebugGuidToTypeMapping (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID correspondiente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="8d717-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="8d717-126">[Estructura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="8d717-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="8d717-127">[Estructura DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) define un búfer de transporte para obtener información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="8d717-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="8d717-128">[Estructura DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) define un búfer de transporte para obtener información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="8d717-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="8d717-129">[Estructura DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) define la información básica sobre un determinado método del generador de perfiles instrumentada.</span><span class="sxs-lookup"><span data-stu-id="8d717-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="8d717-130">[StackTrace_SimpleContext (estructura)](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) proporciona un contexto simple que puede usarse en lugar de un completo `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="8d717-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8d717-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8d717-131">Related Sections</span></span>

 [<span data-ttu-id="8d717-132">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="8d717-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="8d717-134">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="8d717-135">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="8d717-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="8d717-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
